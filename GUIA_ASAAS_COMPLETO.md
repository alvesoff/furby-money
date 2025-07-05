# 🏦 Guia Completo ASAAS - Sandbox, Webhook e Configuração

## 📋 Sua Configuração Atual

✅ **API Key de Produção**: Configurada  
✅ **Wallet ID**: baa46271-9069-4bcb-9950-1fa5263ba946  
✅ **Ambiente**: Produção (https://api.asaas.com/v3)  

---

## 🔧 1. SANDBOX vs PRODUÇÃO

### **SANDBOX (Ambiente de Testes)**
- 🧪 **Para que serve**: Testar integrações sem movimentar dinheiro real
- 🔗 **URL**: `https://sandbox.asaas.com/api/v3`
- 💰 **Pagamentos**: Simulados (não há cobrança real)
- 🔑 **API Key**: Diferente da produção (começa com `$aact_test_`)
- 📱 **App ASAAS**: Tem versão específica para sandbox

### **PRODUÇÃO (Ambiente Real)**
- 💸 **Para que serve**: Processar pagamentos reais
- 🔗 **URL**: `https://api.asaas.com/v3`
- 💰 **Pagamentos**: Reais (com taxas)
- 🔑 **API Key**: Sua chave atual (começa com `$aact_prod_`)
- 📱 **App ASAAS**: Versão normal do app

---

## 🔔 2. WEBHOOK - Como Funciona

### **O que é Webhook?**
O webhook é uma URL que o ASAAS chama automaticamente quando algo acontece (ex: pagamento recebido).

### **Fluxo do Webhook:**
```
1. Cliente paga PIX → 
2. ASAAS processa → 
3. ASAAS chama seu webhook → 
4. Seu sistema atualiza saldo
```

### **Configurar Webhook no ASAAS:**

1. **Acesse o painel ASAAS**
2. **Vá em**: Configurações → Integrações → Webhooks
3. **Adicione a URL**: `https://seu-dominio.com/api/asaas/webhook`
4. **Selecione eventos**:
   - ✅ `PAYMENT_RECEIVED` (Pagamento recebido)
   - ✅ `PAYMENT_OVERDUE` (Pagamento vencido)
   - ✅ `PAYMENT_DELETED` (Pagamento cancelado)

### **Eventos Importantes:**
- `PAYMENT_RECEIVED`: Quando o PIX é pago
- `PAYMENT_OVERDUE`: Quando o PIX vence
- `PAYMENT_DELETED`: Quando o PIX é cancelado

---

## 🚀 3. TESTANDO NO SANDBOX

### **Passo 1: Configurar Sandbox**
```env
ASAAS_ENVIRONMENT=sandbox
ASAAS_BASE_URL=https://sandbox.asaas.com/api/v3
ASAAS_API_KEY=sua_chave_sandbox_aqui
```

### **Passo 2: Criar Cobrança de Teste**
1. Use sua aplicação para criar um depósito
2. O ASAAS gerará um PIX de teste
3. Use o app ASAAS Sandbox para "pagar"

### **Passo 3: Simular Pagamento**
1. **Baixe o app**: ASAAS Sandbox (Google Play/App Store)
2. **Faça login** com sua conta
3. **Escaneie o QR Code** gerado
4. **Confirme o pagamento** (simulado)

---

## 💳 4. DADOS DE TESTE (SANDBOX)

### **CPFs Válidos para Teste:**
- `11144477735`
- `22233344456`
- `33322211198`

### **Cartões de Teste:**
- **Visa**: `4000000000000010`
- **Mastercard**: `5555555555554444`
- **CVV**: `123`
- **Validade**: Qualquer data futura

### **Chaves PIX de Teste:**
- **Email**: `teste@asaas.com`
- **Telefone**: `+5511999999999`
- **CPF**: `11144477735`

---

## 🔐 5. SEGURANÇA E BOAS PRÁTICAS

### **Proteger API Key:**
```bash
# ❌ NUNCA faça isso:
git add .env

# ✅ Sempre adicione no .gitignore:
echo ".env" >> .gitignore
```

### **Validar Webhook:**
```javascript
// Verificar se a requisição vem do ASAAS
const crypto = require('crypto');

function validateWebhook(payload, signature) {
  const hash = crypto
    .createHmac('sha256', process.env.ASAAS_WEBHOOK_SECRET)
    .update(payload)
    .digest('hex');
  
  return hash === signature;
}
```

---

## 📊 6. MONITORAMENTO E LOGS

### **Logs Importantes:**
```javascript
// No seu webhook
console.log('Webhook recebido:', {
  event: req.body.event,
  paymentId: req.body.payment?.id,
  value: req.body.payment?.value,
  status: req.body.payment?.status
});
```

### **Dashboard ASAAS:**
- 📈 **Transações**: Acompanhe em tempo real
- 📋 **Logs de API**: Veja todas as chamadas
- 🔔 **Webhooks**: Status de entrega

---

## 🛠️ 7. CONFIGURAÇÃO COMPLETA

### **Arquivo .env Atual:**
```env
# PRODUÇÃO - CONFIGURADO ✅
ASAAS_API_KEY=$aact_prod_000MzkwODA2MWY2OGM3MWRlMDU2NWM3MzJlNzZmNGZhZGY6OjlhODczYTE5LTIxOTctNGQ0My1iMzA1LWFiMWNkNTEwYTkxOTo6JGFhY2hfNjI5NjQ3NDgtZjRhYS00YTZlLTg3MDYtNjJmYTI2Y2VjODUz
ASAAS_ENVIRONMENT=production
ASAAS_BASE_URL=https://api.asaas.com/v3
ASAAS_WALLET_ID=baa46271-9069-4bcb-9950-1fa5263ba946
```

### **Para Testar (Sandbox):**
```env
# SANDBOX - PARA TESTES
ASAAS_API_KEY=sua_chave_sandbox_aqui
ASAAS_ENVIRONMENT=sandbox
ASAAS_BASE_URL=https://sandbox.asaas.com/api/v3
```

---

## 🚨 8. SOLUÇÃO DE PROBLEMAS

### **Erro: "Unauthorized"**
- ✅ Verifique se a API Key está correta
- ✅ Confirme se está usando a URL certa (sandbox/produção)

### **Webhook não funciona:**
- ✅ URL deve ser HTTPS em produção
- ✅ Verifique se a URL está acessível
- ✅ Confirme os eventos selecionados

### **PIX não é gerado:**
- ✅ Verifique se tem chave PIX cadastrada
- ✅ Confirme se a conta está ativa
- ✅ Veja se não há limite de valor

---

## 📞 9. SUPORTE ASAAS

- 📧 **Email**: suporte@asaas.com
- 📱 **WhatsApp**: (62) 3142-0000
- 📚 **Documentação**: https://docs.asaas.com
- 💬 **Chat**: Disponível no painel

---

## ✅ 10. CHECKLIST FINAL

### **Antes de ir para Produção:**
- [ ] Testou no sandbox
- [ ] Webhook configurado e testado
- [ ] Chave PIX da empresa cadastrada
- [ ] API Key de produção configurada
- [ ] Logs de monitoramento implementados
- [ ] Tratamento de erros implementado
- [ ] Backup das configurações feito

---

## 🎯 PRÓXIMOS PASSOS

1. **Teste no Sandbox** primeiro
2. **Configure o Webhook** no painel ASAAS
3. **Cadastre sua chave PIX** da empresa
4. **Monitore os logs** durante os primeiros pagamentos
5. **Configure alertas** para falhas

**Sua integração está pronta para produção! 🚀**