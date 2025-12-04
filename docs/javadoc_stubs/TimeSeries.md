# TimeSeries

Responsabilidade

- Série temporal que contém pares (RegularTimePeriod, Number) e operações para agregar, atualizar e truncar dados temporais.

Resumo para Javadoc a aplicar na classe fonte

/**
 * Representa uma série temporal indexada por `RegularTimePeriod`. Fornece
 * métodos para adição/atualização de pontos, remoção automática de itens
 * antigos e clonagem.
 */

Pontos a documentar

- Política de aging/pruning (`setMaximumItemAge` etc.)
- Contratos de comparação/ordenamento e comportamento com `null`/`NaN`
