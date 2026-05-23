# 🏢 Multi-Tenant SaaS Backend

Backend multi-tenant com isolamento por tenant, planos e limites por cliente.

## 🛠 Tecnologias
- Kotlin + Spring Boot 3.2
- PostgreSQL
- Servlet Filter para resolução de tenant

## 📋 Funcionalidades
- Isolamento de dados por tenant via `ThreadLocal`
- Resolução de tenant por header `X-Tenant-ID`
- Planos com limites diferentes (FREE / STARTER / PRO / ENTERPRISE)
- Validação de limites antes de adicionar usuários
- Upgrade de plano via API

## 🚀 Como rodar

```bash
docker-compose up -d
./gradlew bootRun
```

## 📡 Endpoints

| Método | Rota | Descrição |
|--------|------|-----------|
| POST | `/api/admin/tenants` | Cria um novo tenant |
| GET | `/api/admin/tenants` | Lista todos os tenants |
| GET | `/api/admin/tenants/{id}/limits` | Limites do plano atual |
| PATCH | `/api/admin/tenants/{id}/plan` | Faz upgrade de plano |

### Usando o sistema
Toda requisição precisa do header `X-Tenant-ID: meu-slug`

## 📊 Limites por Plano

| Plano | Usuários | Features |
|-------|----------|---------|
| FREE | 3 | Reports básicos |
| STARTER | 10 | Analytics avançado |
| PRO | 50 | API access |
| ENTERPRISE | Ilimitado | Tudo + SLA |

---
> Projeto desenvolvido por **Jhonata Breno** — Estudante de ADS | Backend Developer
