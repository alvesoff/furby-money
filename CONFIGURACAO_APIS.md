# 🚀 GUIA COMPLETO - CONFIGURAÇÃO DAS APIS

## 📋 Status Atual do Sistema

### ✅ **JÁ FUNCIONANDO:**
- ✅ MongoDB Atlas (Banco de dados)
- ✅ Sistema de autenticação JWT
- ✅ Servidor web na porta 3000
- ✅ Sistema básico de investimentos
- ✅ Interface de usuário completa

### 🔧 **PRECISA CONFIGURAR:**
- 🔧 PIX (Pagamentos automáticos)
- 🔧 Email (Recuperação de senha)

---

## 🏦 1. CONFIGURAR PIX (ASAAS)

### **Por que ASAAS?**
- ✅ Gateway brasileiro especializado
- ✅ API completa em português
- ✅ Suporte PIX nativo e robusto
- ✅ Taxas competitivas
- ✅ Sandbox gratuito para testes
- ✅ Documentação detalhada
- ✅ Suporte técnico em português

### **Passo a Passo:**

#### **1.1 Criar Conta ASAAS**
1. Acesse: https://www.asaas.com/
2. Clique em **"Criar conta grátis"**
3. Complete o cadastro:
   - Dados pessoais/empresa
   - Documentos necessários
   - Validação de email

#### **1.2 Ativar Sandbox**
1. Faça login na sua conta ASAAS
2. Vá em **"Configurações"** → **"Integrações"**
3. Clique em **"API"**
4. Ative o **"Ambiente Sandbox"**

#### **1.3 Obter API Key**
1. No painel de integrações
2. Copie a **"API Key do Sandbox"**
3. Guarde essa chave com segurança

#### **1.4 Configurar no Sistema**
Abra o arquivo `.env` e substitua:
```env
ASAAS_API_KEY=cole_sua_api_key_aqui
```

#### **1.5 Configurar Chave PIX da Empresa**
1. No painel ASAAS, vá em **"PIX"** → **"Chaves PIX"**
2. Cadastre uma chave PIX (CPF, CNPJ, email ou telefone)
3. Coloque no `.env`:
```env
COMPANY_PIX_KEY=sua_chave_pix_aqui
```

#### **1.6 Configurar Webhook (Opcional)**
1. Em **"Configurações"** → **"Webhooks"**
2. Adicione: `https://seu-dominio.com/api/asaas/webhook`
3. Selecione eventos: **"Pagamento recebido"**, **"Pagamento vencido"**

### **🧪 Testar PIX:**
1. Reinicie o servidor: `Ctrl+C` e `node server.js`
2. Acesse: http://localhost:3000
3. Faça login com: `joao@email.com` / `123456`
4. Vá na carteira e teste um depósito
5. Use os **dados de teste** do ASAAS para simular pagamentos

---

## 📧 2. CONFIGURAR EMAIL (GMAIL)

### **Por que Gmail?**
- ✅ Gratuito e confiável
- ✅ Fácil configuração
- ✅ Boa entregabilidade

### **Passo a Passo:**

#### **2.1 Ativar Verificação em 2 Etapas**
1. Acesse: https://myaccount.google.com/security
2. Clique em **"Verificação em duas etapas"**
3. Siga as instruções para ativar

#### **2.2 Gerar Senha de App**
1. Acesse: https://myaccount.google.com/apppasswords
2. Selecione **"App"** → **"Outro (nome personalizado)"**
3. Digite: **"Furby Investimentos"**
4. Clique em **"Gerar"**
5. **COPIE A SENHA DE 16 CARACTERES**

#### **2.3 Configurar no Sistema**
Abra o arquivo `.env` e substitua:
```env
EMAIL_USER=seu_email@gmail.com
EMAIL_PASS=senha_de_app_de_16_caracteres
```

### **🧪 Testar Email:**
1. Reinicie o servidor
2. Na tela de login, clique em "Esqueci minha senha"
3. Digite um email cadastrado
4. Verifique se recebeu o email

---

## 🔄 3. REINICIAR O SISTEMA

Após configurar PIX e Email:

1. **Parar o servidor atual:**
   - Pressione `Ctrl+C` no terminal

2. **Reiniciar:**
   ```bash
   node server.js
   ```

3. **Verificar se funcionou:**
   - Acesse: http://localhost:3000
   - Teste login, PIX e recuperação de senha

---

## 🆘 PROBLEMAS COMUNS

### **PIX não funciona:**
- ✅ Verifique se copiou o Access Token correto
- ✅ Certifique-se que está usando credenciais de SANDBOX
- ✅ Confirme se a chave PIX da empresa está correta

### **Email não envia:**
- ✅ Verifique se ativou verificação em 2 etapas
- ✅ Confirme se gerou a senha de app corretamente
- ✅ Teste com outro email primeiro

### **Servidor não inicia:**
- ✅ Verifique se não há espaços extras no `.env`
- ✅ Confirme se todas as aspas estão corretas
- ✅ Reinicie o terminal

---

## 📞 SUPORTE

### **Documentações Oficiais:**
- **Mercado Pago:** https://www.mercadopago.com.br/developers/pt/docs
- **Gmail App Passwords:** https://support.google.com/accounts/answer/185833

### **Contatos de Suporte:**
- **Mercado Pago:** https://www.mercadopago.com.br/developers/pt/support
- **Google:** https://support.google.com/accounts

---

## 🎯 PRÓXIMOS PASSOS

Depois de configurar tudo:

1. **Testar todas as funcionalidades**
2. **Configurar webhook do PIX** (para produção)
3. **Migrar para credenciais de produção**
4. **Configurar domínio próprio**
5. **Implementar monitoramento**

---

## 🔐 SEGURANÇA

### **IMPORTANTE:**
- 🚨 **NUNCA** compartilhe suas credenciais
- 🚨 **SEMPRE** use HTTPS em produção
- 🚨 **MUDE** o JWT_SECRET em produção
- 🚨 **MONITORE** transações regularmente

### **Backup do .env:**
Faça backup do arquivo `.env` configurado em local seguro!

---

*Última atualização: $(date)*