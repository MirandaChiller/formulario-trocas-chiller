# GUIA RÁPIDO - Comandos Git

## Primeira vez (Setup Inicial)

```bash
# 1. Inicializar Git na pasta
git init

# 2. Adicionar todos os arquivos
git add .

# 3. Fazer primeiro commit
git commit -m "Formulário de trocas e devoluções - versão inicial"

# 4. Conectar com GitHub (substitua SEU-USUARIO)
git remote add origin https://github.com/SEU-USUARIO/formulario-trocas-chiller.git

# 5. Renomear branch
git branch -M main

# 6. Enviar para GitHub
git push -u origin main
```

## Atualizações Futuras

```bash
# 1. Ver o que foi modificado
git status

# 2. Adicionar mudanças
git add .

# 3. Fazer commit
git commit -m "Descrição da alteração"

# 4. Enviar para GitHub (Vercel atualiza automaticamente)
git push origin main
```

## Comandos Úteis

```bash
# Ver histórico de commits
git log --oneline

# Ver diferenças
git diff

# Desfazer mudanças não commitadas
git checkout .

# Ver branches
git branch

# Puxar mudanças do GitHub
git pull origin main
```

## ⚠️ Importante

- Sempre use Personal Access Token como senha (não a senha do GitHub)
- A Vercel faz deploy automático após cada push
- Aguarde 30-60 segundos após o push para ver as mudanças online
