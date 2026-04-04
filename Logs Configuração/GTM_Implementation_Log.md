# Histórico de Configuração de Tags e Tracking - Funis TIP Digital

Este documento registra as ações realizadas na estrutura de rastreamento do site para garantir a integridade dos dados e o histórico de alterações técnicas.

## 📅 Dados da Implementação
- **Data:** 04/04/2026
- **Responsável:** Antigravity (IA Assitente)
- **ID do Google Tag Manager (GTM):** `GTM-N5FR84QB`
- **ID do Google Analytics 4 (GA4):** `G-0SR7HMXV4Y`

---

## 🛠️ Ações Realizadas no Código-Fonte

Foi realizada a injeção global dos scripts do GTM em todas as páginas do projeto via automação Python para evitar erros manuais.

### Arquivos Atualizados:
1.  `404.html`
2.  `captura/index.html`
3.  `iagestora/index.html`
4.  `iagestoradetrafego/index.html`
5.  `institucional/index.html`
6.  `obrigado/index.html`
7.  `vsl/index.html`

---

## ⚙️ Configurações Realizadas no Painel GTM (v1)

As seguintes configurações foram orientadas e validadas dentro do contêiner do GTM:

### 1. Tag de Configuração do GA4
- **ID da Tag:** `G-0SR7HMXV4Y`
- **Acionador:** `Initialization - All Pages`

### 2. Monitoramento de Conversão (Leads)
- **Nome do Evento:** `generate_lead`
- **Acionador:** `Página de Obrigado - Sucesso` (URL contém `/obrigado/`)

---

## ⚙️ Configurações Realizadas no Painel GTM (v2)
- **Data/Hora:** 04/04/2026 - 10:43 AM

As tags do ecossistema Meta Ads foram implementadas para garantir a rastreabilidade das campanhas pagas.

### 1. Configuração do Meta Pixel (Base)
- **ID do Pixel:** `867360219693005`
- **Modelo de Tag:** Meta Pixel (Official Template by Facebook)
- **Tipo de Evento:** `PageView` (Padrão)
- **Acionador:** `All Pages`
- **Objetivo:** Rastrear acessos em todas as landing pages para criar públicos de Retargeting.

### 2. Monitoramento de Conversão de Leads (Meta)
- **ID do Pixel:** `867360219693005`
- **Tipo de Evento:** `Lead` (Conversão Padrão)
- **Acionador:** `Página de Obrigado - Sucesso` (URL contém `/obrigado/`)
- **Objetivo:** Mensurar o custo por lead (CPL) e otimizar as campanhas de tráfego pago.

### 3. Otimizações de Tracking (Configurações Meta)
- **Correspondência Avançada Automática:** Ativada no Painel do Meta.
- **Access Token CAPI:** Gerado e armazenado no arquivo `.env` para futura implementação de Conversão via Servidor.

---
*Cópia v2 atualizada com sucesso.*
