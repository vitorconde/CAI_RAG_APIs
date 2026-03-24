# Lab 03: Dashboard Operacional com Modelo e Alertas

## Descrição

Este notebook cria um dashboard simples usando matplotlib para visualizar os scores de risco calculados no lab anterior. Além disso, gera relatórios textuais de alertas para estações críticas e de alto risco, facilitando monitoramento operacional.

## Funcionalidades Principais

- **Reutilização do Modelo**: Importa e executa o `build_risk_model()` do lab 02.

- **Visualização**:
  - `plot_top_risk()`: Gera gráfico de barras horizontais coloridas por classe de risco (vermelho para CRÍTICO, etc.).
  - Ordena por score decrescente, mostra top N estações.
  - Salva imagem como `dashboard_risco.png`.

- **Alertas**:
  - `generate_alerts()`: Cria relatório textual com contagens totais, listas de estações críticas e de alto risco, incluindo valores de chuva, nível e score.

## Estrutura do Código

1. **Modelo Base**: Funções de coleta e cálculo de risco.
2. **Dashboard**: Configuração de plot com cores por risco.
3. **Alertas**: Lógica para filtrar e formatar mensagens de alerta.

## Dependências

- `requests`, `pandas`, `numpy`, `matplotlib`.

## Como Executar

1. Instale dependências.
2. Execute o modelo para obter DataFrame de risco.
3. Chame `plot_top_risk(df)` para visualização.
4. Use `generate_alerts(df)` para relatórios.

## Saídas Esperadas

- Gráfico salvo como PNG.
- Relatório textual no console com alertas detalhados.
- Suporte para integração em sistemas operacionais.

Este lab transforma dados de risco em ferramentas práticas de monitoramento.