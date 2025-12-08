📄 README.md — AmazonTech DevLab — Night City Edition

⚡ Backend profissional, autenticado, com auditoria e pronto para AWS. Energia neon, arquitetura limpa, documentação de respeito.

⸻


<div align="center">


🔥 AMAZONTECH DE VLAB — BACKEND FASTAPI + DOCKER + POSTGRES + JWT + AUDITORIA

<img src="https://img.shields.io/badge/Python-3.12-8A2BE2?style=for-the-badge&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/FastAPI-⚡-f000ff?style=for-the-badge&logo=fastapi&logoColor=white"/>
<img src="https://img.shields.io/badge/Docker-READY-00e5ff?style=for-the-badge&logo=docker&logoColor=white"/>
<img src="https://img.shields.io/badge/PostgreSQL-15-00c8ff?style=for-the-badge&logo=postgresql&logoColor=white"/>
<img src="https://img.shields.io/badge/JWT-AUTH-ff00aa?style=for-the-badge&logo=jsonwebtokens&logoColor=white"/>
<img src="https://img.shields.io/badge/API_STATUS-ACTIVE-8A2BE2?style=for-the-badge"/>


</div>



⸻

VISÃO GERAL

Backend completo rodando em FastAPI com:

✔ Autenticação JWT
✔ Auditoria persistente (eventos registrados no banco)
✔ Sistema de Notas vinculado ao usuário autenticado
✔ Painel Admin (listar usuários / promover para admin)
✔ Rodando totalmente em Docker
✔ Banco PostgreSQL dentro do Compose
✔ Pronto para deploy em AWS / EC2 / RDS

Swagger: http://localhost:8005/docs
Healthcheck: http://localhost:8005/health

⸻

ESTRUTURA ATUAL DO PROJETO

AmazonTechDevLab/
├── auth.py             # signup/login/me + auth flow
├── audit.py            # registro de logs
├── audit_routes.py     # rotas de auditoria (admin-only)
├── admin_routes.py     # rotas administrativas
├── notes.py            # CRUD autenticado de notas
├── models.py           # User, Note, AuditLog
├── schemas.py          # Pydantic schemas
├── security.py         # hash PBKDF2 + JWT
├── db.py               # conexão e sessão com PostgreSQL
├── docker-compose.yml  # API + DB
├── Dockerfile
├── requirements.txt
├── start.sh
└── logs/


⸻

COMO SUBIR O AMBIENTE

Ambiente completo com API + PostgreSQL:

docker compose down -v --remove-orphans
docker compose up --build

Acesso principal:

http://localhost:8005

Swagger:

http://localhost:8005/docs


⸻

ENDPOINTS PRINCIPAIS

🔐 Autenticação

Método	Rota	Descrição
POST	/signup	Cria usuário
POST	/login	Gera token JWT
GET	/me	Usuário autenticado

🗒 Notas

Método	Rota
POST	/notes
GET	/notes

🧾 Auditoria

| GET | /audit/logs (admin) |

🧩 Admin

| GET | /admin/users |
| POST | /admin/promote/{id} |

⸻

MODELOS

User → id • username • email • hashed_password • created_at • is_admin
Note → texto vinculado ao usuário
AuditLog → registra ações (signup/login/create_note etc.)

⸻

SEGURANÇA
	•	Hash: PBKDF2-SHA256 (passlib)
	•	JWT com expiração
	•	Rotas protegidas via OAuth2PasswordBearer

hash_password()
verify_password()
create_access_token()


⸻

COMANDOS ÚTEIS

docker compose up --build     # sobe tudo novo
docker compose down           # parar
docker exec -it amazontech_db psql -U postgres -d amazontech_db  # entrar no banco

Promover usuário a admin:

UPDATE users SET is_admin = true WHERE username = 'admin';


⸻

EVOLUÇÃO FUTURA — ROAD TO CLOUD

🟦 Deploy EC2 Free Tier
🟦 Certbot + HTTPS
🟦 RDS para DB gerenciado
🟦 GitHub Actions CI/CD
🟦 Terraform para IaC
🟦 ArgoCD para GitOps

⸻

STATUS FINAL ATUAL

🔥 API rodando estável
🔐 JWT validado
📜 Auditoria funcional
🧩 Admin operante
🐋 Docker pronto para cloud
🚀 Projeto nível portfólio

⸻

Feito por

Rafael Rodrigues — AmazonTech

“Código é aço. Banco é cimento. Infra é guerra.”
“Documentação é o neon que ilumina o beco onde só os fortes passam.”
