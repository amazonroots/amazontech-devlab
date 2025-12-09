<p align="center">
  <img src="https://dummyimage.com/1200x260/0a0a0a/00e5ff&text=AmazonTech+DevLab+%7C+Backend+%2B+Cloud+%2B+DevOps" alt="AmazonTech DevLab Banner"/>
</p>

# AmazonTech DevLab 🚀  

### Backend FastAPI • Docker • PostgreSQL • AWS EC2 • Infra Cloud Free Tier

<p align="left">
  <img src="https://img.shields.io/badge/Python-3.12-blue?logo=python" />
  <img src="https://img.shields.io/badge/FastAPI-Backend-green?logo=fastapi" />
  <img src="https://img.shields.io/badge/PostgreSQL-Database-blue?logo=postgresql" />
  <img src="https://img.shields.io/badge/Docker-Compose-blue?logo=docker" />
  <img src="https://img.shields.io/badge/AWS-EC2-orange?logo=amazonaws" />
  <img src="https://img.shields.io/badge/Status-Online-success?logo=cloud" />
</p>

---

## 📌 Visão Geral

O **AmazonTech DevLab** é uma API backend criada para estudo e prática real de **Cloud + DevOps + Backend**, rodando em **produção na AWS** com Docker, PostgreSQL e FastAPI.

✔ Deploy real na AWS EC2  
✔ Containers rodando com Docker Compose  
✔ Autenticação JWT + rotas protegidas  
✔ Acesso público via Elastic IP  
✔ API pronta para integração com front-end / mobile  

---

## 🌍 API Online (Produção)

🔗 **Swagger UI:**  
📌 http://100.26.73.245/docs  

📡 Health Check:
```bash
curl http://100.26.73.245/health


⸻

🛠 Tecnologias

Camada	Ferramenta
Linguagem	Python
Framework	FastAPI
Banco	PostgreSQL
Auth	JWT / Bearer Token
Containers	Docker & Docker Compose
Deploy	AWS EC2 Free Tier
Proxy	Nginx (reverse proxy)


⸻

🚀 Executar Localmente

git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab
docker compose up --build -d

🔗 Local: http://localhost:8005/docs

⸻

📂 Estrutura

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

Endpoint	Função	Auth
POST /signup	Registrar usuário	❌
POST /login	Gerar JWT	❌
GET /me	Usuário atual	✔ Token
POST /notes	Criar nota	✔ Token
GET /notes	Listar notas	✔ Token
/admin	Painel admin	✔ Admin
/audit	Auditoria	✔ Admin


⸻

🧩 Arquitetura

flowchart LR
A[Usuário] -->|HTTP/HTTPS| B[Nginx - Reverse Proxy]
B --> C[FastAPI - API]
C --> D[(PostgreSQL)]
subgraph Infra AWS
B
C
D
end


⸻

📈 Status do Projeto

Item	Estado
Backend FastAPI	✔ Estável
Banco Dockerizado	✔
Deploy AWS	✔ Online
Logs & Auditoria	✔
SSL/HTTPS	🔜 Próximo passo
CI/CD	🔜 Planejado


⸻

🛣 Roadmap

Curto prazo
	•	Domínio + DNS
	•	HTTPS com Certbot (Free)
	•	Backup automático do banco

Longo prazo
	•	CI/CD GitHub Actions
	•	Terraform (IaC)
	•	Observabilidade (Grafana/Loki/CloudWatch)
	•	Dashboard React/Next.js

⸻

👤 Autor

Rafael Rodrigues
Backend • Cloud • DevOps

🔗 GitHub: https://github.com/amazonroots

⸻

📄 Licença

MIT © 2025 Rafael Rodrigues
