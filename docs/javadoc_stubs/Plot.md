# Plot

Responsabilidade

- Classe base para tipos de plots; coordena layout, eixos, datasets e delega desenho aos renderers.

Resumo para Javadoc a aplicar na classe fonte

/**
 * Base para implementações de plots (XY, Category, Polar, etc). Gerencia
 * espaços, eixos e coordena a chamada de renderers para desenhar os itens.
 */

Pontos a documentar

- Contrato de `draw(...)` e como produzir `PlotRenderingInfo`.
- Mapeamento dataset→axis e como subclasses devem estender o fluxo de desenho.
