# Lab 99: Teste de Análise de PIB

## Descrição

Este notebook é um teste experimental para análise de dados econômicos, utilizando a biblioteca `sidrapy` para obter dados do Produto Interno Bruto (PIB) do IBGE (Instituto Brasileiro de Geografia e Estatística). Integra LLM para responder perguntas sobre os dados.

## Funcionalidades Principais

- **Coleta de Dados**: Usa `get_table()` do sidrapy para tabela 5939 (PIB por região), nível territorial 2 (regiões), período 2020.

- **Processamento**: Limpa e converte valores para numérico, remove não-numéricos.

- **Integração LLM**: Formata dados em string e envia prompt com perguntas sobre primeira linha, soma e ordenação por região, média.

- **Resposta Streaming**: Recebe resposta da LLM em chunks.

## Estrutura do Código

1. **Instalação**: `pip install sidrapy openai`.
2. **Setup LLM**: Cliente para Llama.
3. **Dados**: Coleta via sidrapy.
4. **Limpeza**: Conversão de valores.
5. **Prompt**: Perguntas específicas.
6. **Chat Completion**: Streaming de resposta.

## Dependências

- `sidrapy`, `pandas`, `openai`.

## Como Executar

1. Instale bibliotecas.
2. Configure API.
3. Execute células para obter dados e resposta.

## Saídas Esperadas

- DataFrame de PIB por região.
- Resposta da LLM com análises solicitadas.

Este é um lab de teste, possivelmente para explorar integrações com dados econômicos.