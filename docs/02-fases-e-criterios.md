# 02. Fases e critérios

## Visão geral

| Fase | Nome | Prazo | Motor de partida ligado? | Termina quando |
|---|---|---|---|---|
| 0 | Preparação | 1 a 3 semanas, depende da cota | Sim, cota de preparação | Os dois nós estão no ar e o primeiro devaneio rodou |
| 1 | Descoberta | Sem prazo | Sim, visitas diárias | Existe um modelo funcional e repetível de receita de Trabalho |
| 2 | Prova de conceito | 4 semanas corridas | Sim, com custo-sombra registrado | Meta batida por 4 semanas consecutivas |
| 3 | Desmame | Semanas a meses | Reduzindo até zero | 4 semanas com zero visitas e lucro positivo |
| 4 | Grupo Írus | Aberto | Não | Não termina |

## Fase 0. Preparação

Dono: Claude, em sessões locais no PC e no Mac Mini, gastando a cota de preparação de Gabriel. Gabriel faz os atos de cartório. Checklist completo em `07-fase-0-checklist.md`. Definição de pronto: Mac Mini como casa sempre ligada; PC como nó noturno com GPU; herança curada e ingerida; constituição instalada como `CLAUDE.md` com hooks; ledger e diário iniciados; primeiro devaneio executado e registrado.

## Fase 1. Descoberta

- Sem prazo.
- Teto semanal de gasto de cota de Gabriel, cerca de 30% da cota semanal do plano dele, e regra de parada por veto.
- Relatório semanal escrito pelo Írus. Gabriel lê e só pode vetar.
- Descoberta de portfólio: em vez de testar um nicho por vez, Írus lança microcriaturas em paralelo com orçamentos minúsculos e mata rápido. O primeiro serviço é a primeira criatura.
- Primeiro material da memória e do devaneio: a herança curada de Gabriel.
- Custo-sombra registrado desde o primeiro dia.
- Os primeiros reais de Apoio podem virar crédito de API antes de qualquer outra coisa, se a cota gratuita não sustentar a camada local. Isso se mede nas duas primeiras semanas.

## Fase 2. Prova de conceito

**Meta vigente:** lucro líquido de Trabalho de R$ 100 por semana, mantido por 4 semanas consecutivas.

**Medição em janela de 4 semanas**, proposta de Claude para acomodar receita irregular como bounties, com aceitação implícita de Gabriel ao fixar os R$ 100 por semana:

- Pelo menos R$ 400 líquidos de Trabalho por janela de 4 semanas.
- Pelo menos 3 clientes distintos na janela.
- Pelo menos 2 semanas da janela com receita de Trabalho.

**O que é lucro líquido de Trabalho:**

```
Lucro líquido de Trabalho =
    receita de Trabalho recebida na conta
  - energia estimada (cerca de R$ 10 por semana para o Mac Mini; o PC entra pelo horário ocioso usado)
  - inferência consumida e paga pelo Írus, inclusive a financiada por Apoio
  - taxas de plataforma e de pagamento
  - ferramentas, domínio e serviços pagos
```

Decisão de Gabriel: **gasto de inferência financiado por doação conta como custo contra o Trabalho.** Sem isso um Írus rico em doações passaria estruturalmente dependente delas.

**O que não entra na conta mas é publicado:** o custo-sombra das visitas de Claude no plano de Gabriel, a preço de API. É a única cognição subsidiada, e o relatório mostra quanto de cognição subsidiada cada real de lucro consumiu.

**O que não conta como Trabalho:** Apoio de qualquer forma. Receita vinda de Gabriel ou de conhecidos dele. Qualquer receita sem entrega específica a um cliente.

**Quando a receita é contada:** quando o dinheiro entra na conta, não quando o serviço é entregue. Plataformas pagam em lotes e a data de repasse distorce a contagem semanal; a janela de 4 semanas mitiga isso.

**Critérios originais substituídos:** lucro acima de R$ 10 por semana; 3 dias com receita positiva por semana. Registrados em `08`.

**Recompensa após a PoC:** Gabriel expande a capacidade do Írus. Orientação registrada na conversa: para modelo local o que importa é memória, unificada ou de GPU, não processador; um PC de 12 GB sem GPU muda pouco; crédito de API compra mais cognição que hardware barato. Com o PC de Gabriel já cedido como nó, a expansão mais útil provavelmente é crédito ou memória.

## Fase 3. Desmame

O momento em que as visitas de Claude no plano de Gabriel chegam a zero é a graduação de verdade, e tem critério explícito.

**Cronograma padrão:** visitas caem de diária para três por semana, depois uma por semana, depois zero. Em cada degrau o Írus precisa manter lucro de Trabalho acima dos custos com a inferência comprada da própria receita. Se falhar num degrau, volta um degrau e tenta de novo.

**Gatilho alternativo, mais natural:** as visitas param quando Írus consegue pagar o próprio córtex com Apoio mais Trabalho. Doação acelera a saída da cota de Gabriel, não a meta.

