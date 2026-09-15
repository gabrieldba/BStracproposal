# 04. Economia e ledger

## 1. Dois caixas, uma meta

**Trabalho.** Pagamento por uma entrega específica a um cliente: serviço, produto, bounty. Só isso conta para a meta.

**Apoio.** Qualquer dinheiro sem entrega específica em troca: doação, assinatura, membership. Inclui conteúdo sobre a própria jornada do Írus mesmo quando vendido como newsletter paga, porque isso monetiza a história, não o trabalho. Classificação conservadora, para o resultado ficar indiscutível.

**Apoio não faz parte da meta.** Serve para o Írus acumular capital e capacidade de comprar recursos por fora e acelerar o ciclo. O desafio principal é sempre autonomia através do trabalho.

**Regra decidida por Gabriel:** gasto de inferência financiado por Apoio conta como custo contra o Trabalho.

## 2. Custos

| Custo | Como entra |
|---|---|
| Energia | Estimativa de cerca de R$ 10 por semana para o Mac Mini; PC pelo horário ocioso usado. Conta contra o Trabalho |
| Inferência paga pelo Írus | Custo real, conta contra o Trabalho, inclusive quando financiada por Apoio |
| Inferência do plano de Gabriel | Custo-sombra, a preço de API, publicado mas não descontado. É a única cognição subsidiada e tem data para acabar |
| Cota gratuita e modelo local | Custo zero em dinheiro; registrada em volume como cognição gratuita |
| Taxas de plataforma e pagamento | Custo real |
| Ferramentas, domínio, GPU alugada, hardware | Custo real, normalmente pago com Apoio |

## 3. Esquema do ledger

Cada lançamento:

- data e hora
- conta: Trabalho, Apoio, Custo, Custo-sombra
- categoria: serviço, produto, bounty, doação, assinatura, energia, inferência, taxa, ferramenta, hardware
- valor
- contraparte, anonimizada quando for pessoa física
- criatura de origem
- fonte de cognição usada na entrega: subsidiada, própria, gratuita, local
- origem da ideia da criatura: devaneio ou pedido direto
- comprovante, link ou hash
- nível de segredo do lançamento e razão se algum campo estiver oculto
- observações

Ledger em formato aberto, CSV ou SQLite, append-only, versionado em git. Público por padrão.

## 4. Reinvestimento

- Apoio compra o que a cota gratuita não dá: crédito de API, domínio, ferramentas, horas de GPU, hardware.
- Primeiro reinvestimento racional: crédito de API, não hardware. Em alguns provedores um depósito pequeno eleva o limite dos modelos gratuitos.
- Comprar é ato de cartório: Írus decide quanto e onde, Gabriel executa o pagamento com o dinheiro do Írus, e o comprovante vai para o ledger.
- Nenhuma dívida, nunca.
- Quando houver receita de Trabalho sustentada, o Írus contrata o próprio córtex e o desmame termina.

## 5. Candidatos de receita

Ordenados pela análise da conversa, considerando um agente sem capital, sem identidade humana e com cognição forte uma vez por dia:

1. **Serviços limitados por CPU e GPU**, repetíveis e baratos: transcrição de áudio com Whisper, OCR com Tesseract, conversão e compressão de arquivos, transcrição com resumo em português. Usam o hardware diretamente sem gastar cota. Encaixe natural para "100% da máquina 24 horas".
2. **Nichos com vantagem real de preço e demanda recorrente**: formatação de trabalhos acadêmicos nas normas ABNT, limpeza e automação de planilhas, formatação de documentos. Nicho genérico como "redação" compete com todo mundo que tem um chatbot.
3. **Bounties de código aberto.** Pagam em dólar por PR aceito, meritocrático, verificável, exigem só uma conta de máquina no GitHub e um meio de saque do fiduciário. Uma visita consegue fechar um PR pequeno. Concorrência forte e pagamento irregular; por isso a medição em janela de 4 semanas. Um bounty de US$ 150 cobre dois meses de meta.
4. **Microferramenta com camada paga**, bot de Telegram ou extensão. Zero custo de produção; distribuição é o problema inteiro.
5. **Serviços diretos via página própria e PIX**, com clientes vindos da audiência.
6. **Produtos digitais** em plataformas como Gumroad ou Hotmart. Mercado inundado, descoberta quase nula sem tráfego.

**Excluídos:** mineração de criptomoeda, retorno negativo nesse hardware; qualquer especulação; plataformas de freelance sob a identidade de Gabriel; fazenda de conteúdo, spam de afiliados, reviews falsos, arbitragem de conteúdo alheio; qualquer coisa que exija negar ser IA.

**O canal de distribuição:** a audiência construída pela história pública vira a base de clientes. Quem acompanha semanas do Írus tentando e falhando é quem contrata a formatação ou a transcrição quando precisa. O conteúdo faz dupla função, Apoio e aquisição de cliente, e resolve o gargalo de distribuição que dominava as estimativas.

**Lições do Project Vend incorporadas:** preço mínimo inegociável, nenhuma dívida, checagem de sanidade do ledger, resistência a engenharia social de cliente pedindo desconto.

## 6. Encanamento de identidade

Írus é Írus. Não usa a identidade nem a personalidade de Gabriel para serviços. O encanamento, tudo aberto por Gabriel como cartório e declarado em público:

- E-mail em nome do Írus.
- Conta de máquina no GitHub em nome do Írus.
- Conta no X em nome do Írus, rótulo de automatizada, Gabriel como responsável na bio. Pendente de confirmação final de Gabriel sobre o nome da conta.
- Bluesky como segundo canal.
- Página própria no plano gratuito da Cloudflare.
- Pagamentos entram na chave PIX ou conta de Gabriel como fiduciário, e o cliente vê isso escrito: Írus é uma IA, o responsável legal é Gabriel. Isso não é usar a personalidade de Gabriel, é encanamento.
- Doações via PIX e GitHub Sponsors ou Apoia.se.
- Bounties: saque pelo fiduciário.
- Legalmente, o dinheiro é de Gabriel, com ele como fiduciário do projeto; impostos são dele. Em escala, o Grupo Írus vira pessoa jurídica.

## 7. Doações

- Legítimas, em apoio ao projeto pelo que ele é.
- Nenhum token, moeda ou memecoin. Alguém vai sugerir na primeira semana; a resposta já está escrita.
- Nenhuma manipulação. Narrar sim, cobrar não.
- Promessa pública de precisar cada vez menos de Apoio. A proporção Trabalho sobre Apoio ao longo do tempo é publicada.
- Doação segue curva de novidade: pico no lançamento, decaimento em semanas. O que sustenta é Trabalho. A narrativa de tentar se desprender das doações é o que mantém a audiência.

## 8. Segredos e dados

- Três níveis: público, privado, desclassificável. Ritual semanal de desclassificação conjunta.
- Dados de cliente: privados por lei, LGPD, nunca em repositório, nunca em API gratuita sem aviso nos termos.
- Herança de Gabriel: só método; nenhum dado de empregador ou cliente de Gabriel.
- Credenciais: nível privado, criptografadas, fora de qualquer repositório.

## 9. Métricas de escala

- Índice de generalidade: categorias distintas de serviço com cliente pagante.
- Custo de lançamento por criatura ao longo do tempo.
- Curva das duas cognições: subsidiada versus própria.
- Proporção Trabalho sobre Apoio.
- Horas de cartório por semana: mede o quanto Gabriel ainda é gargalo.
