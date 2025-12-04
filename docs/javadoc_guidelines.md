# Diretrizes de Javadoc / Comentários

Objetivo: fornecer um guia direto para criar comentários Javadoc claros e úteis para este repositório.

Regras rápidas

- Cabeçalho de classe: descreva responsabilidade resumida (1-2 frases). Mencione padrões relevantes (visitor, factory, strategy).
- Cabeçalho de método: descreva o que o método faz, parâmetros (breve), retorno e efeitos colaterais (eventos disparados, mudança de estado).
- Exceptions: documente `@throws` quando aplicável.
- Exemplos: para métodos públicos complexos, inclua um pequeno snippet de uso.
- Visibilidade: documente comportamento público/contratos (imutabilidade, sincronização, requisitos do EDT).

Template de classe

/**
 * [Resumo de responsabilidade da classe].
 *
 * <p>Detalhes, invariantes importantes e referências para classes relacionadas.</p>
 */
public class Example {
    ...
}

Template de método

/**
 * [O que o método faz].
 *
 * @param arg descr. (restrições, unidades)
 * @return descr. (tipo, quando nulo)
 * @throws IllegalArgumentException descr. quando aplicável
 */
public ReturnType method(Type arg) { ... }

Recomendações práticas

- Foco no usuário da API (outro dev), não na implementação.
- Use frases curtas e exemplos quando esclarecer pré-condições.
- Atualize Javadoc junto com mudanças de assinatura.

Automatização

- Use uma combinação de análise estática (grep por classes públicas) e templates para aplicar Javadoc automaticamente.
- Eu posso gerar esboços de Javadoc para N classes selecionadas. Informe quais pacotes ou o número máximo de arquivos a gerar.