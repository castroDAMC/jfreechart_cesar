# ChartPanel

Responsabilidade

- Componente Swing (`JComponent`) responsável por exibir um `JFreeChart`, lidar com interações (zoom, pan, copiar, salvar) e gerenciar buffer de desenho.

Resumo para Javadoc a aplicar na classe fonte

/**
 * Painel Swing para exibição interativa de um `JFreeChart`. Gerencia
 * operações de usuário como zoom, pan e exportação, além de otimizações
 * de buffer para desenho.
 *
 * @see JFreeChart
 */

Pontos a documentar

- Requisitos de execução no EDT ao mudar propriedades UI.
- Comportamento dos métodos de exportação e opções de buffering.
