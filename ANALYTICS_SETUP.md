# 📊 Configuração do Google Analytics

Este projeto está configurado para usar o **Google Analytics 4 (GA4)**, uma ferramenta gratuita do Google para rastrear visitantes e acessos à sua página.

## Como configurar

### 1. Criar conta no Google Analytics

1. Acesse [analytics.google.com](https://analytics.google.com)
2. Faça login com sua conta Google
3. Clique em **"Começar a medir"** ou **"Criar propriedade"**
4. Preencha as informações:
   - **Nome da conta**: ex: "Checkpoint QA"
   - **Nome da propriedade**: ex: "Checkpoint QA - Site"
   - **Fuso horário**: Selecione seu país e moeda
5. Configure os detalhes da empresa (opcional)
6. Aceite os termos de serviço

### 2. Configurar coleta de dados para Web

1. Selecione **"Web"** como plataforma
2. Configure o fluxo de dados:
   - **URL do site**: `https://glaycongx.github.io/CheckpointQA/`
   - **Nome do fluxo**: "Checkpoint QA - Web"
3. Clique em **"Criar fluxo"**

### 3. Copiar o ID de medição

Após criar o fluxo, você verá um **ID de medição** no formato `G-XXXXXXXXXX` (exemplo: `G-ABC123DEF4`).

### 4. Adicionar o ID ao projeto

Abra o arquivo `index.html` e substitua **todas as ocorrências** de `G-XXXXXXXXXX` pelo seu ID real:

```html
<!-- ANTES -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>

<!-- DEPOIS (exemplo com ID G-ABC123DEF4) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-ABC123DEF4"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-ABC123DEF4');
</script>
```

### 5. Fazer deploy

Após substituir o ID, faça commit e push das alterações para que o site no GitHub Pages seja atualizado com o código de analytics.

### 6. Verificar funcionamento

1. Acesse seu site após o deploy
2. Volte ao Google Analytics
3. Vá em **Relatórios → Tempo real**
4. Você deve ver sua visita sendo registrada em tempo real

## O que o Google Analytics rastreia

Com a configuração padrão, o GA4 rastreia automaticamente:

- ✅ **Visualizações de página**: quantas vezes cada página foi acessada
- ✅ **Usuários únicos**: quantas pessoas diferentes visitaram o site
- ✅ **Sessões**: quantas visitas o site teve
- ✅ **Origem do tráfego**: de onde os visitantes vieram (Google, redes sociais, direto, etc.)
- ✅ **Dispositivos**: desktop, mobile, tablet
- ✅ **Localização geográfica**: país e cidade dos visitantes
- ✅ **Tempo de permanência**: quanto tempo as pessoas ficam no site

## Principais relatórios

Depois de alguns dias com dados, você pode acessar:

- **Relatórios → Tempo real**: visitantes ativos no momento
- **Relatórios → Aquisição**: de onde vêm os visitantes
- **Relatórios → Engajamento**: páginas mais visitadas
- **Relatórios → Dados demográficos**: idade, gênero, localização

## Privacidade

O Google Analytics é compatível com LGPD/GDPR, mas você pode adicionar um aviso de cookies se desejar ser mais transparente com os usuários.

## Alternativas gratuitas

Se preferir uma solução mais focada em privacidade:

- **Plausible Analytics**: mais simples e focado em privacidade (tem versão paga, mas com trial gratuito)
- **Umami**: open source e auto-hospedável (gratuito)
- **Simple Analytics**: pago, mas com foco em privacidade

---

**Dúvidas?** Consulte a [documentação oficial do Google Analytics](https://support.google.com/analytics/answer/9304153).
