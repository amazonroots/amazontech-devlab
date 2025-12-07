<p align="center">
  <img src="https://img.shields.io/badge/AMAZONTECH%20DEVLAB-8A2BE2?style=for-the-badge&logo=amazonaws&logoColor=white" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12-8A2BE2?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/FastAPI-⚡-8A2BE2?style=for-the-badge&logo=fastapi&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-READY-000000?style=for-the-badge&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/PostgreSQL-15-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" />
  <img src="https://img.shields.io/badge/JWT-AUTH-8A2BE2?style=for-the-badge&logo=jsonwebtokens&logoColor=white" />
  <img src="https://img.shields.io/badge/STATUS-DEV_ACTIVE-8A2BE2?style=for-the-badge" />
</p>

<h1 align="center">🟣 AmazonTech DevLab – Cyberpunk Backend Edition</h1>

<p align="center">
Backend profissional com FastAPI + Docker + PostgreSQL + JWT + Auditoria + Admin Panel,
pensado para rodar em cloud como se fosse uma API de Night City: resiliente, rastreável e pronta para upgrade.
</p>

---

## 📌 Visão Geral

O **AmazonTech DevLab** é um backend profissional construído em **FastAPI**, com:

- ✅ Autenticação via **JWT**
- ✅ Módulo de **Notas** vinculado por usuário
- ✅ **Trilha de Auditoria** persistente (quem fez o quê e quando)
- ✅ **Admin Panel** para gerenciamento de usuários e promoção para admin
- ✅ Banco **PostgreSQL 15** rodando em container
- ✅ Infra pronta para rodar em **Docker Compose** local e futura AWS (EC2/RDS/EKS)

Toda a operação roda em containers Docker, com foco em:

> **Profissionalismo arquitetural + rastreabilidade total + preparo para Cloud/DevOps.**

---

## 🧭 Sumário

