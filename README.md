# Formulário de Trocas e Devoluções - Chiller Peças

Formulário web para solicitação de trocas, devoluções e acionamento de garantia, integrado com webhook Hablla.

## 📋 Arquivos do Projeto

- `index.html` - Formulário principal
- `vercel.json` - Configuração de deploy Vercel
- `.gitignore` - Arquivos ignorados pelo Git
- `README.md` - Este arquivo

## 🚀 Passo a Passo - Deploy com GitHub e Vercel

### PARTE 1: Configurar GitHub

**1. Criar Repositório no GitHub**

1. Acesse [github.com](https://github.com)
2. Clique no botão **"+"** (canto superior direito) → **"New repository"**
3. Preencha:
   - **Repository name**: `formulario-trocas-chiller`
   - **Description**: "Formulário de trocas e devoluções Chiller Peças"
   - Deixe como **Public**
   - **NÃO** marque "Add a README file"
4. Clique em **"Create repository"**

**2. Subir Arquivos para o GitHub**

No seu computador, abra o terminal/prompt de comando na pasta onde estão os arquivos e execute:

```bash
# Inicializar repositório Git
git init

# Adicionar todos os arquivos
git add .

# Fazer o primeiro commit
git commit -m "Formulário de trocas e devoluções - versão inicial"

# Adicionar o repositório remoto (substitua SEU-USUARIO pelo seu username do GitHub)
git remote add origin https://github.com/SEU-USUARIO/formulario-trocas-chiller.git

# Renomear branch para main
git branch -M main

# Enviar para o GitHub
git push -u origin main
```

**Importante**: Quando pedir usuário e senha:
- **Username**: Seu username do GitHub
- **Password**: Use um [Personal Access Token](https://github.com/settings/tokens) ao invés da senha
  - Vá em GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
  - Generate new token → Marque "repo" → Generate token
  - Copie o token e use como senha

---

### PARTE 2: Fazer Deploy na Vercel

**1. Criar Conta na Vercel**

1. Acesse [vercel.com](https://vercel.com)
2. Clique em **"Sign Up"**
3. Selecione **"Continue with GitHub"**
4. Autorize a Vercel a acessar sua conta GitHub

**2. Importar Projeto**

1. No dashboard da Vercel, clique em **"Add New..."** → **"Project"**
2. Localize o repositório **"formulario-trocas-chiller"**
3. Clique em **"Import"**
4. Na tela de configuração:
   - **Project Name**: `formulario-trocas-chiller` (ou outro nome de sua preferência)
   - **Framework Preset**: Deixe como **"Other"**
   - **Root Directory**: `./` (padrão)
   - **Build Command**: Deixe vazio
   - **Output Directory**: Deixe vazio
5. Clique em **"Deploy"**

**3. Aguardar Deploy**

- O processo leva cerca de 30-60 segundos
- Você verá uma animação de confetes quando finalizar ✨
- A Vercel vai gerar uma URL tipo: `https://formulario-trocas-chiller.vercel.app`

**4. Copiar a URL**

1. Após o deploy, clique em **"Visit"** para testar
2. Copie a URL completa que aparece no navegador
3. Esta é a URL que você vai usar no iframe do Hablla

---

### PARTE 3: Integrar no Hablla

**1. Configurar HTML Element Component**

Na tela de configuração do Hablla que você mostrou:

**Campo: HTML Tag**
```
div
```

**Campo: CSS Class**
```
formulario-container
```

**Campo: HTML**
```html
<iframe 
  src="https://formulario-trocas-chiller.vercel.app" 
  width="100%" 
  height="1800px" 
  frameborder="0" 
  style="border: none; overflow: hidden;"
  allowfullscreen>
</iframe>
```
*Substitua a URL pela sua URL da Vercel*

**Campo: Attributes**
- Attribute: `allowfullscreen`
- Value: `true`

**Campo: Custom CSS Class** (opcional)
```css
.formulario-container iframe {
  min-height: 1800px;
  width: 100%;
  display: block;
  margin: 0 auto;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}
```

**2. Salvar e Testar**

1. Clique em **"Save"** no Hablla
2. Acesse o formulário através do fluxo do Hablla
3. Teste o envio completo com upload de arquivos

---

## 🔄 Como Fazer Atualizações no Formulário

Quando precisar modificar o formulário:

```bash
# 1. Edite os arquivos necessários (index.html, etc)

# 2. Adicione as mudanças
git add .

# 3. Faça commit com descrição clara
git commit -m "Descrição da alteração realizada"

# 4. Envie para o GitHub
git push origin main
```

**A Vercel faz deploy automático!** Assim que você fizer push para o GitHub, a Vercel detecta e atualiza automaticamente em 30-60 segundos.

---

## 📡 Webhook Configurado

**URL**: `https://webhook.hablla.com/v1/69396a75d031db1d0cde7080`

### Estrutura dos Dados Enviados

```json
{
  "cliente": "Nome ou Razão Social",
  "solicitante": "Nome do Solicitante",
  "email": "email@exemplo.com",
  "telefone": "(11) 98765-4321",
  "numeroNF": "123456",
  "tipoSolicitacao": "troca|devolucao|garantia",
  "itens": "Nome dos itens conforme NF",
  "descricao": "Descrição detalhada do caso",
  "arquivos": [
    {
      "nome": "foto.jpg",
      "tipo": "image/jpeg",
      "tamanho": 123456,
      "conteudo": "data:image/jpeg;base64,..."
    }
  ],
  "dataEnvio": "2025-12-10T15:30:00.000Z",
  "origem": "Formulário Web - Trocas e Devoluções"
}
```

---

## 🎨 Funcionalidades Implementadas

✅ Upload de múltiplos arquivos (drag & drop ou clique)
✅ Conversão de arquivos para Base64
✅ Validação de campos obrigatórios
✅ Máscara automática de telefone
✅ Mensagens de sucesso/erro
✅ Loading durante envio
✅ Design responsivo (mobile, tablet, desktop)
✅ Integração direta com webhook Hablla

---

## 🆘 Solução de Problemas

**Problema**: Erro ao fazer push para GitHub
- **Solução**: Verifique se criou o Personal Access Token e está usando ele como senha

**Problema**: Deploy falhou na Vercel
- **Solução**: Verifique se todos os arquivos foram enviados corretamente para o GitHub

**Problema**: Formulário não aparece no Hablla
- **Solução**: Verifique se a URL do iframe está correta e se o site está acessível

**Problema**: Webhook não está recebendo dados
- **Solução**: Abra o Console do navegador (F12) e verifique se há erros. Confirme se a URL do webhook está correta.

---

## 📞 Suporte

Para dúvidas ou problemas:
1. Verifique os logs no Console do navegador (F12)
2. Verifique o dashboard da Vercel para erros de deploy
3. Teste o webhook diretamente usando ferramentas como Postman

---

## 📝 Licença

Projeto desenvolvido para Chiller Peças - Uso Interno

---

**Desenvolvido com Claude para Chiller Peças** 🔧
