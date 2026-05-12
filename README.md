# 💆 Log Wellbeing — Portal de Agendamento de Massagens

Sistema interno de agendamento de serviços de bem-estar para colaboradores da **Logcomex**.

---

## 📁 Arquivos

| Arquivo | Descrição |
|---|---|
| `agendamento.html` | Portal principal de agendamento (uso dos colaboradores) |
| `admin.html` | Painel administrativo com relatórios, gestão de loggers e disponibilidade |
| `logwellbeing-design.html` | Referência de design da interface |

---

## 🚀 Como usar

Basta abrir os arquivos diretamente no navegador — não requer servidor ou instalação.

### Portal de Agendamento (`agendamento.html`)
1. Faça login com seu **nome completo** e **e-mail** (o `@logcomex.com` é preenchido automaticamente)
2. Escolha entre **Cadeira de Massagem** ou **Massageador de Pés**
3. Selecione um horário disponível
4. Confirme sua reserva

> ⚠️ Somente **1 agendamento por dia** é permitido por colaborador. Caso já tenha um, o sistema oferece a opção de remarcar.

### Painel Administrativo (`admin.html`)
Acesse pelo botão discreto **"Acesso Admin"** no rodapé da sidebar do portal principal.

- **Credenciais:** usuário `admin` / senha `admin123`

#### Funcionalidades do Admin
- **Dashboard** — visão geral do dia + busca de agendamentos por e-mail
- **Agendamentos** — lista com filtros por data, serviço e status
- **Disponibilidade** — bloquear/liberar horários, agendar diretamente
- **Loggers** — gestão de colaboradores com histórico de agendamentos
- **Relatórios** — taxa de ocupação, horários de pico, gráficos por período

---

## 🎨 Design

- **Fonte:** Poppins (Google Fonts)
- **Paleta:** Roxo `#5B21B6` · Sidebar `#1E1B4B` · Fundo `#F4F5F9`
- **Layout:** Sidebar fixa + banner com ilustração SVG + grid de cards

---

## 💾 Armazenamento

Dados salvos via **localStorage** nas chaves:
- `lw_v7_bookings` — agendamentos
- `lw_v7_clients` — loggers cadastrados
- `lw_v7_blocked` — horários bloqueados

> Para sincronização, portal e admin devem rodar no mesmo navegador/domínio.

---

## 🕐 Horários

Das **09h00** às **17h40**, slots de **20 minutos** · 27 horários/dia · 2 pessoas por slot.

---

*Desenvolvido com Claude (Anthropic) · Logcomex Internal Tools*
