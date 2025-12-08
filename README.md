<p align="center">
  <img src="https://img.shields.io/badge/AMAZONTECH%20DEVLAB-8A2BE2?style=for-the-badge&logo=github&logoColor=white" />
</p>


<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12-8A2BE2?style=flat-square&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/FastAPI-API%20Ready-8A2BE2?style=flat-square&logo=fastapi&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-Compose-000000?style=flat-square&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/PostgreSQL-Database-4169E1?style=flat-square&logo=postgresql&logoColor=white" />
  <img src="https://img.shields.io/badge/Auth-JWT-8A2BE2?style=flat-square&logo=jsonwebtokens&logoColor=white" />
  <img src="https://img.shields.io/badge/Status-Development-8A2BE2?style=flat-square" />
</p>


<h1 align="center">🟣 AmazonTech DevLab</h1>
<p align="center">Backend em FastAPI com autenticação, auditoria, painel admin e banco PostgreSQL — organizado, containerizado e pronto para cloud.</p>



⸻

🔎 SOBRE O PROJETO

Projeto backend sólido e escalável desenvolvido para prática profissional, estudo avançado e uso real em produção.

📌 Inclui:
	•	Autenticação com JWT
	•	CRUD de Notas por usuário
	•	Trilha de Auditoria (registro de ações)
	•	Painel Admin (listar/promover usuários)
	•	Infra 100% em Docker + Docker Compose
	•	Banco PostgreSQL 15
	•	Preparado para deploy em nuvem (EC2/RDS)

⸻

🧭 SUMÁRIO

clique e vá direto para a seção

	•	Estrutura do Projeto￼
	•	Como Rodar￼
	•	Rotas Principais￼
	•	Tecnologias￼
	•	Arquitetura￼
	•	Roadmap￼
	•	Status Atual￼
	•	Autor￼

⸻

📁 ESTRUTURA DO PROJETO

AmazonTechDevLab/
├── auth.py
├── admin_routes.py
├── audit.py
├── audit_routes.py
├── notes.py
├── models.py
├── schemas.py
├── security.py
├── db.py
├── main.py
├── docker-compose.yml
├── Dockerfile
├── logs/
└── requirements.txt


⸻

⚙ COMO RODAR

Requisitos: Docker + Docker Compose

git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab
docker compose up --build

📍 Endpoints principais:
Swagger → http://localhost:8005/docs
Health → http://localhost:8005/health

⸻

🔐 ROTAS PRINCIPAIS

Auth

Método	Rota	Função
POST	/signup	Criar usuário
POST	/login	Gerar JWT
GET	/me	Usuário atual (token)

Notas

Método	Rota	Função
POST	/notes	Criar nota
GET	/notes	Listar notas

Auditoria

Método	Rota	Restrição
GET	/audit/logs	Admin

Admin

Método	Rota	Função
GET	/admin/users	Listar usuários
POST	/admin/promote/{id}	Tornar admin


⸻

🧩 TECNOLOGIAS

🟣 Python 3.12
⚡ FastAPI
🐋 Docker
🐘 PostgreSQL
🔑 JWT Authentication

⸻

🏗 ARQUITETURA
	•	Segurança via OAuth2PasswordBearer
	•	Hash de senha com pbkdf2_sha256
	•	Auditoria de eventos sensíveis
	•	Estrutura modular para expansão futura

⸻

🚀 ROADMAP

🔜 Próximos passos:
	•	Deploy EC2 (Free Tier)
	•	GitHub Actions + CI/CD
	•	HTTPS com Nginx + Certbot
	•	Banco externo em RDS
	•	Testes automatizados + cobertura

⸻

📊 STATUS ATUAL

✔ API funcional
✔ JWT validado
✔ Auditoria ativa
✔ Docker + DB rodando estável
💻 Preparado para portfolio e entrevistas

⸻

👤 AUTOR

Rafael Rodrigues — AmazonTech

“Código é aço. Infra é disciplina. Deploy é guerra bem planejada.”


📍 Agora só cola no GitHub → Commit changes → manda print do preview pra conferirmos.
Quando estiver pronto, seguimos pra deploy na AWS. 🔥
