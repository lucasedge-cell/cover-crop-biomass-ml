# Cover Crop Biomass Estimation with Machine Learning and Remote Sensing

Non-destructive estimation of cereal rye (*Secale cereale* L.) cover crop biomass from spectral vegetation indices derived from UAV multispectral imagery, comparing six machine learning regression models under Leave-One-Out Cross-Validation.

Developed at the Federal University of Santa Catarina (UFSC), with data collected in a field experiment in North Platte, Nebraska (USA) during a research assistantship at the University of Nebraska–Lincoln. Results presented at the ASA-CSSA-SSSA Annual Meeting, 2025.

## Objective

Replace traditional destructive biomass sampling (cutting, drying and weighing — time- and labor-intensive) with an estimation approach based on remote sensing and machine learning, enabling monitoring at operational scale.

## Methodology

- **Dataset:** 51 samples × 26 spectral vegetation indices derived from UAV multispectral imagery; reference biomass from georeferenced destructive sampling
- **Target:** dry biomass (`Biomass_g`)
- **Validation:** Leave-One-Out Cross-Validation (LOOCV) — appropriate for the small sample size
- **Preprocessing:** RobustScaler inside a scikit-learn Pipeline to prevent data leakage
- **Metrics:** R², CCC (Concordance Correlation Coefficient), RMSE, MAE, NRMSE, MAPE, bias and RPD (Ratio of Performance to Deviation)

## Models compared

| Notebook | Model |
|----------|-------|
| `LOOCV_01_CatBoost.ipynb` | CatBoost Regressor |
| `LOOCV_02_RandomForest.ipynb` | Random Forest Regressor |
| `LOOCV_03_LightGBM.ipynb` | LightGBM Regressor |
| `LOOCV_04_KRR.ipynb` | Kernel Ridge Regression |
| `LOOCV_05_GPR.ipynb` | Gaussian Process Regression |
| `LOOCV_06_PLS.ipynb` | Partial Least Squares (PLS) |
| `LOOCV_07_Comparacao_Geral.ipynb` | Side-by-side comparison of all six models |

Partial Least Squares (PLS) achieved the best overall performance.

## Tech Stack

Python · scikit-learn · CatBoost · LightGBM · pandas · numpy · matplotlib

## Running the notebooks

Each notebook is self-contained and runs on Google Colab or a local Jupyter environment. It auto-detects the environment; on Colab it prompts for the data file upload.

```
pip install catboost lightgbm scikit-learn pandas numpy openpyxl scipy
```

## Author

Lucas de Matos Siebeneichler — Agronomist (UFSC)

---

# Estimativa de Biomassa de Plantas de Cobertura com Machine Learning e Sensoriamento Remoto

Estimativa não destrutiva da biomassa de centeio (*Secale cereale* L.), utilizado como planta de cobertura, a partir de índices de vegetação derivados de imagens multiespectrais de VANT (drone), comparando seis modelos de regressão de aprendizado de máquina sob validação Leave-One-Out.

Projeto desenvolvido na Universidade Federal de Santa Catarina (UFSC), com dados coletados em experimento em North Platte, Nebraska (EUA), durante atuação como assistente de pesquisa na University of Nebraska–Lincoln. Resultados apresentados no congresso anual da ASA-CSSA-SSSA, 2025.

## Resumo

Seis modelos de regressão foram treinados e comparados para estimar a biomassa seca a partir de 26 índices de vegetação (51 amostras), utilizando validação cruzada Leave-One-Out (LOOCV), adequada ao tamanho reduzido da amostra, com pré-processamento por RobustScaler dentro de Pipeline para evitar data leakage. As métricas incluem R², CCC, RMSE, MAE, NRMSE, MAPE, viés e RPD. O PLS obteve o melhor desempenho geral.

**Ferramentas:** Python · scikit-learn · CatBoost · LightGBM · pandas · numpy
