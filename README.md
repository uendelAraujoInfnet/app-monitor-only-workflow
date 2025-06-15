## 🧩 Git, Branches e Tags na Entrega Contínua

### 🔁 O papel do Git na entrega contínua

O Git é essencial em pipelines de entrega contínua porque permite versionar o código de forma segura, colaborativa e automatizada. Com ele, é possível:

- Controlar alterações no código com histórico completo de modificações.
- Reverter versões quando erros são identificados em ambientes de produção.
- Automatizar ações (via GitHub Actions) em resposta a eventos como push, pull request ou tags.
- Colaborar em equipe, separando tarefas e funcionalidades sem impactar o código principal.

Na prática, o Git se integra diretamente com sistemas CI/CD, permitindo que cada nova alteração dispare validações, testes e deploys automaticamente.

### 🌿 Importância de branches

As *branches* (ramificações) são fundamentais para organizar o fluxo de trabalho. Elas permitem que diferentes funcionalidades, correções e experimentos sejam desenvolvidos de forma isolada e segura. Exemplos:

- `main`: branch principal e estável do projeto.
- `ci/setup`: configuração inicial do pipeline e documentação.
- `feature/*`, `bugfix/*`: convenções para novas funcionalidades ou correções.

Trabalhar com branches evita conflitos de código, facilita revisões e garante estabilidade no ambiente principal.

### 🔖 Importância das tags

As *tags* identificam versões específicas do código no repositório. São úteis para:

- Marcar lançamentos estáveis (ex: `v1.0.0`, `v0.1.0`);
- Referenciar pontos confiáveis no tempo;
- Integrar com ferramentas de deploy, que podem usar as tags como gatilho.

No projeto `appmonitor-pipeline`, a tag `v0.1.0` marca a **primeira versão estável**, contendo o script inicial e a documentação base do pipeline.

---

## 🔐 Diferenças entre Variáveis, Secrets e Contextos

- `env`: variável de ambiente local do job.
- `vars`: variáveis definidas na aba Settings > Variables (não seguras).
- `secrets`: variáveis sensíveis, criptografadas e ocultadas automaticamente nos logs.

---

# 📡 AppMonitor Pipeline

Este projeto simula a monitoração de aplicações web por meio de pipelines CI/CD com **GitHub Actions**. Apesar de não conter uma aplicação real, toda a estrutura de automação, segurança, deploy e diagnóstico foi implementada para fins de aprendizado prático em DevOps.

---

## 🛠️ Tecnologias e Ferramentas

- Git e GitHub
- GitHub Actions
- Shell Script (Bash)
- Variáveis, Secrets e Contextos
- Workflows com validação, testes e deploy
- Logs, Debugs e Job Summaries
- Ambientes com aprovação manual

---

## 🚀 Etapas Implementadas

### ✅ Etapa 1 — Controle de Versão
- Branch `ci/setup` criada
- Commits separados: `status-check.sh` e `README.md`
- Tag `v0.1.0` adicionada e release publicado

### ⚙️ Etapa 2 — Pipeline de Integração Contínua (`ci.yml`)
- Validação de script
- Execução simulada de testes
- Geração e upload de artefato `report.zip`

### 🔐 Etapa 3 — Variáveis e Secrets (`run-monitor.yml`)
- Uso de contextos: `env`, `vars` e `secrets`
- Variáveis globais definidas via GitHub UI

### 📋 Etapa 4 — Logs e Diagnóstico
- Ativação de debug
- Mensagens `::warning::` e `::error::`
- Summaries e badge de status do workflow

### 🧪 Etapa 5 — Deploy com Aprovação (`deploy.yml`)
- Ambiente `production` configurado
- Simulação de deploy bloqueado até aprovação

### 🩺 Etapa 6 — Diagnóstico de Falhas (`diagnostic.yml`)
- Checagem de variáveis obrigatórias
- Mensagens claras de erro e sugestão de correções

---

## 📦 Como Executar o Script

```bash
chmod +x status-check.sh
./status-check.sh
```

---

## 📊 Badge de Status

![CI Status](https://img.shields.io/github/actions/workflow/status/uendelAraujoInfnet/app-monitor-only-workflow/ci.yml?branch=main)

---

## 📁 Estrutura de Diretórios

```
.github/
└── workflows/
    ├── ci.yml
    ├── run-monitor.yml
    ├── deploy.yml
    └── diagnostic.yml

status-check.sh
README.md
```

---

## 📸 Evidências (exemplo)

As evidências visuais (prints de tela) estão disponíveis na pasta `/evidencias`, contendo:

- Execução dos workflows
- Configuração de variáveis e secrets
- Summaries de jobs e artefatos
- Release com tag `v0.1.0`

---