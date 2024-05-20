# IC50-prediction
## Notion с материалами
https://www.notion.so/ML-Project-b0aaaf46503e4d00985996a710d5e053
## Предобработка данных
Значения целевой переменной в предоставленном датасете распределены отнюдь не равномерно. В то время, как большинство значений сосредоточены около нуля, несколько отдельных значений IC50 достигают двух и даже трех тысяч. 
![image](https://github.com/Marrinka/IC50-prediction/assets/90869368/86678763-4602-4cea-99ff-cf4b6331a190)

Перед началом обучения мы избавляемся от выбросов и отсекаем все значения, большие 20:
![image](https://github.com/Marrinka/IC50-prediction/assets/90869368/687d4e62-875d-4b60-b805-d0aae76a6690)

## Модели и способы работы со SMILES-представлением

Ниже представлена таблица, демонстрирующая метрики (MSE) на валидационной выборке для каждого из выбранных способов:

|   SMILES preprocessing       | Combination of Linear Layers | CNN + bidirectional GRU | Transformer | Linear regressioon |    CatBoost
|------------------------------|------------------------------|-------------------------|-------------|--------------------|----------------
|------------------------------|     mse       |     r2       |     mse     |    r2     |  mse  |  r2 |    mse   |   r2    |   mse  |   r2
| Morgan's Fingerprints (2D)   |     7.48      |              |             |           |       |     |          |         |        |
| Custom descriptors list (2D) |               |              |             |           |       |     |          |         |        |
| Morgan's Fingerprints + 1D   |               |              |             |           |       |     |          |         |        |
| Custom descriptors list + 1D |      8.6      |    inf       |             |           |       |     |          |         |        |
|               3D             |                              |             |           |       |     |          |         |        |
