# Lab 05: Chat Conversacional com LLM

## Descrição

Este notebook implementa um sistema de chat conversacional alimentado por LLM, utilizando dados de risco hidrológico como contexto. Permite interações interativas onde o usuário pode fazer perguntas sobre os dados, recebendo respostas baseadas no modelo de linguagem.

## Funcionalidades Principais

- **Configuração LLM**: Cliente OpenAI para Llama 3.1-8B via Cloudera.
Utilizaremos a mesma configuração do lab anterior. ***Lembre-se de reativar seu token***

- **Coleta de Dados**: Funções para baixar chuva e níveis, similar aos labs anteriores.

- **Modelo de Risco**: Calcula scores combinados de chuva e nível.

- **Chat Interativo**: (Código sugere setup para loop de chat, embora não mostrado completamente; presume integração de contexto em conversas).

Você poderá perguntar coisas como:
```
“Quais estações estão em maior risco?”
“Existe alguma estação com chuva alta e nível baixo?”
“Quais cidades parecem mais preocupantes?”
“Explique a diferença entre as 3 estações mais críticas.”
“Há indício de extravasamento?”
```
Extra:
`"Agora explique para um leigo."`

## Estrutura do Código

1. **Setup**: Configuração do cliente LLM.
2. **Dados**: Coleta e processamento.
3. **Risco**: Cálculo de scores.
4. **Chat**: Lógica para interações conversacionais (baseada no contexto dos dados).

## Dependências

- `requests`, `pandas`, `numpy`, `openai`.

## Como Executar

1. Instale dependências.
2. Configure API.
3. Execute coleta e modelo.
4. Inicie chat interativo (ajuste código para loop se necessário).

## Saídas Esperadas

- Respostas conversacionais sobre dados de risco.
- Interações dinâmicas com o usuário.

Este lab evolui para aplicações interativas de IA.