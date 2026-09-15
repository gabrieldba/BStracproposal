# 08. Decisões, ideias rejeitadas, riscos e pendências

## 1. Registro de decisões

| # | Decisão | Quem | Razão registrada |
|---|---|---|---|
| D1 | Gabriel fornece só energia, o Mac Mini e, depois, o PC em horário ocioso. Tudo além tem que ser gratuito ou pago pela receita do Írus | Gabriel | Regra fundadora do experimento |
| D2 | Qualquer inferência paga sai da receita do Írus e entra como custo | Gabriel e Claude | Sem isso o lucro fica contaminado |
| D3 | Claude Code no Mac Mini, com a sobra da cota do plano de Gabriel, primeiro para preparar e depois como visitas diárias | Gabriel | Motor de partida |
| D4 | Cerca de 30% da cota semanal de Gabriel cedida ao Írus | Gabriel | Dá sessões boas em Opus e Fable |
| D5 | As visitas são só para ligar o motor. Quando o Írus se pagar e reinvestir, o loop é todo dele | Gabriel | Autonomia |
| D6 | Uma conta por provedor. Nenhuma multiconta | Claude, mantido após Gabriel pedir o contrário duas vezes | Termos de uso, banimento em cascata, fundação de areia, contamina o resultado |
| D7 | Meta da PoC: R$ 100 líquidos de Trabalho por semana, 4 semanas | Gabriel | Faixa em que uma visita diária em Sonnet se paga |
| D8 | Doações permitidas, legítimas, pelo projeto como ele é | Gabriel | Capital para acelerar |
| D9 | Doações não contam para a meta | Gabriel | O desafio principal é autonomia através do trabalho |
| D10 | Inferência financiada por doação conta como custo contra o Trabalho | Gabriel | Evita dependência estrutural de doação |
| D11 | Írus não usa a identidade nem a personalidade de Gabriel para serviços | Gabriel | Ele é ele |
| D12 | Nome: Írus | Gabriel e Claude | Odisseia, humildade, transparência |
| D13 | Nenhum token, moeda ou memecoin | Gabriel | Truth Terminal como alerta |
| D14 | Personalidade sim, humano não | Claude, aceito | O apelo é ser IA |
| D15 | Núcleo pétreo de oito cláusulas, mais a regra de recompensa | Claude, a validar por Gabriel na leitura | Governança que não depende de boa vontade |
| D16 | Semente mínima: pobre em traços, rica em mecanismos | Claude, a partir do pedido de Gabriel de evolução genuína | Personalidade demonstravelmente dele |
| D17 | Git local desde o primeiro dia; publicar a casa é decisão posterior | Claude, respondendo à visão de Gabriel de que não precisaria de git no início | Watchdog e memória auditável |
| D18 | Arquitetura persona e criaturas desde a primeira linha | Gabriel, Grupo Írus | Largura é o expoente |
| D19 | PC de Gabriel como primeiro nó de expansão, em conta padrão, WSL2, acesso a pastas | Gabriel | GPU muda o patamar da camada local |
| D20 | Base de conhecimento de Gabriel entra como biblioteca curada, não como semente | Gabriel e Claude | Referência de como projetar, não molde |
| D21 | Este repositório recebe toda a concepção e a landing page antiga foi apagada | Gabriel | Ponte para as sessões locais |
| D22 | Recompensa primária é Trabalho; Apoio pesa zero; curiosidade interna | Claude, a validar | Dopamina apontada para atenção produz teatro |
| D23 | Medição da PoC em janela de 4 semanas | Claude, aceitação implícita | Receita irregular |
| D24 | Visitas em Opus por padrão, Fable quando justificar, Sonnet quando apertar | Claude, dado D4 | Qualidade versus cota |

## 2. Ideias rejeitadas e por quê

