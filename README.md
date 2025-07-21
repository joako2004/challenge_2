# Churn Prediction Pipeline

## 📋 Descripción del Proyecto

Construcción de un pipeline de Machine Learning para predecir la probabilidad de cancelación (churn) de clientes de un servicio de telecomunicaciones. El objetivo es anticipar quiénes podrían darse de baja y proponer estrategias de retención basadas en los hallazgos.

---

## 🎯 Objetivos

1. Preparar datos:
   - Eliminar identificadores irrelevantes.
   - Codificar categóricas con One‑Hot Encoding.
   - Imputar valores faltantes y transformar tipos.
   - Balancear clases con SMOTE.
2. Seleccionar variables:
   - Matriz de correlación.
   - Filtrar por correlación absoluta ≥ 0.2 con `Churn`.
   - Análisis dirigido con boxplots y countplots.
3. Entrenar y evaluar dos modelos:
   - Árbol de Decisión (max\_depth).
   - Random Forest (max\_depth).
4. Medir desempeño con métricas:
   - Accuracy, Precision, Recall, F1‑Score.
   - Matriz de confusión.
   - Detección de over/underfitting.
5. Interpretar resultados:
   - Importancia de variables.
   - Insights y propuestas de retención.

---

## 🔧 Instalación

1. Clonar repositorio
   ```bash
   git clone https://github.com/tu-usuario/churn-prediction.git
   cd churn-prediction
   ```
2. Crear entorno e instalar dependencias
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```

---

## 📊 Resultados Clave

- **Decision Tree (max\_depth=4)**

  - Accuracy: 0,78
  - Precisión: 0,62
  - Recall: 0,43
  - F1‑Score: 0,51

- **Random Forest (n\_estimators=100, max\_depth=6)**

  - Accuracy: 0,80
  - Precisión: 0,69
  - Recall: 0,38
  - F1‑Score: 0,49

**Factores Más Influyentes**

| Árbol de Decisión (top 3)                 | Random Forest (top 3)                     |
| ----------------------------------------- | ----------------------------------------- |
| 1. `internet_TechSupport`                 | 1. `customer_tenure`                      |
| 2. `customer_tenure`                      | 2. `internet_TechSupport`                 |
| 3. `internet_InternetService_Fiber optic` | 3. `internet_InternetService_Fiber optic` |

---

## 💡 Estrategias de Retención

1. **Potenciar el Soporte Técnico**

   - Onboarding proactivo y atención 24/7.
   - Llamadas de bienvenida y tutoriales guiados.

2. **Programas de Fidelización Temprana**

   - Descuentos o beneficios en primeros 3 meses.
   - Comunicación personalizada.

3. **Incentivos a Contratos Largos**

   - Ofertas “Two Year” con descuentos.
   - Upgrades gratuitos al renovar.

4. **Optimizar Oferta de Fibra Óptica**

   - SLA claros y monitoreo activo.
   - Bundles con streaming incluido.

5. **Flexibilizar Métodos de Pago**

   - Incentivos para domiciliación bancaria.
   - Recordatorios previos al cobro.

6. **Segmentación por Nivel de Factura**

   - Planes ajustados a facturas altas.
   - Revisar experiencia de cargos bajos.

---

## 🔭 Futuras Mejoras

- Optimizar hiperparámetros con `GridSearchCV`.
- Incluir modelos de boosting (XGBoost, LightGBM).
- Validación cruzada anidada y curvas de aprendizaje.
- Pipeline de inferencia en producción (FastAPI).
