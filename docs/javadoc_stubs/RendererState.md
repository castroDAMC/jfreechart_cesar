# RendererState

Responsabilidade

- Objeto que carrega estado temporário do renderer durante a operação de desenho (ex.: caches, referências ao Graphics2D, informações por série).

Resumo para Javadoc a aplicar na classe fonte

/**
 * Contém o estado transitório usado por um renderer enquanto processa
 * chamadas de desenho. Implementações concretas devem documentar o que
 * armazenam e quando reinicializar.
 */

Pontos a documentar

- Ciclo de vida: quando é criado, reutilizado e liberado.
- Campos relevantes que implementações customizadas devem fornecer.
