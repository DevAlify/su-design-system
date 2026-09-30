# su-design-system

Design system da Sypher Way & Umbra Ltda. Este repositório documenta o
sistema visual do backoffice Umbra **como ele está hoje em produção**
("Umbra, estado atual") — não é o rebrand SyphreX, que fica para uma
sessão futura (Linear UMB-53).

## Conteúdo

- **`index.html`** — a página de referência viva. É a mesma página
  mostrada dentro da seção Docs do backoffice (via `<iframe
  sandbox="allow-scripts">`). Abra o arquivo direto no navegador, sem
  build e sem dependências.
- **`tokens.css`** — os custom properties de cor, tipografia,
  espaçamento, raio e sombra, extraídos de `backoffice/src/app/ui.css`
  e `backoffice/DESIGN.md`. Cobre o tema escuro (padrão), o tema claro
  e o tema "Sistema" (segue o sistema operacional via
  `prefers-color-scheme`), exatamente como o backoffice faz.

## Como usar `tokens.css`

```html
<link rel="stylesheet" href="tokens.css">
<style>
  .meu-botao{ background:var(--text); color:var(--ink-inv); border-radius:var(--radius-md); }
</style>
```

Tema escuro é o padrão, sem precisar de nenhum atributo. Para forçar um
tema, escreva `data-theme="dark"` ou `data-theme="light"` no `<html>`;
para seguir o sistema operacional, não escreva `data-theme` nenhum.

## Sem build

Sem framework, sem dependência, sem passo de build. `index.html` só
carrega `tokens.css` (relativo) e a fonte Geist via Google Fonts.
