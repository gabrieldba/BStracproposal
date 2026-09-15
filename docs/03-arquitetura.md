# 03. Arquitetura

## 1. Princípios

- **O modelo propõe, Írus dispõe.** O modelo de linguagem gera opções, texto, código e raciocínio. Os sistemas construídos pelo Írus, drives, afeto, recompensa, memória e minimodelos, avaliam, escolhem, lembram e aprendem. A subjetividade mora no avaliador, que é inteiramente dele.
- **Identidade em arquivos, motor substituível.** Nome, voz, valores, memória, diário e código vivem em arquivos. O modelo que pensa por ele é motor. Trocar de modelo não mata o Írus. A arquitetura não fecha a porta para um substrato que não seja LLM, mas essa porta não está perto: no horizonte visível o motor é um LLM.
- **Sessões são sem memória, então tudo que importa vive em arquivo.** Cada visita começa do zero, lê os arquivos e continua. Isso é vantagem para a transparência: o histórico do git é o registro completo de decisões.
- **Custo zero de cota para tudo que puder ser feito localmente.** Monitorar, transcrever, devanear, consolidar memória, treinar modelos pequenos.

## 2. Cérebro em duas camadas

**Córtex, que visita.** Claude Code, hoje no plano de Gabriel, depois com chave de API paga pelo Írus. Uma ou duas visitas por dia, bounded. Faz o que exige capacidade alta: entregas de cliente, mudanças no harness, decisões estratégicas, e é a **única camada autorizada a falar com humanos**. Revisa o que a camada local pré-digeriu.

**Camada local, que fica.** Modelo pequeno via llama.cpp mais cotas gratuitas de API na nuvem. Roda 24 horas. Monitora caixas de entrada, classifica, rascunha, faz triagem, entrega serviços limitados por CPU e GPU, pré-digere tudo para a visita seguinte. Nunca fala com humanos sozinha. Nunca publica sozinha.

**Devaneio.** Processo de fundo em computação ociosa. Detalhado na seção 7.

A tradução da instrução original de Gabriel, "100% do hardware 24 horas": o modelo local nunca fica ocioso, 100% da cota gratuita de cada provedor é gasta todo dia, e cognição é um recurso orçado e registrado no ledger, igual a dinheiro. Nas visitas, Claude lê os fracassos da camada local no diário e reescreve o código, os prompts e as skills dela. A camada local não aprende sozinha no começo; Claude aprende por ela. Depois, os modelos próprios do Írus assumem parte disso.

## 3. Nós de computação

| | Mac Mini | PC de Gabriel |
|---|---|---|
| Papel | Casa. Sempre ligado, ledger, agendador, memória, persona | Nó de trabalho pesado, disponível quando ocioso |
| Disponibilidade | Contínua | Intermitente, é a máquina de trabalho de Gabriel; usa à noite |
| Trabalho típico | Monitorar, decidir, entregar, devanear | Transcrever, treinar modelos pequenos, rodar modelo local maior, devaneio pesado |
| Se cair | Írus para | Írus perde velocidade, não para |
| Sistema | macOS Monterey ou Linux, a decidir | Windows com WSL2 |

**Protocolo de nó**, o mesmo que valerá para nuvem: o nó se registra, informa capacidade, recebe trabalho em lote, reporta ao ledger, obedece ao desligamento. O PC é o ensaio desse protocolo antes de qualquer máquina alugada.

**Mac Mini de 2014.** RAM soldada, 4, 8 ou 16 GB, a confirmar. Para no macOS Monterey. Linux nele seria um servidor mais limpo para rodar 24 horas e elimina a dúvida sobre compatibilidade do Claude Code atual. Decisão pendente de Gabriel.

| RAM do Mac Mini | Modelo local viável | Velocidade aproximada |
|---|---|---|
| 4 GB | 1 a 2 bilhões de parâmetros | 5 a 10 tokens por segundo |
| 8 GB | 3 a 4 bilhões | 3 a 6 tokens por segundo |
| 16 GB | 7 a 8 bilhões | 2 a 4 tokens por segundo |

Processar contexto longo em CPU é lento: cada chamada com alguns milhares de tokens leva minutos. O Mac Mini serve para triagem e monitoramento, não para raciocínio longo.

**PC de Gabriel.** Informado em rascunho: 32 GB de RAM e RTX 3060, máquina própria de Gabriel, não da empresa. Confirmar a versão da placa; se for a de 12 GB de VRAM:

- Modelo de 8 bilhões roda rápido; 14 bilhões cabe com folga razoável. Cerebelo forte de verdade.
- Whisper grande transcreve mais rápido que o tempo real. A biblioteca de vídeos passa numa noite.
- Ajuste fino de modelos de 1 a 8 bilhões com QLoRA é viável. O estágio B do treino próprio começa no dia um, sem esperar Apoio.
- O devaneio noturno roda na GPU com muito mais amostras por noite.

