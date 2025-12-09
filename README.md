<p align="center">
  <img src="da348e15a643411f3e3d6eb8be4613bff71d1e8cd1398ef2d6527de13467c096.png" width="100%" />
</p>

### ☁️ AmazonTech DevLab **Backend completo rodando em produção real na AWS EC2 · FastAPI · Docker · PostgreSQL · JWT · Nginx**

<p align="center">
  <img src="https://img.shields.io/badge/Status-Online-success?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/AWS-Cloud-orange?style=for-the-badge&logo=amazonaws"/>
  <img src="https://img.shields.io/badge/FastAPI-Backend-00ffc8?style=for-the-badge&logo=fastapi"/>
  <img src="https://img.shields.io/badge/Docker-Container-blue?style=for-the-badge&logo=docker"/>
  <img src="https://img.shields.io/badge/PostgreSQL-Database-0277bd?style=for-the-badge&logo=postgresql"/>
  <img src="https://img.shields.io/badge/JWT-Auth-critical?style=for-the-badge"/>
</p>

🔗 **Swagger público:**  
http://100.26.73.245:8005/docs  

> Não é localhost. Não é mock. **É produção real rodando 24/7 via Cloud AWS.**

---

## 🧭 O que é este projeto?

O **AmazonTech DevLab** é meu laboratório pessoal de **Cloud + Backend + DevOps**, criado com um objetivo claro:

> **Aprender Cloud na prática e provar que sou capaz de construir, configurar e publicar uma aplicação completa sozinho.**

Eu não tinha um projeto pronto para subir — então eu criei um.  
Desenvolvi o backend, implementei autenticação, contêinerizei a aplicação, preparei o banco e subi para a nuvem.

Este repositório documenta não apenas o código, mas **a jornada técnica**.

---

## 🧩 Por que ele existe

- Para **praticar arquitetura real**, não apenas teoria  
- Para **subir um serviço completo para a AWS** com infraestrutura própria  
- Para aprender **segurança, rede, deploy, logs, escalabilidade e automação**  
- Para construir a base de projetos futuros (como o *Sentinel-21*)  
- Para ter **um case sólido de Cloud/DevOps** no meu portfólio  

Feito **100% solo**, do zero, sem tutorial mastigado, com erro, tentativa, solução e deploy final.

> **Projeto raiz do meu ecossistema AmazonTech.  
O primeiro tijolo da minha carreira Cloud.**

---

## ⚙ Stack Técnica

| Camada | Tecnologias |
|---|---|
| Linguagem | Python 3.11 |
| Framework | FastAPI |
| Banco | PostgreSQL (volume persistente) |
| Containers | Docker + Docker Compose |
| Cloud | AWS EC2 (Ubuntu 24.04) |
| Rede | Security Groups + Elastic IP |
| Proxy | Nginx Reverse Proxy porta 80 |
| Autenticação | JWT Tokens |
| Observação | Acesso global em produção |

---

## 🛠 Como rodar localmente

Clone o repositório e suba a stack Docker:

🔗 (clique aqui):
https://github.com/amazonroots/amazontech-devlab

📄 Docs Local:
http://localhost:8005/docs

⸻

☁ Deploy em Cloud AWS

Estruturado como produção real — servidor, rede, infraestrutura e acesso global.

Componente	Status
AWS EC2 (Ubuntu 24.04)	🟢 Online
Elastic IP (fixo)	🟢 Configurado
Docker Compose (API + DB)	🟢 Rodando
PostgreSQL Persistente	🟢 Ativo
Nginx Reverse Proxy (80)	🟢 Funcionando
Endpoint Público	🟢 Acessível mundialmente
SSL + Domínio	🔜 Próxima etapa
CI/CD GitHub Actions	📌 Planejado


⸻

📊 Evolução do Projeto

[██████████████] Backend + CRUD Notes
[██████████████] JWT Auth
[██████████████] Docker + PostgreSQL Persistente
[██████████████] Deploy AWS EC2
[██████████████] Nginx Proxy + Porta 80
[██████░░░░░░░░] Domínio + HTTPS (em andamento)
[██░░░░░░░░░░░░] CI/CD + Observabilidade (planejado)


⸻

🔮 Próximos passos (roadmap)
	•	Domínio próprio + Certbot (HTTPS)
	•	Pipeline CI/CD com GitHub Actions
	•	Logs + Monitoramento (Grafana/Prometheus/Loki)
	•	Banco migrado para Amazon RDS
	•	Escalonamento com ECS/EKS
	•	Documentação técnica detalhada da arquitetura

⸻

🌌 Visão e Continuidade

Este é apenas o primeiro projeto do meu ciclo DevOps/Cloud.

O próximo será o Sentinel-21 — Segurança e Firewall Cognitivo para IA.
Depois virão microserviços, mensageria, filas, RDS, observabilidade, automação.

Cada repositório terá sua própria história.
Este aqui é onde tudo começou.

⸻

👤 Autor

Rafael Rodrigues – AmazonTech  
Backend • Cloud • DevOps  
Email: rafael.amazontech@gmail.com

Não fiz para testar. Fiz para colocar no ar.
Cloud não se aprende só lendo — se aprende deployando.

