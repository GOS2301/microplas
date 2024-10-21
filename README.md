# Predição de Concentração de Microplásticos na Costa Litorânea Brasileira

Este projeto visa prever a distribuição da concentração de microplásticos ao longo da costa litorânea brasileira utilizando técnicas de geoprocessamento e aprendizado de máquina. O projeto integra dados geoespaciais e ambientais, como correntes oceânicas, uso da terra e fontes de poluição, com modelos preditivos para gerar mapas de concentração de microplásticos.

## Estrutura do Projeto

1. **Coleta de Dados**
    - Utilizamos diversas fontes de dados geoespaciais e ambientais para obter informações sobre correntes oceânicas, batimetria, uso da terra, entre outros.
    - Bases de dados usadas:
      - [Copernicus Marine Environment Monitoring Service (CMEMS)](https://marine.copernicus.eu/)
      - [NOAA Global Marine Debris Database](https://marinedebris.noaa.gov/)
      - [GEBCO - General Bathymetric Chart of the Oceans](https://www.gebco.net/)
      - [INPE - Instituto Nacional de Pesquisas Espaciais](http://www.inpe.br/)
      - [IBGE Geoportal](https://www.ibge.gov.br/geociencias/)

    **Estrutura de Diretórios:**
    ```bash
    /dados_microplasticos/
        ├── satelite/
        ├── batimetria/
        ├── poluicao/
        └── uso_terra/
    ```

2. **Pré-processamento de Dados**
    - Utilizamos ferramentas de geoprocessamento como [QGIS](https://qgis.org/) ou [ArcGIS](https://www.esri.com/en-us/arcgis/about-arcgis/overview) para processar os dados obtidos. O processamento inclui:
      - Limpeza e normalização dos dados.
      - Interpolação de dados geoespaciais (IDW, Kriging) quando necessário.
      - Integração de camadas de dados para gerar um conjunto de dados consolidado.
    
    **Ferramentas:**
    - QGIS/ArcGIS para geoprocessamento.
    - Python (`geopandas`, `rasterio`, `shapely`, `numpy`, etc.) para processamento de dados.

3. **Modelagem de Aprendizado de Máquina**
    - Utilizamos bibliotecas de aprendizado de máquina, como **scikit-learn**, **XGBoost** e **TensorFlow**, para construir modelos preditivos com base em fatores ambientais, correntes oceânicas e dados de concentração de microplásticos.
    - Modelos usados:
      - Random Forest
      - Regressão Linear
      - Redes Neurais (ANNs, CNNs)

4. **Validação dos Modelos**
    - A validação dos modelos é feita utilizando cross-validation e técnicas como MAE (Erro Médio Absoluto) e RMSE (Raiz do Erro Quadrático Médio) para verificar a precisão.
    - Dividimos os dados em conjuntos de treino e teste para evitar overfitting.

5. **Visualização e Relatório**
    - Geramos mapas preditivos da distribuição de microplásticos utilizando ferramentas como QGIS.
    - O relatório final documenta a metodologia, resultados e interpretações.

## Estrutura de Arquivos

A estrutura de arquivos do projeto segue um formato modular para facilitar a organização e o desenvolvimento:

```bash
/
├── README.md               # Este documento
├── data/                   # Diretório com os dados brutos e processados
│   ├── raw/                # Dados brutos não processados
│   ├── processed/          # Dados processados prontos para modelagem
├── notebooks/              # Jupyter notebooks para exploração de dados e modelagem
├── src/                    # Scripts de processamento de dados e modelos
│   ├── preprocessing.py    # Script de pré-processamento de dados
│   ├── train_model.py      # Script para treinar o modelo de aprendizado de máquina
│   └── evaluation.py       # Script para avaliação dos modelos
├── models/                 # Diretório onde os modelos treinados serão armazenados
└── results/                # Resultados das predições e visualizações (mapas, gráficos)
