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

## ⚙️ Configurações Realizadas no Painel GTM (v3)
- **Data/Hora:** 06/04/2026 - 07:05 PM
- **Responsável:** Antigravity (IA Assitente)

Implementação do rastreamento de vendas (E-commerce) e configuração de parâmetros avançados para a IA Gestora.

### 1. Rastreamento de Vendas (E-commerce GA4)
- **Nome do Evento:** `purchase`
- **Modelo de Tag:** Google Analytics: Evento do GA4
- **Configurações E-commerce:** Ativado (Uso de Camada de Dados/DataLayer)
- **Parâmetros Capturados:** `transaction_id`, `value`, `currency`, `items[]`
- **Acionador:** `Evento Personalizado - purchase`
- **URL de Destino:** `/obrigado2/` (Processamento de dados via URL params da Cakto)

### 2. Rastreamento de Vendas (Meta Purchase)
- **ID do Pixel:** `867360219693005`
- **Tipo de Evento:** `Purchase` (Conversão Padrão)
- **Propriedades (Object Properties):** `value`, `currency`, `order_id`
- **Correspondência Avançada (Advanced Matching):** Mapeamento de `customer_email` e `customer_name`
- **Acionador:** `Evento Personalizado - purchase`

### 3. Variáveis de Camada de Dados (v2)
Para possibilitar o Advanced Matching e a análise da IA, foram criadas as seguintes variáveis no GTM:
- `dlv - customer_email` -> `customer_email`
- `dlv - customer_name` -> `customer_name`
- `dlv - purchase_value` -> `purchase_value`
- `dlv - order_id` -> `order_id`

---
*Log V3 atualizado e validado via GTM Preview Mode.*

## ⚙️ Configuração de Análise via Terminal (v4)
- **Data/Hora:** 06/04/2026 - 07:25 PM
- **Responsável:** Antigravity (IA Assitente)

Habilita a capacidade da IA de ler métricas diretamente via terminal para gerar relatórios de performance de funil (Meta vs GA4).

### 1. Integração Google Cloud (GA4)
- **Método:** Google Service Account (Conta de Serviço)
- **Arquivo de Chave:** `credentials-GA4.json`
- **Permissão:** Leitor de Propriedade (Property Viewer) no GA4
- **Objetivo:** Consultar eventos de `purchase` e `generate_lead` programaticamente.

### 2. Integração Meta Ads API
- **Token:** Access Token Validado (System User)
- **Conta de Anúncios:** `META_AD_ACCOUNT_ID` (Pendente inserção do ID final no .env)
- **Objetivo:** Consultar gastos (`spend`), impressões e cliques para cálculo de ROAS e CPC.

### 3. Próximos Passos
- Criação do script `analytics_report.py` para automação de fechamento diário/semanal.
- Cruzamento de dados de checkout (Cakto) com dados de tráfego (Meta/Google).

---
*Log V4 atualizado. Infraestrutura de dados pronta para análise automatizada.*
