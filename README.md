# Proyecto de Recuperación de Oro  

## Descripción del proyecto  

Este proyecto aborda el problema de **predecir la recuperación de oro** en una planta de procesamiento.  
La meta es optimizar el proceso tecnológico, mejorando la eficiencia en la obtención de concentrados y reduciendo pérdidas.  

Se trabajó con un dataset que incluye múltiples características del proceso de flotación y purificación, y se desarrollaron modelos de machine learning capaces de predecir:  

- **Recuperación del concentrado Rougher** (`rougher.output.recovery`)  
- **Recuperación final del concentrado** (`final.output.recovery`)  

---

## Proceso tecnológico  

El oro se obtiene a partir del mineral extraído mediante las siguientes etapas:  

1. **Flotación**  
   - La mezcla de mineral de oro se introduce en las plantas de flotación para obtener:  
     - **Concentrado Rougher** (oro con alta concentración).  
     - **Colas Rougher** (residuos con baja concentración de metales).  
   - La estabilidad de este proceso puede verse afectada por condiciones físico-químicas de la pulpa de flotación.  

2. **Purificación**  
   - El concentrado Rougher pasa por dos etapas de purificación.  
   - Como resultado se obtiene el **concentrado final** y las nuevas colas.  

---

## Metodología  

- Se probaron distintos algoritmos de regresión.  
- El mejor desempeño se alcanzó utilizando **XGBoost** con búsqueda de hiperparámetros.  
- La métrica utilizada fue **sMAPE (Symmetric Mean Absolute Percentage Error)**.  

---

## Resultados  

Mejores modelos encontrados:  

- **Rougher** → `best_model_rougher_xgboost`  
  - sMAPE(Rougher) = **5.37%**  
  - Hiperparámetros: `n_estimators=40`, `max_depth=3`, `learning_rate=0.1`  

- **Final** → `best_model_final_xgboost`  
  - sMAPE(Final) = **8.34%**  
  - Hiperparámetros: `n_estimators=20`, `max_depth=4`, `learning_rate=0.1`  

Cálculo global:  

\[
sMAPE_{final} = 7.59\%
\]

---

## Conclusiones  

- Los modelos predicen con un error promedio relativo del **7.59%**, considerado **muy satisfactorio** para el contexto industrial.  
- Se demuestra que es posible anticipar con buena precisión tanto la recuperación del concentrado Rougher como la recuperación final.  
- Este nivel de precisión puede apoyar la **toma de decisiones en tiempo real**, permitiendo:  
  - Ajustar parámetros operativos.  
  - Optimizar el rendimiento del proceso.  
  - Reducir pérdidas de oro durante la producción.  

---

## Habilidades desarrolladas en el proyecto  

- Preprocesamiento de datos industriales complejos.  
- Implementación y validación de modelos de **machine learning** (XGBoost).  
- Optimización de hiperparámetros y evaluación con **validación cruzada**.  
- Uso de métricas especializadas (sMAPE).  
- Comunicación de resultados y análisis de impacto para la operación industrial.  

---

