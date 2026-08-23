# KPIs de Negócio - Fase 2

Cliente: clube do Campeonato Brasileiro Série A.
Objetivo: monitorar risco de rebaixamento e apoiar decisões de planejamento
esportivo e financeiro ao longo da temporada.

## 1. Risco de rebaixamento previsto (%)

Probabilidade de queda na temporada seguinte, gerada pelo modelo preditivo (Fase 2 —
Analytics). Fonte: saída do modelo de classificação sobre `rebaixado_prox_temporada`.
**Depende da modelagem, só fica disponível depois do notebook de modelagem preditiva.**

## 2. Distância da zona de rebaixamento (pontos)

Diferença de pontos entre o clube e o 17º colocado (limite da Z4), atualizada a cada
rodada. Fonte: classificação clube-temporada (já pronta, Fase 1).

## 3. Aproveitamento de pontos (%)

Pontos conquistados / pontos possíveis (jogos disputados × 3). Comparado à média
histórica de clubes que se salvaram vs. que caíram nas mesmas faixas de aproveitamento.
Fonte: classificação clube-temporada.

## 4. Forma recente (pontos nas últimas 5 rodadas)

Testa H1 (queda de forma no fim da temporada como sinal de risco futuro). Fonte:
tabela Partidas + variável temporada.

## 5. Aproveitamento mandante vs. visitante (%)

Testa H2 (dependência excessiva de resultados em casa). Fonte: classificação
clube-temporada, separada por mando de campo.

## 6. Taxa histórica de rebaixamento por faixa de pontuação

% de clubes que caíram na temporada seguinte, agrupados por faixas de pontos da
temporada atual (ex.: 30-35 pts, 36-40 pts, 41-45 pts...). KPI descritivo, disponível
sem esperar o modelo — dá contexto de "risco de base" desde já.

Fonte: elaborado pelo autor (2026), a partir da base analítica validada na Fase 1.
