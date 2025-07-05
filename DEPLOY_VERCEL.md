# Deploy na Vercel - Furby Investimentos

## ✅ Sim, você pode hospedar tudo junto na Vercel!

Seu projeto está configurado para funcionar na Vercel com backend e frontend juntos. O arquivo `vercel.json` foi atualizado com todas as configurações necessárias.

## 🚀 Passos para Deploy

### 1. Configurar Variáveis de Ambiente na Vercel

No painel da Vercel, vá em **Settings > Environment Variables** e adicione:

```
MONGODB_URI = mongodb+srv://api:api123@cluster0.4h4fdrw.mongodb.net/furby_investimentos?retryWrites=true&w=majority&appName=Cluster0
JWT_SECRET = furby_felipe
ASAAS_API_KEY = $aact_prod_000MzkwODA2MWY2OGM3MWRlMDU2NWM3MzJlNzZmNGZhZGY6OjlhODczYTE5LTIxOTctNGQ0My1iMzA1LWFiMWNkNTEwYTkxOTo6JGFhY2hfNjI5NjQ3NDgtZjRhYS00YTZlLTg3MDYtNjJmYTI2Y2VjODUz
ASAAS_WALLET_ID = baa46271-9069-4bcb-9950-1fa5263ba946
COMPANY_PIX_KEY = a90517e4-00c9-4208-b921-130a75948cbf
```

### 2. Fazer Deploy

1. Conecte seu repositório GitHub à Vercel
2. A Vercel detectará automaticamente as configurações do `vercel.json`
3. O deploy será feito automaticamente

### 3. URL do seu projeto

```
https://furby-money-hzlfuxy0k-alvesoffs-projects.vercel.app/
```

## 🔧 Correções Implementadas

### ✅ Problemas Corrigidos:

1. **Configuração Vercel**: Arquivo `vercel.json` completamente reconfigurado
2. **Roteamento**: Configurado para servir frontend e API corretamente
3. **MongoDB Memory Server**: Removido (não funciona em serverless)
4. **Conexão MongoDB**: Otimizada para ambiente serverless
5. **CORS**: Configurado para aceitar o domínio da Vercel
6. **Variáveis de Ambiente**: Mapeadas corretamente

### 📁 Estrutura de Deploy:

- **Frontend**: Servido estaticamente (HTML, CSS, JS, imagens)
- **Backend**: Função serverless em `/api/index.js`
- **Rotas API**: Todas em `/api/*`
- **Arquivos Estáticos**: Servidos diretamente

## 🌐 Como Funciona

- **Frontend**: `https://seu-dominio.vercel.app/` → `index.html`
- **API**: `https://seu-dominio.vercel.app/api/*` → Função serverless
- **Páginas**: `https://seu-dominio.vercel.app/dashboard.html` → Páginas estáticas
- **Assets**: `https://seu-dominio.vercel.app/css/styles.css` → Arquivos estáticos

## ⚠️ Importante

1. **MongoDB Atlas**: Certifique-se que o MongoDB Atlas está acessível
2. **Variáveis de Ambiente**: Configure todas as variáveis na Vercel
3. **ASAAS Webhook**: Atualize a URL do webhook no painel ASAAS para:
   ```
   https://furby-money-hzlfuxy0k-alvesoffs-projects.vercel.app/api/asaas/webhook
   ```

## 🔍 Testando o Deploy

Após o deploy, teste:

1. **Frontend**: Acesse a URL principal
2. **API Health**: `https://seu-dominio.vercel.app/api/health`
3. **Login**: Teste o sistema de autenticação
4. **PIX**: Teste as funcionalidades de pagamento

## 🆘 Solução de Problemas

Se houver problemas:

1. Verifique os logs na Vercel
2. Confirme as variáveis de ambiente
3. Teste a conexão MongoDB
4. Verifique se o ASAAS está configurado corretamente

---

**✅ Seu projeto está pronto para deploy na Vercel!**