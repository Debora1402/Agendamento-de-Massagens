# 📋 Contexto do Projeto — Log Wellbeing

> **Documento de continuidade** — use este arquivo para retomar o projeto em uma nova conversa com o Claude sem perder nenhum contexto.

---

## 🏢 Sobre o Projeto

**Nome:** Log Wellbeing  
**Empresa:** Logcomex  
**Tipo:** Sistema interno de agendamento de massagens para colaboradores  
**Status:** ✅ Em produção no GitHub Pages  
**URL pública:** `https://debora1402.github.io/Agendamento-de-Massagens/`  
**Repositório:** `https://github.com/Debora1402/Agendamento-de-Massagens`  

---

## 🔗 Links de Acesso Rápido

| O quê | Link |
|---|---|
| 🌐 Portal de agendamento (usuários) | https://debora1402.github.io/Agendamento-de-Massagens/ |
| 🔧 Painel admin | https://debora1402.github.io/Agendamento-de-Massagens/admin.html |
| 🎨 Referência de design | https://debora1402.github.io/Agendamento-de-Massagens/logwellbeing-design.html |
| 📦 Repositório GitHub | https://github.com/Debora1402/Agendamento-de-Massagens |
| ⚙️ Settings do repositório | https://github.com/Debora1402/Agendamento-de-Massagens/settings |
| 📄 GitHub Pages (configuração) | https://github.com/Debora1402/Agendamento-de-Massagens/settings/pages |
| 🔑 Gerenciar tokens GitHub | https://github.com/settings/tokens |
| 📁 Ver arquivos do repositório | https://github.com/Debora1402/Agendamento-de-Massagens/tree/main |

---

## 🔑 Credenciais e Tokens

### Acessos do Sistema

| Sistema | Usuário | Senha |
|---|---|---|
| Painel Admin (`admin.html`) | `admin` | `admin123` |
| Botão "Acesso Admin" (sidebar do portal) | — | `admin123` |
| GitHub (conta) | `Debora1402` | *(sua senha do GitHub)* |

### Token GitHub (Personal Access Token)

> ⚠️ **ATENÇÃO:** Nunca salve o token diretamente neste arquivo — o GitHub detecta e bloqueia automaticamente. Guarde o token em local seguro (ex: bloco de notas offline, gerenciador de senhas).

**Token atual:** *(guarde no seu gerenciador de senhas ou bloco de notas — não coloque aqui)*  
**Formato:** começa com `ghp_` seguido de 36 caracteres

#### Como gerar um novo token:
1. Acesse https://github.com/settings/tokens
2. Clique em **"Generate new token (classic)"**
3. Nome: `log-wellbeing-claude`
4. Expiration: **No expiration** (ou 1 ano)
5. Marque o escopo: ✅ `repo` (acesso total ao repositório)
6. Clique **"Generate token"** e copie imediatamente
7. Guarde em local seguro e informe ao Claude no início de cada nova conversa

#### Como o Claude usa o token (para referência):
```bash
git clone https://SEU_TOKEN@github.com/Debora1402/Agendamento-de-Massagens.git
git push origin main
```

---

## 📁 Arquivos do Projeto

| Arquivo | Descrição | URL de acesso |
|---|---|---|
| `agendamento.html` | Portal principal (colaboradores) | `/agendamento.html` |
| `admin.html` | Painel administrativo | `/admin.html` |
| `logwellbeing-design.html` | Referência de design | `/logwellbeing-design.html` |
| `index.html` | Redirect automático para agendamento.html | `/` |
| `README.md` | Documentação do repositório | — |

---

## 🔑 Credenciais e Acessos

| Sistema | Usuário | Senha |
|---|---|---|
| Painel Admin (`admin.html`) | `admin` | `admin123` |
| Botão "Acesso Admin" (sidebar do portal) | — | `admin123` |
| GitHub (repositório) | Debora1402 | *(sua senha do GitHub)* |

---

## 💾 Estrutura de Dados (localStorage)

Todos os dados são salvos no **localStorage do navegador**. As chaves são:

```
lw_v7_bookings   → agendamentos
lw_v7_clients    → loggers (colaboradores) cadastrados  
lw_v7_blocked    → horários bloqueados pelo admin
```

### Estrutura de um Booking
```json
{
  "id": 1234567890,
  "service": "cadeira",
  "date": "2025-05-12",
  "time": "09:00",
  "agenda": 1,
  "clientEmail": "nome.sobrenome@logcomex.com",
  "clientName": "Nome Completo",
  "createdAt": "2025-05-12T...",
  "cancelled": false,
  "adminCreated": false
}
```