1. [Linha do Tempo (Diário Técnico)](#-linha-do-tempo--diário-técnico)
2. [Arquitetura Geral](#-arquitetura-geral)
3. [Módulos da API](#-módulos-da-api)
4. [Modelos & Schemas](#-modelos--schemas)
5. [Segurança & JWT](#-segurança--jwt)
6. [Auditoria](#-auditoria)
7. [Admin Panel](#-admin-panel)
8. [Docker & Execução Local](#-docker--execução-local)
9. [Casos Reais de Erro Resolvidos](#-casos-reais-de-erro-resolvidos)
10. [Status Atual do Projeto](#-status-atual-do-projeto)
11. [Roadmap (Próximas Etapas)](#-roadmap-próximas-etapas)
12. [Rodando em 30 segundos](#-rodando-em-30-segundos)
13. [Plano de Deploy AWS](#-plano-de-deploy-aws-ec2)
14. [Autor](#-autor)

---

## 🕒 Linha do Tempo – Diário Técnico

**Dia 1 — 06/11/2025**  
**Tema:** montar ambiente, limpar lixo antigo e estruturar o projeto do zero.

- Ferramentas preparadas:
  - Docker Desktop
  - Docker Compose
  - Python 3.12
  - VS Code + extensões
- Problemas:
  - Diretórios antigos gerando conflito
  - VS Code abrindo pasta errada
  - Docker sem `docker-compose.yml` correto
  - Containers e imagens antigas sujando o ambiente
- Ações:
  - Limpeza geral de containers, volumes e imagens
  - Ajuste do VS Code para abrir sempre a pasta certa
  - Criação/recriação dos arquivos base do projeto
- Resultado:
  - Projeto abrindo corretamente
  - Esqueleto do backend de pé, mas ainda instável

---

**Dia 2 — 07/11/2025**  
**Tema:** Docker + banco + bug crítico do bcrypt.

- Erro ao usar `/signup`:

  > `ValueError: password cannot be longer than 72 bytes`

- Causa:
  - Limitação do `bcrypt` no tamanho da senha
- Decisão:
  - Migrar para `pbkdf2_sha256` via `passlib`
- Resultado:
  - Infra (Docker + PostgreSQL) estável
  - Bug isolado na camada de segurança, não na infra

---

**Dia 3 — 08/11/2025**  
**Tema:** refatorar segurança + JWT estável.

- Alterações:
  - Remoção do `bcrypt`
  - Adoção de `pbkdf2_sha256`
  - Refino de `auth.py`, `security.py`, `schemas.py`
- Endpoints testados:
  - `/signup`
  - `/login`
  - `/me`
  - `/notes`
- Resultado:
  - Fluxo JWT 100% funcional
  - Criação de notas vinculadas ao usuário autenticado
  - Início da trilha de auditoria com `log_action`

---

**Sessões seguintes (11/11, 17/11, 07/12/2025)**

- Consolidação da autenticação
- Garantia de que `is_admin` funciona corretamente
- Auditoria plugada em eventos sensíveis
- Limpeza de rotas antigas/experimentais
- Swagger exibindo **apenas** o que deve estar público

---

## 🏛 Arquitetura Geral

Estrutura de arquivos (visão “Night City Grid”):

```text
AmazonTechDevLab/
├── admin_routes.py      # Rotas /admin/*
├── ai_routes.py         # (Reservado para futuras features de AI)
├── audit.py             # Função log_action()
├── audit_log.py         # Modelo de log (separado)
├── audit_routes.py      # Rotas /audit/logs (admin only)
├── auth.py              # /signup, /login, /me
├── db.py                # engine, SessionLocal, Base
├── docker-compose.yml   # Orquestra API + PostgreSQL
├── Dockerfile           # Build da imagem da API
├── logs/                # Pasta para trilhas de auditoria
├── main.py              # App FastAPI principal
├── models.py            # User, Note, AuditLog
├── notes.py             # CRUD de notas
├── requirements.txt     # Dependências Python
├── schemas.py           # Schemas Pydantic
├── security.py          # Hash + JWT
├── start.sh             # Script de entrada do container
└── tests/
    └── test_health.py   # Teste base /health

Módulos centrais:
	•	Core Auth → auth.py + security.py + schemas.py + models.py
	•	Notes → notes.py + models.Note
	•	Audit → audit.py + audit_routes.py + models.AuditLog
	•	Admin → admin_routes.py + is_admin no modelo User

⸻

🧩 Módulos da API

🔐 Auth (auth.py)
	•	POST /signup
	•	Cria usuário com senha hasheada
	•	POST /login
	•	Valida credenciais
	•	Retorna access_token (Bearer)
	•	GET /me
	•	Retorna dados do usuário autenticado

📓 Notes (notes.py)
	•	GET /notes
	•	Lista notas do usuário logado
	•	POST /notes
	•	Cria nota vinculada ao current_user

📊 Auditoria (audit_routes.py)
	•	GET /audit/logs
	•	Lista eventos de auditoria
	•	Somente admin

🛡 Admin (admin_routes.py)
	•	GET /admin/users
	•	Lista todos os usuários
	•	POST /admin/promote/{user_id}
	•	Promove usuário a admin
	•	Ambas as rotas exigem:
	•	Usuário autenticado
	•	is_admin = True

⸻

🧬 Modelos & Schemas

models.User
	•	id
	•	username (único)
	•	email (único)
	•	hashed_password
	•	created_at
	•	is_admin (bool)
	•	Relacionamentos:
	•	notes → 1:N com Note
	•	audit_logs → 1:N com AuditLog

models.Note
	•	id
	•	text
	•	created_at
	•	owner_id → FK para User.id

models.AuditLog
	•	id
	•	action
	•	detail
	•	ip
	•	user_id (opcional)
	•	created_at

Principais Schemas (schemas.py)
	•	UserCreate
	•	UserOut
	•	LoginIn
	•	Token
	•	NoteCreate
	•	NoteOut
	•	NoteList
	•	AuditLogOut
	•	AuditLogList

⸻

🔐 Segurança & JWT

Implementada em security.py:
	•	Hash de senha:
	•	pbkdf2_sha256 via passlib.context.CryptContext
	•	Funções principais:
	•	hash_password(plain_password)
	•	verify_password(plain, hashed)
	•	create_access_token(data: dict)
	•	decode_token(token: str)
	•	Integração com FastAPI:
	•	OAuth2PasswordBearer(tokenUrl="/login")
	•	get_current_user() → usado como dependency nas rotas protegidas

Resultado: fluxo de autenticação robusto, sem o limite de 72 bytes do bcrypt.

⸻

📊 Auditoria

Função central em audit.py:

log_action(db, action, detail=None, user=None, ip=None)

Eventos típicos registrados:
	•	signup
	•	login_success
	•	login_failed
	•	note_created
	•	Demais eventos sensíveis que forem surgindo

Consulta dos logs:
	•	Endpoint: GET /audit/logs
	•	Restrições:
	•	Usuário autenticado
	•	is_admin = True
	•	Ordenação:
	•	Logs do mais recente para o mais antigo

⸻

🛡 Admin Panel

Tudo sob o namespace /admin:
	•	GET /admin/users
	•	Lista todos os usuários
	•	POST /admin/promote/{user_id}
	•	Promove usuário a admin
	•	Segurança:
	•	JWT obrigatório
	•	is_admin = True validado em dependency específica (require_admin())

⸻

🐳 Docker & Execução Local

Dockerfile (visão conceitual)
	•	Base: python:3.12-slim
	•	Passos:
	1.	Copiar requirements.txt
	2.	pip install -r requirements.txt
	3.	Copiar código para /app
	4.	WORKDIR /app
	5.	Comando:
	•	uvicorn main:app --host 0.0.0.0 --port 8000 --reload

docker-compose.yml

Serviços:
	•	db
	•	image: postgres:15
	•	container_name: amazontech_db
	•	environment:
	•	POSTGRES_USER=postgres
	•	POSTGRES_PASSWORD=postgres
	•	POSTGRES_DB=amazontech_db
	•	ports: "5432:5432"
	•	volumes: postgres_data:/var/lib/postgresql/data
	•	api
	•	build: .
	•	container_name: amazontech_api
	•	command: uvicorn main:app --host 0.0.0.0 --port 8000 --reload
	•	volumes: .:/app
	•	depends_on: db
	•	environment:
	•	DATABASE_URL=postgresql+psycopg2://postgres:postgres@db:5432/amazontech_db
	•	ports: "8005:8000" → host 8005, container 8000

Volumes:
	•	postgres_data

⸻

🧯 Casos Reais de Erro Resolvidos

Erro 48 – OSError: [Errno 48] Address already in use
	•	Causa:
	•	Container amazontech_api já ocupando a porta
	•	Tentativa de rodar uvicorn localmente fora do Docker
	•	Solução:
	•	docker compose down -v --remove-orphans
	•	Padronização: sempre rodar pelo Docker, nunca uvicorn solto
	•	Resultado:
	•	curl http://localhost:8005/health → { "status": "ok" }

⸻

🔥 Status Atual do Projeto
	•	✅ Autenticação com JWT estável
	•	✅ Auditoria persistente em banco
	•	✅ Admin Panel funcional
	•	✅ Docker Compose rodando limpo
	•	✅ Arquitetura organizada e enxuta
	•	✅ Pronto para:
	•	Portfólio
	•	GitHub
	•	Entrevistas técnicas
	•	Futuro deploy em AWS

⸻

🛣 Roadmap – Próximas Etapas

Curto prazo
	•	Subir backend em AWS EC2 (Free Tier)
	•	Adicionar print do Swagger no README
	•	Adicionar tabela de rotas com exemplos de request/response

Médio prazo
	•	Configurar CI/CD com GitHub Actions
	•	Reverse proxy com Nginx + Certbot (HTTPS)
	•	Migrar banco do container para RDS PostgreSQL

Longo prazo
	•	IaC com Terraform
	•	Orquestração com EKS
	•	GitOps com ArgoCD
	•	Camada de AI Safety / Sentinel (futuro “firewall cognitivo”)

⸻

⚙ Rodando em 30 segundos

Pré-requisitos:
	•	Docker
	•	Docker Compose

Passos:

git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab
docker compose up --build

Depois, acessar:
	•	Swagger: http://localhost:8005/docs

Fluxo sugerido de teste:
	1.	POST /signup
	2.	POST /login
	3.	Copiar o access_token
	4.	Usar Authorize no Swagger
	5.	GET /me
	6.	POST /notes
	7.	GET /notes
	8.	(Se admin) GET /audit/logs e GET /admin/users

⸻

☁ Plano de Deploy AWS EC2

Visão geral

Cliente → Internet → EC2 (Ubuntu) → Docker Compose → API + PostgreSQL

Passos principais:
	1.	Criar conta AWS (Free Tier ativa)
	2.	Criar usuário IAM com MFA (uso na CLI)
	3.	Configurar AWS CLI local (aws configure)
	4.	Criar instância EC2 (t2.micro/t3.micro – Ubuntu)
	5.	Liberar portas:
	•	22 (SSH) – restrita ao seu IP
	•	8005 (HTTP) – acesso público (ou via ALB no futuro)
	6.	Instalar Docker + Docker Compose na EC2
	7.	Clonar repositório:
	•	git clone https://github.com/amazonroots/amazontech-devlab.git
	8.	Rodar:
	•	docker compose up --build -d
	9.	Testar:
	•	http://SEU_IP_EC2:8005/docs

⸻

👤 Autor

Rafael Rodrigues (AmazonTech)
	•	Backend / Cloud / DevOps em construção
	•	Foco em infra profissional, segurança, auditoria e AI Safety
	•	Projeto pensado como laboratório real de backend + cloud para portfólio, entrevistas e futuro deploy em produção.
