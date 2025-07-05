# Upload para GitHub - Furby Investimentos

## 🚀 Guia Completo para Subir o Projeto no GitHub

### 1. Preparar o Repositório Local

Abra o terminal/PowerShell na pasta do projeto e execute:

```bash
# Inicializar repositório Git (se ainda não foi feito)
git init

# Adicionar todos os arquivos
git add .

# Fazer o primeiro commit
git commit -m "Initial commit: Furby Investimentos Platform"
```

### 2. Criar Repositório no GitHub

1. Acesse [GitHub.com](https://github.com)
2. Clique em **"New repository"** (botão verde)
3. Configure:
   - **Repository name**: `furby-investimentos`
   - **Description**: `Plataforma de investimentos com integração MongoDB e PIX`
   - **Visibility**: Private (recomendado) ou Public
   - **NÃO** marque "Add a README file" (já temos)
4. Clique em **"Create repository"**

### 3. Conectar e Fazer Upload

Após criar o repositório, execute no terminal:

```bash
# Adicionar origem remota (substitua SEU_USUARIO pelo seu username)
git remote add origin https://github.com/SEU_USUARIO/furby-investimentos.git

# Definir branch principal
git branch -M main

# Fazer upload para GitHub
git push -u origin main
```

### 4. Comandos Alternativos (se der erro)

Se houver problemas, tente:

```bash
# Forçar push (cuidado - só use se necessário)
git push -f origin main

# Ou configurar upstream
git push --set-upstream origin main
```

### 5. Configurar Git (se for primeira vez)

Se for seu primeiro uso do Git:

```bash
# Configurar nome e email
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@exemplo.com"
```

### 6. Verificar Upload

Após o upload:
1. Acesse seu repositório no GitHub
2. Verifique se todos os arquivos estão lá
3. Confirme se o README.md está sendo exibido

### 7. Próximos Passos - Deploy Automático

Com o código no GitHub, você pode:

1. **Conectar à Vercel**:
   - Acesse [vercel.com](https://vercel.com)
   - Clique em "New Project"
   - Importe seu repositório GitHub
   - Configure as variáveis de ambiente
   - Deploy automático!

2. **Variáveis de Ambiente na Vercel**:
   ```
   MONGODB_URI = mongodb+srv://api:api123@cluster0.4h4fdrw.mongodb.net/furby_investimentos?retryWrites=true&w=majority&appName=Cluster0
   JWT_SECRET = furby_felipe
   ASAAS_API_KEY = $aact_prod_000MzkwODA2MWY2OGM3MWRlMDU2NWM3MzJlNzZmNGZhZGY6OjlhODczYTE5LTIxOTctNGQ0My1iMzA1LWFiMWNkNTEwYTkxOTo6JGFhY2hfNjI5NjQ3NDgtZjRhYS00YTZlLTg3MDYtNjJmYTI2Y2VjODUz
   ASAAS_WALLET_ID = baa46271-9069-4bcb-9950-1fa5263ba946
   COMPANY_PIX_KEY = a90517e4-00c9-4208-b921-130a75948cbf
   ```

### 8. Comandos Úteis para o Futuro

```bash
# Verificar status
git status

# Adicionar mudanças
git add .

# Fazer commit
git commit -m "Descrição das mudanças"

# Enviar para GitHub
git push

# Puxar mudanças do GitHub
git pull
```

### 9. Estrutura do Projeto no GitHub

Seu repositório terá:
```
furby-investimentos/
├── api/
├── backend/
├── css/
├── js/
├── img/
├── logo/
├── *.html
├── package.json
├── vercel.json
├── README.md
└── DEPLOY_VERCEL.md
```

### ⚠️ Importante

1. **Arquivo .env**: O GitHub **NÃO** deve receber o arquivo `.env` com suas credenciais
2. **Gitignore**: Certifique-se que existe um `.gitignore` com:
   ```
   .env
   node_modules/
   .vercel
   ```

### 🆘 Problemas Comuns

**Erro de autenticação**:
- Use token pessoal em vez de senha
- Configure SSH keys

**Arquivo muito grande**:
- Use Git LFS para arquivos grandes
- Remova arquivos desnecessários

**Conflitos**:
- Use `git pull` antes de `git push`
- Resolva conflitos manualmente

---

**✅ Após seguir estes passos, seu projeto estará no GitHub e pronto para deploy automático na Vercel!**