# ChartElement

Responsabilidade

- Interface para elementos do gráfico que suportam o padrão Visitor (`ChartElementVisitor`).

Resumo para Javadoc a aplicar na interface fonte

/**
 * Representa um elemento no modelo de gráfico que pode aceitar um
 * {@link ChartElementVisitor} para permitir operações de travessia.
 */

Pontos a documentar

- Contrato do método `receive`: se `visitor` pode ser nulo e qual sequência de
chamadas é esperada.
