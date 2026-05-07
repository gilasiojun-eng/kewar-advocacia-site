# GUIA COMPLETO — KEWAR RAMOS ADVOCACIA
## Como subir o site na Hostinger + Respostas às suas dúvidas

---

## PARTE 1 — PREPARAÇÃO (5 minutos)

### Arquivos que você recebeu:
```
index.html          → Página inicial
previdenciario.html → Página Previdenciário  
saude.html          → Página Saúde
aereo.html          → Página Aéreo
```

### Antes de subir, faça ESTAS substituições nos arquivos:

Abra cada .html em um editor (Bloco de Notas serve) e substitua:

| O que está                    | O que colocar              |
|-------------------------------|---------------------------|
| `SEU_NUMERO`                  | Seu número com DDD, sem espaço: ex: `5511999999999` |
| `OAB/XX XXXXXX`               | Seu número da OAB         |
| `contato@kewaneramosadvocacia.com` | Seu e-mail real       |
| `Seu endereço completo aqui`  | Endereço do escritório    |
| `LINK_GOOGLE_MEU_NEGOCIO`     | Link do seu perfil Google |

---

## PARTE 2 — UPLOAD NA HOSTINGER (10 minutos)

### Passo a Passo:

**1. Acesse o painel Hostinger**
- Acesse: hpanel.hostinger.com
- Entre com seu e-mail e senha

**2. Vá em "Gerenciador de Arquivos"**
- No painel, clique em "Sites"
- Clique no seu domínio (kewaneramosadvocacia.com)
- Clique em "Gerenciador de Arquivos"

**3. Entre na pasta public_html**
- Você verá uma pasta chamada `public_html`
- Clique duas vezes para entrar nela
- Esta é a pasta raiz do seu site

**4. Faça upload dos arquivos**
- Clique no botão "Carregar arquivos" (ícone de upload)
- Selecione TODOS os 4 arquivos .html de uma vez
- Aguarde o upload completar

**5. Verifique o index.html**
- O arquivo `index.html` deve estar na raiz de `public_html`
- Não coloque em subpastas

**6. Teste imediatamente**
- Abra o navegador
- Acesse: kewaneramosadvocacia.com
- O site deve carregar em até 5 minutos

---

## PARTE 3 — SUBDOMÍNIOS PARA LANDING PAGES

Para criar LPs separadas (ex: previdenciario.kewaneramosadvocacia.com):

**1. No painel Hostinger:**
- Vá em "Sites" → seu domínio
- Clique em "Subdomínios"
- Clique em "Criar subdomínio"

**2. Crie cada subdomínio:**
```
previdenciario → aponta para /public_html/lp-previdenciario/
saude          → aponta para /public_html/lp-saude/
aereo          → aponta para /public_html/lp-aereo/
```

**3. Crie as pastas no Gerenciador de Arquivos:**
- Dentro de public_html, crie as pastas: lp-previdenciario, lp-saude, lp-aereo
- Coloque o index.html de cada LP dentro da pasta correspondente

---

## PARTE 4 — PIXEL META (FACEBOOK) + GTM

### Instalação via GTM (modo mais fácil):

**Passo 1: Criar conta no Google Tag Manager**
- Acesse: tagmanager.google.com
- Crie uma conta com o nome do escritório
- Crie um "Container" para o site
- Copie os 2 trechos de código que o GTM vai fornecer

**Passo 2: Adicionar GTM nos arquivos HTML**
- Abra cada arquivo .html
- Cole o primeiro trecho logo após a tag `<head>` (já tem o marcador nos arquivos)
- Cole o segundo trecho logo após `<body>`

O GTM já tem espaço reservado. Procure no código:
```html
<!-- GTM Head: cole aqui o snippet do Google Tag Manager -->
<!-- GTM Body: cole aqui o snippet noscript do GTM -->
```

**Passo 3: Adicionar Pixel Meta via GTM**
- No GTM, vá em Tags → Nova Tag
- Escolha "Meta Pixel" (ou Custom HTML)
- Cole seu ID do Pixel Meta
- Configure para disparar em "All Pages"
- Publique o container

**Passo 4: Google Analytics (GA4) via GTM**
- No GTM, nova Tag → "Google Analytics: GA4 Configuration"
- Insira o ID de medição (G-XXXXXXXXXX)
- Dispara em All Pages
- Publique

---

## PARTE 5 — FORMULÁRIO DE CONTATO