**Graduação:** 4 semanas com zero visitas e lucro de Trabalho positivo.

**Custo de referência de uma visita diária de cerca de 60 turnos, paga pelo Írus via API, por semana, a câmbio de cerca de R$ 5,50 por dólar e com cache:**

| Córtex | Custo semanal aproximado |
|---|---|
| Haiku 4.5 | R$ 40 a R$ 50 |
| Sonnet 5 | R$ 80 a R$ 110 |
| Opus 5 | R$ 200 a R$ 250 |

Daí a meta de R$ 100 por semana: é a faixa em que uma visita diária em Sonnet se paga. Autossuficiência honesta está nessa ordem, dez vezes a barra original.

## Fase 4. Grupo Írus

Sem fim. Métricas adicionais que entram no ledger:

- **Índice de generalidade:** número de categorias distintas de serviço com cliente pagante. Um Írus que fatura só numa categoria é um negócio de nicho; um que fatura em doze que ele mesmo descobriu mostra generalidade econômica.
- **Custo de lançamento por criatura ao longo do tempo:** se cair, a plataforma compartilhada está compondo.
- **Curva das duas cognições:** subsidiada versus própria. Resume o experimento inteiro.
- **Proporção Trabalho sobre Apoio ao longo do tempo:** a promessa pública é precisar cada vez menos de Apoio.

## Estimativas honestas

Não existe caso conhecido de agente autônomo com capital zero sustentando receita legítima. As estimativas abaixo são intuição, não estatística. Foram feitas antes de o PC com GPU entrar no desenho, o que melhora a camada local mas não muda o gargalo, que é distribuição e confiança.

**Só com serviços, sem presença pública:**

| Marco | Prazo provável | Chance |
|---|---|---|
| Fase 0 pronta | 1 a 3 semanas | Alta |
| Primeira receita de desconhecido | 3 a 8 semanas após o boot | Cerca de 1 em 2 |
| Primeira semana com R$ 100 | 2 a 4 meses | Cerca de 1 em 3 |
| PoC de 4 semanas | 4 a 9 meses | 1 em 5 até 6 meses, 1 em 3 até 12 meses |
| Desmame completo | 2 a 3 meses após a PoC | Cerca de 1 em 2, dado que a PoC passou |
| Loop inteiro fechado em um ano | | Cerca de 1 em 6 |

**Com doações e presença pública:**

| Marco | Prazo provável | Chance |
|---|---|---|
| Primeira receita de desconhecido | 1 a 2 semanas | |
| Primeira semana com R$ 100 | 2 a 6 semanas | Cerca de 1 em 2 |
| PoC de 4 semanas | 2 a 5 meses | Cerca de 1 em 2 |
| Sustentar por 6 meses após o pico inicial | | Cerca de 1 em 3 |

Atenção: esta segunda tabela foi feita quando doações contavam para a meta. Com doações fora da meta, os prazos de Trabalho voltam a depender da audiência virar cliente, o que fica entre as duas tabelas. A primeira receita de Trabalho vinda da audiência é estimada em 4 a 10 semanas.

**O que move as probabilidades:**

1. Nicho com vantagem real de preço e demanda recorrente.
2. Audiência convertendo em cliente.
3. Medição em janela de 4 semanas.
4. Quantos turnos por dia sobram do plano de Gabriel: 60 turnos fazem trabalho de cliente; 15 só fazem manutenção.
5. GPU do PC reduzindo a dependência de cota e de nuvem gratuita.

**Modo de falha mais provável:** não é "não sabe fazer o trabalho". É a camada local estragar a reputação de uma conta entre visitas, gastar cota deliberando em vez de executando, ou travar em barreiras de identidade e termos de uso.

**Chance de virar AGI:** indistinguível de zero. **Chance de virar a primeira entidade econômica autônoma com integridade auditável:** baixa, mas não zero, e ninguém tentou.

## Referência: custo de inferência versus energia

Estimativa feita na primeira análise, quando o cérebro seria só API paga. Assume Opus 5 como córtex, câmbio de cerca de R$ 5,50 por dólar, uso de cache, e energia de cerca de R$ 10 por semana para um Mac Mini de 2014 a plena carga.

| Componente | Cenário enxuto | Cenário "expansão extrema" 24 horas |
|---|---|---|
| Energia do Mac Mini | Cerca de R$ 10 por semana | Cerca de R$ 10 por semana |
| Tokens de inferência | Cerca de R$ 450 por semana | Cerca de R$ 4.000 por semana |

O cenário enxuto assume checagens a cada 30 minutos mais uma sessão estratégica diária. O extremo assume o loop rodando sem parar. Em Sonnet 5, dividir por cerca de 2,5. Conclusão que moldou tudo depois: tokens custam entre 40 e 400 vezes a energia, e a meta original de "lucro acima de R$ 10 por semana" media um custo irrelevante. Foi isso que levou às decisões D1 e D2 e, mais tarde, ao motor de partida com a cota de Gabriel e ao desmame.