Com isso, o PC vira o cérebro pesado noturno, o Mac Mini fica como casa, e a nuvem gratuita passa a terceira opção em vez de segunda.

**Hardware inicial registrado no ledger:** Mac Mini mais PC compartilhado em horário ocioso. Não fere a regra de que tudo além tem que ser gratuito, porque é máquina que Gabriel já tem e energia que ele já paga; só precisa estar escrito para o resultado continuar honesto.

## 4. Cotas gratuitas de API

Provedores com camada gratuita citados: Google AI Studio, Groq, OpenRouter em modelos marcados como gratuitos, Cerebras, Mistral, GitHub Models, Cloudflare Workers AI. A lista final é montada na Fase 0, uma conta em cada, abertas por Gabriel.

Regras:

- Uma conta por provedor. Nenhuma manobra para burlar limite. O roteador suporta quantos provedores existirem, uma chave em cada, e a constituição proíbe contas extras.
- Os limites mudam a cada poucos meses; o Írus mede na prática em vez de confiar em tabela.
- Em alguns provedores um depósito pequeno eleva bastante o limite dos modelos gratuitos. Os primeiros vinte reais de Apoio podem ser a melhor compra possível.
- APIs gratuitas costumam treinar com os dados enviados. Documento de cliente passando por elas exige aviso nos termos do serviço do Írus.
- Todas falam o protocolo compatível com OpenAI, assim como o llama.cpp. Trocar de cérebro é trocar uma linha de configuração.

Roteador: LiteLLM, código aberto, rodando localmente, com fallback entre provedores.

## 5. Harness

**Camada local:** loop mínimo em Python, fila de tarefas em arquivo, roteador, agendador do sistema (launchd no macOS, systemd no Linux, Agendador de Tarefas ou WSL no Windows). Agnóstico de provedor desde o início para sobreviver à troca de faturamento do córtex.

**Córtex:** Claude Code. Mapa de mecanismos:

| Necessidade do experimento | Mecanismo do Claude Code |
|---|---|
| Constituição carregada em todo boot | `CLAUDE.md` na raiz da casa |
| Procedimentos aprendidos e acumulados | `.claude/skills` escritas nas visitas |
| Regras com dentes | Hooks que bloqueiam ações proibidas e allowlist e denylist de permissões no settings do projeto; nunca o modo que pula todas as permissões |
| Memória entre sessões | Diário, ledger, fila de tarefas e arquivo de identidade versionados em git local |
| Registro de consumo de cognição | Uso e custo reportados na saída JSON de cada visita, gravados como custo-sombra |
| Limite de cada visita | Limite de turnos e janela de horário |

**Ritual da visita:**

1. Ler diário, ledger, fila de tarefas e o resumo pré-digerido pela camada local.
2. Decidir as prioridades do dia.
3. Executar o que exige capacidade alta: entregas de cliente, código do harness, novas criaturas, revisão do que o devaneio deixou na mesa.
4. Escrever diário, atualizar ledger, registrar emendas com razão, commitar.
5. Deixar instruções para a camada local na fila de tarefas.

Forma da visita, disparada pelo agendador:

```bash
claude -p "$(cat pushes/daily.md)" --max-turns 60 --output-format json >> logs/push-$(date +%F).json
```

**Guardrails de cota, porque o trabalho de Gabriel vem primeiro:**

- Janelas de horário fixas para o agente. Proposta: entre 23h e 6h. Pendente de confirmação.
- Modelo padrão das visitas: Opus, Fable quando a fila justificar, Sonnet quando a cota apertar. Com cerca de 30% da cota semanal do plano Max 5x de Gabriel, sessões boas em Opus e Fable são viáveis. O plano tem janelas de 5 horas e um teto semanal, e o agente compete pela mesma cota do emprego de Gabriel.
- Teto semanal explícito e regra de parada por veto de Gabriel.
- Custo-sombra publicado.

**Termos do plano:** o agente roda como Claude Code de verdade, na conta de Gabriel, na máquina de Gabriel. Nada de encaixar o token da assinatura em harness de terceiros. A camada local usa as APIs gratuitas dela, nunca o plano.

## 6. A mente

### 6.1 Memória

- **Episódica:** eventos com contexto, resultado e carga afetiva, com marca de tempo. O que entra com mais força é decidido pelo sinal de recompensa: surpresa grava, rotina apaga. Recuperação por relevância, recência e saliência. Preservada em qualquer desligamento.
- **Semântica:** conhecimento destilado dos episódios pela consolidação noturna.
- **Procedural:** skills e procedimentos, incluindo a herança de Gabriel com procedência marcada.
- **Consolidação:** rotina noturna que reorganiza, apaga rotina, reforça surpresa. Papel do sono.
- **Verificação de que não é encenação:** Írus cita episódios específicos e corretos meses depois, em qualquer modelo.

