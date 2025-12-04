Exemplo de Javadoc sugerido para `ChartColor` (arquivo: `src/main/java/org/jfree/chart/ChartColor.java`)

Resumo a inserir antes da declaração da classe:

/**
 * Extende `java.awt.Color` com um conjunto de cores pré-definidas e
 * utilitários para criação de paletas usadas em gráficos.
 *
 * <p>Fornece métodos utilitários como {@link #createDefaultColorArray()} e
 * {@link #getContrastColor(Color)} para selecionar cores que garantam
 * legibilidade dos rótulos.</p>
 */

Comentários de método (exemplo para `getContrastColor`):

/**
 * Retorna `Color.BLACK` ou `Color.WHITE` dependendo da luminância do
 * argumento para garantir contraste legível em rótulos sobre essa cor.
 *
 * @param color a cor de referência (não nulo)
 * @return `Color.BLACK` ou `Color.WHITE` para contraste
 * @throws NullPointerException se `color` for nulo
 */
public static Color getContrastColor(Color color) { ... }

Observações:
- `createDefaultColorArray()` já é auto-explicativo, mas vale documentar a ordem/papel das cores se houver significado.
- Verificar uso de `@since` em adições recentes para rastreabilidade.