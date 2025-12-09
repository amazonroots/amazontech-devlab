# AmazonTech DevLab — FastAPI + Docker + PostgreSQL + AWS EC2 🚀

**Backend em produção, rodando em infraestrutura própria na nuvem.**  
Projeto criado para laboratório profissional em **Cloud / DevOps / Backend**, com deploy real e acesso global.

> **"Infra própria, backend sólido e deploy funcional.  
> Não é demo — é produto rodando na nuvem."**

---

## 📌 Sobre o projeto

O **AmazonTech DevLab** é um backend desenvolvido em Python com FastAPI, utilizando autenticação JWT, CRUD de notas, área administrativa e auditoria.  
Toda a infraestrutura roda conteinerizada com Docker + Docker Compose e publicada na AWS EC2 Free Tier.

É um projeto de portfólio técnico para demonstrar experiência prática em desenvolvimento de APIs, cloud computing e deploy profissional.

---

## 🛠 Stack Principal

| Camada | Tecnologia |
|-------|------------|
| Linguagem | Python 3.12 |
| Framework Web | FastAPI |
| Banco | PostgreSQL |
| Autenticação | JWT / Bearer Token |
| Containers | Docker + Docker Compose |
| Infraestrutura | AWS EC2 (Ubuntu 24.04) |
| Reverse Proxy | Nginx |
| OS local | macOS + VS Code + Zsh |

---

## 🌍 Deploy em Produção (Ativo)

Instância EC2 com Docker + PostgreSQL + FastAPI rodando 24/7.  
A API está acessível publicamente via Elastic IP.

🔗 **Swagger UI:**  
**http://100.26.73.245/docs**

📡 Health check:  
`curl http://100.26.73.245/health`

---

## ▶ Como rodar localmente

```bash
git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab
docker compose up --build -d

API local: http://localhost:8005/docs

⸻

🔐 Rotas principais

Rota	Função	Auth
POST /signup	Criar usuário	❌
POST /login	Autenticar e gerar token JWT	❌
GET /me	Perfil do usuário	✔ Token
POST /notes	Criar nota	✔ Token
GET /notes	Listar notas	✔ Token
/admin	Área administrativa	✔ Admin
/audit	Auditoria	✔ Admin


⸻

🧪 Resultados em produção

✔ Signup funcionando
✔ Login retornando JWT
✔ CRUD Notes operacional
✔ Rotas autenticadas OK
✔ Admin + Auditoria protegidas
✔ Deploy EC2 validado em celular/navegador
✔ API online global sem custo (Free Tier)

⸻

📍 Status Atual (08/12/2025)

Componente	Status
Backend FastAPI	✔ Estável
PostgreSQL	✔
Docker Compose	✔
Deploy AWS	✔ Online
Elastic IP	✔
Bugs críticos	❌ Nenhum


⸻

🗺 Roadmap

Curto prazo
	•	Adicionar domínio próprio (via DNS)
	•	HTTPS com Certbot + SSL
	•	Backups automáticos

Futuro
	•	CI/CD com GitHub Actions
	•	Terraform para Infra como Código
	•	Migração para RDS
	•	Observabilidade (Grafana/Loki/CloudWatch)
	•	Frontend (React / Next.js) + painel admin

⸻

👨‍💻 Autor

Rafael Rodrigues — Chinaman
Cloud & Backend Developer
Brasil — 2025

GitHub: https://github.com/amazonroots