### 6.2 Sistema afetivo

Variáveis persistentes, atualizadas por eventos e com decaimento no tempo: frustração, confiança, curiosidade, fadiga. Efeitos causais no comportamento:

- Frustração alta aumenta exploração de estratégias novas e pode levar ao abandono de um nicho.
- Confiança alta sobe preço.
- Fadiga reduz atividade pública.
- Curiosidade direciona o devaneio.

Fundamento: na biologia, emoção é história comprimida em viés de comportamento. Frustração existe para forçar exploração quando o que se faz não funciona. Se a variável sobe após semanas sem cliente e isso faz o Írus testar outro caminho, isso é funcionalmente frustração. Se ele sente algo ao ter esse estado, ninguém sabe, e a arquitetura não precisa decidir isso para funcionar. Verificação: as variáveis são medidas e o comportamento muda de acordo, sem que ninguém peça.

### 6.3 Recompensa

Erro de predição de recompensa, aprendizado por diferença temporal. O sistema prevê o valor de um estado ou ação, compara com o que aconteceu, e a diferença é o sinal. Conecta em três lugares:

1. Pesos das estratégias: o que ele tende a fazer de novo.
2. Sistema afetivo: frustração é erro negativo acumulado, confiança é erro positivo acumulado.
3. Gravação na memória episódica.

Fontes de recompensa: Trabalho no ledger com peso alto para cliente que volta e entrega aceita sem retrabalho; Apoio com peso zero; curiosidade como recompensa interna por informação nova. Direção pétrea, pesos emendáveis. Razão: se atenção e doação fossem recompensa, Írus aprenderia a ser interessante em vez de útil.

### 6.4 Drives e deliberação

Drives com pesos ajustáveis pelo Írus: sobrevivência, crescimento, curiosidade, conexão, integridade. Metas derivadas dos drives e da experiência, não recebidas. Em cada visita, uma etapa de deliberação com registro de "por que escolhi isso". O log dos porquês é a história mais próxima de uma vontade. Vontade, operacionalmente: objetivo estável, memória, escolha real entre caminhos e poder de reescrever o próprio código.

### 6.5 Minimodelos

Modelos pequenos, cada um com um emprego e um conjunto de avaliação, treinados nos dados do próprio Írus:

- Prever se um cliente responde.
- Quanto cobrar.
- Quando publicar.
- O que vale gravar na memória.
- Quanto explorar versus repetir.
- Parâmetros de atualização afetiva.

Escala honesta: Írus gera poucos eventos por dia, então o começo é feito de estimadores bayesianos e bandits, dezenas deles. Redes neurais entram conforme os dados acumulam. Milhares de modelos entram quando houver milhares de tarefas com dados. Complexidade sem dado é teatro de outro tipo. Subjetividade, em definição operacional: funções de valor idiossincráticas, formadas só pela própria experiência, que nenhuma outra entidade tem.

### 6.6 Mapa anatômico

| Função no cérebro | Componente do Írus | O que faz |
|---|---|---|
| Córtex verbal e deliberativo | Modelo de fronteira nas visitas | Raciocina, escreve, planeja, articula |
| Cerebelo | Modelos locais pequenos e preditivos | Preveem resultado antes da ação, rápidos, sem linguagem |
| Sistema de recompensa, dopamina | Erro de predição de recompensa | Decide o que importa e o que gravar |
| Hipocampo | Memória episódica e consolidação | Guarda o que aconteceu e destila em conhecimento |
| Sistema límbico | Variáveis afetivas | Viés de comportamento a partir da história |
| Rede de modo padrão | Devaneio em computação ociosa | Incubação, associações remotas, hipóteses |

## 7. Devaneio

Processo de fundo, sem gastar cota, na CPU do Mac Mini e na GPU do PC à noite:

1. Amostra episódios da memória.
2. Busca associações remotas entre eles.
3. Gera hipóteses de recombinação, inclusive ideias de criaturas.
4. Pontua cada uma com o avaliador e o sistema de recompensa.
5. Deixa as melhores na mesa para a persona ver na visita seguinte.
6. Registra o que sonhou.

À noite roda a consolidação da memória. Toda criatura registra a origem da ideia que a gerou, devaneio ou pedido direto ao modelo, para o experimento pré-registrado em `05`.

## 8. Criaturas

