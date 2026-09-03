# LP-advogacia

# Aragão · Vilela — landing page de advocacia (fictícia)

## Marca fictícia
Aragão · Vilela — Sociedade de Advogados. São Paulo e Recife, desde 1998.
Posicionamento: "Litígio não se improvisa". Contencioso estratégico, arbitragem,
societário, sucessões, reestruturação, investigações internas.
Sócios: Helena Aragão, Rubens Vilela, Marina Bittencourt, Otávio Prado.

## Direção de arte
- Paleta: bone `#E9E3D6` · ink `#15140F` · sage `#3B4430` · vermelhão `#B33A1E` (acento) · greige `#8A8272`
- Tipos: Fraunces (display variável, tracking −0.035em) · Archivo (corpo) · IBM Plex Mono (labels/§)
- Conceito: "dossiê" — grid de 12 colunas visível em hairlines, seções numeradas §01–§08,
  blocos sangrando para fora da viewport, textura de grão SVG animado em multiply.

## Efeitos implementados
1. Reveal tipográfico por linha com máscara (`overflow:hidden` + `translateY`) e stagger via `--d`
2. Sticky pin nas áreas de atuação, com troca de imagem e numeração
3. Scroll horizontal pinado na seção de casos (fallback: swipe com scroll-snap no mobile)
4. Parallax por camadas nas fotos + máscara/saturação no hover dos retratos
5. Canvas generativo: malha de pontos de tinta que reage ao mouse no hero
6. Cursor custom com ring atrasado, botões magnéticos, underline animado
7. Palavras da declaração acendendo conforme o scroll
8. Nav que inverte para escuro sobre seções ink
Easing padrão `cubic-bezier(.16,1,.3,1)`, 400–800ms. Tudo desligado em `prefers-reduced-motion`.

## Obrigatório no rodapé (pedido do Caik)
- Crédito e link para https://github.com/CaikRian
- Aviso de que o escritório e todos os dados são fictícios / site de demonstração
- Aviso de que todas as fotografias foram geradas por IA

## Aprendizados reutilizáveis
- O sandbox não alcança fonts.googleapis.com — screenshots de verificação saem com fonte fallback.
- Artifact: o arquivo publicado não leva doctype/html/head/body; imagens precisam ser data URI.
  O `build.py` gera as duas versões (artifact + standalone) a partir do mesmo template.
- Cuidado recorrente: aplicar `grid-column` no filho em vez do wrapper quebra o layout silenciosamente.
