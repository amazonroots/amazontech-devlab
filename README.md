<p align="center">
  <img src="da348e15a643411f3e3d6eb8be4613bff71d1e8cd1398ef2d6527de13467c096.png" width="100%"/>
</p>

<h1 align="center">☁️ AmazonTech DevLab</h1>
<h3 align="center">Backend completo rodando em produção real na AWS · FastAPI · Docker · PostgreSQL · JWT · Nginx</h3>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Online-success?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/AWS-Cloud-orange?style=for-the-badge&logo=amazonaws"/>
  <img src="https://img.shields.io/badge/FastAPI-Backend-00ffc8?style=for-the-badge&logo=fastapi"/>
  <img src="https://img.shields.io/badge/Docker-Containers-blue?style=for-the-badge&logo=docker"/>
  <img src="https://img.shields.io/badge/PostgreSQL-Database-0277bd?style=for-the-badge&logo=postgresql"/>
  <img src="https://img.shields.io/badge/JWT-Auth-critical?style=for-the-badge"/>
</p>

---

🔗 **Swagger público (API em produção):**  
📍 http://100.26.73.245:8005/docs  

> **Sem localhost. Sem simulação. É produção real 24/7 rodando na AWS.**

---

## 🧭 O que é o AmazonTech DevLab?

Um laboratório de **Cloud + Backend + DevOps** projetado com um objetivo direto:

> **Aprender infraestrutura e produção de verdade, construindo algo que vai para o ar — e não só para o notebook.**

Aqui eu construí tudo do zero:  
Backend → Contêinerização → Banco persistente → Rede → Deploy → Proxy → Acesso global.

É meu **case inicial de produção**, fundação do meu ecossistema AmazonTech.

---

## 🎯 Por que esse projeto existe?

✔ Criar experiência real em Cloud — não só teoria  
✔ Subir aplicação completa com infraestrutura própria  
✔ Aprender segurança, logs, proxy, rede e automação  
✔ Construir base para o projeto maior **Sentinel-21**  
✔ Ter um projeto forte no portfólio para o mercado

> **Sem copiar — construído com cabeça, erro, correção e sangue no teclado.**

---

## ⚙ Stack Técnica

| Camada | Ferramentas |
|---|---|
| Linguagem | Python 3.11 |
| Framework | FastAPI |
| Banco | PostgreSQL com volume persistente |
| Containers | Docker + Docker Compose |
| Cloud | AWS EC2 (Ubuntu 24.04) |
| Rede | Security Groups + Elastic IP |
| Proxy | Nginx Reverse (porta 80) |
| Auth | JWT Tokens |
| Deploy | Produção global |

---

## 🛠 Rodando localmente

### 📦 Requisitos
- Docker
- Docker Compose
- Python 3.10+ (opcional — se quiser rodar sem Docker)

### 🚀 Executar com Docker

```bash
git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab
docker-compose up --build


⸻


<details>
<summary><strong>☁️ Deploy em Cloud AWS (clique para expandir)</strong></summary>


Configuração em produção real — com infraestrutura, persistência e acesso externo.

Componente	Status
AWS EC2 (Ubuntu 24.04)	🟢 Online
Elastic IP	🟢 Configurado
Docker Compose	🟢 Rodando
PostgreSQL Persistente	🟢 Ativo
Nginx Reverse Proxy	🟢 Funcionando
Endpoint público	🟢 Acessível globalmente
SSL + Domínio	🔜 Em andamento
CI/CD GitHub Actions	📌 Planejado

</details>



⸻

📊 Evolução do projeto

[██████████████] Backend + CRUD Notes
[██████████████] JWT Auth
[██████████████] Docker + Volume PG
[██████████████] Deploy AWS EC2
[██████████████] Nginx Proxy porta 80
[██████░░░░░░░░] Domínio + HTTPS
[██░░░░░░░░░░░░] CI/CD + Observabilidade


⸻

🗺 Roadmap
	•	Domínio próprio + HTTPS (Certbot)
	•	CI/CD com GitHub Actions
	•	Logs e monitoramento (Grafana/Prometheus/Loki)
	•	Banco migrado para Amazon RDS
	•	Escalonamento com ECS/EKS
	•	Documentação arquitetural completa

⸻

🌌 Visão de futuro

Este é o primeiro passo do meu ciclo DevOps/Cloud.
O próximo será Sentinel-21 — Firewall Cognitivo para IA.
Depois: microserviços, filas, monitoramento, automação e alta disponibilidade.

Cada repositório será uma peça desse universo.
E este aqui é a origem da jornada.

⸻

👤 Autor

Rafael Rodrigues — AmazonTech
Backend • Cloud • DevOps
📩 rafael.amazontech@gmail.com

Não fiz para testar. Fiz para colocar no ar.
Cloud não se aprende lendo — se aprende deployando.
