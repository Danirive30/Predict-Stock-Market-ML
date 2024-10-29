# Predicción del S&P 500 con Machine Learning

Este proyecto utiliza datos históricos del S&P 500 para predecir tendencias en el precio de cierre diario del índice, aplicando técnicas de aprendizaje automático, específicamente un modelo de Random Forest. A partir de datos obtenidos con la librería `yfinance`, se entrenan y prueban modelos para anticipar la dirección del mercado en base a varios indicadores.

## Contenido del Proyecto

1. **Descarga de Datos**: Obtiene y guarda los datos históricos del índice S&P 500 utilizando la API `yfinance`. Si los datos ya están almacenados en un archivo `csv`, se carga directamente desde el archivo para optimizar tiempos.

2. **Preparación de Datos**:
   - Calcula y añade columnas de predicción (`Tomorrow` y `Target`) para definir la dirección del mercado.
   - Genera nuevos indicadores (`Close_Ratio`, `Trend`) basados en promedios móviles y tendencias acumuladas, a lo largo de distintos horizontes temporales (2, 5, 60, 250, 1000 días).
   - Limpia y transforma el conjunto de datos para que sea apto para el modelo.

3. **Modelo de Machine Learning**:
   - Entrena un modelo de **Random Forest** usando datos históricos.
   - Separa el conjunto de datos en entrenamiento y prueba para evaluar el rendimiento del modelo.
   - Evalúa la precisión del modelo, específicamente usando la métrica de `precision_score`.

4. **Backtesting**: 
   - Realiza un backtest con pasos de ventana móviles para evaluar el rendimiento del modelo sobre el tiempo, simulando un entorno de trading continuo.
   - Los resultados se analizan visualmente y mediante estadísticas para ajustar el modelo.

## Estructura de Archivos

- **`sp500.csv`**: Archivo de datos históricos del S&P 500.
- **`main.py`**: Código principal para la obtención de datos, entrenamiento del modelo y predicción.
- **`README.md`**: Descripción del proyecto (este archivo).

## Requisitos

- **Python 3.x**
- **yfinance**: Para la descarga de datos de mercado.
- **pandas**: Para la manipulación de datos.
- **scikit-learn**: Para los modelos de Machine Learning.

Instala las dependencias con:
```bash
pip install yfinance pandas scikit-learn
```


# Predict-Stock-Market-ML
