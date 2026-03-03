# TelecomX-Challenge-parte-2

# 📡 Predicción de Cancelación de Clientes (Customer Churn) - Telecom X parte 2

[Google Colab](https://colab.research.google.com/drive/1Hu8saZBzikw_HFKm_PSZmJpFqJjQ1sYE?usp=sharing).

## 📝 Descripción del Proyecto

Este proyecto es una solución **end-to-end de Machine Learning** desarrollada para Telecom X. El objetivo principal es predecir el *Churn* (cancelación de servicios) analizando datos demográficos, financieros y de comportamiento.

La implementación identifica a los usuarios con alto riesgo de abandono y extrae los factores clave que impulsan esta decisión, permitiendo al equipo de Retención ejecutar acciones proactivas basadas en datos.

---

## ⚙️ Tecnologías y Librerías Utilizadas

| Categoría | Herramientas |
| --- | --- |
| **Lenguaje** | Python |
| **Manipulación de Datos** | `pandas`, `numpy` |
| **Visualización** | `matplotlib`, `seaborn` |
| **Machine Learning** | `scikit-learn` (Logistic Regression, Random Forest) |
| **Balanceo de Datos** | `imblearn` (SMOTE) |

---

## 🧠 Pipeline del Proyecto

### 1. Limpieza y Transformación de Datos

* **Saneamiento:** Manejo de valores nulos y corrección de inconsistencias en columnas.
* **Feature Engineering:** Transformación de variables categóricas mediante **One-Hot Encoding**.
* **Target:** Conversión de la variable objetivo a formato binario ($1$ = Cancela, $0$ = Se queda).

### 2. Análisis Exploratorio de Datos (EDA)

* **Multicolinealidad:** Identificación de variables altamente correlacionadas (ej. `customer_tenure` vs `account_Charges.Total`).
* **Comportamiento Temporal:** Se descubrió que la mayor tasa de fuga ocurre críticamente en los **primeros 15 meses** de servicio.

### 3. Preprocesamiento Avanzado

* **Validación:** División estratificada (80/20) para mantener la proporción de la variable objetivo.
* **SMOTE:** Aplicación de sobremuestreo sintético para corregir el desbalance de clases (**73% retención vs 26% fuga**).
* **Estandarización:** Uso de `StandardScaler` para optimizar modelos basados en gradiente.

### 4. Modelado y Evaluación

Se priorizó la métrica de **Recall (Sensibilidad)** sobre el Accuracy global, debido a que el costo de negocio de un *Falso Negativo* (no detectar a un cliente que se va) es significativamente mayor al de un *Falso Positivo*.

---

## 📊 Resultados y Conclusiones Clave

### Modelo Ganador: **Regresión Logística**

A diferencia de Random Forest, la Regresión Logística demostró una mayor capacidad de generalización y un **Recall superior** en el conjunto de prueba, evitando el overfitting.

### Importancia de Variables (Feature Importance)

* 🟢 **Escudo de Retención:** La **Antigüedad** es el factor protector más fuerte. Clientes que superan los 18 meses tienen una probabilidad de fuga mínima.
* 🔴 **Detonantes de Fuga:** El servicio de **Fibra Óptica** se identificó como el principal impulsor de cancelación, seguido de **Cargos Mensuales elevados** y el uso de **Cheque Electrónico**.

---

## 💡 Recomendaciones de Negocio

* **Fidelización Temprana:** Redirigir esfuerzos de retención exclusivamente a usuarios en sus primeros 12 meses.
* **Auditoría Técnica:** Investigar la estabilidad o el precio del servicio de Fibra Óptica, dado su alto impacto en el Churn.
* **Incentivos Contractuales:** Promover la migración de contratos "mes a mes" a contratos anuales mediante descuentos estratégicos.

---

## 🚀 Cómo utilizar este proyecto

1. Accede al notebook directamente en [Google Colab](https://colab.research.google.com/drive/1Hu8saZBzikw_HFKm_PSZmJpFqJjQ1sYE?usp=sharing).
2. Asegúrate de tener instaladas las dependencias: `pip install pandas scikit-learn imbalanced-learn seaborn`.
3. Ejecuta las celdas en orden para reproducir el pipeline de entrenamiento.

---

**Realizado por** Idabel Coparropa
**Contacto** idabelcoparropa382@gmail.com 

*Se puede utilizar este proyecto para fines educativos siempre y cuando se dé créditos*

