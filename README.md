# StockFlow

Sistema de controle de estoque e vendas, construído do zero como projeto de estudo em **Cloud/DevOps**.

> **Status:** em desenvolvimento. Este README evolui junto com o projeto.

## Por que este projeto existe

Eu possuo projetos em que controlo estoque e vendas de forma manual. O StockFlow nasce desse problema real: registrar produtos, acompanhar o estoque e calcular o lucro de cada venda.

O objetivo de aprendizado é maior que o sistema em si. A cada fase, uma nova camada de infraestrutura e automação é adicionada ao mesmo projeto, até ele rodar na nuvem com deploy automático.

## O que o StockFlow vai fazer

- Cadastrar, consultar, atualizar e remover produtos (nome, quantidade, preço, categoria)
- Registrar vendas e calcular o lucro automaticamente
- Manter o histórico de movimentações de estoque
- Autenticar usuários com dois perfis: **admin** (gerencia tudo) e **vendedor** (só registra vendas)
- Expor tudo por uma **API REST**

## Arquitetura planejada

```
Internet
   │
   ▼
Nginx (proxy reverso)
   │
   ▼
StockFlow API (FastAPI, container Docker)
   │
   ▼
PostgreSQL
```

Na versão final, o ambiente roda na AWS (EC2, S3, CloudWatch), é criado por código com Terraform e é publicado por um pipeline do GitHub Actions a cada `git push`.

## Tecnologias

| Área | Ferramenta |
|---|---|
| API | Python, FastAPI |
| Banco de dados | SQLite (início), PostgreSQL (depois) |
| Containers | Docker, Docker Compose, Nginx |
| Nuvem | AWS (EC2, S3, IAM, CloudWatch) |
| CI/CD | GitHub Actions |
| Infraestrutura como código | Terraform |

## Roadmap

- [X] Servidor Linux seguro (SSH por chave, firewall, serviço systemd, backup em Bash)
- [ ] API mínima do StockFlow com testes (pytest)
- [ ] Deploy na AWS (EC2 + Security Groups + S3 + alarme no CloudWatch)
- [ ] Containerização com Docker Compose (API + PostgreSQL + Nginx)
- [ ] Pipeline CI/CD com GitHub Actions
- [ ] Infraestrutura como código com Terraform
- [ ] Autenticação (JWT) e perfis de usuário

## Estrutura do repositório

```
stockflow/
├── app/        # código da API
├── tests/      # testes automatizados
├── docs/       # diagramas e anotações
├── infra/      # Terraform e scripts (mais adiante)
└── README.md
```

## Como rodar

Em breve. Esta seção será preenchida quando a primeira versão da API estiver pronta.

## Sobre mim

Estudante de Ciência da Computação, focado em Cloud e DevOps. Acompanhe a evolução do projeto pelo histórico de commits.
