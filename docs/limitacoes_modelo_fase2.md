# Limitações do Modelo Preditivo — Fase 2

## O que era o plano original

As hipóteses da Fase 1 (H1, H2, H3) previam um modelo com múltiplas variáveis:
desempenho geral (pontos, saldo de gols), forma recente, desempenho mandante vs.
visitante, e estatísticas complementares de jogo (posse de bola, finalizações,
precisão de passe) nas temporadas em que essas colunas são confiáveis (2015-2023 e
2025). A ideia era testar qual combinação de sinais mais se relaciona ao risco de
rebaixamento futuro.

## O que a base de dados permite na prática

O Campeonato Brasileiro tem 20 clubes por temporada, com aproximadamente 4
rebaixamentos por ano. Isso limita a quantidade de exemplos positivos disponíveis
para treinar e avaliar o modelo: entre 2006 e 2024 (19 temporadas com desfecho
conhecido), existem apenas 50 casos de rebaixamento no total. Com 8 variáveis
explicativas testadas inicialmente, isso dá menos de 5 eventos por variável, abaixo
do mínimo geralmente recomendado (10) para coeficientes estáveis em regressão
logística.

Testado na prática, o modelo com todas as variáveis originais apresentou coeficientes
com sinal invertido (ex.: mais vitórias associado a mais risco), causado por
colinearidade entre pontos, posição e vitórias/empates/derrotas, variáveis que, em
grande parte, carregam a mesma informação sob formas diferentes.

## Decisão tomada

O modelo final usa uma única variável (posição final na temporada), que produziu o
melhor F1 entre as combinações testadas (0,369) e o único coeficiente com direção
coerente. As variáveis de H2 (mandante/visitante) e H3 (estatísticas complementares)
não foram incorporadas nesta versão, não porque as hipóteses estejam erradas, mas
porque a quantidade de dados disponível não sustenta um modelo mais amplo sem gerar
instabilidade.

## O que isso significa para a leitura dos resultados

O modelo é um primeiro sinal de risco baseado no indicador mais forte e mais estável
disponível (posição), não uma modelagem completa de todos os fatores levantados na
Fase 1. Ampliar o modelo exigiria mais temporadas de dados (o rebaixamento é um evento
raro por natureza) ou uma unidade de análise diferente da atual (ex.: nível de
partida em vez de temporada, o que geraria muito mais linhas, ao custo de redefinir
o problema).

Fonte: elaborado pelo autor (2026), a partir dos resultados registrados nas Issues
#12 e #13.
