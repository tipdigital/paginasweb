# 📄 Documentação Técnica: Integração API Cakto (Escalaí)

Este documento documenta os requisitos técnicos e o fluxo de integração entre as páginas de venda/checkout da Cakto e o ecossistema do Escalaí.

## 1. Credenciais e Host
- **Base API:** `https://api.cakto.com.br`
- **Autenticação:** `POST /public_api/token/` (OAuth2 Client Credentials)
- **Variáveis de Ambiente (Configuradas no `.env`):**
    *   `CAKTO_CLIENT_ID`
    *   `CAKTO_CLIENT_SECRET`
    *   `CAKTO_WEBHOOK_SECRET`

---

## 2. Configuração de Webhooks
O sistema espera receber eventos da Cakto no seguinte endpoint para liberação de acesso:

- **URL:** `https://thetipdigital.com.br/api/webhooks/cakto` (ou subdomínio Escalaí)
- **Evento Crítico:** `purchase_approved`
- **Payload Esperado (Campos Obrigatórios):**
    *   `data.customer.email`: E-mail do comprador (chave de acesso do aluno).
    *   `data.product.id`: UUID do produto na Cakto (deve bater com o cadastrado no painel Escalaí).

---

## 3. Mapeamento de Status de Pedido
O sistema reconhece os seguintes status como "Acesso Liberado" ao consultar a API diretamente:
- `paid`
- `approved`
- `purchase_approved`

---

## 4. Fluxo de Produto no Escalaí
Ao criar uma página de vendas, o ID do produto (UUID) gerado na Cakto deve ser copiado para o campo **"ID Produto Cakto"** no gerenciador de membros do Escalaí. Sem esse vínculo, o acesso não é liberado automaticamente.

---

## 5. Estrutura de Retorno (Exemplo de Consulta de Pedidos)
Para consultas via API (`/public_api/orders/`), o retorno vem encapsulado em um array `results`:

```json
{
  "results": [
    {
      "status": "purchase_approved",
      "customer": { "email": "aluno@exemplo.com" },
      "product": { "id": "uuid-do-produto-cakto" }
    }
  ]
}
```

---
*Este documento é um guia técnico para agentes de automação e desenvolvedores.*
