# AmazonTech DevLab 🚀  
Backend FastAPI | Docker | PostgreSQL | AWS EC2

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python)
![FastAPI](https://img.shields.io/badge/FastAPI-API-green?logo=fastapi)
![Docker](https://img.shields.io/badge/Docker-Compose-blue?logo=docker)
![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-blue?logo=postgresql)
![AWS](https://img.shields.io/badge/Cloud-AWS%20EC2-orange?logo=amazonaws)
![Status](https://img.shields.io/badge/Deploy-Online-success)

---

## 📌 Visão Geral

**AmazonTech DevLab** é uma API backend desenvolvida com **FastAPI + PostgreSQL**, containerizada com **Docker Compose** e hospedada na **AWS EC2 Free Tier**.  
Projeto criado como laboratório profissional para prática real de infraestrutura em nuvem, deploy, autenticação JWT e boas práticas Dev/Cloud.

✔ Deploy real em produção  
✔ Containers rodando com Docker  
✔ Banco PostgreSQL isolado  
✔ JWT Auth com rotas protegidas  
✔ Swagger UI aberto ao público  

---

## 🌍 API em Produção

🔗 **Swagger UI:**  
📌 http://100.26.73.245/docs  

📡 Health Check:
```bash
curl http://100.26.73.245/health


⸻

🛠 Tecnologias Utilizadas
	•	Python + FastAPI
	•	PostgreSQL (container)
	•	Docker + Docker Compose
	•	Nginx (reverse proxy)
	•	AWS EC2 Free Tier
	•	Autenticação JWT + Bearer Token

⸻

🚀 Como rodar localmente

git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab
docker compose up --build -d

API local: http://localhost:8005/docs

⸻

📂 Estrutura do Projeto

amazontech-devlab/
├─ app/
│  ├─ main.py
│  ├─ auth/
│  ├─ notes/
│  ├─ admin/
│  └─ audit/
├─ docker-compose.yml
├─ Dockerfile
└─ README.md


⸻

🔐 Rotas principais

Rota	Função	Auth
POST /signup	Criar usuário	❌
POST /login	Login + Token JWT	❌
GET /me	Info do usuário	✔
POST /notes	Criar nota	✔
GET /notes	Listar notas	✔
/admin	Área administrativa	✔ Admin
/audit	Auditoria	✔ Admin


⸻

📈 Status Atual

Item	Status
Backend FastAPI	✔
Banco PostgreSQL	✔
Deploy AWS EC2	✔ Online
Docker Compose	✔
Swagger Docs	✔ Público
SSL/HTTPS	❌ a implementar


⸻

🗺 Roadmap

Curto prazo
	•	Configurar domínio + DNS
	•	HTTPS com Certbot (free)
	•	Backup automático do PostgreSQL

Próximos passos
	•	CI/CD com GitHub Actions
	•	IaC com Terraform
	•	Observabilidade (Grafana/Loki)
	•	Frontend (React) + Dashboard

⸻

👨‍💻 Autor

Rafael Rodrigues
Backend & Cloud Development

GitHub: https://github.com/amazonroots
