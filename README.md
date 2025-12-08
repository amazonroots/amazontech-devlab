<p align="center">
  <img src="https://img.shields.io/badge/AMAZONTECH%20DEVLAB-2E2A52?style=for-the-badge&logo=amazonaws&logoColor=white" />
</p>


<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/FastAPI-BACKEND-009688?style=for-the-badge&logo=fastapi&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-COMPOSE-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/PostgreSQL-15-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" />
  <img src="https://img.shields.io/badge/JWT-AUTH-F7DF1E?style=for-the-badge&logo=jsonwebtokens&logoColor=black" />
  <img src="https://img.shields.io/badge/Status-Active-4CAF50?style=for-the-badge" />
</p>



⸻

🟣 AmazonTech DevLab — Backend Profissional

API backend desenvolvida com FastAPI, Docker, PostgreSQL e JWT Authentication, com auditoria completa, painel admin, CRUD de notas, arquitetura organizada, documentação clara e pronta para deploy na AWS.

Este repositório serve como laboratório real de backend + cloud, usado para estudo, portfólio e evolução contínua.

⸻

📌 Recursos Principais
	•	🔐 Autenticação JWT
	•	🗒 Notas por usuário autenticado
	•	🧾 Auditoria de ações (login, criação, etc)
	•	🛡 Admin Panel com promoção de usuários
	•	🐳 Infra completa em Docker Compose
	•	🗃 PostgreSQL 15 como banco
	•	🚀 Pronto para deploy em EC2/RDS

Swagger UI → http://localhost:8005/docs
Healthcheck → http://localhost:8005/health

⸻

🧱 Arquitetura do Projeto

AmazonTechDevLab/
├── admin_routes.py      # Rotas administrativas
├── audit.py             # Função log_action()
├── audit_routes.py      # Logs de auditoria (admin-only)
├── auth.py              # /signup /login /me
├── db.py                # Conexão com PostgreSQL
├── docker-compose.yml   # API + Database
├── Dockerfile           # Build da aplicação
├── logs/                # Registros de atividade
├── main.py              # App principal FastAPI
├── models.py            # User, Note, AuditLog
├── notes.py             # CRUD de notas
├── schemas.py           # Schemas Pydantic
├── security.py          # Hash + JWT
└── tests/               # Testes futuros


⸻

🔐 Segurança & JWT
	•	Hash com pbkdf2_sha256
	•	Token de acesso via Bearer
	•	Middleware centralizado para autenticação
	•	Rotas protegidas apenas com token válido

Funções-chave:

hash_password()
verify_password()
create_access_token()
get_current_user()


⸻

🗒 Notas

Método	Rota	Descrição
POST	/notes	Cria nota
GET	/notes	Lista notas do usuário


⸻

🧾 Auditoria

Tudo que importa fica rastreado.

Eventos registrados:

signup
login_success
login_failed
note_created

Consulta:

GET /audit/logs   # Admin


⸻

🛡 Admin Panel

Permite gestão de usuários:

Método	Rota	Função
GET	/admin/users	Lista usuários
POST	/admin/promote/{id}	Promove para admin


⸻

🐳 Executando com Docker

Requisitos: Docker + Docker Compose

git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab
docker compose up --build

Acesse:

📄 Swagger → http://localhost:8005/docs
🔍 Health → http://localhost:8005/health

Fluxo de teste rápido:
	1.	POST /signup
	2.	POST /login
	3.	Cole token → Authorize
	4.	/me, /notes

⸻

🚀 Roadmap — Evolução

Curto prazo
	•	Prints do Swagger no README
	•	Deploy AWS EC2 Free Tier

Médio prazo
	•	GitHub Actions (CI/CD)
	•	HTTPS com Nginx + Certbot
	•	Banco em RDS

Longo prazo
	•	Terraform (IaC)
	•	EKS & Infra escalável
	•	Observability + metrics

⸻

👤 Autor

Rafael Rodrigues — AmazonTech
Backend | Cloud | DevOps | Infra & Deploy

“Projeto prático para consolidar conhecimento, documentação viva e evolução contínua.”
