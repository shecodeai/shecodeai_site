# Roadmap de Melhorias — Shecode.AI

Baseado na análise UX/UI e SEO do site. As tarefas estão ordenadas por impacto e dependência.

Legenda: `[ ]` pendente · `[x]` concluído · `[🔑]` precisa de info sua primeiro

---

## Sprint 1 — SEO Técnico In-Page (sem dependência, ~1h)

Tudo dentro do `index.html`, pode executar agora.

- [x] Adicionar `<meta name="description">` com descrição otimizada
- [x] Adicionar `<link rel="canonical" href="https://shecodeai.com.br/"/>` 
- [x] Adicionar `<meta name="robots" content="index, follow"/>`
- [x] Adicionar Open Graph tags (`og:title`, `og:description`, `og:url`, `og:image`, `og:type`, `og:locale`, `og:site_name`)
- [x] Adicionar Twitter Card tags (`twitter:card`, `twitter:title`, `twitter:description`, `twitter:image`)
- [x] Adicionar JSON-LD Schema.org `Organization` antes do `</body>`
- [x] Corrigir alt text das imagens Amazon: `alt="Logo Amazon — Parceira Integradora Oficial"`
- [x] Adicionar `rel="preconnect"` para Google Fonts (otimização de carregamento)
- [x] Formulário: adicionar `required` nos campos nome, email e mensagem

---

## Sprint 2 — Arquivos de SEO (sem dependência, ~20 min)

Novos arquivos na raiz do repositório.

- [x] Criar `robots.txt` com `Allow: /` e link para o sitemap
- [x] Criar `sitemap.xml` com a URL principal do site
- [ ] Verificar que o GitHub Pages está servindo esses arquivos corretamente

---

## Sprint 3 — Imagem OG (🔑 precisa de você, ~20 min)

A imagem OG é o preview que aparece quando o link é compartilhado no WhatsApp, LinkedIn, etc.

### O que você precisa fazer:
> **🔑 Criar `images/og-image.png`** (1200 × 630 px)  
> Sugestão: usar [Canva](https://www.canva.com) ou Figma  
> Conteúdo: gradiente roxo → pink da marca + logo + tagline "Tecnologia que Transforma"  
> Salvar como PNG e colocar em `images/og-image.png`

- [ ] 🔑 **VOCÊ:** Criar og-image.png (1200×630px) e salvar em `images/`
- [ ] Após criar a imagem: adicionar as duas linhas abaixo no `<head>` do index.html:
  ```html
  <meta property="og:image" content="https://shecodeai.com.br/images/og-image.png"/>
  <meta name="twitter:image" content="https://shecodeai.com.br/images/og-image.png"/>
  ```

---

## Sprint 4 — Google Search Console (🔑 precisa de você, ~20 min)

Necessário para monitorar indexação, erros e performance de busca.

### O que você precisa fazer:
> **🔑 Acessar o [Google Search Console](https://search.google.com/search-console)**  
> Adicionar propriedade: `https://shecodeai.com.br`  
> Escolher verificação por DNS (recomendado via GitHub Pages) ou por meta tag  
> Após verificar: Submeter sitemap em "Sitemaps" → `https://shecodeai.com.br/sitemap.xml`

- [ ] 🔑 **VOCÊ:** Verificar propriedade no Google Search Console
- [ ] 🔑 **VOCÊ:** Submeter sitemap no Search Console
- [ ] (Opcional) 🔑 **VOCÊ:** Decidir se quer Google Analytics 4 — dá dados de tráfego mas adiciona um script externo. Pode medir resultados do SEO.

---

## Sprint 5 — Redes Sociais no Footer (🔑 precisa de você, ~30 min)

O footer atual só tem navegação. Adicionar contato e redes sociais aumenta confiança.

### O que você precisa informar:
> **🔑 Me informe:**  
> - URL do LinkedIn da Shecode.AI (se existir)  
> - URL do Instagram da Shecode.AI (se existir)  
> - Alguma outra rede social ativa?

- [ ] 🔑 **VOCÊ:** Informar as URLs das redes sociais
- [ ] Após receber: atualizar footer com ícones SVG das redes + e-mail de contato + WhatsApp
- [ ] Adicionar as redes no JSON-LD `sameAs` do Schema.org (Sprint 1)
- [x] Atualizar copyright: trocar `2025` por JS dinâmico

---

## Sprint 6 — UX: Depoimentos (🔑 aguardando conteúdo, ~1h)

**Status: aguardando você acessar os clientes para coletar depoimentos.**

### O que você precisa coletar:
> **🔑 Para cada depoimento, coletar:**  
> - Texto do depoimento (2-4 linhas)  
> - Nome da pessoa  
> - Cargo e empresa  
> - (Opcional) foto da pessoa  
> - Resultado específico se possível ("aumentamos X%", "em Y meses")

- [ ] 🔑 **VOCÊ:** Coletar 3 depoimentos de clientes reais
- [ ] Após receber: criar seção `#depoimentos` entre Serviços e Propósito (mockup já definido)

---

## Sprint 7 — Acessibilidade e Ajustes Finos (~30 min)

Pode fazer a qualquer momento, sem dependência.

- [x] Adicionar skip link "Ir para o conteúdo principal" (primeiro elemento do body)
- [x] Adicionar `aria-expanded="false"` no botão hamburger, atualizado via JS ao abrir/fechar
- [x] Adicionar `aria-hidden="true"` nos blobs decorativos do hero
- [ ] Aumentar fontes de 11px para 12px em `.hss-label`, `.vc-label`, `.service-badge`
- [ ] Adicionar `@media (max-width: 1024px)` para otimizar layout em tablets

---

## Backlog — Sem Prazo Definido

- [ ] Página de política de privacidade (se for adicionar Analytics)
- [ ] Blog ou seção de conteúdo (aumenta SEO orgânico a longo prazo)
- [ ] Otimização de imagens PNG para WebP (melhora performance)
- [ ] Lazy loading nas imagens

---

## Checklist de Verificação Pós-Implementação

Após cada sprint, verificar:

| Ferramenta | O que verificar |
|---|---|
| [opengraph.xyz](https://www.opengraph.xyz) | Preview do link no WhatsApp/LinkedIn |
| [schema.org/validator](https://validator.schema.org) | Schema.org sem erros |
| Google Search Console | Indexação e erros de rastreamento |
| Chrome DevTools → Lighthouse | Score de SEO e Performance |
| axe DevTools (extensão Chrome) | Erros de acessibilidade |