### Opção Gratuita: Formspree
1. Acesse: formspree.io
2. Crie conta gratuita
3. Crie um formulário
4. Copie o endpoint gerado (ex: https://formspree.io/f/XXXXXXXX)
5. Nos arquivos HTML, substitua:
   ```html
   action="#"
   ```
   Por:
   ```html
   action="https://formspree.io/f/SEU_CODIGO"
   ```
   E remova o JavaScript de submit falso no final do index.html

### Opção com CRM: RD Station
- Crie conta em rdstation.com.br (tem plano grátis)
- Crie um formulário dentro do RD
- Cole o código embed no lugar do formulário atual

---

## PARTE 6 — AVALIAÇÕES DO GOOGLE

### RESPOSTA À SUA DÚVIDA:

**Pode puxar avaliações do Google? SIM, mas com limitações.**

**Forma mais fácil (sem API):**
Copie o texto das avaliações reais do seu Google Meu Negócio e cole manualmente nos cards de avaliação que já estão nos arquivos HTML. Isso é 100% permitido.

**Como fazer:**
1. Abra seu Google Meu Negócio
2. Vá em Avaliações
3. Copie o nome (pode usar só o primeiro nome + inicial) e o texto
4. Cole no HTML onde está "Maria S.", "João P.", etc.

**Cuidado com a OAB:**
- Não use avaliações como argumento de venda
- Não exiba avaliações que prometam resultado
- Adicione o aviso que já está no código: "Avaliações publicadas com consentimento"
- Prefira manter só a nota média e o link para o Google

**API do Google (mais avançado):**
Existe a Google Places API que puxa avaliações em tempo real, mas:
- Exige conta de desenvolvedor Google
- Tem custo após certo volume
- Para implementar, precisaria de um arquivo JavaScript adicional
- Posso criar isso para você se quiser — me peça

---

## PARTE 7 — VERCEL + GITHUB vs. HOSTINGER

### RESPOSTA À SUA DÚVIDA:

**Vercel + GitHub faz sentido para o seu caso?**

| Critério | Hostinger | Vercel + GitHub |
|----------|-----------|-----------------|
| Facilidade para leigo | ✅ Muito fácil | ❌ Requer conhecimento de Git |
| SEO | ✅ Excelente (servidor BR) | ✅ Excelente |
| Velocidade | ✅ Ótima (servidor SP) | ✅ Ótima (CDN global) |
| Custo | ✅ Já pago | ✅ Gratuito para sites estáticos |
| Subdomínios | ✅ Painel fácil | ⚠️ Requer configuração DNS |
| Integração CRM | ✅ Qualquer um | ✅ Qualquer um |
| WordPress | ✅ Direto no painel | ❌ Não roda WordPress |

**RECOMENDAÇÃO PARA SEO:**
Vercel e GitHub Pages performam MUITO BEM no Google. A Vercel usa CDN global e HTTPS automático — isso é ótimo para Core Web Vitals.

**Mas para você, que é leigo:**
→ Continue na Hostinger por enquanto. Os sites HTML que você recebeu vão funcionar perfeitamente lá.
→ Quando quiser escalar (WordPress, blog, múltiplos sites), avalie migrar para Vercel.

---

## PARTE 8 — SEO PÓS-UPLOAD

### Faça isso logo após subir o site:

**1. Google Search Console**
- Acesse: search.google.com/search-console
- Adicione seu domínio
- Verifique a propriedade (método HTML — baixe o arquivo e coloque em public_html)
- Submeta o sitemap: kewaneramosadvocacia.com/sitemap.xml

**2. Google Business Profile**
- Acesse: business.google.com
- Complete TODOS os campos
- Adicione fotos do escritório (mínimo 10)
- Descreva as áreas de atuação nos campos disponíveis

**3. Sitemap (crie este arquivo)**
Crie um arquivo `sitemap.xml` em public_html com este conteúdo:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url><loc>https://www.kewaneramosadvocacia.com/</loc><priority>1.0</priority></url>
  <url><loc>https://www.kewaneramosadvocacia.com/previdenciario.html</loc><priority>0.9</priority></url>
  <url><loc>https://www.kewaneramosadvocacia.com/saude.html</loc><priority>0.9</priority></url>
  <url><loc>https://www.kewaneramosadvocacia.com/aereo.html</loc><priority>0.9</priority></url>
</urlset>
```

**4. Robots.txt**
Crie um arquivo `robots.txt` em public_html:
```
User-agent: *
Allow: /
Sitemap: https://www.kewaneramosadvocacia.com/sitemap.xml
```

---

## RESUMO: O QUE FAZER PRIMEIRO

1. ✅ Faça as substituições (número WhatsApp, OAB, endereço)
2. ✅ Faça upload dos 4 arquivos no public_html da Hostinger
3. ✅ Crie o sitemap.xml e o robots.txt
4. ✅ Cadastre o Google Business Profile completo
5. ✅ Crie o Google Search Console e submeta o sitemap
6. ✅ Configure o GTM (pode levar 1-2h, mas vale muito)
7. ✅ Atualize as avaliações com os dados reais do seu Google

---

**Dúvidas? Me pergunte a qualquer momento.**