### Estrutura de um Client
```json
{
  "email": "nome.sobrenome@logcomex.com",
  "name": "Nome Completo",
  "createdAt": "2025-05-12T..."
}
```

### Estrutura de um Blocked
```json
{
  "date": "2025-05-12",
  "svc": "cadeira",
  "time": "09:00",
  "createdAt": "2025-05-12T..."
}
```

---

## 🎨 Design System

| Token | Valor | Uso |
|---|---|---|
| `--purple` | `#5B21B6` | Roxo principal |
| `--purple-mid` | `#7C3AED` | Roxo destaque / botões |
| `--purple-btn` | `#6D28D9` | Botão primário |
| `--purple-light` | `#8B5CF6` | Roxo claro |
| `--purple-100` | `#EDE9FE` | Fundo roxo suave |
| `--purple-50` | `#F5F3FF` | Fundo roxo muito suave |
| `--dark` | `#1E1B4B` | Sidebar / texto |
| `--bg` | `#F4F5F9` | Fundo geral |
| `--white` | `#FFFFFF` | Cards |
| `--sidebar-bg` | `#1E1B4B` | Sidebar |
| **Fonte** | `Poppins` | Weights: 300, 400, 500, 600, 700 |

### Layout Principal (página home)
```
┌─────────────────────────────────────────┐
│  SIDEBAR (220px)  │  MAIN AREA          │
│  ─────────────    │  ┌───────────────┐  │
│  Logo             │  │ Topbar        │  │
│  Menu:            │  ├───────────────┤  │
│  - Início         │  │ Welcome Banner│  │
│  - Agendamentos   │  │ (lilás + SVG) │  │
│                   │  ├───────────────┤  │
│  [Acesso Admin]   │  │ Cards Grid    │  │
│  [Avatar / Sair]  │  │ [Cad] [Pés]  │  │
└─────────────────────────────────────────┘
```

---

## ⚙️ Regras de Negócio

| Regra | Detalhe |
|---|---|
| Horários disponíveis | 09h00 às 17h40, slots de 20 min = 27 horários/dia |
| Capacidade por slot | Máximo **2 pessoas** por horário |
| Limite por pessoa | **1 agendamento por dia** por colaborador |
| Tentativa de 2º agendamento | Mostra modal com opção de **remarcar** |
| E-mail | Sufixo `@logcomex.com` é pré-preenchido automaticamente |
| Login | Nome completo + prefixo do e-mail obrigatórios |
| Cancelamento | Libera o slot automaticamente |

---

## 🗺️ Fluxo do Usuário (agendamento.html)

```
LOGIN
  → Preenche nome + e-mail (@logcomex.com automático)
  → Upsert no lw_v7_clients

HOME
  → Ver banner de boas-vindas com ilustração SVG
  → Escolher serviço (Cadeira ou Pés)
  
  [Se já tem agendamento hoje]
  → Modal "Você já tem agendamento" com opção Remarcar ou Manter

DATETIME
  → Ver slots disponíveis/lotados/encerrados do dia
  → Selecionar horário

FORM
  → Dados preenchidos automaticamente da sessão (readonly)
  → Confirmar

CONFIRM
  → Animação de check
  → Modal automático com prévia do e-mail
  → Link para Google Agenda
  → Opções: novo agendamento / ver do dia / cancelar
```

---

## 🔧 Funcionalidades do Admin (admin.html)

### Dashboard
- 4 stat cards: agendamentos hoje, total, loggers, slots disponíveis
- Campo de busca por e-mail: logger vê **apenas os próprios** agendamentos do dia
- Tabela completa de todos os agendamentos do dia (visão admin)

### Agendamentos
- Lista com filtros: data de/até, serviço, status (ativo/cancelado)
- Botão cancelar inline por agendamento

### Disponibilidade
- Grid visual de todos os 27 slots do dia
- Cores: 🟢 livre | 🟡 parcial | 🔴 lotado/bloqueado
- Cada slot ocupado mostra o **nome do logger** + botão **✕ cancelar**
- Botão "Agendar" — admin agenda diretamente para alguém (com auto-fill se já cadastrado)
- Botão "Bloquear/Liberar" por slot individual
- Modal "Bloquear intervalo" — bloquear faixa de horários de uma vez

### Loggers
- Grid de cards com busca em tempo real
- Ver histórico de agendamentos por logger
- Editar nome e e-mail (sincroniza todos os bookings relacionados)

### Relatórios
- Períodos: semana ou mês
- Stat cards: total, taxa de ocupação, horário de pico
- Gráfico de barras: demanda por horário
- Gráfico donut: distribuição por serviço
- Tabela de todos os horários por demanda

