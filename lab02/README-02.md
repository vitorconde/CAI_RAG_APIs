# Lab 02: Modelo de Risco Real

## Descrição de Negócio

Este modelo avalia o risco de cada estação, combinando dois fatores principais: quanto choveu e quão alto está o nível de água.
`risc_score = (rain_score * w1) + (level_score * w2)`
Onde rain_score é a normalização de precipitação observada em relação ao máximo da janela temporal.
E level_score é a razão entre o nível atual e os thresholds hidrológicos (atenção, alerta, emergência, extravasamento).

## Descrição Tecnica

Este notebook implementa um modelo de risco hidrológico combinando dados de chuva e níveis de água. Ele calcula scores de risco baseados em ratios entre níveis atuais e referências críticas (atenção, alerta, emergência, extravasamento), integrando precipitação para uma avaliação abrangente.

## Funcionalidades Principais

- **Coleta de Dados**:
  - `get_rain_data()`: Baixa medições de chuva.
  - `get_level_data()`: Baixa níveis de água com referências críticas via API `now_flu`.

- **Normalização**:
  - `prepare_rain_df()`: Padroniza DataFrame de chuva.
  - `prepare_level_df()`: Padroniza DataFrame de níveis com colunas de referência.

- **Cálculo de Risco**:
  - `calculate_level_ratio()`: Computa score baseado na proximidade do nível atual às referências (ex.: nível / atenção).
  - `classify_risk()`: Classifica em CRÍTICO (>=0.95), ALTO (>=0.75), MÉDIO (>=0.45), BAIXO.

- **Modelo Integrado**:
  - `build_risk_model()`: Junta dados de chuva e nível, calcula scores combinados (40% chuva + 60% nível), classifica e ordena por risco.

## Estrutura do Código

1. **Funções de Coleta**: Reutilizam lógica dos labs anteriores com ajustes para níveis.
2. **Normalização**: Garante colunas consistentes e conversões numéricas.
3. **Regras de Risco**: Lógica para avaliar proximidade a thresholds críticos.
4. **Pipeline Principal**: Integra tudo em um DataFrame final de risco.

## Dependências

- `requests`, `pandas`, `numpy`.

## Como Executar

1. Instale dependências.
2. Execute funções em ordem.
3. Ajuste `hours` para período de análise.
4. O DataFrame resultante inclui scores e classes de risco.

## Saídas Esperadas

- DataFrame merged com colunas de risco.
- Scores numéricos e classificações categóricas.
- Base para dashboards e alertas nos próximos labs.

Este modelo fornece uma avaliação quantitativa de riscos hidrológicos.