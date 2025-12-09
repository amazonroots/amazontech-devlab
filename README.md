
# ☁ AmazonTech DevLab  
**Backend em produção com deploy real em Cloud AWS EC2 • FastAPI • Docker • PostgreSQL • JWT • Nginx**

<p align="center">
  <img src="https://img.shields.io/badge/Status-Online-success?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Cloud-AWS-orange?style=for-the-badge&logo=amazonaws"/>
  <img src="https://img.shields.io/badge/Backend-FastAPI-0affc2?style=for-the-badge&logo=fastapi"/>
  <img src="https://img.shields.io/badge/Infra-Docker-blue?style=for-the-badge&logo=docker"/>
  <img src="https://img.shields.io/badge/DB-PostgreSQL-0277bd?style=for-the-badge&logo=postgresql"/>
  <img src="https://img.shields.io/badge/Auth-JWT-critical?style=for-the-badge"/>
</p>

🔗 **API em Produção (Swagger):**  
http://100.26.73.245:8005/docs

> Projeto desenvolvido com foco em Cloud Deployment e Infra real — **não é local, não é demo.**

---

## 📌 Objetivo
Criar um backend completo e subir para **produção na AWS**, simulando ambiente real de empresa com:

- Provisionamento de servidor EC2
- Configuração de segurança e rede (Security Groups)
- Elastic IP (IP fixo)
- Deploy com Docker Compose
- Proxy reverso com Nginx porta 80
- Banco persistente PostgreSQL

Este repositório existe para demonstrar **Cloud Skills + Deploy real**, não apenas código.

---

## ⚙ Tecnologias

| Camada | Ferramentas |
|---|---|
| Linguagem | Python 3.11 |
| Framework | FastAPI |
| Banco | PostgreSQL (volume persistente) |
| Contêiner | Docker + Docker Compose |
| Cloud | AWS EC2 (Ubuntu 24.04, Elastic IP) |
| Rede | Security Groups, Porta 80/8005 liberadas |
| Proxy | Nginx Reverse Proxy |
| Auth | JWT Tokens |

---

## 💻 Como rodar localmente

```bash
git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab
docker-compose up -d

Docs local:
http://localhost:8005/docs

Requisitos: Docker + Docker Compose

⸻

☁ Deploy na AWS

Componente	Status
AWS EC2 Ubuntu 24.04	🟢 Online
Elastic IP (fixo)	🟢 Configurado
Docker Compose	🟢 API + DB rodando
PostgreSQL Persistente	🟢
Nginx porta 80	🟢 Reverse proxy ativo
Endpoint Público	🟢 Acessível no mundo
SSL/Domain	🔜 Prox. etapa
CI/CD	🔜 Planejado


⸻

📊 Progresso do Projeto (clean + profissional)

[██████████████] 100% Backend + CRUD Notes
[██████████████] 100% JWT Auth + Rotas privadas
[██████████████] 100% Docker + PostgreSQL persistente
[██████████████] 100% Deploy AWS EC2 + API Live
[██████████████] 100% Nginx Reverse Proxy + Porta 80
[██████░░░░░░░░] 60% SSL + Domínio custom
[██░░░░░░░░░░░░] 20% CI/CD • Observabilidade • RDS


⸻

🧭 Roadmap
	•	🔐 Domínio + HTTPS (Certbot)
	•	🚀 CI/CD GitHub Actions
	•	📊 Logging + Monitoramento
	•	🐘 DB → RDS
	•	📦 Escalonamento → ECS/EKS

⸻

👤 Autor — Responsável pela Infra & Deploy

Rafael Rodrigues  
Backend • Cloud • DevOps  
Email: rafael.amazontech@gmail.com

Comecei pelo backend — mas o objetivo sempre foi Cloud.
E Cloud só prova quando está no ar.
