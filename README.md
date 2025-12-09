⚔️ AmazonTech DevLab — Backend em Produção

FastAPI • Docker • PostgreSQL • JWT Auth • AWS EC2 Free Tier

Backend real rodando globalmente — autenticação, banco persistente, admin, auditoria e deploy sólido na AWS.

<p align="center">
🚀 <b>Online e acessível publicamente</b>  
📡 <a href="http://3.235.187.206:8005/docs" target="_blank">http://3.235.187.206:8005/docs</a>  
</p>



⸻

🔥 O que é isso?

Um backend pronto para uso, construído para ser laboratório Cloud/DevOps real, sem papo furado.
Código versionado, dockerizado e publicado na AWS EC2 — rodando na internet sem pagar 1 centavo.

💥 Não é demo.
💥 Não é projeto de faculdade.
É backend em produção, real e público.

⸻

🧠 Stack Principal

🔧 Tecnologia	Uso
FastAPI	Core da API
PostgreSQL	Banco de dados
Docker + Docker Compose	Containers e orquestração
JWT Authentication	Login + Tokens
AWS EC2 Free Tier	Deploy global
Nginx Reverse Proxy	Camada Web (porta 80)
Swagger UI	Documentação pública


⸻

🏗 Arquitetura

          ┌───────────────┐
          │    Cliente     │
          └───────┬───────┘
                  │ HTTP
          ┌───────▼────────────────────────┐
          │            NGINX                │
          │ (porta 80 → 8005 → backend)     │
          └───────┬────────────────────────┘
                  │ Docker Network
       ┌──────────▼───────────┐   ┌──────────────┐
       │     FASTAPI API      │   │  POSTGRESQL   │
       │ (Auth, Notes, Admin) │   │  DB Persist   │
       └──────────────────────┘   └──────────────┘


⸻

📡 Deploy AWS EC2

📍 Instância: Ubuntu 24.04 — t2.micro (Free Tier)
📍 Porta pública: 80 → 8005 (API)
📍 Containers sob demanda — sem custo extra

✔ Acessível via celular
✔ Logs controlados
✔ Banco persistente
✔ Produção ativa

⸻

🧪 Testado em Produção

Endpoint	Resultado
/signup	✔ Cria usuário
/login	✔ Gera JWT
/me	✔ Autenticado
/notes	✔ CRUD Total
/admin & /audit	🔐 Apenas admin


⸻

💾 Rodar local

git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab
docker compose up --build

📍 Acesso local → http://localhost:8005/docs

⸻

🛣 Roadmap (continuará crescendo 💪)
	•	🔜 HTTPS + Certbot
	•	🔜 Backup automático do DB
	•	🔜 CI/CD com GitHub Actions
	•	🔜 Migração para RDS
	•	🔜 Dashboard Web Admin (React)
	•	🔜 Monitoramento (Grafana/Loki)
	•	🚀 Futuro: Kubernetes/EKS

⸻

📌 Commit Change obrigatório ao editar README

git add README.md
git commit -m "docs: update README visual modern + arquitetura + roadmap"
git push origin main


⸻

👤 Autor

Rafael Rodrigues (Chinaman)
📧 rafael.amazontech@gmail.com
Cloud • DevOps • Backend • FastAPI • AWS
