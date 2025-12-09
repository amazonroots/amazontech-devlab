🦾 AmazonTech DevLab — Backend for the Brave

Infra real. Deploy real. Zero brincadeira.
FastAPI + Docker + AWS + PostgreSQL + JWT + Nginx.

<p align="center">
  <img src="https://img.shields.io/badge/Cloud-AWS_EC2-black?style=for-the-badge&logo=amazonaws"/>
  <img src="https://img.shields.io/badge/APIs-FastAPI-black?style=for-the-badge&logo=fastapi"/>
  <img src="https://img.shields.io/badge/Security-JWT/Auth-black?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/DevOps-Docker_&_Nginx-black?style=for-the-badge&logo=docker"/>
  <img src="https://img.shields.io/badge/Status-Online%20Global-green?style=for-the-badge"/>
</p>



⸻

📌 O Propósito

Esse sistema existe pra provar uma coisa:
Eu entrego produto. Em produção. Sem enrolação.
Não é localhost, não é mockup — é microsserviço real rodando no mundo.

🔗 Swagger/API Online:
http://100.26.73.245:8005/docs
(até o domínio e SSL chegarem — primeira fase concluída)

⸻

🧬 DNA do Projeto

Microsserviço escalável em FastAPI, protegido por JWT, com PostgreSQL persistente e módulo de admin + auditoria.
Tudo containerizado e colocado na AWS via EC2, sem muleta.

Do zero para a nuvem.
Sem time. Sem tutorial guiado. Só engenharia.

📦 Stack (direto ao ponto)
	•	Python + FastAPI
	•	PostgreSQL
	•	Docker & Docker Compose
	•	AWS EC2 (Ubuntu 24.04)
	•	Nginx Reverse Proxy
	•	JWT Authentication
	•	Auditoria + Admin Panel

⸻

☁️ Arquitetura Cloud/DevOps

Elemento	Stack	Por que isso importa
Infra	AWS EC2 (Ubuntu 24.04)	Produção real, IaaS de verdade.
Deploy	Docker + Docker Compose	Reprodutível e portátil.
Networking	Elastic IP + Security Groups	IP fixo, firewall configurado.
Proxy & Web Layer	Nginx Reverse Proxy	Rota estável, pronto pra SSL.
DB	PostgreSQL containerizado	Persistência real dos dados.
Auth	JWT	Sessão stateless, padrão enterprise.
Governança	Admin + Auditoria	Rastro de ações — compliance-friendly.


⸻

🔥 Features
	•	Registro/Login com JWT
	•	Rotas autenticadas (/me)
	•	CRUD completo de Notes
	•	Painel Admin
	•	Auditoria de ações críticas
	•	Banco PostgreSQL persistente

Simples por fora. Robusto por dentro.

⸻

📸 Preview (prints)

(adicione prints depois — visual vende)

/docs (Swagger)
Auth em ação
CRUD funcionando


⸻

🛰 Deploy Timeline (sem romance — só fatos)

Data	Evento	Resultado
08/12/2025	Provisionamento EC2 + Docker/Compose	API e DB rodando em produção
09/12/2025	Elastic IP + Nginx + Security Group	Rede estável, porta 80 ok

Status: online, ativo, acessível globalmente.

⸻

🧭 Por que isso importa para o mercado?

Porque um dev iniciante normalmente só tem CRUD local.
Aqui tem:

✔ Deploy real na AWS
✔ Segurança com JWT
✔ Infra Dockerizada
✔ Banco durável
✔ Arquitetura modular pronta pra escalar

Isso coloca o AmazonTech DevLab na prateleira de portfólio sério, não projeto escolar.

⸻

🔥 Como rodar localmente

Rapidão:

# Clone o projeto
git clone https://github.com/seuuser/AmazonTechDevLab.git
cd AmazonTechDevLab

# Subir containers
docker-compose up -d

# Acessar
http://localhost:8005/docs

Sem configuração manual. Plug & play.

⸻

🗺 Roadmap (próximas mutações do monstro)
	•	Domínio + HTTPS (Certbot)
	•	Pipeline CI/CD (GitHub Actions)
	•	Banco migrando para RDS
	•	Observabilidade: Grafana/Loki
	•	Futuro: ECS/EKS para escalar

A visão?
Enterprise. Sem pedir licença.

⸻

👤 Autor

Rafael Rodrigues — AmazonTech
Backend | Cloud | DevOps
📧 rafael.amazontech@gmail.com

“Código é poesia. Infra é guerra.
E o DevLab é meu campo de batalha.”

⸻


<p align="center">
  <sub>⚡ From zero to cloud. Built at night. Deployed ao amanhecer.</sub>
</p>
