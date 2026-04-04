# Histórico de Apontamento de Domínio (DNS) - Cloudflare

Este documento registra a migração do gerenciamento de DNS para o Cloudflare, garantindo maior velocidade e proteção para o domínio principal.

## 📅 Dados da Operação
- **Data:** 04/04/2026
- **Domínio:** `thetipdigital.com.br` (Raiz e Subdomínios)
- **Registrador (Origem):** Hostgator
- **Gerenciador de DNS (Destino):** Cloudflare

---

## 🛠️ Configurações Realizadas

### 1. Migração de Nameservers (DNS)
A autoridade de DNS foi transferida da Hostgator para o Cloudflare. Os servidores de nome foram alterados para:
*   **Servidor 1:** `tara.ns.cloudflare.com`
*   **Servidor 2:** `yichun.ns.cloudflare.com`

### 2. Status da Propagação
- **Início:** 10:18 AM (Horário Local)
- **Tempo Estimado:** De alguns minutos até 24 horas (Geralmente leva menos de 30 minutos com Cloudflare).

---

## 🔒 Benefícios Ativados
Com o Cloudflare agora no comando, as seguintes tecnologias serão configuradas:
1.  **SSL Flexível/Completo:** Cadeado de segurança ativado automaticamente.
2.  **Proxy (Nuvem Laranja):** Esconde o IP real do servidor e protege contra ataques.
3.  **Edge Caching:** O site será servido a partir dos servidores globais do Cloudflare para maior velocidade.

## ⚙️ Configuração Cloudflare Pages (Custom Domains)
- **Data/Hora:** 04/04/2026 - 11:08 AM
- **Status:** Unificado (Apenas 1 aplicação ativa no Cloudflare)

A aplicação foi vinculada aos domínios oficiais utilizando o Cloudflare API Tooling para garantir a persistência das configurações de SSL e Proxy.

### Domínios Vinculados ao Projeto `paginasweb`:
1.  **Raiz (Apex):** `thetipdigital.com.br` -> `initializing/active`
2.  **Subdomínio www:** `www.thetipdigital.com.br` -> `initializing/active`

### Automação de Deploy:
Todo o código foi sincronizado com o repositório **`tipdigital/paginasweb`** no GitHub. Agora, cada atualização no código enviada via `git push` refletirá automaticamente no domínio principal.

---
*Cópia v2 atualizada com sucesso.*
