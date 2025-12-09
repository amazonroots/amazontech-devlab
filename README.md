🦾 AmazonTech DevLab — Backend for the Brave

Infra real. Deploy real. Zero brincadeira.
FastAPI • Docker • AWS • PostgreSQL • JWT • Nginx

<p align="center">
  <img src="https://img.shields.io/badge/Cloud-AWS_EC2-black?style=for-the-badge&logo=amazonaws"/>
  <img src="https://img.shields.io/badge/FastAPI-Production-green?style=for-the-badge&logo=fastapi"/>
  <img src="https://img.shields.io/badge/Database-PostgreSQL-blue?style=for-the-badge&logo=postgresql"/>
  <img src="https://img.shields.io/badge/Security-JWT-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Docker-Containers-blue?style=for-the-badge&logo=docker"/>
  <img src="https://img.shields.io/badge/Status-Online_Globally-brightgreen?style=for-the-badge"/>
</p>



⸻

📌 Objetivo

Esse projeto existe por um motivo simples:
entregar produto real em produção, e não apenas código rodando em localhost.

🔗 API Online — Swagger Docs:
http://100.26.73.245:8005/docs

(domínio + SSL em breve — etapa atual é infraestrutura ativa em produção)

⸻

🧬 O DNA do Projeto

Backend em FastAPI, seguro com JWT, usando PostgreSQL persistente, containerizado, com Admin + Auditoria, rodando em AWS EC2, orquestrado com Docker e servido via Nginx Reverse Proxy.

Código é arte. Infra é guerra.
E esse projeto foi levado da ideia para a nuvem sem tutoria, sem time — só engenharia.

⸻

🧪 Stack Técnica

Camada	Tecnologia
Linguagem	Python 3.11
Framework	FastAPI
Banco	PostgreSQL (Volume Persistente)
Deploy	Docker + Docker Compose
Infra Cloud	AWS EC2 (Ubuntu 24.04)
Proxy	Nginx Reverse Proxy
Segurança	JWT Auth
Observabilidade	Logs + Auditoria


⸻

⚙ Principais Features
	•	Registro/Login com JWT
	•	Rotas autenticadas como /me
	•	CRUD completo de Notes
	•	Painel Admin com permissões elevadas
	•	Auditoria registrando ações
	•	PostgreSQL persistente
	•	Infra 100% rodando em produção

Minimalista na superfície. Robusto por dentro.

⸻

💻 Como Rodar Localmente

📥 1. Clonar o repositório

git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab

🔧 2. Requisitos
	•	Docker instalado
	•	Docker Compose habilitado

(Se quiser alterar variáveis do banco, ajuste o .env antes de subir)

🚀 3. Subir o projeto

docker-compose up -d

Isso vai iniciar:
	•	Backend (FastAPI)
	•	Banco PostgreSQL (volume persistente configurado)

🌐 4. Acessar localmente

http://localhost:8005/docs

Pronto. Está rodando igual ao ambiente em produção.

⸻

🛰 Deploy & Infra Overview

Item	Status
Deploy EC2	✔ ativo
Docker/Compose	✔ rodando
IP Elástico	✔ fixo
Nginx Reverse Proxy	✔ configurado
API Pública	✔ online
SSL + Domínio	🔜 próximo passo
CI/CD	🔜 planejado
RDS + Observabilidade	🔜 evolução futura


⸻

📜 Changelog (Commit Changes)

Data	Evento	Resultado
06/12/2025	Base FastAPI + CRUD inicial	✔
07/12/2025	Implementação de JWT Auth (/register, /login, /me)	✔
08/12/2025	Dockerização + Compose + Volume DB	✔
08/12/2025	Deploy EC2 — API acessível globalmente	✔
09/12/2025	Nginx + Security Groups + Firewall configurado	✔ estável
09/12/2025	Admin + Auditoria adicionados	✔ aplicado
10/12/2025	Revisão endpoints + otimizações	✔
Próximo	Domínio + SSL com Certbot	🔜
Futuro	CI/CD + Grafana/Loki + RDS + ECS/EKS	🎯 evolução

Commit title recomendado no GitHub:

docs: update README with Changelog, Local Setup and UX improvements


⸻

🧭 Por que esse projeto importa?

Porque junior normalmente só mostra CRUD local.
Aqui é backend real, com deploy real, com segurança real.

Te posiciona acima da média porque mostra:

✔ Infra Cloud real (AWS)
✔ Deploy containerizado
✔ Segurança e auditoria
✔ Banco persistente
✔ Estrutura escalável
✔ Projeto profissional para portfolio e vagas

⸻

📸 Previews (insira quando quiser)

Coloque prints do Swagger, containers rodando, request funcionando
Visual vende.

docs.png
container_running.png
notes_crud.gif


⸻

🗺 Roadmap
	•	SSL + domínio custom
	•	Automação de deploy com GitHub Actions
	•	Observabilidade com Loki/Grafana
	•	Migração do DB para RDS
	•	Escalonamento com ECS/EKS

Objetivo final: Enterprise Grade.

⸻

👤 Autor

Rafael Rodrigues (AmazonTech)
Backend • Cloud • DevOps
📧 rafael.amazontech@gmail.com

“From Zero to Cloud.
Build at night. Deploy at dawn.”

⸻


<p align="center">
  <sub>🦾 AmazonTech DevLab — Backend for the Brave</sub><br/>
  <sub>Se chegou até aqui, você já entendeu o recado.</sub>
</p>
