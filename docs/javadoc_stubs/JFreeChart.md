# JFreeChart

Responsabilidade

- Estrutura de alto nível que representa um gráfico completo: contém `Plot`, títulos, legendas e configurações globais.

Resumo para Javadoc a aplicar na classe fonte

/**
 * Representa um gráfico completo com `Plot`, títulos, legendas e
 * configurações de estilo. Fornece métodos para desenhar o gráfico em
 * `Graphics2D`, aplicar temas e serializar o estado.
 *
 * <p>Uso típico:
 * <pre>
 * ChartFactory.createXYLineChart(...);
 * </pre>
 * </p>
 */

Pontos a documentar

- Contratos de serialização
- Thread-safety e restrições do EDT (operações que alteram estado do gráfico)
- Principais métodos públicos: `draw(...)`, `setTitle(...)`, `getPlot()`
