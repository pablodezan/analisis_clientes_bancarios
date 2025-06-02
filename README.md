Análisis de Clientes Bancarios

Este proyecto explora el comportamiento de una cartera de clientes de una entidad bancaria ficticia, con el objetivo de identificar patrones de retención y abandono (churn), perfiles financieros y características por país. El análisis se realizó combinando consultas SQL, DAX en Power BI y visualizaciones interactivas. El objetivo fue construir un tablero de control que pueda ayudar a la toma de decisiones.

---

📄 Dataset utilizado

Archivo CSV con información de 10.000 clientes:

* Identificación
* Score crediticio
* País
* Género, edad, antigüedad
* Balance, salario estimado
* Número de productos, tarjeta de crédito, miembro activo
* Churn: 1 (se fue), 0 (se quedó)

---

📊 Objetivos del Proyecto

1. Cargar los datos a una base MySQL
2. Responder consultas clave usando SQL
3. Crear vistas SQL para conectarlas a Power BI
4. Aplicar medidas con DAX para análisis y KPIs
5. Construir un dashboard profesional
6. Documentar el proceso como portfolio profesional

---

📈 Tecnologías utilizadas

* MySQL (estructura, consultas y vistas)
* Power BI (DAX y visualizaciones)
* Git + GitHub (versionado y documentación)

---

📃 Consultas SQL realizadas

Se realizaron consultas básicas para exploración inicial:

-- Total de clientes
SELECT COUNT(*) FROM clientes;

-- Churn vs retenidos
SELECT churn, COUNT(*) FROM clientes GROUP BY churn;

-- Clientes por país
SELECT country, COUNT(*) FROM clientes GROUP BY country;

-- Saldo promedio
SELECT ROUND(AVG(balance), 2) FROM clientes;

-- Salario promedio
SELECT ROUND(AVG(estimated_salary), 2) FROM clientes;


Vistas creadas:

* vista\_churn\_totales
* vista\_clientes\_pais
* vista\_saldo\_promedio
* vista\_salario\_promedio

Estas vistas se utilizaron para facilitar el análisis en Power BI.

---

📊 Medidas DAX utilizadas

Se crearon varias medidas con DAX para enriquecer el dashboard:

Clientes Totales = COUNTROWS(clientes)
Clientes Activos = CALCULATE(COUNTROWS(clientes), clientes[active_member] = 1)
Clientes con Tarjeta = CALCULATE(COUNTROWS(clientes), clientes[credit_card] = 1)
Saldo Promedio = AVERAGE(clientes[balance])
Salario Promedio = AVERAGE(clientes[estimated_salary])
Edad Promedio = AVERAGE(clientes[age])

---

## 🌐 Visualizaciones en Power BI

* Tarjetas: total de clientes, activos, con tarjeta
* Gráfico de área: evolución temporal de clientes por país
* Dona: distribución por rango etario
* Tabla: saldo promedio mensual por país
* Mapa: ubicación geográfica
* Segmentadores: país, año, retención

---

## 📁 Estructura del proyecto

.
├── sql
│   └── vistas.sql
├── powerbi
│   └── dashboard.pbix
├── data
│   └── bank_customers.csv
└── README.md

---
🚀 Conclusiones

* La mayoría de los clientes se concentra entre 26 y 45 años
* El país con mayor tasa de churn fue Alemania
* Los clientes con tarjeta o más productos tienen menor churn
* El balance y el salario presentan alta variabilidad
* El dashboard permite explorar la cartera de clientes desde distintas dimensiones



🚜 Autor

**Pablo Dezan**
Analista de Datos

