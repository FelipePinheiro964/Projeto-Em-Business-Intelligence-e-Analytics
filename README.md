# Projeto em Business Intelligence e Analytics

Trabalho da disciplina **Projeto em Business Intelligence e Analytics** (PUCRS Online) — Fase 1 e Fase 2.
Autor: Felipe Pinheiro Fossá

## Sobre o projeto

O Campeonato Brasileiro Série A rebaixa 4 clubes a cada temporada, com forte impacto financeiro e esportivo para os clubes envolvidos. Este projeto usa dados históricos de desempenho (2006–2025) para estimar, de forma antecipada, o risco de rebaixamento de cada clube.

**Objetivo geral:** transformar dados de desempenho clube-temporada em um indicador preditivo de risco de rebaixamento, apresentado por meio de uma solução de BI e Analytics.

## Arquitetura da solução

1. **Dados do Campeonato Brasileiro** — dados históricos das temporadas (fonte: Kaggle).
2. **Preparação dos dados** — limpeza, tratamento e padronização (Python/Jupyter).
3. **Base analítica clube × temporada** — organização dos indicadores de desempenho.
4. **Modelagem + validação temporal** — Regressão Logística, avaliada com validação cruzada temporal (janela expansiva).
5. **Previsão do risco de rebaixamento** — geração da probabilidade prevista para a temporada de 2025, exportada para CSV e consumida pelo dashboard.

## Ferramentas utilizadas

- **Python** (pandas, numpy, scikit-learn, matplotlib, seaborn) — preparação de dados, modelagem preditiva e visualizações
- **Jupyter Notebook** — desenvolvimento e documentação da análise
- **Tableau Public** — construção e publicação do dashboard
- **Git/GitHub** — versionamento e histórico do projeto

## Estrutura do repositório

- `01_analise_dataset.ipynb` — análise exploratória e preparação da base analítica
- `02_modelagem_preditiva.ipynb` — modelagem preditiva (Regressão Logística) e geração das previsões
- `Projeto-em-bi-analytics.twb` — arquivo do dashboard Tableau

## Resultados do modelo

Validação cruzada temporal (2014–2024, 176 previsões agregadas, `class_weight="balanced"`):

| Métrica  | Valor |
| -------- | ----- |
| Precisão | 0,26  |
| Recall   | 0,77  |
| F1-score | 0,39  |

O recall foi priorizado por objetivo de negócio: é preferível superestimar o risco em times seguros do que deixar de sinalizar um time que de fato será rebaixado.

## Dashboard

Disponível no Tableau Public:
https://public.tableau.com/app/profile/felipe.pinheiro.foss./viz/Projeto-em-bi-analytics/Dashboard

## Como rodar localmente

```bash
pip install -r requirements.txt
jupyter notebook
```

## Licença

© 2026 Felipe Pinheiro. Todos os direitos reservados.

Este projeto é disponibilizado publicamente para fins de consulta e avaliação acadêmica.
Nenhuma permissão é concedida para copiar, modificar, distribuir ou reutilizar o código,
documentação ou materiais deste projeto sem autorização do autor.