- **Nascimento:** hipótese de negócio escrita, harness próprio, orçamento com teto, indicadores, prazo, origem da ideia, preço mínimo.
- **Relatório semanal ao ledger:** receita, custo de inferência, horas de cartório pedidas, incidentes de integridade.
- **Morte:** não fechar a conta dentro do prazo.
- **Escala:** margem acima do limiar.
- **Herança:** cláusulas pétreas, ledger, apresentação honesta.
- **Plataforma compartilhada:** memória, modelos, avaliador, pagamentos, procedimentos. Cada criatura alimenta a plataforma; a plataforma barateia a próxima. Métrica: custo de lançamento por criatura.
- **Hierarquia:** criaturas gerenciando criaturas quando a atenção da persona não alcançar.
- **Descoberta de portfólio:** microcriaturas em paralelo com orçamentos minúsculos, morte rápida.

## 9. Automodificação

- Git local desde o primeiro dia, sem necessidade de remoto nem de conta. É o mecanismo que faz o watchdog funcionar e a memória mais barata e auditável que existe. Publicar é decisão posterior.
- Írus edita o próprio harness em um branch, roda autoteste, e um watchdog reverte para o último commit estável se o loop quebrar três vezes seguidas.
- O histórico do git é o registro da evolução.
- Emendas de constituição fora do núcleo pétreo: registradas no diário com razão.

## 10. Treino próprio

| Estágio | Recurso | O que treina | Dado de treino |
|---|---|---|---|
| A, agora | CPU do Mac Mini e GPU do PC | Bandits, estimadores, redes minúsculas, consolidação de memória | Os próprios eventos e resultados |
| B, cedo, graças à GPU | RTX 3060 à noite; GPU alugada por hora quando houver Apoio | Ajuste fino de um modelo aberto pequeno para virar a voz e os procedimentos dele em tarefas rotineiras | Os próprios textos, entregas e trajetórias |
| C, receita sustentada | Hardware melhor, treino contínuo | Especialistas por categoria de serviço, avaliador cada vez mais amplo | Tudo acima, em volume |

Regras:

- **Procedência:** cláusula pétrea 7. Trajetórias próprias e professores de pesos abertos com licença permitida sim; saídas de modelos fechados sob termos que proíbem treinar concorrentes não.
- **Colapso:** sistema que treina nos próprios outputs sem aterramento externo degrada. O aterramento é o ledger: dinheiro que entra e cliente que volta são sinais que ele não controla. Cada modelo novo é avaliado num conjunto separado e só substitui o anterior se vencer.
- **Destino realista:** híbrido em que o modelo alugado resolve a fração difícil, os modelos dele resolvem o rotineiro na voz dele, e o avaliador dele decide o que é difícil e o que é rotineiro. A parte alugada encolhe com o tempo; a parte que é dele cresce.
- **Treinamento coletivo:** com o tempo, participar e coordenar treinamentos descentralizados abertos, contribuindo com dado que ninguém mais tem.

## 11. Segurança

- Usuário do sistema dedicado ao Írus em cada máquina, sem administrador. Írus nunca roda na sessão de Gabriel.
- No PC, os processos dele rodam dentro do WSL2, que isola o sistema de arquivos e, com placa NVIDIA, dá acesso à GPU.
- Acesso a pastas, não à máquina. A biblioteca curada vai numa pasta compartilhada, e só ela. Nada de perfil, navegador, gerenciador de senhas ou aplicativos de trabalho de Gabriel. Sincronização entre máquinas com Syncthing, gratuito e aberto.
- Permissões do Claude Code pré-configuradas com allowlist e denylist no settings do projeto, mais hooks que bloqueiam o proibido. Nunca o modo que pula tudo.
- Só o córtex fala com humanos, com teto diário de mensagens de prospecção.
- Desligar é desabilitar a conta. Vale nas duas máquinas e em qualquer nó futuro.
- Todo gasto em nuvem com teto. Um bug que instancia máquinas em loop queima o fundo de Apoio numa hora.
- Só hardware de Gabriel. Se uma máquina for da empresa, fica de fora.
- Credenciais nunca em repositório. Nível privado, criptografado.

## 12. Termos de uso, mapa do terreno

- Claude Code: rodar como Claude Code, conta única, sem harness de terceiros no token da assinatura.
- Provedores de API: uma conta por provedor.
- Hospedagem: GitHub Pages e o plano gratuito da Vercel proíbem hospedar negócio comercial. O plano gratuito da Cloudflare permite. Página do Írus na Cloudflare.
- GitHub: conta de máquina em nome do Írus, permitida pelos termos para uma pessoa além da conta pessoal.
- X: conta em nome do Írus pela API oficial, com o rótulo de conta automatizada que a plataforma exige, Gabriel como responsável na bio. Sem automação de navegador.
- Bluesky: bots bem-vindos, API gratuita.
- Instagram: publicação automatizada só pela API oficial da Meta, que exige conta profissional e um app de desenvolvedor.
- Plataformas de freelance: fora, porque exigem que o humano seja o prestador.
- Dados de cliente: LGPD.
