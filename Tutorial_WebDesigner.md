# 🚀 Tutorial: Estrutura de Funil de Alta Conversão no Cloudflare Pages

Este guia descreve como configurar o seu ambiente de funnel de páginas estáticas no **Cloudflare Pages** conectado ao **GitHub**, permitindo que você crie slugs rápidos (ex: `/captura`, `/vsl`) em segundos e sem derrubar o seu site atual.

---

## 📋 1. Pré-Requisitos (Checklist do que já deve estar pronto)

Antes de começar a configuração no Cloudflare, garanta que:
- [ ] **Domínio Contratado**: Exemplo: `thetipdigital.com.br`
- [ ] **Conta no Cloudflare**: Criada via método de login do GitHub (Recomendado).
- [ ] **Repositório GitHub**: Criado e clonado na sua máquina (ex: `tipdigital/paginasweb`).
- [ ] **Estrutura de Código Criada**: Com pastas dedicadas (ex: `/captura/index.html`) para seus slugs.
- [ ] **Arquivos Committados Localmente**: Pelo menos um commit inicial na branch `main` do seu projeto.

*(Dica: Peça ao **Antigravity** para criar sua estrutura de pastas, arquivos HTML premiums e commits iniciais. Ele fará isso localmente em segundos)*.

---

## 🛠️ 2. Passo a Passo de Configuração

### **Etapa 1: Enviar Arquivos para o GitHub**
Antes de ir ao Cloudflare, o repositório precisa de arquivos na web. Abra o terminal na pasta do projeto e execute:
```bash
git push origin main
```

---

### **Etapa 2: Acessando o Cloudflare Pages**
1. Acesse o **Dashboard do Cloudflare**.
2. No menu lateral esquerdo, vá em **Compute (Workers)** ou **Workers & Pages**.
3. Clique no botão azul 🔵 **Create Application** (Criar Aplicação) no topo/canto da tela.
4. Na parte superior da próxima tela, você verá abas: selecione **Pages**.
5. Clique em **Connect to Git** (Conectar ao Git).

---

### **Etapa 3: Integração e Build**
1. Autorize a conta do **GitHub** e escolha o repositório do seu projeto (ex: `paginasweb`).
2. Vá para a tela de **Set up builds and deployments** e configure exatamente assim:
   - **Framework Preset**: Escolha `None` (Estático)
   - **Build Command**: Deixe em branco/vazio
   - **Build Output Directory**: Digite apenas `/` (Raiz)
3. Clique em **Save and Deploy**.

*Cloudflare vai criar sua URL temporária gratuita (ex: `paginasweb.pages.dev`). Suas rotas `/captura`, `/vsl` já estarão acessíveis nesse link.*

---

## 🌐 3. Configurar Domínio de Testes (Sem Downtime)

Para testar no seu próprio domínio sem quebrar o site principal hospedado em outro local (como no **GHL**):

1. Acesse o painel do seu projeto no Cloudflare Pages.
2. Clique na aba **Custom Domains** (Domínios Personalizados).
3. Clique em **Set up a Custom Domain**.
4. Insira um subdomínio de testes (ex: `lp.thetipdigital.com.br` ou `promo.*`).
5. Siga as instruções para que o Cloudflare resolva o apontamento.

---

## 💡 Maximizando com o Antigravity
Sempre que precisar de um novo slug:
1. Peça ao **Antigravity**: *"Crie um design premium para o slug /leads"*.
2. Ele fará a criação da pasta `/leads/index.html` e do CSS localmente.
3. Você roda `git push` e o Cloudflare atualiza **sozinho**, sem que você precise abrir nenhuma plataforma arrasta-e-solta!
