# AbstractRenderer

Responsabilidade

- Classe base com utilitários para renderers: gerencia listas de `Paint`, `Stroke`, `Shape` por série e lógica comum de notificação.

Resumo para Javadoc a aplicar na classe fonte

/**
 * Classe base que fornece funcionalidades comuns para renderers, como
 * lookup tables para paints/strokes/shapes por série e gerenciamento de
 * listeners.
 */

Pontos a documentar

- Convenções para sobrescrever métodos de lookup
- Quando chamar `notifyListeners` ao alterar propriedades
