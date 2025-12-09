📌 AMAZONTECH DEVLAB

Backend Real · FastAPI · Docker · PostgreSQL · JWT Auth · AWS EC2 Deploy

Backend sólido, com autenticação, auditoria, admin e deploy real em produção global.
Não é demo. É aplicação funcional rodando na nuvem.

⸻

🚀 Stack Principal

Área	Tecnologia
Linguagem	Python 3.12
Framework	FastAPI
Banco	PostgreSQL
Infra	Docker & Docker Compose
Cloud	AWS EC2 (Ubuntu 24.04 - Free Tier)
Auth	JWT Access Token
Auditoria	Logs internos de ações
Deploy	Produção acessível globalmente


⸻

🌍 Deploy Atual

📡 API Online → http://3.235.187.206:8005/docs

Status de Produção

Serviço	Porta	Estado
API FastAPI	8005 → 8000 interno via Docker	✔ Online
PostgreSQL	5432	✔ Rodando
Autenticação JWT	✔	
CRUD Notes	✔	
Admin & Auditoria	✔	


⸻

📒 Diário Técnico – Último Marco (08/12/2025)
	1.	Instância criada na AWS EC2
	2.	Instalação Docker + Compose
	3.	Projeto clonado e containerizado
	4.	Deploy rodando 100% funcional
	5.	Testes completos via insomnia/browser
	6.	API acessível globalmente (via IPv4 público)
	7.	UFW liberado + Security Group configurado
	8.	Proxy reverso via Nginx configurado para porta 80 (pronto para HTTPS futuro)
	9.	Elastic IP configurado para endpoint fixo

⸻

🔐 Endpoints Principais

Método	Rota	Descrição
POST	/signup	Criação de usuário
POST	/login	Gera JWT
GET	/me	User autenticado
POST	/notes	Cria nota
GET	/notes	Lista notas
ADMIN	/admin	Área restrita
AUDIT	/audit	Logs internos


⸻

🧩 Arquitetura (Resumo Técnico)

FastAPI  →  Controllers
         →  Services
         →  Models (SQLAlchemy)
         →  Auth + JWT
         →  Auditoria
         →  PostgreSQL
         →  Docker Compose
         ↓
       AWS EC2 (produção)


⸻

🛠 Como rodar localmente

git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab
docker compose up --build

Swagger → http://localhost:8000/docs

⸻

☁ Como rodar em produção (EC2 já configurado)

ssh -i ~/.ssh/amazontech-key.pem devlab@3.235.187.206
cd amazontech-devlab
sudo docker compose up --build -d
sudo docker ps


⸻

🔥 Roadmap Realista

Etapa	Status	Próximo passo
Deploy EC2	✔	
Elastic IP	✔	
Nginx porta 80	✔	
HTTPS Certbot	⏳	implementar
Domínio próprio	⏳	futuramente
CI/CD GitHub Actions	⏳	auto-deploy
RDS + Backup	⏳	expansão
Observabilidade Grafana	⏳	produção robusta
Painel Web Admin	⏳	optional


⸻

📁 Estrutura do projeto

amazontech-devlab/
│── app/
│   ├── auth/
│   ├── notes/
│   ├── admin/
│   ├── audit/
│   └── db.py
│── docker-compose.yml
│── Dockerfile
│── README.md ← este arquivo


⸻

🔥 Commit Change obrigatório

Depois de colar o README:

git add README.md
git commit -m "docs: README final revisado e estruturado profissionalmente"
git push origin main


⸻

👤 Autor

Rafael Rodrigues (Chinaman)
Cloud · DevOps · Backend Engineering

📎 GitHub: https://github.com/amazonroots
📩 Contato: rafael.devcloud@proton.me (se quiser coloco outro)
