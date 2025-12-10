# 🚀 PASSO A PASSO COMPLETO - Deploy Vercel + GitHub

## ✅ PARTE 1: GITHUB (5 minutos)

### 1️⃣ Criar Repositório

📍 Acesse: https://github.com
- Clique no **"+"** (canto superior direito)
- Selecione **"New repository"**
- Nome: `formulario-trocas-chiller`
- Descrição: `Formulário de trocas e devoluções Chiller Peças`
- Tipo: **Public**
- ❌ NÃO marque "Add a README"
- Clique **"Create repository"**

### 2️⃣ Preparar Arquivos no Computador

📁 Baixe todos os arquivos que te enviei:
- ✅ index.html
- ✅ vercel.json
- ✅ .gitignore
- ✅ README.md
- ✅ COMANDOS-GIT.md

📂 Coloque todos em uma pasta chamada `formulario-trocas-chiller`

### 3️⃣ Enviar para GitHub

🖥️ Abra o Terminal/Prompt na pasta e execute:

```bash
git init
git add .
git commit -m "Versão inicial do formulário"
git remote add origin https://github.com/SEU-USUARIO/formulario-trocas-chiller.git
git branch -M main
git push -u origin main
```

🔑 **ATENÇÃO**: Quando pedir senha, use **Personal Access Token**

Como conseguir o token:
1. GitHub → Settings (ícone do seu perfil)
2. Developer settings (menu lateral, último item)
3. Personal access tokens → Tokens (classic)
4. Generate new token (classic)
5. Note: "Token Vercel Deploy"
6. Marque: ✅ repo (todos os checkboxes abaixo)
7. Generate token
8. **COPIE O TOKEN** (só aparece uma vez!)
9. Use este token como senha no terminal

---

## ✅ PARTE 2: VERCEL (3 minutos)

### 1️⃣ Criar Conta

📍 Acesse: https://vercel.com
- Clique **"Sign Up"**
- Escolha **"Continue with GitHub"**
- Autorize a Vercel

### 2️⃣ Importar Projeto

No dashboard da Vercel:
- Clique **"Add New..."** → **"Project"**
- Localize: `formulario-trocas-chiller`
- Clique **"Import"**

### 3️⃣ Configurar Deploy

Na tela de configuração:
- Project Name: `formulario-trocas-chiller`
- Framework Preset: **Other** (deixe como está)
- Build Command: *deixe vazio*
- Output Directory: *deixe vazio*
- Clique **"Deploy"**

### 4️⃣ Aguardar Deploy

⏱️ Aguarde 30-60 segundos
🎉 Você verá confetes quando finalizar!

### 5️⃣ Copiar URL

Sua URL será algo como:
```
https://formulario-trocas-chiller.vercel.app
```

**COPIE ESTA URL!** Você vai precisar dela no Hablla.

---

## ✅ PARTE 3: HABLLA (2 minutos)

### Configurar HTML Element Component

Na tela do Hablla:

**1. HTML Tag:**
```
div
```

**2. CSS Class:**
```
formulario-container
```

**3. HTML:**
```html
<iframe 
  src="https://SEU-PROJETO.vercel.app" 
  width="100%" 
  height="1800px" 
  frameborder="0" 
  style="border: none; overflow: hidden;">
</iframe>
```
⚠️ **Substitua** `https://SEU-PROJETO.vercel.app` pela sua URL da Vercel!

**4. Attributes:**
- Attribute: `allowfullscreen`
- Value: `true`

**5. Salvar:**
- Clique **"Save"**
- Teste o formulário!

---

## 🔄 ATUALIZAÇÕES FUTURAS

Quando precisar alterar o formulário:

```bash
# 1. Edite o arquivo index.html
# 2. No terminal, execute:

git add .
git commit -m "Atualização: descrição da mudança"
git push origin main
```

✨ **A Vercel atualiza sozinha em 30 segundos!**

---

## 📊 RESUMO

| Etapa | Tempo | Status |
|-------|-------|--------|
| GitHub Setup | 5 min | ⬜ |
| Vercel Deploy | 3 min | ⬜ |
| Hablla Config | 2 min | ⬜ |
| **TOTAL** | **10 min** | |

---

## 🆘 PROBLEMAS COMUNS

❌ **"Permission denied" no Git**
→ Use Personal Access Token como senha, não a senha do GitHub

❌ **"Deploy failed" na Vercel**
→ Verifique se todos os arquivos foram para o GitHub

❌ **Formulário não aparece no Hablla**
→ Confirme se a URL do iframe está correta

❌ **Webhook não recebe dados**
→ Abra F12 no navegador e veja se há erros no Console

---

## 📞 CHECKLIST FINAL

Antes de considerar concluído, verifique:

- ✅ Repositório criado no GitHub
- ✅ Todos os arquivos enviados para GitHub
- ✅ Deploy na Vercel realizado com sucesso
- ✅ URL da Vercel copiada
- ✅ Iframe configurado no Hablla
- ✅ Teste de envio realizado
- ✅ Webhook recebendo dados

**Tudo OK? Parabéns! 🎉**

---

💡 **Dica Pro**: Salve o link do seu projeto na Vercel nos favoritos para acessar rapidamente o dashboard e ver logs.

**Link dashboard Vercel**: https://vercel.com/dashboard
