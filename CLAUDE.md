# She.codeAI — Landing Page

## Visão Geral do Projeto

Site institucional da **She.codeAI**, empresa de tecnologia liderada por mulheres, especializada em desenvolvimento de software, inteligência artificial, plataforma de performance para vendas online e soluções para vendas online.

O site é uma **single-page landing page** em HTML/CSS puro, sem frameworks ou dependências externas além das Google Fonts.

---

## Estrutura do Repositório

```
shecodeai-site/
├── index.html       ← toda a página (HTML + CSS inline)
├── robots.txt       ← permissões para bots (Google, IA, etc.)
├── sitemap.xml      ← mapa do site para indexação
├── llms.txt         ← descrição estruturada para modelos de IA
├── CLAUDE.md        ← este arquivo
├── SKILL.md         ← skill de manutenção do site
└── README.md        ← instruções de deploy
```

---

## Stack Técnica

- **HTML5 + CSS3** puro — sem frameworks, sem JavaScript de terceiros
- **Google Fonts**: `Inter` (corpo) + `Sora` (títulos e destaques)
- **Ícones**: SVG inline (sem biblioteca externa)
- **Responsivo**: breakpoint principal em `768px`
- **Sem build step** — editar e abrir direto no navegador

---

## Sistema de Design

### Paleta de Cores (variáveis CSS)

```css
--purple:       #7B5EA7   /* roxo principal */
--purple-light: #EDE7F6   /* roxo suave (fundos) */
--purple-mid:   #B39DDB   /* roxo médio (bordas, ícones) */
--pink:         #C2185B   /* pink principal */
--pink-light:   #FCE4EC   /* pink suave (fundos) */
--pink-mid:     #F48FB1   /* pink médio */
--dark:         #1C1B2E   /* fundo escuro (seções escuras) */
--text:         #2D2B3A   /* texto principal */
--text-muted:   #6B6880   /* texto secundário */
--bg:           #FAFAFA   /* fundo geral */
--white:        #FFFFFF
--border:       #E8E4F0   /* bordas suaves */
--grad:         linear-gradient(135deg, #7B5EA7 0%, #C2185B 100%)
```

### Tipografia

- **Títulos/destaques**: `font-family: 'Sora', sans-serif` — `font-weight: 700`
- **Corpo**: `font-family: 'Inter', sans-serif` — `font-weight: 400/500`
- **Labels de seção**: `font-size: 13px`, `text-transform: uppercase`, `letter-spacing: 0.1em`, cor `--purple`

---

## Seções da Página (em ordem)

| ID | Seção | Classe principal |
|----|-------|-----------------|
| `#inicio` | Hero | `.hero` |
| `#quem-somos` | Quem Somos | `.about` |
| `#servicos` | O Que Fazemos | `.services` |
| `#proposito` | Propósito (MVV) | `.mvv` |
| `#contato` | Fale Conosco | `.contact` |

---

## Informações de Contato

- **WhatsApp**: +55 11 97498-8612
- **Link WA**: `https://wa.me/5511974988612?text=Olá!%20Gostaria%20de%20saber%20mais%20sobre%20as%20soluções%20da%20Shecode.AI`

---

## Tom e Voz da Marca

- **Feminino** — sempre usar "parceira", "integradora", quando se referir a empresa SheCodeAI(nunca o masculino genérico)
- **Direto e confiante** — sem jargão excessivo, sem promessas milagrosas
- **Humano + tech** — equilíbrio entre acolhimento e precisão técnica
- **Nome da empresa**: sempre **She.codeAI** (S maiúsculo, ponto após "She", "code" minúsculo, AI maiúsculo)

---

## Diretrizes para Edições

### Ao alterar textos
- Manter sentence case nos títulos (não Title Case)
- Não repetir "liderança feminina" em múltiplas seções — já aparece nos Valores
- Sempre mencionar "She.codeAI" pelo nome em pelo menos uma seção de serviços

### Ao alterar cores
- Sempre usar as variáveis CSS definidas em `:root` — nunca hardcodar hex diretamente no HTML
- Gradiente padrão da marca: `var(--grad)` — roxo → pink

### Ao adicionar seções
- Seguir padrão: `.section-label` (label pequena) → `.section-title` (h2) → `.section-sub` (subtítulo opcional) → conteúdo
- Seções claras usam `background: var(--white)` ou `var(--bg)`
- Seções escuras usam `background: var(--dark)` (somente para destaque)

### Ícones
- Usar SVG inline com `stroke` — não usar emojis
- Tamanho padrão: `22x22px`, `stroke-width: 1.8`, `stroke-linecap: round`
- Cores: `stroke="#7B5EA7"` (roxo) ou `stroke="#C2185B"` (pink)

### Ao atualizar conteúdo do site

Sempre que fizer alterações relevantes no conteúdo do `index.html` (novos textos, seções, serviços), atualizar também o campo `<lastmod>` no `sitemap.xml` com a data atual no formato `YYYY-MM-DD`.

O `lastmod` é uma data **estática** — não se atualiza sozinha. O Google usa esse campo para saber quando o site foi modificado pela última vez.

---

## Deploy

O site está publicado via **GitHub Pages** em `shecodeai.com.br`.

Para publicar mudanças: basta fazer `git push origin main` — o GitHub Pages atualiza automaticamente em 1-2 minutos.

---

## Comandos Git

### Primeira vez (branch local é `master`, remoto espera `main`)

```powershell
git branch -m master main        # renomeia branch local
git push origin main             # sobe para o GitHub
```

### Atualizações do dia a dia

```powershell
git add index.html               # ou os arquivos alterados
git commit -m "descrição breve"
git push origin main
```

### Verificar estado antes de commitar

```powershell
git status    # arquivos modificados
git diff      # o que mudou linha a linha
```

### Criar e trabalhar em uma nova branch

```powershell
git checkout -b nome-da-branch   # cria e já entra na branch
git push origin nome-da-branch   # sobe a branch para o GitHub

# quando terminar, voltar para main e fazer merge
git checkout main
git merge nome-da-branch
git push origin main
```

---

## Rodar o projeto localmente

O site não tem build step — basta abrir o arquivo no navegador:

```powershell
# Windows — abre direto no navegador padrão
start index.html

# Ou arraste o arquivo index.html para qualquer aba do navegador
```

Para ver mudanças: salve o arquivo e recarregue a página (`F5` ou `Ctrl+R`).

