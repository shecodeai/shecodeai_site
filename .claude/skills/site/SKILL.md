---
name: site
description: >
  Use esta skill sempre que precisar editar, atualizar ou expandir o site da Shecode.AI
  (index.html). Cobre alterações de texto, cores, seções, componentes, novos serviços,
  depoimentos, imagens, formulários e qualquer mudança no layout ou conteúdo da landing page.
  Acione também para dúvidas sobre a estrutura do projeto, padrões de design da marca,
  ou para criar novas seções seguindo a identidade visual existente.
---

# Skill: Manutenção do Site Shecode.AI

## Contexto

Este projeto é uma **landing page HTML/CSS puro** sem build step.  
Toda a lógica de estilo está em `<style>` inline no `index.html`.  
Leia sempre o `CLAUDE.md` do repositório antes de qualquer edição para garantir consistência.

---

## Fluxo de Edição

1. **Leia o `CLAUDE.md`** para entender a paleta, tom de voz e diretrizes
2. **Identifique o ID da seção** alvo (ver tabela em CLAUDE.md)
3. **Edite somente o necessário** — evite refatorar CSS não relacionado
4. **Valide o feminino**: parceira, integradora
5. **Não use emojis como ícones** — use SVG inline
6. **Sempre use variáveis CSS** (`var(--purple)`, `var(--grad)`, etc.) — nunca hex direto no HTML

---

## Padrões de Componentes

### Nova seção padrão

```html
<section class="NOME-CLASSE" id="ANCHOR">
  <div class="section-inner">
    <div class="section-label">Label pequena em roxo</div>
    <h2 class="section-title">Título da seção</h2>
    <p class="section-sub">Subtítulo opcional, máx 2 linhas.</p>
    <!-- conteúdo -->
  </div>
</section>
```

CSS mínimo para nova seção:
```css
.NOME-CLASSE { background: var(--white); } /* ou var(--bg) ou var(--dark) */
```

### Card de serviço

```html
<div class="service-card">
  <div class="service-icon si-purple">
    <svg width="22" height="22" viewBox="0 0 24 24" fill="none"
         stroke="#7B5EA7" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round">
      <!-- path do ícone -->
    </svg>
  </div>
  <h3>Título do serviço</h3>
  <p>Descrição curta e direta.</p>
  <span class="service-badge">Badge</span>
</div>
```

### Badge/pill de valor

```html
<span class="vpill">Nome do valor</span>       <!-- seção escura -->
<span class="tag">Nome da tag</span>            <!-- seção clara -->
<span class="hero-pill">Pill do hero</span>     <!-- hero, roxo -->
<span class="hero-pill pink">Pill pink</span>   <!-- hero, pink -->
```

---

## Checklist para Qualquer Edição

- [ ] Texto em sentence case (não Title Case)
- [ ] Gênero feminino em toda referência à empresa
- [ ] Nome "Shecode.AI" grafado corretamente (com ponto)
- [ ] Ícones em SVG inline (não emoji)
- [ ] Cores via variáveis CSS (não hex hardcoded)
- [ ] Testar responsivo (breakpoint 768px)
- [ ] Link WhatsApp preservado: `https://wa.me/5511974988612`

---

## Adicionando Novos Itens ao Formulário de Contato

Localize o `<select id="assunto">` e adicione dentro:
```html
<option>Nome da nova opção</option>
```

Não incluir serviços que são ferramentas internas (ex: IA, automação) — apenas o que o cliente compra.

---

## Adicionando Depoimentos (quando houver)

Criar seção `.testimonials` entre `#servicos` e `#proposito`:

```html
<section class="testimonials" id="depoimentos">
  <div class="section-inner">
    <div class="section-label">O que dizem sobre nós</div>
    <h2 class="section-title">Resultados reais,<br/>palavras reais</h2>
    <div class="testimonials-grid">
      <div class="testimonial-card">
        <p class="testimonial-text">"Depoimento aqui."</p>
        <div class="testimonial-author">
          <strong>Nome</strong>
          <span>Cargo, Empresa</span>
        </div>
      </div>
    </div>
  </div>
</section>
```

CSS sugerido:
```css
.testimonials { background: var(--bg); }
.testimonials-grid { display: grid; grid-template-columns: repeat(3,1fr); gap: 1.25rem; }
.testimonial-card { background: var(--white); border: 1px solid var(--border); border-radius: 16px; padding: 1.5rem; }
.testimonial-text { font-size: 15px; color: var(--text-muted); line-height: 1.8; margin-bottom: 1rem; font-style: italic; }
.testimonial-author strong { display: block; font-size: 14px; color: var(--dark); }
.testimonial-author span { font-size: 13px; color: var(--text-muted); }
```

