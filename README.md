<p align="center">
  <img src="https://img.shields.io/badge/AmazonTech_DevLab-Backend_Cloud-orange?style=for-the-badge&logo=aws"/>
  <img src="https://img.shields.io/badge/FastAPI-Running%20In%20Production-009688?style=for-the-badge&logo=fastapi"/>
  <img src="https://img.shields.io/badge/Docker-Containerized-blue?style=for-the-badge&logo=docker"/>
  <img src="https://img.shields.io/badge/PostgreSQL-Database-336791?style=for-the-badge&logo=postgresql"/>
  <img src="https://img.shields.io/badge/Status-Online_Globally-green?style=for-the-badge"/>
</p>

---

<h1 align="center">⚡ AmazonTech DevLab — API Cloud Production</h1>
<p align="center">Backend real, em contêiner, rodando na AWS EC2 — autenticação JWT, notas, auditoria e admin.</p>

---

### 🚀 Deploy Online
📍 **Swagger Docs:**  
🔗 http://3.235.187.206:8005/docs  

_Acessível pelo celular, notebook ou qualquer dispositivo._  
Rodando **sem localhost**, **sem VPN**, **mundo inteiro acessa**.

---

## 🏗 Stack & Infra

| Camada | Tecnologia |
|---|---|
| Linguagem | Python |
| Framework | FastAPI |
| Banco | PostgreSQL (via Docker) |
| Auth | JWT completo + admin |
| Deploy | AWS EC2 (Ubuntu) |
| Infra | Docker + Docker Compose |
| Segurança | SG Rules + SSH Key |
| Monitoramento inicial | Logs Docker + HealthCheck |

---

## 📜 Features Principais

✔ Login & Registro com JWT  
✔ Rotas protegidas /auth  
✔ CRUD de **Notes** com token  
✔ Sistema **Admin** real  
✔ **Auditoria de ações** integrada  
✔ Banco PostgreSQL persistente  
✔ Deploy EC2 **sem tutoriais — real world**  
✔ API acessível globalmente  

---

## 🔥 Diário Técnico do Deploy

📅 **08/12/2025 — backend entrou na nuvem**

1. Criação da EC2  
- Ubuntu 24.04 | t3.micro Free Tier  
- SSH configurado com `amazontech-key.pem`

2. Setup do ambiente  
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install docker.io docker-compose -y

	3.	Deploy com Docker

git clone <repo>
cd amazontech-devlab
sudo docker compose up --build -d

	4.	Serviços online

API: 8005 → 8000 internal
Postgres: 5432

	5.	Testes realizados
✔ /signup
✔ /login → token JWT ok
✔ /notes CRUD
✔ /admin e /audit com permissão
✔ Health check via curl externo

⸻

📌 Status Atual

Módulo	Situação
Backend API	Online
JWT Auth	OK
Notes CRUD	OK
Auditoria	OK
Admin	OK
Deploy AWS	Ativo e Público
Bugs	Nenhum crítico


⸻

🧭 Roadmap Evolução

🔹 Conectar domínio próprio
🔹 HTTPS + Certbot/Nginx
🔹 Backup & automations
🔹 CI/CD com GitHub Actions
🔹 Observability (Grafana/Loki)
🔹 Migração futura para RDS
🔹 Dashboard Web (React)

⸻

🖥 Visão Arquitetural

Mac → SSH → EC2 → Docker → FastAPI → PostgreSQL
               │
               └── Exposed → Internet (porta 8005)

Não é demo. É produto real em produção.
Infra própria, autenticação real, banco real, API pública.

⸻

📄 Autor

Rafael Rodrigues
📧 rafael.amazontech@gmail.com

🔹 Cloud & Backend Dev em construção
🔹 Criador do AmazonTech DevLab
🔹 Evoluindo para CI/CD + Infra escalável
