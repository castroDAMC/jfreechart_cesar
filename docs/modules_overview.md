# Visão Geral dos Módulos e Pacotes

Este documento apresenta uma visão condensada dos principais pacotes do repositório e seu papel funcional.

Principais pacotes

- `org.jfree.chart` — Núcleo da API de gráficos.
  - Contém classes como `JFreeChart`, `ChartPanel`, `ChartFactory` e utilitários de alto nível.
  - Responsabilidade: construir, configurar e orquestrar o desenho dos charts (titulos, subtitles, legendas, overlays).

- `org.jfree.chart.plot` — Implementações de plots (e.g., `XYPlot`, `CategoryPlot`, `PolarPlot`).
  - Responsabilidade: calcular áreas de desenho, eixos, layout dos elementos do gráfico e coordenar renderers.
  - Fluxo típico: recebe `Dataset` → calcula escalas/intervalos → delega a renderers o desenho dos itens.

- `org.jfree.chart.renderer` — Renderers e estratégias de desenho.
  - Responsabilidade: transformar valores do `Dataset` em chamadas de desenho (formas, linhas, cores, fills).
  - Pontos críticos: loops de desenho em grandes datasets; evitar alocações por item.

- `org.jfree.data` — Modelos de dados (datasets), coleções e utilitários.
  - Inclui subpacotes: `time` (TimeSeries), `xy`, `category`, `statistics`, `xml`.
  - Responsabilidade: representar conjuntos de dados usados pelos plots e emitir eventos de mudança.
  - Pontos críticos: consistência de eventos, mutabilidade e cópia/clonagem para operações concorrentes.

- `org.jfree.chart.title`, `org.jfree.chart.legend`, `org.jfree.chart.text` — elementos gráficos e layout.
  - Responsabilidade: composição de títulos/subtítulos, legendas e layout de textos.

- `org.jfree.chart.util`, `org.jfree.chart.ui` — utilitários e helpers.
  - Responsabilidade: operações auxiliares (formatos, medidas, utilitários de desenho, transformações de cor).

- `org.jfree.chart.urls` — Geradores de URLs (para imagem-maps em saídas HTML), útil para interatividade em servidores.

Fluxo de execução (alto nível)

1. Aplicação cria um `Dataset` (ou usa um `Dataset` existente).  
2. `ChartFactory` (ou construtor manual) cria `JFreeChart` vinculando `Dataset` ao `Plot` apropriado.  
3. `Plot` configura e coordena eixos e `Renderer(s)`.  
4. `Renderer` itera sobre itens do `Dataset` e desenha em `Graphics2D`.  
5. Eventos (`DatasetChangeEvent`, `PlotChangeEvent`) propagam-se para atualizar views (`ChartPanel`, exportadores).

Pontos de atenção / hotspots

- Performance: renderers que iteram por todos os pontos devem minimizar alocações e preferir passes únicos.  
- Memória: grandes `TimeSeries` e `DefaultXYZDataset` podem crescer muito — considere sampling/decimation para visualização.  
- Threading: atualizações de GUI devem ocorrer no EDT (Swing); uso em servidores requer atenção a concorrência no acesso aos datasets.  
- Localização/Resources: bundles e `package-info.java` presentes — verifique encoding e fallback.

Como usar esta visão

- Use este arquivo como referência rápida para localizar responsabilidades.
- Para documentação API completa, execute `mvn javadoc:javadoc`.
- Para melhorar a documentação de código, aplique os templates do `docs/javadoc_examples/` nas classes-chave (renderers, plots, datasets).