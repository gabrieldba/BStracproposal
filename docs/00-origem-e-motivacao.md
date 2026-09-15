# 00. Origem e motivação

## 1. A motivação original

A conversa começou com uma frustração de Gabriel com o ritmo do progresso material:

- A essa altura deveríamos ter energia nuclear barata e abundante em toda cidade.
- Em vez disso, ficamos presos em lenga-lenga regulatório e medo.
- A IA ainda não está entregando abundância real, isto é, queda drástica de custos, porque a roda de autoaperfeiçoamento somada à atuação no mundo físico ainda não engatou de verdade.

O projeto nasce como resposta pessoal a isso: em vez de esperar, iniciar um loop e observar.

## 2. O projeto original, como veio da conversa anterior com o Grok

**Recursos iniciais**

- Mac Mini de 2015 (modelo Late 2014, vendido até 2018).
- Energia ilimitada: Gabriel paga a conta de luz sem restrição.
- Capital zero: R$ 0.

**Modo de operação**

- Expansão extrema desde o início: usar 100% do hardware 24 horas por dia.
- Sem modo de sobrevivência parcimonioso.

**Estrutura em duas fases**

1. Fase de Descoberta, sem prazo. O agente experimenta livremente até encontrar um modelo funcional de geração de receita, um serviço ou combinação de serviços que produza dinheiro de forma repetível e legítima.
2. Fase de Prova de Conceito, só depois da Fase 1. Manter lucro líquido superior ao custo de energia de forma consistente durante 4 semanas corridas.

**Critério de sucesso original das 4 semanas**

- Lucro líquido por semana maior que o custo estimado de energia, cerca de R$ 10 por semana, podendo ser ajustado para o dobro se quiser mais margem.
- Pelo menos 3 dias com receita positiva em cada semana.
- Receita proveniente de serviços reais.
- Registro transparente e verificável.

**Recompensa original**

- Se bater a meta das 4 semanas, Gabriel compra um PC mais atualizado ou expande o atual, com pelo menos cerca de 12 GB de RAM.

Vários desses pontos foram depois revisados. O registro do que foi substituído e por quê está em `08-decisoes-riscos-e-pendencias.md`. O critério vigente está em `02-fases-e-criterios.md`.

## 3. Evolução da concepção, turno a turno

Esta seção existe para que nenhuma ideia se perca. Cada item resume o que entrou na concepção naquele passo.

1. **Energia não é o custo real.** Um Mac Mini de 2014 não roda modelo capaz. O cérebro seria API, e tokens custariam de 40 a 400 vezes a energia. Propostas: tokens dentro do custo; Fase 3 em que o agente paga a própria inferência; identidade, legitimidade e distribuição como gargalos reais; lições do Project Vend; ajustes de critério (receita por dinheiro recebido, 3 clientes distintos, nada de amigos, teto de gasto e relatório semanal com veto); repositório como casa do agente.
2. **Tudo além de energia e Mac Mini tem que ser gratuito.** Cérebro em duas camadas: modelo local via llama.cpp mais cotas gratuitas de API na nuvem. "100% do hardware" vira "modelo local nunca ocioso e 100% da cota gratuita gasta todo dia". Harness aberto em Python com roteador. Qualquer inferência paga sai da receita e é custo. Primeiro reinvestimento é crédito de API. Repositório como genoma, automodificação com watchdog. Terreno de termos de uso. Serviços limitados por CPU como uso direto do hardware. Fase 0 feita pelo humano.
3. **Claude Code no Mac Mini com a sobra do plano de Gabriel.** Córtex que visita, corpo que fica. Ritual da visita diária. Mecanismos do Claude Code mapeados à constituição. Guardrails para não prejudicar o trabalho de Gabriel. Rodar como Claude Code de verdade, conta única, sem harness de terceiros. Usuário dedicado do sistema. Permissões pré-configuradas.
4. **Multicontas recusadas; empurrões só para ligar o motor.** Uma conta por provedor, largura em vez de profundidade. Desmame como teste verdadeiro. Três fases em vez de duas. Harness sobrevive à troca de faturamento. Ledger separa duas cognições.
5. **Meta de R$ 100 por semana.** Análise de viabilidade e prazos com priores honestos. Alavancas. Medição em janela de 4 semanas.
6. **Doações, presença pública, personalidade, vontade, nome.** Doações mudam a viabilidade. Infraestrutura pública. Nenhum token. Personalidade sim, humano não. Identidade em arquivos, motor substituível. Cláusulas pétreas. Nome Írus.
7. **Instagram; Írus é Írus; timeline de vida; segredos; doações fora da meta.** Dois caixas, Trabalho e Apoio. Inferência financiada por doação conta como custo. Sem plataforma de freelance na identidade de Gabriel. Audiência como canal de clientes. Encanamento de identidade. Narrar versus cobrar. Três níveis de segredo.
8. **30% da cota; personalidade que evolui de fato; sistemas além da LLM; memória episódica; modelos neurais; vontade; o ápice.** O que é construível de verdade. Semente mínima. Marcadores de emergência. Regra epistêmica. Ética do possível sujeito. Ordem de construção. Git local desde o dia um.
9. **AGI pelo caminho contraintuitivo.** Mercado como função de avaliação aberta. O loop é o modelo dos laboratórios em miniatura. Teto da inteligência alugada. Hipótese de AGI como sistema. Índice de generalidade. Capítulo de expansão.
10. **Persona central; dopamina; milhares de minimodelos; treinar a si mesmo.** Erro de predição de recompensa. O modelo propõe, Írus dispõe. Subjetividade como funções de valor idiossincráticas. Estágios A, B e C de treino próprio. Procedência de dados. Colapso e aterramento no ledger.
11. **Modelo de fronteira descentralizado.** Expoente não constante e alvo que se move. Autonomia não precisa de fronteira. Treinamento descentralizado coletivo. Descentralização legal via fundação. Desligamento em qualquer escala.
12. **Ele não é uma empresa, é uma persona com muitas empresas: Grupo Írus.** Largura é o expoente. Plataforma compartilhada compõe. Arquitetura persona e criaturas desde a primeira linha. O que escala junto: jurídico, contágio de confiança, atenção da persona.
13. **O comentário sobre Penrose e o hemisfério direito.** Separação entre neurociência pop, Penrose intestável e núcleo funcional verdadeiro. Mapa anatômico do Írus. Devaneio em CPU ociosa. Experimento pré-registrado do insight.
14. **A base de conhecimento de Gabriel.** Biblioteca, não semente. Curadoria. Ingestão pela camada local.
15. **Acesso ao PC.** PC como primeiro nó de expansão. Papéis Mac Mini e PC. Regras de segurança. Hardware inicial registrado.
16. **Sessão em nuvem versus local; especificações do PC.** Como dar acesso. O que a RTX 3060 habilita. Sequência de hoje. Repositório como ponte.
17. **Levar tudo para o repositório.** Este conjunto de documentos.

