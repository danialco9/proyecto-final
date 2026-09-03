# Instrucciones del Proyecto

## Alcance de trabajo
- Trabajar solo dentro de la carpeta `proyecto final`.
- No modificar `data/raw/`; contiene el dataset original y debe conservarse intacto.
- Antes de hacer cambios, explicar que se va a hacer y por que, y esperar confirmacion del usuario.

## Contexto
Este proyecto es un TFG / Fin de Master: un sistema inteligente para predecir el riesgo de lesion en deportistas amateurs usando Machine Learning.

La demo principal esta hecha en Streamlit. El usuario introduce datos de perfil, entrenamiento, recuperacion, sueno y nutricion. El sistema devuelve:
- Score de riesgo de 0 a 100.
- Clasificacion BAJO / MEDIO / ALTO.
- Factores principales de riesgo.
- Recomendaciones personalizadas.

## Fuente principal de informacion
- Para decisiones de alcance, documentacion, defensa, guion, presentacion y siguientes pasos, usar principalmente los PDF de `docs/`.
- Especialmente relevantes:
  - `docs/guia_presentacion_final.pdf`: enfoque de la defensa, producto funcionando, valor, datos, resultados y limitaciones.
  - `docs/Plan de Trabajo TFG.pdf`: fases, hitos, tareas y entregables previstos.
  - `docs/diagrama de flujo final.pdf`: flujo funcional esperado del MVP.
  - `docs/prediccion.pdf`: material visual/conceptual de apoyo.
- `README.md`, `CLAUDE.md`, notebooks y app sirven como apoyo tecnico, pero los PDF mandan para documentacion final y defensa.

## Estado actual
- Estructura del proyecto creada.
- Dataset original disponible en `data/raw/`.
- Notebooks completos:
  - `notebooks/01_EDA.ipynb`
  - `notebooks/02_Features.ipynb`
  - `notebooks/03_Modelos.ipynb`
- App Streamlit completa en `app/app.py`.
- Modelos entrenados guardados en `models/`.

## Modelo activo
- Modelo elegido: XGBoost.
- Archivo principal: `models/mejor_modelo.pkl`.
- Scaler: `models/scaler.pkl`.
- Columnas esperadas: `models/feature_columns.pkl`.
- Nombre del modelo: `models/mejor_modelo_nombre.pkl`.
- Numero de features: 23.

Resultados documentados:

| Modelo | Accuracy | ROC-AUC |
|---|---:|---:|
| Regresion Logistica | 0.933 | 0.997 |
| Random Forest | 0.973 | 1.000 |
| XGBoost | 0.960 | 0.999 |
| Ensemble | 0.960 | 0.999 |

## Siguiente fase
La siguiente fase indicada por el proyecto es B6: testing y validacion de la app.

Despues vendra B7: documentacion final, memoria y slides.

## Estructura relevante
```text
proyecto final/
  app/
    app.py
  data/
    raw/
      collegiate_athlete_injury_dataset.csv
    processed/
      train.csv
      validation.csv
      test.csv
      *.png
  docs/
    *.pdf
  models/
    *.pkl
  notebooks/
    01_EDA.ipynb
    02_Features.ipynb
    03_Modelos.ipynb
  README.md
  CLAUDE.md
  requirements.txt
```

## Criterios para futuras tareas
- Priorizar que la demo funcione bien para defensa en vivo.
- No centrarse en explicar codigo linea a linea si la tarea esta relacionada con la defensa.
- Validar carga de modelos, predicciones y visualizacion Streamlit antes de dar por terminada la app.
- Documentar claramente limitaciones: dataset pequeno, datos sinteticos de sueno/nutricion y ausencia de series temporales para ACWR.
- Mantener el stack actual: Python, pandas, numpy, scikit-learn, xgboost, imbalanced-learn, matplotlib, seaborn, plotly, streamlit y joblib.
