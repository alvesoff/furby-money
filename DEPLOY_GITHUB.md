# 🚀 Deploy no GitHub - Furby Money

## 📋 Passo a Passo Completo

### 1. 🔧 Preparar o Repositório Local

```bash
# Navegar para o diretório do projeto
cd "c:\Users\Gustavo\Desktop\Furby\furby-investimentos-main"

# Inicializar repositório Git (se não existir)
git init

# Adicionar o repositório remoto
git remote add origin https://github.com/alvesoff/furby-money.git

# Verificar se o remote foi adicionado
git remote -v
```

### 2. 📁 Preparar Arquivos para Commit

```bash
# Adicionar todos os arquivos
git add .

# Fazer o primeiro commit
git commit -m "🚀 Initial commit - Furby Money Platform

✅ Features implementadas:
- Sistema de autenticação JWT
- Integração PIX com ASAAS
- Dashboard de investimentos
- Sistema de carteira
- Automação de pagamentos
- MongoDB Atlas integrado
- Frontend responsivo
- API REST completa"
```

### 3. 🌐 Fazer Push para GitHub

```bash
# Fazer push para o repositório
git push -u origin main

# Se der erro de branch, tentar:
git branch -M main
git push -u origin main
```

### 4. 🔐 Se Pedir Autenticação

**Opção 1: Token de Acesso Pessoal**
1. Vá em: GitHub → Settings → Developer settings → Personal access tokens
2. Gere um novo token com permissões de repositório
3. Use o token como senha quando solicitado

**Opção 2: GitHub CLI**
```bash
# Instalar GitHub CLI
winget install GitHub.cli

# Fazer login
gh auth login

# Fazer push
git push -u origin main
```

### 5. 🚀 Deploy Automático no Vercel

**Após o push no GitHub:**

1. **Acesse**: https://vercel.com
2. **Conecte** sua conta GitHub
3. **Importe** o repositório `alvesoff/furby-money`
4. **Configure** as variáveis de ambiente:

```env
MONGODB_URI=mongodb+srv://api:api123@cluster0.4h4fdrw.mongodb.net/furby_investimentos?retryWrites=true&w=majority&appName=Cluster0
JWT_SECRET=furby_felipe
ASAAS_API_KEY=$aact_prod_000MzkwODA2MWY2OGM3MWRlMDU2NWM3MzJlNzZmNGZhZGY6OjlhODczYTE5LTIxOTctNGQ0My1iMzA1LWFiMWNkNTEwYTkxOTo6JGFhY2hfNjI5NjQ3NDgtZjRhYS00YTZlLTg3MDYtNjJmYTI2Y2VjODUz
ASAAS_ENVIRONMENT=production
ASAAS_BASE_URL=https://api.asaas.com/v3
ASAAS_WALLET_ID=baa46271-9069-4bcb-9950-1fa5263ba946
COMPANY_PIX_KEY=sua_chave_pix_da_empresa
PIX_PROVIDER=asaas
NODE_ENV=production
```

5. **Deploy** automático será iniciado
6. **URL final**: `https://furby-money.vercel.app`

### 6. ⚙️ Configurar Webhook no ASAAS

**Após deploy bem-sucedido:**

1. **Acesse**: https://www.asaas.com
2. **Vá em**: Configurações → Integrações → Webhooks
3. **Adicione**: `https://furby-money.vercel.app/api/asaas/webhook`
4. **Selecione eventos**:
   - ✅ `PAYMENT_RECEIVED`
   - ✅ `PAYMENT_OVERDUE`
   - ✅ `PAYMENT_DELETED`

### 7. 🧪 Testar a Aplicação

**Credenciais de teste:**
- **Admin**: `admin@furby.com` / `admin123`
- **Usuário**: `user1@furby.com` / `user123`

**Funcionalidades para testar:**
- ✅ Login/Registro
- ✅ Dashboard de investimentos
- ✅ Depósito PIX (QR Code real)
- ✅ Saque PIX
- ✅ Histórico de transações

### 8. 📊 Monitoramento

**Logs do Vercel:**
```bash
# Instalar Vercel CLI
npm i -g vercel

# Ver logs em tempo real
vercel logs
```

**Painel ASAAS:**
- Dashboard → Vendas (transações)
- Configurações → Webhooks (status)

---

## 🔄 Comandos Úteis

### Atualizar Código
```bash
git add .
git commit -m "📝 Descrição da mudança"
git push
```

### Ver Status
```bash
git status
git log --oneline
```

### Reverter Mudanças
```bash
# Reverter arquivo específico
git checkout -- arquivo.js

# Reverter último commit
git reset --soft HEAD~1
```

---

## ✅ Checklist Final

- [ ] Código no GitHub
- [ ] Deploy no Vercel
- [ ] Variáveis de ambiente configuradas
- [ ] Webhook ASAAS configurado
- [ ] Chave PIX da empresa cadastrada
- [ ] Testes realizados
- [ ] Monitoramento ativo

**🎉 Sua plataforma estará online em: `https://furby-money.vercel.app`**