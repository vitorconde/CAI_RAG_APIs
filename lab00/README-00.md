# Lab 00: Extração de Dados de Chuva

## Descrição

Este notebook inicia o projeto com a extração de dados de precipitação da API pública da São Paulo Águas (SPAguas). Ele demonstra como coletar medições atuais de estações meteorológicas, processar a resposta JSON e salvar os dados em formatos reutilizáveis como JSON e CSV.

## Funcionalidades Principais

- **Requisição à API**: Utiliza `requests.get()` para acessar `https://apps.spaguas.sp.gov.br/sibh/api/v2/measurements/now`, configurando parâmetros como:
  - `station_type_id`: 1 (para estações de chuva).
  - `hours`: Período de medição (padrão 1 hora).
  - `show_all`: "false" (mostra apenas estações ativas).
  - `serializer`: "complete" (dados detalhados).
  - `public`: "true" (dados públicos).

```
url = "https://apps.spaguas.sp.gov.br/sibh/api/v2/measurements/now"

params = {
    "station_type_id": 1,
    "hours": 1,              # 1 até 72
    "show_all": "false",     # true ou false
    "serializer": "complete",# complete ou simplify
    "public": "true"         # true ou false
}

response = requests.get(url, params=params, timeout=30)
response.raise_for_status()

data = response.json()

```

- **Processamento de Dados**: Converte a lista de medições em um DataFrame pandas com `pd.json_normalize()`, facilitando a manipulação.

- **Salvamento de Dados**:
  - Salva o JSON completo em `dados_chuva.json`.
  - Converte e salva em CSV (`dados_chuva.csv`) para compatibilidade com outras ferramentas.

- **Análise Básica**:
  - Conta o número de registros recebidos.
  - Calcula o tamanho do arquivo em bytes, KB e MB.

## Estrutura do Código

1. **Importações**: `requests`, `pandas`, `json`.
2. **Requisição e Resposta**: Coleta dados da API com tratamento de erro (`response.raise_for_status()`).
3. **Normalização**: Cria DataFrame a partir do JSON.
4. **Salvamento**: Persiste dados em disco.
5. **Estatísticas**: Imprime métricas básicas do conjunto de dados.

## Dependências

- `requests`: Para HTTP requests.
- `pandas`: Para DataFrames.
- `json`: Para manipulação de JSON.

## Como Executar

1. Certifique-se de que as dependências estão instaladas (`pip install requests pandas`).
2. Execute as células sequencialmente.
3. Ajuste `params` para personalizar a coleta (ex.: aumentar `hours` para mais dados históricos).
4. Verifique os arquivos gerados: `dados_chuva.json` e `dados_chuva.csv`.

## Saídas Esperadas

- Arquivo `dados_chuva.json`: Contém a resposta bruta da API.
- Arquivo `dados_chuva.csv`: Dados tabulares prontos para análise.
- Prints no console com contagem de registros e tamanho do arquivo.

Este notebook estabelece a base de dados para os próximos labs, garantindo acesso consistente aos dados de chuva.