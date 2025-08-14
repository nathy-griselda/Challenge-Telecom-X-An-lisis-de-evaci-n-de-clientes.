# 📊 Challenge Telecom X: análisis de evasión de clientes
Segundo Challenge de Data Science por Alura Latam G8

Este proyecto consiste en un análisis exploratorio y visual del fenómeno de **churn (evasión de clientes)** usando un dataset proporcionado por una empresa ficticia de telecomunicaciones llamada **Telecom X**.  
El análisis se realizó en Python, utilizando herramientas como `pandas`, `matplotlib`, `seaborn` y `numpy`.

> 💡 El objetivo es identificar qué factores se relacionan más con la cancelación de servicios por parte de los clientes y proponer estrategias de retención basadas en los hallazgos.

---

## 📁 Contenido del proyecto

- Exploración general del dataset.
- Limpieza y transformación de variables.
- Análisis de correlaciones con la variable `churn`.
- Visualización de patrones importantes.
- Generación de nuevas variables (`total_services`).
- Interpretación de resultados y propuesta de acción.

---

## 🧰 Tecnologías y librerías utilizadas

- **Python 3.x**
- **Pandas** – Manipulación y análisis de datos.
- **NumPy** – Operaciones numéricas.
- **Matplotlib** – Visualización básica.
- **Seaborn** – Visualizaciones estadísticas avanzadas.
- **Google Colab** – Entorno de desarrollo.

---

## 📊 Dataset

El dataset incluye información sobre clientes de Telecom X, como:

- Servicios contratados (internet, líneas múltiples, respaldo en línea, etc.).
- Información demográfica (edad, tipo de contrato, género).
- Información de facturación (`account_charges_total`, `account_charges_monthly`).
- Tiempo de permanencia (`customer_tenure`).
- Variable objetivo: `churn` (1 = cliente que se fue, 0 = cliente que sigue).

---

## 🚀 Cómo ejecutar el análisis

1. Abre el archivo `.ipynb` en Google Colab o Jupyter Notebook.
2. Asegúrate de tener las siguientes librerías instaladas:

```bash
pip install pandas matplotlib seaborn numpy
```

3. Ejecuta el notebook desde la primera celda.

---

## 🔍 Estructura del análisis

### 1. Carga y visualización inicial de datos
- Se importan librerías y se cargan los datos desde una fuente externa o archivo.
- Se muestra un resumen con `.info()` y `.head()`.

### 2. Limpieza de datos
- Conversión de variables booleanas y categóricas.
- Eliminación de valores faltantes (`NaN`) en columnas críticas.
- Conversión de la variable `churn` a tipo entero.

### 3. Análisis exploratorio
- Se analiza la distribución de clientes según `churn`.
- Se calculan correlaciones entre `churn` y variables como:
  - `customer_tenure`
  - `account_charges_total`
  - `account_charges_monthly`
  - `Cuentas_Diarias` (aparentemente una métrica de actividad)
- Se visualizan resultados mediante `heatmap`, `boxplot` y `histplot`.

### 4. Creación de nuevas variables
- Se genera la variable `total_services` que suma los servicios activos de cada cliente.

```python
servicios = [
    'phone_phoneservice', 'phone_multiplelines',
    'internet_onlinesecurity', 'internet_onlinebackup',
    'internet_deviceprotection', 'internet_techsupport',
    'internet_streamingtv', 'internet_streamingmovies'
]
```

### 5. Visualización e interpretación
- Gráficos clave:
  - Matriz de correlación (`sns.heatmap`)
  - Distribución de `total_services` según `churn` (`sns.boxplot`)
- Se identifica que clientes con **mayores cargos mensuales** o **menos tiempo con la empresa** tienden a darse de baja con mayor frecuencia.

---

## 📈 Hallazgos principales

- Existe una correlación **negativa moderada** entre `customer_tenure` y `churn`: clientes nuevos tienden más a abandonar.
- Los **clientes que pagan más al mes** tienen más probabilidad de irse (`account_charges_monthly`).
- A mayor número de servicios contratados (`total_services`), **menor es la tasa de churn**.
- Clientes mayores (`seniorcitizen`) también tienen una ligera mayor tendencia al churn.

---

## 🧠 Propuesta de estrategia

Basado en los hallazgos, se propone:

- Ofrecer **bonificaciones o descuentos** a clientes con cargos mensuales altos.
- Implementar una **estrategia de onboarding y seguimiento para nuevos clientes**, especialmente en los primeros meses.
- Incentivar la contratación de más servicios (bundles, combos) como método de fidelización.
- Segmentar campañas de retención enfocadas en clientes con pocos servicios activos o con baja antigüedad.

---

## 📌 Archivos

- `Challenge Telecom X_ análisis de evasión de clientes.ipynb` – Notebook con todo el análisis y visualizaciones.
- `README.md` – Este documento de referencia.

---

## 🧑 Autor

**Nataly Aviña Mejorada**  
Ingeniera Química y estudiante de Ciencia de Datos en Alura Latam
Contacto: nataly.griselda@gmail.com    
LinkedIn: https://mx.linkedin.com/in/nataly-avi%C3%B1a-mejorada-a4aa7913a

---

## 📄 Licencia

Este proyecto se distribuye bajo la licencia MIT. Puedes usarlo, modificarlo y compartirlo libremente con fines educativos o profesionales.
