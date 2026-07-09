# 📊 Análisis de Ventas B2B y Detección Temprana de Churn Rate (Sector Gastronómico)

## 📌 Contexto del Proyecto
Este proyecto analiza el comportamiento de compra de una cartera de clientes B2B (empresas gastronómicas, panificadoras y cafeterías) para optimizar la toma de decisiones comerciales. 

El desafío principal consistió en procesar un registro transaccional crudo que presentaba problemas típicos de bases de datos reales: 
Registros corruptos por errores de sistema, métodos de pago inconsistentes y valores nulos.

## 🛠️ Stack Tecnológico
* **Lenguaje:** Python
* **Procesamiento y Limpieza de Datos:** Pandas, NumPy
* **Visualización:** Matplotlib, Seaborn

## 🧹 Limpieza y Transformación de Datos (ETL)
Para asegurar la calidad del análisis, se realizó un preprocesamiento exhaustivo:
1. **Manejo de Errores de ERP:** Se identificaron y aislaron fallas de registro del sistema origen (logs de error de Ruby en columnas transaccionales).
2. **Normalización:** Se estandarizaron los métodos de pago ingresados con texto libre mediante diccionarios y métodos de string.
3. **Ingeniería de Características (Feature Engineering):** Se construyó la métrica de **Ingreso Total Real**, calculando la facturación por transacción neta de descuentos aplicados.

## 📈 Hallazgos Clave de Negocio (EDA)

### 1. Concentración de la Facturación
Se analizó el Top 10 de clientes para entender la dependencia comercial de la empresa.
<img width="736" height="434" alt="image" src="https://github.com/user-attachments/assets/bdbcb959-4b96-45e7-aa60-03dd5e9758d2" />


### 2. Estacionalidad de las Ventas
Se evaluó la evolución de los ingresos mensuales para identificar patrones de demanda y picos de venta.
<img width="879" height="354" alt="image" src="https://github.com/user-attachments/assets/62d36b65-ac82-41ac-aca1-65da4318f684" />


### 3. Modelo de Retención: Cálculo del Churn Rate
En el rubro B2B, retener un cliente es crítico. Dado que la base de datos no indicaba explícitamente el abandono, se construyó un modelo basado en la **Recencia** de compra:
* Se calculó la cantidad de días de inactividad por cada cliente.
* Se estableció un umbral de negocio de **60 días sin compras** para clasificar a una cuenta como Churn.
* **Resultado:** *4 clientes son Churn con una tasa de abandono entre 61 y 158 días*.

## 🚀 Próximos Pasos Posibles
* Implementar un análisis RFM (Recencia, Frecuencia, Valor Monetario) completo.
* Desarrollar un modelo de Machine Learning (ej: Random Forest) para predecir la probabilidad de fuga de clientes activos.



todos los datos utilizados en este desarrollo son ficticios.
