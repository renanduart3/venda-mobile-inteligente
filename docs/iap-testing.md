---
layout: default
title: Guia de Testes de In-App Purchases (IAP)
---

# 🧪 Guia de Testes de In-App Purchases (IAP)

Este documento fornece instruções para testar compras no aplicativo (In-App Purchases) usando o Google Play Console.

## Visão Geral

O Venda Mobile Inteligente utiliza o sistema de In-App Purchases do Google Play para oferecer o plano Premium. Este guia ajuda a testar essas funcionalidades antes do lançamento para produção.

## Configuração Inicial

### 1. Acesso ao Google Play Console

1. Acesse [Google Play Console](https://play.google.com/console)
2. Selecione o aplicativo "Venda Mobile Inteligente"
3. Navegue até: **Monetização** → **Produtos** → **Assinaturas**

### 2. Produtos IAP Configurados

#### Premium Mensal
- **Product ID:** `premium_monthly`
- **Preço:** R$ 29,90/mês
- **Período:** Mensal
- **Grace Period:** 7 dias

#### Premium Anual
- **Product ID:** `premium_annual`
- **Preço:** R$ 299,00/ano
- **Período:** Anual
- **Grace Period:** 7 dias

## Tipos de Teste

### Teste 1: Licença de Teste (Test License)

Permite testar sem pagamento real.

#### Configuração:
1. No Play Console: **Configuração** → **Licença de teste**
2. Adicione emails de testadores
3. Configure resposta de licença: `LICENSED`

#### Como Testar:
1. Instale o app em um dispositivo com conta de testador
2. Tente fazer upgrade para Premium
3. Selecione um plano (mensal ou anual)
4. A compra será simulada sem cobrança real

### Teste 2: Faixa de Teste Fechado (Closed Track)

Teste com grupo fechado de usuários.

#### Configuração:
1. **Versões** → **Teste fechado**
2. Crie uma versão de teste
3. Adicione testadores por email ou lista
4. Publique a versão de teste

#### Como Testar:
1. Testadores recebem link de opt-in
2. Baixam o app através do link especial
3. Podem testar IAP com pagamento real (reembolsável)

### Teste 3: Contas de Teste de Pagamento

Permite testar fluxo completo sem cobrança.

#### Configuração:
1. **Configuração** → **Contas de teste de licença**
2. Adicione contas Gmail de testadores
3. Testadores podem fazer "compras" sem cobrança

#### Como Testar:
1. Use conta de teste configurada
2. Fluxo completo de compra é executado
3. Nenhuma cobrança real é feita
4. Testador pode simular cancelamento, renovação, etc.

## Cenários de Teste

### ✅ Teste 1: Compra Nova Assinatura

**Objetivo:** Verificar fluxo de nova assinatura

**Passos:**
1. Abra o app com conta não-Premium
2. Navegue para: **Configurações** → **Premium**
3. Selecione plano (Mensal ou Anual)
4. Complete o fluxo de compra
5. Verifique se o status Premium foi ativado

**Resultado Esperado:**
- ✅ Compra processada com sucesso
- ✅ Status Premium ativado imediatamente
- ✅ Recursos Premium desbloqueados

---

### ✅ Teste 2: Cancelamento de Assinatura

**Objetivo:** Verificar comportamento após cancelamento

**Passos:**
1. Com assinatura ativa, abra Play Store
2. **Menu** → **Assinaturas** → **Venda Mobile Inteligente**
3. Clique em **Cancelar assinatura**
4. Confirme o cancelamento
5. Volte ao app

**Resultado Esperado:**
- ✅ Status Premium mantido até fim do período pago
- ✅ Notificação sobre cancelamento
- ✅ Após vencimento, volta ao plano gratuito

---

### ✅ Teste 3: Grace Period (Período de Tolerância)

**Objetivo:** Testar período de 7 dias de tolerância

**Passos:**
1. Configure método de pagamento inválido
2. Aguarde vencimento da assinatura
3. Observe comportamento nos próximos 7 dias

**Resultado Esperado:**
- ✅ Usuário mantém acesso Premium por 7 dias
- ✅ Notificações sobre problema de pagamento
- ✅ Após 7 dias sem regularização, perde acesso Premium

---

### ✅ Teste 4: Renovação Automática

**Objetivo:** Verificar renovação automática

**Passos:**
1. Aguardar data de renovação
2. Verificar se pagamento foi processado
3. Confirmar continuidade do acesso Premium

**Resultado Esperado:**
- ✅ Renovação automática bem-sucedida
- ✅ Continuidade do acesso Premium
- ✅ Recibo enviado ao usuário

---

### ✅ Teste 5: Upgrade de Plano

**Objetivo:** Testar mudança de mensal para anual

**Passos:**
1. Com assinatura mensal ativa
2. Tente assinar o plano anual
3. Verifique crédito proporcional

**Resultado Esperado:**
- ✅ Upgrade processado
- ✅ Crédito proporcional aplicado (gerenciado pelo Play)
- ✅ Nova data de renovação definida

---

### ✅ Teste 6: Restore Purchase (Restaurar Compra)

**Objetivo:** Restaurar compra em novo dispositivo

**Passos:**
1. Faça compra Premium em dispositivo A
2. Instale app em dispositivo B com mesma conta
3. Abra **Configurações** → **Premium** → **Restaurar Compra**

**Resultado Esperado:**
- ✅ Compra detectada automaticamente
- ✅ Status Premium restaurado
- ✅ Recursos Premium disponíveis

---

### ✅ Teste 7: Erro de Conexão

**Objetivo:** Testar comportamento offline

**Passos:**
1. Desabilite internet
2. Tente fazer upgrade para Premium
3. Observe mensagem de erro

**Resultado Esperado:**
- ✅ Mensagem clara de erro
- ✅ Sugestão para verificar conexão
- ✅ Possibilidade de tentar novamente

---

## Ferramentas de Teste

### 1. Google Play Console
- Painel de assinaturas ativas
- Histórico de transações
- Logs de erros de IAP

### 2. Android Debug Bridge (ADB)
```bash
# Limpar dados do app para teste limpo
adb shell pm clear com.vendamobile.inteligente

# Ver logs relacionados a billing
adb logcat | grep -i billing
```

### 3. Firebase Console
- Analytics de conversão IAP
- Eventos de compra
- Funis de conversão

## Checklist de Validação

Antes de lançar em produção, valide:

- [ ] Compra de assinatura mensal funciona
- [ ] Compra de assinatura anual funciona
- [ ] Cancelamento funciona corretamente
- [ ] Grace period de 7 dias está configurado
- [ ] Renovação automática funciona
- [ ] Upgrade de plano funciona
- [ ] Downgrade/cancelamento funciona
- [ ] Restore purchase funciona
- [ ] Notificações de pagamento funcionam
- [ ] Tratamento de erros está adequado
- [ ] UI reflete status correto (Premium/Gratuito)
- [ ] Recursos Premium são desbloqueados/bloqueados corretamente

## Problemas Comuns

### Erro: "Item já possui propriedade"
**Solução:** Cancele a assinatura de teste e aguarde alguns minutos

### Erro: "Produto não encontrado"
**Solução:** Verifique se os Product IDs estão corretos no código e no Play Console

### Compra não restaurada
**Solução:** Certifique-se de usar a mesma conta Google em ambos dispositivos

### Grace Period não funcionando
**Solução:** Verifique configuração no Play Console: Assinatura → Configurações → Grace Period

## Documentação Oficial

Para mais informações:
- [Google Play Billing Documentation](https://developer.android.com/google/play/billing)
- [Testing In-App Purchases](https://developer.android.com/google/play/billing/test)
- [Subscription Testing](https://support.google.com/googleplay/android-developer/answer/6062777)

## Suporte

Problemas durante testes?
- **Email:** [suporte@vendamobile.app](mailto:suporte@vendamobile.app)
- **GitHub Issues:** [Reportar problema](https://github.com/renanduart3/venda-mobile-inteligente/issues)

---

## Notas Importantes

⚠️ **Atenção:**
- Sempre teste em ambiente de teste antes de produção
- Use contas de teste configuradas no Play Console
- Documentar todos os resultados de teste
- Validar com diferentes tipos de dispositivos Android

🔔 **Lembrete:**
- Testes de IAP podem levar algumas horas para refletir no Play Console
- Mudanças de configuração podem levar até 24h para propagar
- Sempre teste em versão de teste fechado antes de lançar para produção

---

**Bons testes!** 🚀
