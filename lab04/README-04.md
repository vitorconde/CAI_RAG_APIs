# Lab 04: LLM Explicando Eventos

## Descrição

Este notebook integra um modelo de linguagem (LLM) para explicar cenários hidrológicos baseados nos dados de risco. Utiliza a API do Cloudera AI Inference (compatível com OpenAI) para enviar contexto dos dados e receber explicações narrativas sobre estações críticas.

## Funcionalidades Principais

- **Configuração LLM**: Cliente OpenAI apontando para endpoint Llama 3.1-8B, com chave de API.
```
BASE_URL = ""
API_KEY = ""
MODEL_NAME = ""
```
Vamos buscar a configuração anterior seguindo os próximos passos.

![CAI Home](../img/model_endpoints01.png)
Clique em Model Endpoints

![CAI Model Endpoints](img/model_endpoints02.png)
Clique no modelo que vamos usar - llama-31-8b

![CAI Home](img/model_endpoints01.png)
Clique em Model Endpoints



- **Modelo de Risco**: Reutiliza funções dos labs anteriores para calcular scores.

- **Contexto para LLM**:
  - `build_llm_context()`: Formata top 10 estações em texto legível, incluindo valores de chuva, nível, scores e referências.

- **Explicação**:
  - `explain_events_with_llm()`: Monta prompt pedindo análise simples, destaques críticos, razões de preocupação e diferenças entre chuva e nível.
  - Envia para LLM e retorna resposta.

## Estrutura do Código

1. **Setup LLM**: Importações e configuração do cliente.
2. **Dados e Modelo**: Coleta e cálculo de risco.
3. **Contexto**: Formatação textual dos dados.
4. **Prompt e Resposta**: Interação com LLM para explicações.

## Dependências

- `requests`, `pandas`, `numpy`, `openai`.

## Como Executar

1. Instale `pip install openai`.
2. Configure `API_KEY` e `BASE_URL` (ajuste para seu ambiente).
3. Execute pipeline de dados.
4. Chame `explain_events_with_llm(df)` para obter explicação.

## Saídas Esperadas

- Resposta textual da LLM explicando o cenário atual.
- Análises contextuais baseadas apenas nos dados fornecidos.

Este lab adiciona inteligência interpretativa aos dados numéricos.