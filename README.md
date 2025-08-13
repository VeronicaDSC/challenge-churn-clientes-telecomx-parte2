# challenge-churn-clientes-telecomx-parte2
**Como parte do processo de aprendizagem para o curso de ciências de dados ministrado pela Alura e idealizada pela Oracle Next Education:**
________________________________________________________________________________________________
# Desafio

🧠 Objetivos:
Preparar os dados para a modelagem (tratamento, encoding, normalização).

Realizar análise de correlação e seleção de variáveis.

Treinar dois ou mais modelos de classificação.

Avaliar o desempenho dos modelos com métricas.

Interpretar os resultados, incluindo a importância das variáveis.

Criar uma conclusão estratégica apontando os principais fatores que influenciam a evasão.
_______________________________________________________________________________________________
# Etapas 
🛠️ Preparação dos Dados
*Remoção colunas irrelevantes
*Encoding
*Proporção de Evasão
*Balanceamento de classes
*Normalização
🎯 Correlação e Seleção de Variáveis
*Análise de Correlação
*Análises Direcionadas
🤖 Modelagem Preditiva
*Separação dos dados
*Avaliação dos Modelos
_______________________________________________________________________________________________
📋  Interpretação e Conclusões
Escolha dos modelos
Modelo 1 — Regressão Logística (com normalização)

Escolhido porque é um modelo linear, interpretável e funciona bem em problemas de classificação binária como a evasão de clientes.

Necessidade de normalização: Modelos baseados em distância ou com otimização gradiente (como Regressão Logística, KNN e SVM) são sensíveis a escalas diferentes entre variáveis. Sem normalizar, variáveis com valores maiores dominariam o cálculo, distorcendo os resultados.

Modelo 2 — Random Forest (sem normalização)

Escolhido porque é um modelo não linear e robusto, que lida bem com relações complexas entre variáveis e não é sensível à escala dos dados.

Não exige normalização porque os algoritmos baseados em árvores fazem divisões condicionais (splits) que não dependem da magnitude dos valores, apenas da ordem.

# Treinamento e avaliação
Treinamento

Predição

Cálculo de métricas (Acurácia, Precisão, Recall, F1-score)

Matriz de confusão com visualização via Seaborn
__________________________________________________________________________________________
 Interpretação dos Modelos
Logistic Regression
Acurácia (0.7662) → O modelo acerta cerca de 76,6% das previsões.

Precisão (0.5518) → Entre todos os clientes que o modelo previu como evasão, 55,18% realmente evadiram.
Isso significa que há alguns falsos positivos (o modelo "acusou" evasão mas o cliente ficou).

Recall (0.6364) → O modelo conseguiu encontrar 63,64% dos clientes que realmente evadiram.
Isso é relevante, pois um recall alto é importante em problemas de churn — é pior não detectar um cliente prestes a sair.

F1-score (0.5911) → Combinação de precisão e recall, mostra equilíbrio moderado.

Matriz de confusão:

1262 → Clientes que ficaram e foram corretamente classificados.

357 → Clientes que saíram e foram corretamente classificados.

290 → Falsos positivos (clientes que ficaram, mas o modelo disse que sairiam).

204 → Falsos negativos (clientes que saíram, mas o modelo disse que ficariam).

📌 Resumo: Modelo levemente mais voltado para detectar evasão (bom recall), mas com risco de "acusar" alguns clientes que não sairiam.

Random Forest
Acurácia (0.7672) → Muito próximo da regressão logística (76,7%).

Precisão (0.5604) → Levemente maior que na regressão logística.

Recall (0.5704) → Menor que na regressão logística, significa que perde mais casos reais de evasão.

F1-score (0.5654) → Pouco abaixo da regressão logística.

Matriz de confusão:

1301 → Clientes que ficaram e foram corretamente classificados.

320 → Clientes que saíram e foram corretamente classificados.

251 → Falsos positivos.

241 → Falsos negativos.

📌 Resumo: Modelo mais equilibrado em relação a falsos positivos e negativos, mas menos sensível para detectar quem vai evadir.

Logistic Regression: melhor recall → mais útil para identificar clientes que vão sair (útil para ações preventivas).

Random Forest: melhor precisão → mais útil para ter certeza de que um cliente que foi marcado realmente vai sair (útil para otimizar recursos).

_____________________________________________________________________________________________
Conclusões e Estratégias
Principais fatores (baseado na análise exploratória prévia e importância das variáveis):

Tipo de contrato (clientes com contrato mensal tendem a evadir mais).

Tempo de contrato baixo (clientes novos evadem mais).

Pagamento por "electronic check" (maior taxa de churn).

Ausência de serviços extras (streaming, segurança online, backup) → indicam menor engajamento.

Estratégias sugeridas:

Campanhas de retenção para clientes com contrato mensal → incentivo para migrarem para contratos anuais.

Ofertas de pacotes adicionais (serviços de valor agregado) para aumentar engajamento.

Descontos ou bônus para novos clientes nos primeiros meses → reduzir evasão inicial.

Atenção especial aos clientes que pagam por “electronic check” → pode indicar perfil menos fiel.


