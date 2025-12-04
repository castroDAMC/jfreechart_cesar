# Pacote `org.jfree.chart.plot`

Responsabilidade

- Implementações dos diferentes tipos de plots (ex.: `XYPlot`, `CategoryPlot`, `PolarPlot`, `FastScatterPlot`) que coordenam eixos, áreas de desenho e renderers.

Principais classes

- `Plot` (classe base) — layout, espaço de dados e ciclo de vida do plot.
- `XYPlot`, `CategoryPlot`, `PolarPlot` — implementações concretas para tipos de dados específicos.
- `PlotRenderingInfo`, `PlotState`, `PlotOrientation` — estruturas auxiliares para a etapa de desenho e para comunicação de metadados.

Fluxos de execução

1. `Plot` recebe contexto de desenho e configura `Renderer`/eixos.
2. Para cada dataset associado, o `Plot` calcula bounds e chama o(s) `Renderer(s)` para desenhar os itens.
3. `Plot` produz `PlotRenderingInfo` usado para gerar entidades (interação) e tooltips/URL.

Pontos críticos

- Coordenação entre múltiplos datasets/axes (mapeamento de dataset→axis).
- Performance na iteração por itens (renderers devem minimizar alocações em loops críticos).
- Precisão de cálculos de bounds e transformações entre coordenadas de dados e pixels.

Sugestões de documentação

- Exemplos de uso para `CombinedDomainXYPlot` / `CombinedRangeXYPlot`.
- Explicar as etapas de `draw()` do `Plot` e como implementar um `Renderer` eficiente.