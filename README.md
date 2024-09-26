Joao Pedro Gonzaga e Felipe Berthoux

Vamos simplificar a explicação de como funcionam as *media queries* no CSS de forma mais direta e fácil de entender.

### 1. **Print (Impressão)**
As *media queries* podem ajustar o design de uma página quando ela vai ser impressa. Por exemplo, quando alguém clicar para imprimir a página, você pode esconder elementos que não fazem sentido no papel, como menus ou imagens, e ajustar o tamanho do texto para algo mais legível.

**Exemplo:**
Quando a página é impressa, o menu e a galeria de imagens desaparecem, e o texto fica em preto com um tamanho de fonte apropriado para impressão. O CSS seria assim:
`@media print { header, nav, .gallery { display: none; } body { font-size: 12pt; color: black; } }`

### 2. **Larguras de Dispositivos Diferentes (Smartphone, Tablet, Desktop)**
As *media queries* também são usadas para ajustar o layout conforme o tamanho da tela muda. Você pode definir "pontos de interrupção" (ou *breakpoints*) para alterar o design em smartphones, tablets e computadores.

- **Para Smartphones**: Se a largura da tela for menor que 600px, como em um smartphone, o menu, que normalmente é horizontal, vira uma lista vertical. Além disso, o layout da galeria de imagens muda para duas colunas ao invés de quatro, e o texto em várias colunas vira uma única coluna.
`@media (max-width: 600px) { nav ul { flex-direction: column; align-items: center; } .gallery { grid-template-columns: repeat(2, 1fr); } .columns { column-count: 1; } }`

- **Para Tablets**: Entre 601px e 1024px, o layout muda de novo. Em um tablet, a galeria mostra três colunas, e o texto é distribuído em duas colunas, aproveitando mais o espaço da tela.
`@media (min-width: 601px) and (max-width: 1024px) { .gallery { grid-template-columns: repeat(3, 1fr); } .columns { column-count: 2; } }`

- **Para Desktops**: Quando a tela for maior que 1025px, como em um computador, a galeria volta a ter quatro colunas, e o texto é distribuído em três colunas, aproveitando ainda mais o espaço disponível.
`@media (min-width: 1025px) { .gallery { grid-template-columns: repeat(4, 1fr); } .columns { column-count: 3; } }`

### 3. **Disposição dos Dispositivos (Paisagem e Retrato)**
Além de ajustar para tamanhos de tela, você também pode usar *media queries* para detectar se o dispositivo está em modo **paisagem** (horizontal) ou **retrato** (vertical).

- **Paisagem**: Quando o dispositivo está na horizontal, como quando você deita o celular de lado, o fundo pode mudar de cor e o texto no menu pode ficar maior para preencher melhor o espaço.
`@media (orientation: landscape) { body { background-color: #f0f0f0; } nav ul li { font-size: 1.2rem; } }`

- **Retrato**: Quando o dispositivo está na vertical, o fundo volta para o branco e o texto no menu pode ficar um pouco menor para caber melhor na tela.
`@media (orientation: portrait) { body { background-color: #ffffff; } nav ul li { font-size: 1rem; } }`

### Resumo:
As *media queries* ajudam a deixar seu site "inteligente", adaptando o design para diferentes telas e dispositivos, como celulares, tablets e computadores. Elas também ajustam o layout conforme a orientação do dispositivo e até quando alguém quiser imprimir a página. Dessa forma, seu site sempre fica bonito e fácil de usar, não importa o jeito que é acessado.
