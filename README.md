# Desafio de Ciência de Dados – IMDB

Este projeto entrega:
- **EDA** + hipóteses (com gráficos),
- Respostas às perguntas do desafio,
- **Modelagem** para prever `IMDB_Rating` (regressão),
- Caso prático: predição para *The Shawshank Redemption*,
- Artefato do modelo em **`model_imdb_rating.pkl`**.

### Como rodar

### Via Google Colab
1. Adicione essa pasta no google colab e abra o arquivo `LH_CD_ANDRESSACAROLINEDAROCHAPEREIRA.ipynb`.
2. Ajuste o caminho do CSV na primeira célula (`DATA_PATH`), se necessário.
3. Execute as células em ordem. 
   - Modelo é salvo em `LH_CD_ANDRESSACAROLINEDAROCHAPEREIRA/model_imdb_rating.pkl`.
### Via link do colab

Link: https://colab.research.google.com/drive/1CBuN8WXn1WkUUSUFLddYWsccntRC-VAy?usp=sharing

### O que o projeto faz

- EDA: distribuições de IMDB_Rating e Gross (log1p), relações Votos x Nota e Votos x Faturamento, correlações, boxplots por gênero.

### Perguntas:

- Recomendação via Weighted Rating (nota ajustada por popularidade).

- Fatores para faturamento: No_of_Votes domina, seguido de Released_Year_num, Meta_score etc.

- Overview → Gênero (TF-IDF + LogReg): acurácia modesta (classes comuns), texto ajuda mas não resolve sozinho.

### Modelagem de IMDB_Rating (Regressão):

- Features numéricas: Runtime_min, Meta_score, No_of_Votes, Released_Year_num, Gross_log1p.

- Categóricas: Certificate, Director_top, Star1_top–Star4_top (Top-K + One-Hot).

- Pré-processamento: imputação (mediana/moda), padronização (num), One-Hot (cat).

- Modelos: Linear Regression, Random Forest, Gradient Boosting.

- Métrica: RMSE (principal) e MAE (apoio).

> Melhor: Gradient Boosting (ex.: RMSE ≈ 0.185; MAE ≈ 0.148).

### Caso prático – Shawshank

- Input conforme enunciado.

- Previsão: ~8.81%.

- Nota conhecida: 9.30 → filme é outlier positivo; intervalo plausível baseado no RMSE: 8.62–9.00.


### Licença
MIT.
- ❤️ Feito por Andressa Caroline
