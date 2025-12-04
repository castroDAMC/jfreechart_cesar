# Pacote `org.jfree.chart`

Responsabilidade

- Núcleo de alto nível da API de gráficos — classes que representam um gráfico completo (`JFreeChart`), painéis de exibição (`ChartPanel`), fábricas (`ChartFactory`) e temas (`StandardChartTheme`).

Principais classes

- `JFreeChart` — modelo principal que agrega `Plot`, títulos, legendas e configurações globais.
- `ChartPanel` — componente Swing que exibe um `JFreeChart`, lida com eventos de input (zoom, pan) e exportação.
- `ChartFactory` — métodos utilitários para construir instâncias prontas de `JFreeChart` (pie, bar, xy, etc.).
- `ChartColor`, `ChartElement` — utilitários e interfaces de suporte.

Fluxos de execução

1. Aplicação cria/obtém um `Dataset` e chama `ChartFactory` ou constrói manualmente um `JFreeChart`.
2. `JFreeChart` encapsula `Plot` e delega operação de desenho ao `Plot`.
3. `ChartPanel` recebe repaint e delega para `JFreeChart.draw(Graphics2D, Rectangle)`.

Pontos críticos

- `ChartPanel` e a integração com o EDT (Swing): operações de UI devem ocorrer no *Event Dispatch Thread*.
- Serialização de `JFreeChart` (muitos componentes implementam `Serializable`) — mudanças nas classes podem quebrar serialização.
- Configuração de temas e internacionalização: bundles de recursos e `StandardChartTheme` impactam o visual global.

Sugestões de documentação

- Adicionar exemplos de uso curto em `JFreeChart` e `ChartPanel` (criar um gráfico simples com `ChartFactory`).
- Documentar requisitos de thread para métodos públicos que alteram o estado do gráfico.