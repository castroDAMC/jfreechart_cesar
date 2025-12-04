# Copilot – Instruções Gerais para Documentação, Análise e Refatoração

## Objetivo
1. Entender e documentar a aplicação, incluindo seus fluxos principais.
2. Identificar vulnerabilidades e code smells.
3. Quantificar problemas por categoria (Segurança e Qualidade).
4. Priorizar quais problemas devem ser resolvidos primeiro.
5. Criar um documento de planejamento de refatoração.
6. Sugerir trechos de código já refatorados.
7. Integrar ferramenta SAST e gerar relatório separado.

## Como o Copilot deve trabalhar
- Ler o código do repositório.
- Produzir documentação clara e objetiva dos principais fluxos da aplicação.
- Detectar vulnerabilidades e code smells.
- Classificar cada problema por categoria:
  - **Segurança**
  - **Qualidade do Código**
- Contabilizar cada tipo encontrado (ex: X SQL injections, Y Null Pointer risks, Z duplicações, etc.)
- Priorizar baseado em:
  - severidade
  - impacto
  - risco
  - complexidade da correção
- Criar um plano consolidado com:
  - problemas priorizados
  - descrição detalhada
  - sugestões de refatoração (com exemplos de código)
- Integrar uma ferramenta SAST (como CodeQL, Semgrep, Sonar ou outra disponível).
- Gerar relatório SAST em arquivo separado.

## Formato das entregas
1. **documentação.md**
2. **relatorio_vulnerabilidades.md**
3. **plano_refatoracao.md**
4. **sast_report.json / .md**

## Estilo que deve ser seguido
- Escrita técnica, direta.
- Tabelas sempre que possível.
- Nenhum texto genérico: usar termos específicos do código analisado.