---

## 👥 Divisão de Responsabilidades

### 🧑‍💻 Claude (IA) é responsável por:
- Escrever e manter todo o código HTML/CSS/JavaScript
- Criar e atualizar os arquivos no repositório GitHub via API
- Implementar novas funcionalidades solicitadas
- Corrigir bugs
- Manter consistência visual e de dados entre os arquivos
- Fazer push para o GitHub quando solicitado

### 👩‍💼 Débora (você) é responsável por:
- Definir requisitos e funcionalidades desejadas
- Aprovar ou solicitar ajustes no design
- Gerenciar o repositório GitHub (visibilidade, Pages, etc.)
- Configurar o GitHub Pages quando necessário
- Compartilhar o link com os colaboradores da Logcomex
- Usar o painel admin no dia a dia
- Guardar e renovar o token do GitHub quando necessário

---

## 📝 Histórico de Decisões Importantes

| Data | Decisão |
|---|---|
| Início | Sistema em HTML puro (sem framework), localStorage para dados |
| Iteração | Design evoluiu de dark/tech → luxury spa → Poppins clean com sidebar |
| Login | Campo e-mail com `@logcomex.com` fixo e visível como sufixo |
| Sidebar | Fundo `#1E1B4B` roxo-escuro com nav items e avatar do usuário logado |
| Banner | Ilustração SVG minimalista em linhas roxas (pessoa na maca de massagem) |
| Limite | 1 agendamento/dia por pessoa; tentativa extra abre modal de remarcação |
| Admin gate | Botão discreto na sidebar do portal; senha `admin123` |
| "Clientes" | Renomeado para **"Loggers"** em todo o sistema admin |
| Disponibilidade | Slots mostram nome do logger agendado + botão cancelar direto |
| GitHub | Repositório público para GitHub Pages gratuito funcionar |
| index.html | Redirect automático para `agendamento.html` na raiz |

---

## 🚀 Como Retomar em Nova Conversa

Copie e cole o seguinte prompt para iniciar uma nova conversa com o Claude:

---

```
Olá! Vou te passar o contexto de um projeto que desenvolvemos juntos para que possamos continuar.

PROJETO: Log Wellbeing — sistema interno de agendamento de massagens da Logcomex
REPOSITÓRIO: https://github.com/Debora1402/Agendamento-de-Massagens
URL PÚBLICA: https://debora1402.github.io/Agendamento-de-Massagens/
TOKEN GITHUB: ghp_XXXXXXXXXXXXXXXX  ← coloque seu token atual aqui

ARQUIVOS:
- agendamento.html → portal dos colaboradores
- admin.html → painel administrativo
- index.html → redirect para agendamento.html

TECNOLOGIA: HTML + CSS + JS puro, sem frameworks, dados em localStorage

CHAVES localStorage:
- lw_v7_bookings (agendamentos)
- lw_v7_clients (loggers)
- lw_v7_blocked (horários bloqueados)

DESIGN:
- Fonte: Poppins (300/400/500/600/700)
- Roxo principal: #5B21B6 / #7C3AED / #6D28D9
- Sidebar: #1E1B4B (220px fixa, fundo roxo-escuro)
- Fundo: #F4F5F9
- Layout: sidebar + banner lilás (#ECE9FF) com ilustração SVG (pessoa na maca) + grid 2 cards

CREDENCIAIS ADMIN: usuário "admin" / senha "admin123"

REGRAS DE NEGÓCIO:
- 1 agendamento/dia por pessoa (tentativa extra → modal de remarcação)
- 2 vagas por slot, 27 slots/dia (09h-17h40, 20min cada)
- E-mail @logcomex.com pré-fixado no login
- Admin pode cancelar agendamentos direto na tela de Disponibilidade

DOCUMENTO DE CONTEXTO COMPLETO:
https://github.com/Debora1402/Agendamento-de-Massagens/blob/main/CONTEXTO_PROJETO.md

[DESCREVA AQUI O QUE VOCÊ QUER MUDAR OU ADICIONAR]
```

---

## 📌 Próximas Melhorias Possíveis (backlog)

- [ ] Notificação real por e-mail (integração com SendGrid ou similar)
- [ ] Agendamentos para datas futuras (não só hoje)
- [ ] Exportar relatórios em CSV/PDF
- [ ] Confirmação de presença pelo logger no dia
- [ ] Histórico de agendamentos do próprio usuário logado
- [ ] Modo mobile com sidebar recolhível

---

*Última atualização: maio de 2025 · Desenvolvido com Claude Sonnet (Anthropic)*
