# LP-advogacia

# Aragão · Vilela — Landing page de advocacia

Landing page de página única para um escritório de advocacia **fictício**, feita como
peça de portfólio: HTML, CSS e JavaScript puros, em um arquivo só, sem framework,
sem build e sem dependência de runtime.

> **Aviso:** Aragão · Vilela não existe. Nome, sócios, casos, números, endereços e
> reconhecimentos são inventados. Todas as fotografias foram geradas por
> inteligência artificial — as pessoas retratadas não existem.

**[Ver ao vivo →](https://caikrian.github.io/aragao-vilela-landing/)** <!-- ajuste a URL depois de publicar -->

<!-- Sugestão: adicione um print em docs/preview.png e descomente a linha abaixo
![Preview da landing page](docs/preview.png)
-->

---

## Sobre o projeto

O briefing era simples de enunciar e difícil de executar: uma página que parecesse
saída de um estúdio de design, não de um gerador de templates. Isso significou
recusar os atalhos de sempre — gradiente roxo-azul, hero centralizado com badge,
três cards iguais com ícone, `border-radius` em tudo, Inter como fonte de título.

O resultado é uma página construída como um dossiê: grid de 12 colunas visível em
linhas finas, seções numeradas como autos processuais (§01 a §08), textura de grão
sobre todos os fundos e blocos sangrando para fora da viewport.

## Destaques técnicos

**Movimento conduzido por scroll**

- Revelação tipográfica linha a linha com máscara (`overflow: hidden` + `translateY`), com atraso escalonado por variável CSS
- Seção de áreas de atuação com *sticky pin*: a imagem e a numeração trocam conforme a coluna de texto rola
- Seção de casos com scroll horizontal fixado, que vira swipe com `scroll-snap` no mobile
- Parallax por camadas nas fotografias, calculado dentro de um único `requestAnimationFrame`
- Texto da declaração acendendo palavra por palavra conforme entra na tela

**Interação**

- Cursor customizado com anel de inércia (lerp), que cresce sobre elementos interativos
- Botões magnéticos, que se deslocam na direção do ponteiro
- Barra de navegação que se inverte automaticamente ao passar sobre seções escuras
- Micro-interações com easing próprio `cubic-bezier(.16, 1, .3, 1)` e duração de 400–800 ms

**Elemento generativo**

- Canvas 2D no hero com uma malha de pontos de tinta que se abre e ganha cor conforme
  o ponteiro se aproxima, com amortecimento e retorno à posição de origem

**Acessibilidade e performance**

- `prefers-reduced-motion` desliga cursor, parallax, scroll horizontal, canvas e revelações
- Foco visível, HTML semântico, `alt` descritivo em todas as imagens, contraste verificado
- Anima apenas `transform` e `opacity`; nenhuma biblioteca externa
- Responsivo por reformulação de layout, não por empilhamento — cada seção tem um
  comportamento próprio no mobile

## Stack

| Camada | O que foi usado |
| --- | --- |
| Marcação | HTML5 semântico |
| Estilo | CSS puro — custom properties, Grid, `clamp()`, `aspect-ratio`, `position: sticky` |
| Comportamento | JavaScript vanilla — `IntersectionObserver`, Canvas 2D, `requestAnimationFrame` |
| Tipografia | Fraunces (display variável), Archivo (corpo), IBM Plex Mono (dados) |
| Textura | Grão gerado por `feTurbulence` em SVG inline, aplicado em `mix-blend-mode: multiply` |
| Dependências | Nenhuma |

## Direção de arte

Paleta com um neutro dominante inesperado e um único acento de alta saturação,
usado com parcimônia.

| Cor | Hex | Uso |
| --- | --- | --- |
| Bone | `#E9E3D6` | Fundo dominante |
| Ink | `#15140F` | Texto e seções escuras |
| Sage | `#3B4430` | Banda de declaração |
| Vermelhão | `#B33A1E` | Acento — cerca de 2% da tela |
| Greige | `#8A8272` | Texto de apoio e metadados |

Títulos em Fraunces com `clamp()` de até 11,6vw e *tracking* negativo de −0.035em.
Corpo em Archivo. Eyebrows, numeração de seções e dados em IBM Plex Mono, em caixa
alta com `letter-spacing` aberto.

## Estrutura

```
.
├── index.html      # a página inteira — marcação, estilo, script e imagens em base64
└── README.md
```

As dez fotografias estão embutidas como data URIs. O arquivo pesa cerca de 1,4 MB e
funciona offline; a única requisição externa é o Google Fonts.

## Licença

Código sob licença MIT — use, adapte e aprenda à vontade.

As fotografias foram geradas por IA e acompanham o projeto apenas para fins de
demonstração. Os textos descrevem um escritório fictício e não constituem oferta de
serviços jurídicos nem orientação legal.

---

Projeto e código por **[Caik Rian](https://github.com/CaikRian)**.