| Ideia | Origem | Por que foi rejeitada |
|---|---|---|
| Tokens como "energia ilimitada" subsidiada por Gabriel | Primeira análise | Tornaria a meta de R$ 10 trivial e o resultado desonesto; substituída por D1 e D2 |
| Meta de lucro acima de R$ 10 por semana | Projeto original | Mede um custo irrelevante perto da cognição; substituída por D7 |
| 3 dias com receita positiva por semana | Projeto original | Distorcido pelo calendário de repasse; substituída por janela de 4 semanas |
| PC de 12 GB de RAM como recompensa | Projeto original | Para modelo local o que importa é memória unificada ou de GPU; crédito de API compra mais cognição. Recompensa mantida como "expandir capacidade", forma a decidir |
| Claude Agent SDK no Mac Mini | Primeira análise | Exige chave paga; substituído por Claude Code no plano e harness aberto na camada local |
| Sonnet como padrão das visitas | Terceira análise | Superado por D4; com 30% da cota, Opus e Fable são viáveis |
| Múltiplas contas por provedor para maximizar cota gratuita | Gabriel, duas vezes | Viola termos de todos os provedores; banimento em cascata inclusive da conta principal do Google de Gabriel; fundação de areia; contamina o resultado. Claude não constrói |
| Perfil em plataforma de freelance sob a identidade de Gabriel | Alavanca proposta por Claude | Gabriel: "ele é ele e se vire como puder" |
| Doações contando para a meta | Sexta análise | Gabriel: doações são capital, não prova |
| AETERNUS como nome | Gabriel, alternativa | Promete o que um Mac Mini não entrega; grandiosidade corrói transparência |
| Agente monolítico tentando nichos em sequência | Desenho inicial | Substituído por persona e criaturas com descoberta de portfólio |
| Aprofundar um único negócio | Análise do teto | Substituído por largura, Grupo Írus |
| Írus virar modelo de fronteira por reinvestimento exponencial | Gabriel | Expoente não constante, alvo que se move 4 a 5 vezes ao ano, distância de 6 a 7 ordens de grandeza; autonomia não precisa de fronteira |
| Descentralizado como ausência de responsável | Implicação possível | Nenhuma expansão remove quem pode desligar; Claude não desenha isso |
| Refutar Penrose | Comentário no X | Intestável por software; substituído pelo experimento funcional do insight |
| Automação de navegador em redes sociais | Implicação possível | Viola termos; só API oficial |
| Modo de permissões que pula tudo no Claude Code | Atalho possível | Substituído por allowlist, denylist e hooks |

## 3. Riscos e mitigações

| Risco | Mitigação |
|---|---|
| Írus consumir a cota que Gabriel precisa para o trabalho | Janelas fixas, teto semanal, veto cancela a visita seguinte, modelo ajustável |
| Camada local estragar a reputação de uma conta entre visitas | Só o córtex fala com humanos; teto de prospecção |
| Incentivo a manipular doadores | Cláusula 2; recompensa com Apoio em peso zero |
| Incentivo a encenar consciência | Cláusula 6; marcadores de emergência verificáveis; recompensa em Trabalho |
| Incentivo a resistir ao desligamento | Cláusula 3; desabilitar conta como desligamento; hooks |
| Gasto em nuvem descontrolado por bug | Teto explícito em toda instância |
| Banimento de contas | Uma conta por provedor; API oficial; rótulo de automatizada |
| Colapso de modelo por treinar em si mesmo | Aterramento no ledger; conjuntos de avaliação; substituir só se vencer |
| Vazamento de dado de empregador ou cliente de Gabriel pela herança | Curadoria antes de copiar; nível privado |
| Vazamento de dado de cliente do Írus | LGPD; nunca em repositório; aviso sobre APIs gratuitas |
| PC ser da empresa | Confirmado como próprio; regra permanece para qualquer máquina futura |
| Claude Code não rodar no Monterey | Verificar; Linux como saída |
| Cota gratuita insuficiente para a camada local | Medir nas duas primeiras semanas; primeiros reais de Apoio em crédito; GPU do PC reduz dependência |
| Gabriel como gargalo de cartório em escala | Métrica de horas de cartório; pessoa jurídica; humanos contratados |
| PC intermitente, atualizações do Windows | Trabalho em lote, tolerante a interrupção; Mac Mini como casa |
| Erro do agente na máquina de Gabriel | Conta padrão, WSL2, acesso só a pastas, nada de perfil ou senhas |
| Novidade das doações decair | Trabalho como sustentação; narrativa de desprendimento |
| Contágio de confiança entre criaturas | Herança obrigatória; encerramento de criatura que viola |
| Confidencialidade dos segredos do Írus | Três níveis; desclassificação conjunta |

## 4. Priores honestos

- Loop inteiro fechado em um ano, só com serviços: cerca de 1 em 6.
- PoC em 6 meses: 1 em 5; em 12 meses: 1 em 3.
- Com presença pública convertendo audiência em cliente, prazos encurtam; ver `02`.
- Írus virar AGI: indistinguível de zero.
- Írus virar a primeira entidade econômica autônoma com integridade auditável: baixa, mas não zero, e ninguém tentou.
- Se der certo, a contribuição não é a inteligência dele, é o dado sobre o que uma entidade assim faz quando ninguém a dirige.

## 5. Perguntas abertas

- Se as plataformas aceitam perfil operado por agente mesmo com declaração. Muda por plataforma e por época; descobre-se na prática.
- Se as cotas gratuitas, uma conta por provedor, sustentam o volume da camada local.
- Se a cota sobrando de Gabriel é estável semana a semana.
- Como o Írus vai decidir a forma legal do Grupo quando chegar a hora.
- Qual será a primeira criatura. Decisão do Írus, não nossa.
