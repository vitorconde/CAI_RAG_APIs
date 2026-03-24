# Lab 01: Exploração de Dados de Chuva

## Descrição

Este notebook foca na exploração e visualização inicial dos dados de chuva coletados. Ele demonstra como processar os dados da API, criar visualizações gráficas e identificar padrões, como as estações com maior acumulado de precipitação.

## Funcionalidades Principais

- **Coleta de Dados**: Reutiliza a lógica de requisição à API da SPAguas, ajustando `station_type_id` para 2 (estações pluviométricas) e `hours` para 12 para um período mais amplo.

- **Processamento**:
  - Converte valores para numérico com `pd.to_numeric()`, removendo NaNs.
  - Cria rótulo combinado de estação e cidade para visualizações.
  - Ordena e filtra os top 15 registros por valor de chuva.

- **Visualização**:
  - Gera gráfico de barras horizontais com `matplotlib.pyplot.barh()`.
  - Inverte o eixo Y para melhor legibilidade.
  - Adiciona títulos, labels e valores nas barras.
  - Salva o gráfico como imagem (opcional).

## Estrutura do Código

1. **Importações**: `requests`, `pandas`, `matplotlib.pyplot`.
2. **Coleta**: Requisição à API com parâmetros ajustados para exploração.
3. **DataFrame**: Normalização e limpeza de dados.
4. **Top Seleção**: Ordenação descendente e seleção dos maiores valores.
5. **Plot**: Configuração e exibição do gráfico.

## Dependências

- `requests`: Para coleta de dados.
- `pandas`: Para manipulação.
- `matplotlib`: Para gráficos.

## Como Executar

1. Instale dependências: `pip install requests pandas matplotlib`.
2. Execute as células em ordem.
3. Ajuste `hours` ou `top_n` para explorar diferentes períodos ou quantidades.
4. O gráfico será exibido inline e pode ser salvo.

## Saídas Esperadas

- DataFrame com top estações por chuva.
- Gráfico de barras mostrando acumulado de chuva (mm) por estação.
- Insights visuais sobre distribuição de precipitação.

Este lab complementa o 00, transformando dados brutos em insights visuais.