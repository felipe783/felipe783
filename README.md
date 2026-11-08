<h1 align="center">Felipe Prior Mulinari</h1>

<p align="center">
  Estudante de Engenharia de Software na FAG<br/>
  <sub>backend · inteligência artificial · infraestrutura</sub>
</p>

<p align="center">
  <a href="https://felipemulinari.vercel.app"><img src="https://img.shields.io/badge/Portf%C3%B3lio-felipemulinari.vercel.app-1b2bff?style=for-the-badge&labelColor=101114" alt="Portfólio: felipemulinari.vercel.app"/></a>
  <a href="mailto:felipemulinarii@gmail.com"><img src="https://img.shields.io/badge/E--mail-felipemulinarii%40gmail.com-1b2bff?style=for-the-badge&logo=gmail&logoColor=white&labelColor=101114" alt="E-mail: felipemulinarii@gmail.com"/></a>
</p>

---

Meu foco é **inteligência artificial, machine learning e backend**: treinar e avaliar modelos e construir as APIs que colocam esses modelos para funcionar. Aprendo construindo e documento o que descubro, inclusive o que deu errado.

> O [**portfólio**](https://felipemulinari.vercel.app) tem os estudos de caso completos, com decisões, limitações e próximos passos de cada projeto.

## Projetos em destaque

### IA_Ratos · visão computacional

Conta os passos das quatro patas de ratos filmados em esteira, uma tarefa que em pesquisa de marcha é feita à mão, quadro a quadro.

- **Como:** um YOLO11n treinado no projeto, com uma classe por pata, e um rastreador próprio por máquina de estados. A pata levantou quando a detecção some por 0,15 s e pousou quando volta estável por 0,18 s. Cada passo vira um evento auditável no vídeo.
- **Desafio:** a comparação com humanos era injusta, porque em 15 dos 21 vídeos o humano contou só um trecho. No recorte comparável, o erro (MAPE) é de 12,35%.
- **Entrega:** API FastAPI com autenticação (Argon2), fila de análises e limites de recurso; app desktop em Tauri com atualização assinada; deploy com Docker e GitHub Actions.

`Python` `YOLO11n` `PyTorch` `OpenCV` `FastAPI` `PostgreSQL` `Tauri` `Docker`<br/>
<sub>Projeto em equipe de quatro pessoas · repositório privado · [estudo de caso](https://felipemulinari.vercel.app/projetos/ia-ratos)</sub>

### [Snake DQN](https://github.com/felipe783/Teste_AI) · aprendizado por reforço

Um agente que aprende Snake com Double DQN em PyTorch. A primeira versão aprendia a comer e depois se encurralava no próprio corpo.

- **Como:** o estado passou de 11 para 21 entradas, 12 delas calculadas por BFS: espaço livre e rota até a comida e até a cauda para cada ação. O treino longo roda headless em Docker num servidor.
- **Desafio:** uma auditoria mostrou que o agente estagnou em ~100 pontos e que selecionar e avaliar nas mesmas partidas inflava o resultado. Com sementes fora da seleção, ele faz 101,0 ± 10,3 pontos em 40 partidas. A auditoria também corrigiu dois bugs de checkpoint e deixou o treino 4,5× mais rápido.

`Python` `PyTorch` `Docker` `unittest`<br/>
<sub>Experimental · [estudo de caso](https://felipemulinari.vercel.app/projetos/snake-dqn)</sub>

<p align="center">
  <img src="https://raw.githubusercontent.com/felipe783/Teste_AI/main/assets/snake_dqn.gif" alt="Agente DQN jogando Snake" width="320"/>
</p>

### Hivecast · telemetria offline-first

Sou o desenvolvedor do RaspberryAgent, a camada de software de uma colmeia inteligente: coleta peso e temperatura vindos dos sensores e sincroniza com o servidor mesmo com a rede caindo.

- **Como:** SQLite com WAL funciona como fila persistente, e cada medição recebe um UUID na origem. Assim a leitura fica segura no commit local e reenviar nunca duplica. Retry com backoff separa falhas temporárias de permanentes.
- **Desafio:** revisando a validação, encontrei faixas de temperatura que descartariam exatamente as anomalias que o monitoramento existe para detectar.

`Python` `SQLite` `Pydantic Settings` `httpx` `pytest`<br/>
<sub>Projeto de um colega, com equipe de hardware · repositório privado · [estudo de caso](https://felipemulinari.vercel.app/projetos/hivecast)</sub>

### [Protheus](https://github.com/felipe783/Protheus) · extração de documentos

API que recebe PDF, XML, DOCX ou ODT, classifica o tipo de documento e extrai os campos de CRLV-e, Cartão CNPJ e NF-e.

- **Como:** Regex para layouts fixos, que são previsíveis e fáceis de testar, e leitores por extensão criados via Factory, em camadas inspiradas em Clean Architecture.

`Python` `FastAPI` `pypdf` `python-docx` `pytest`<br/>
<sub>Em desenvolvimento · [estudo de caso](https://felipemulinari.vercel.app/projetos/protheus)</sub>

### [Financeiro](https://github.com/felipe783/Controle_Financeiro) · gestão financeira pessoal

Contas, investimentos com cotações, patrimônio, orçamentos e metas.

- **Como:** cada usuário só vê os próprios dados por Row-Level Security no PostgreSQL, com `FORCE`, garantido pelo banco e não só pela aplicação. Desligando o RLS, 12 dos 14 testes de isolamento falham.

`Python` `FastAPI` `SQLAlchemy` `PostgreSQL` `React` `TypeScript` `Docker`<br/>
<sub>Em desenvolvimento · [estudo de caso](https://felipemulinari.vercel.app/projetos/financeiro)</sub>

## Outros projetos

| Projeto | O que é | Stack |
|---|---|---|
| [Budgeting](https://github.com/felipe783/Api_ReconhecimentoVoz) | Gastos por voz: o áudio é transcrito e um LLM usa *tool calling* para registrar ou consultar transações | Java, Spring Boot, Spring AI, MySQL |
| [Problema do Papai Noel](https://github.com/felipe783/Problema_Papai-Noel) | Sincronização com 1 mutex e 4 variáveis de condição, com 25 execuções medidas (Sistemas Operacionais) | C11, pthreads, Python |
| S.C.A e frontends demonstrativos | Interfaces sem backend para apresentações; o S.C.A aproxima colegas de escola que jogam os mesmos jogos. Demos: [S.C.A](https://sca-sempre-com-amigos.vercel.app) · [Taewkondo](https://taewkondo.vercel.app) · [M&J](https://mj-psi-dun.vercel.app) | TypeScript, React, Next.js, Vitest |
| [Bot-Discord](https://github.com/felipe783/Bot-Discord) | Slash commands com história colaborativa diária, Blackjack e busca de mods no Modrinth | Python, discord.py, Docker |
| [Missão Espacial](https://github.com/felipe783/Missao_Espacial-JAVA) | Centro de controle de missões (atividade de sala) | Java, Spring Boot, MySQL, Flyway |

## Tecnologias

Listo só o que aparece em código meu.

| Área | Uso em projetos | Estudando |
|---|---|---|
| Linguagens | Python, Java, C, TypeScript, SQL | |
| Backend | FastAPI, Spring Boot, Spring AI, SQLAlchemy, Alembic | |
| Dados | PostgreSQL (RLS), SQLite, MySQL, pandas | |
| IA e ML | PyTorch (DQN), YOLO (Ultralytics), OpenCV, LLM com tools | adaptação de pesos e *machine unlearning* (tema do TCC) |
| Infraestrutura | Docker, Linux (Ubuntu Server), Nginx, GitHub Actions | AWS EC2 |
| Testes | pytest, unittest, Vitest | |

## Formação e experiência

- **Engenharia de Software**, FAG (em curso).
- **Java & Spring Boot AI Developer** (Globant) e **Backend Java com Spring AI** (NTT DATA), bootcamps na DIO.
- **Suporte técnico** na [MX Soluções](https://mxsolucoes.com.br), para um provedor de internet de Cuiabá.
- Mantenho um **servidor doméstico** em Ubuntu Server, com containers, monitoramento pelo Uptime Kuma e alertas no Telegram.

---

<p align="center">
  <a href="https://felipemulinari.vercel.app">Portfólio</a> ·
  <a href="mailto:felipemulinarii@gmail.com">felipemulinarii@gmail.com</a>
</p>
