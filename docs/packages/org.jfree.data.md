# Pacote `org.jfree.data`

Responsabilidade

- Modelos e utilitários de dados que alimentam plots: interfaces `Dataset` e implementações concretas (`TimeSeries`, `XYSeries`, `DefaultXYZDataset`, `CategoryDataset`, etc.).

Principais classes/subpacotes

- `time` — `TimeSeries`, `TimeSeriesCollection`, `RegularTimePeriod` e utilitários de manipulação temporal.
- `xy` — `XYSeries`, `XYDataset` e implementações variadas.
- `category` — datasets para gráficos de categoria.
- `statistics` — classes para cálculos estatísticos e conjuntos especializados (histogramas, box-and-whisker).

Fluxos de execução

1. Aplicação popula/atualiza `Dataset`.
2. `Dataset` emite `DatasetChangeEvent` para listeners (plots, renderers) ao mudar.
3. `Plot` e `Renderer` consomem dados para calcular bounds e desenhar.

Pontos críticos

- Consistência de eventos: assegurar que datasets disparem eventos corretamente após mutações.
- Memória e versão dos dados: grandes séries temporais exigem políticas de pruning/sampling.
- Conversões entre tipos (ex.: `Number` → double) com atenção a `NaN` e `null`.

Sugestões de documentação

- Documentar contratos de notificação (`fireDatasetChanged()`), semântica de cópia/clonagem e thread-safety esperada.
- Exemplos de melhores práticas para datasets de long-lived/alta-velocidade (decimation, janela deslizante).