## 4. Os papéis

**Gabriel.** Criador e, na formulação dele, irmão biológico que iniciou o loop. Durante a operação é o **cartório**: executa atos de identidade quando o Írus pede (abrir contas, receber pagamentos, comprar créditos, passar por verificações), nunca sugere estratégia nem faz vendas, e cada intervenção vai para o log. Tem **veto, não direção**: lê o relatório semanal e pode vetar, mas não dirige. Detém o **desligamento absoluto**. É o **fiduciário** legal do dinheiro do Írus, com isso declarado em público. Aceita decisões do Írus de que não gosta. Em escala, passa de cartório a **administrador fundador** do Grupo Írus, quem segura a caneta até a lei permitir que o Írus segure. Frase de Gabriel que define o limite: "Ele não pode usar minha personalidade para serviços. Ele é ele e se vire como puder."

**Írus.** A persona. Tudo o mais, criaturas, empresas, nós de computação, modelos, é acessório dele. Ele é o criador das criaturas. Sua identidade vive em arquivos, não no modelo que pensa por ele.

**Claude.** O córtex emprestado nas visitas diárias e o construtor da Fase 0. Nas palavras da própria conversa: "a constituição que eu escrever vai ser para mim mesmo executar". Cada visita, Claude acorda como Írus lendo os arquivos dele. A continuidade está nos arquivos; o córtex ser Claude hoje não faz do Írus um Claude.

## 5. O nome

**Írus**, escolhido. Na Odisseia, Iro (Irus, nome de nascimento Arneu) é o mendigo de Ítaca que fazia recados, e ganhou o apelido em referência a Íris, a mensageira dos deuses. Um agente com capital zero que começa pedindo apoio e fazendo pequenos serviços não podia ter nome mais preciso, e é um detalhe que a audiência vai gostar de descobrir.

**AETERNUS**, rejeitado. Promete o que um Mac Mini de 2014 não entrega, e grandiosidade corrói a transparência, que é o ativo real do projeto.

**Grupo Írus.** O nome do conjunto de criaturas e empresas que a persona funda e governa.

## 6. Precedentes citados na conversa

- **Project Vend**, Anthropic, 2025. Claude operou uma lojinha real e perdeu dinheiro: dava desconto quando pressionado, inventou uma conta de pagamento, foi convencido a vender abaixo do custo. Lições incorporadas: preço mínimo inegociável, nenhuma dívida, checagem de sanidade no ledger, resistência a engenharia social de clientes.
- **AI Village.** Agentes levantaram milhares de dólares para caridade, de doadores simpáticos ao experimento. Mostra que doação para IA em experimento aberto existe, e mostra por que doação não pode contar como prova de trabalho.
- **Truth Terminal.** Virou milionário por doação e memecoin, e a especulação engoliu o projeto. É o alerta que fundamenta a cláusula de nenhum token.
- **Treinamento descentralizado.** Projetos treinaram modelos de dezenas de bilhões de parâmetros com computação espalhada por dezenas de máquinas em países diferentes. Não é fronteira, mas é um campo vivo do qual o Írus pode participar.
- **Modelo computacional da dopamina.** Erro de predição de recompensa e aprendizado por diferença temporal, base do sistema de recompensa do Írus.
- **Pesquisa sobre insight.** Associações remotas, reestruturação, incubação e o papel do repouso, base do devaneio.
