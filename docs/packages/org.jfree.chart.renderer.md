# Pacote `org.jfree.chart.renderer`

Responsabilidade

- Contém renderers que traduem valores do `Dataset` em chamadas de desenho (`Graphics2D`): formas, linhas, preenchimentos, cores e labels.

Principais classes

- `AbstractRenderer` / `AbstractXYItemRenderer` / `AbstractCategoryItemRenderer` — classes base com lógica comum (listas de paint, stroke, shapes por série).
- Renderers concretos: `BarRenderer`, `LineAndShapeRenderer`, `XYBarRenderer`, `BoxAndWhiskerRenderer`, `WaferMapRenderer`, `FastScatterPlot`.

Fluxos de execução

1. `Plot` configura e chama `Renderer.drawItem(...)` (ou métodos equivalentes) por item/serie.
2. O `Renderer` consulta o `Dataset` e faz transformações de coordenadas antes de desenhar.
3. Valores para legendas, tooltips e entidades podem ser criados pelo renderer.

Pontos críticos

- Loop de desenho por item é o hot-path — evitar alocações, preferir buffers reutilizáveis.
- Gerenciamento de visibilidade de séries/itens (flags `seriesVisible`, `itemVisible`).
- Consistência entre renderers e `LegendItem` gerado (indices/keys corretos).

Sugestões de documentação

- Checklist para implementar novo `Renderer` (contratos, quando notificar listeners, criação de `RendererState`).
- Padrões de otimização (evitar novos objetos por item; usar `FloatBuffer`/primitivos quando aplicável).