# DefaultXYDataset

Responsabilidade

- Implementação de `XYDataset` baseada em arrays `double[][]` para representar várias séries XY.

Resumo para Javadoc a aplicar na classe fonte

/**
 * Implementação de `XYDataset` que armazena séries como arrays de double e
 * fornece acesso eficiente para renderers em hot-path.
 */

Pontos a documentar

- Contrato de estabilidade/defensive copy ao retornar arrays
- Conversões e tratamento de `NaN`/`null` nos métodos de acesso
