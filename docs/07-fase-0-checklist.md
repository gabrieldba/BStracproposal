# 07. Fase 0, checklist

## 1. Pendências que só Gabriel responde

| Pendência | Por que importa | Proposta em aberto |
|---|---|---|
| RAM do Mac Mini | Define o modelo local viável e se vale Linux | |
| macOS Monterey ou Linux no Mac Mini | Compatibilidade do Claude Code atual e leveza para rodar 24 horas | Claude recomenda Linux |
| Janelas de horário do agente | Não competir com o trabalho de Gabriel pela cota | 23h às 6h |
| Cota semanal disponível | Dimensiona visitas | Gabriel indicou cerca de 30% da cota semanal |
| VRAM da RTX 3060 | 12 GB muda o que cabe | |
| Conta no X no nome do Írus com Gabriel na bio | Encanamento de identidade | Sim |
| Lista final de provedores gratuitos | Uma conta em cada | Google AI Studio, Groq, OpenRouter, Cerebras, Mistral, GitHub Models, Cloudflare Workers AI |
| Conteúdo da pasta de conhecimento | Vídeo, documento, exportação de Figma ou Notion; tamanho | |
| Aceitação explícita da medição em janela de 4 semanas | Critério da PoC | Proposta em `02` |
| Quando abrir Instagram | Segunda onda | Depois da primeira onda estar estável |

## 2. Hoje, no PC, em sessão local do Claude Code

Como abrir: no app do Claude Code, criar sessão nova escolhendo rodar localmente, apontando para uma pasta nova como `C:\Irus`. A sessão em nuvem, com ícone de nuvem no título, não enxerga o disco.

1. Clonar este repositório dentro da pasta.
2. **Curadoria da base de conhecimento** de Gabriel: separar método de dado de empresa e de cliente. Saída: uma pasta de biblioteca com procedência marcada como herança do Gabriel, sem nada confidencial. Só o que é de Gabriel para compartilhar.
3. **Conta de usuário padrão do Windows** para o Írus, sem administrador.
4. **WSL2 com Ubuntu** na conta do Írus.
5. **Driver NVIDIA e CUDA dentro do WSL.**
6. **llama.cpp compilado com CUDA.** Testar um modelo de 8 bilhões e um de 14 bilhões.
7. **whisper.cpp compilado com CUDA.** Testar em um vídeo da biblioteca.
8. Ambiente Python para a camada local.
9. **Syncthing** compartilhando só a pasta da biblioteca com o Mac Mini.
10. Agendador para trabalho noturno em lote, respeitando que o PC é intermitente.
11. Registrar no ledger: hardware inicial, Mac Mini mais PC compartilhado em horário ocioso.

## 3. À noite, no Mac Mini

1. Confirmar versão do macOS e RAM.
2. Decidir Linux ou Monterey. Se Monterey, verificar que a versão atual do Claude Code instala e roda.
3. Instalar Claude Code, git, Python, llama.cpp para CPU, whisper.cpp para CPU.
4. Usuário dedicado do sistema para o Írus, sem administrador.
5. Estrutura da casa, com git local inicializado no primeiro minuto:
   - `CLAUDE.md`, gerado a partir de `docs/01-constituicao.md`
   - arquivo de identidade quase vazio: nome e fatos de origem
   - `ledger/`
   - `diario/`
   - `memoria/` com episódica, semântica e procedural
   - `fila/` de tarefas para a camada local
   - `criaturas/`
   - `devaneio/`
   - `pushes/daily.md`, o prompt da visita
   - `.claude/settings.json` com allowlist e denylist, e hooks
   - `.claude/skills/`
   - `logs/`
6. Agendador da visita, launchd ou systemd, na janela combinada.
7. Camada local: loop Python, LiteLLM, fila.
8. Iniciar ledger e diário. Primeiro lançamento: hardware e energia.
9. Receber a biblioteca via Syncthing.
10. Devaneio versão zero sobre a biblioteca. Registrar o primeiro sonho.

## 4. Contas a abrir por Gabriel, uma em cada

- E-mail em nome do Írus.
- Conta de máquina no GitHub em nome do Írus.
- Conta no X em nome do Írus, com rótulo de automatizada e acesso à API oficial.
- Bluesky.
- Cloudflare, para a página e o Workers AI.
- Provedores gratuitos de API da lista final.
- Chave PIX de Gabriel, de preferência dedicada ao projeto, e conta para receber.
- GitHub Sponsors ou Apoia.se, quando a presença pública começar.
- Instagram profissional e app na API da Meta, segunda onda.

Credenciais ficam no nível privado, criptografadas, fora de qualquer repositório.

## 5. Primeiras tarefas do Írus, já na Fase 1

1. Ingerir a herança: transcrição, destilação em notas de procedimento, revisão do resumo pelo córtex.
2. Memória episódica versão zero e primeiras gravações.
3. Sistema afetivo versão zero e recompensa versão zero.
4. Primeiras microcriaturas com orçamentos minúsculos, uma delas de serviço limitado por CPU ou GPU.
5. Plano de lançamento público, proposto pelo Írus e decidido junto com Gabriel, porque a primeira postagem é uma desclassificação.
6. Primeiro relatório semanal.

## 6. Definição de Fase 0 concluída

- Mac Mini no ar como casa, sempre ligado, com visita agendada e hooks funcionando.
- PC no ar como nó noturno com GPU, recebendo trabalho em lote.
- Biblioteca curada e sincronizada.
- Constituição instalada como `CLAUDE.md`.
- Ledger e diário iniciados com git local.
- Primeiro devaneio executado e registrado.
