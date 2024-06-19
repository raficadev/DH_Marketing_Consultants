# DH Marketing Consultants

[![Power BI](https://img.shields.io/badge/Power%20BI-2.0%2B-yellow.svg)](https://powerbi.microsoft.com/)
[![DAX Studio](https://img.shields.io/badge/DAX%20Studio-3.0%2B-blue.svg)](https://daxstudio.org/)
[![Bravo](https://img.shields.io/badge/Bravo-1.0%2B-red.svg)](https://bravo.bi/)

El objetivo es explorar y analizar una serie de datos del departamento de marketing de DH Marketing Consultants utilizando Power BI para la creación de un reporte. El director de marketing necesita generar valor a través de estos datos y pide un análisis. El análisis debe basarse en los diferentes factores que podemos medir del dataset. La empresa requiere los datos organizados por fechas, campañas y productos.

> [!NOTE]
> - Limpieza de datos.
> 
> - Transformación de datos.
> 
> - Visualización de datos.

---
## Tabla de Contenidos
1. [Dataset](#dataset)
2. [ETL](#etl)
3. [Esquema de estrella](#esquema-de-estrella)

---
## Dataset
Los datos proporcionados contienen información relacionada con los distintos perfiles de clientes, las campañas de marketing, el montante obtenido por productos vendidos y las plataformas de venta utilizadas junto con otros datos de gran interés que ofrecen un potencial significativo para extraer una gran cantidad de información valiosa.

Los datos han sido obtenidos desde [kaggle](https://www.kaggle.com/datasets/rodsaldanha/arketing-campaign). El contexto se basa en la necesidad de crear un modelo de respuesta que proporcione un impulso significativo a la eficiencia de una campaña de marketing al aumentar las respuestas o reducir los gastos. Pudiendo prever quiénes responderán a una oferta de producto o servicio en base a un perfil, lo cual puede optimizar la estrategia de marketing y maximizar los recursos invertidos en la campaña.


#### Clasificación de datos
Una vez realizada la limpieza y transformación de los datos, se han podido clasificar los 29 campos que conforman el dataset en 4 grupos principales:

<details>
<summary>1. Información personal:</summary>

> ID Cliente
> 
> Año Nacimiento
> 
> Edad
> 
> Educación
> 
> Estado Civil
>
> Ingresos
>
> Hijos
>
> Fecha cliente
</details>

<details>
<summary>2. Comportamiento de compras:</summary>

> Última compra
> 
> Compras Descuento
>
> Compras Web
>
> Compras Catálogo
>
> Compras Tienda
>
> Visitas Web
</details>

<details>
<summary>3. Gastos en productos:</summary>

> Cantidad Vino
>
> Cantidad Fruta
>
> Cantidad Carne
>
> Cantidad Pescado
>
> Cantidad Dulces
>
> Cantidad Oro
</details>

<details>
<summary>4. Campañas de marketing:</summary>

> Campaña 1
>
> Campaña 2
>
> Campaña 3
>
> Campaña 4
>
> Campaña 5
>
> Quejas
>
> Respuesta
>
> Total Campañas Aceptadas
</details>

---
## ETL

#### Extracción
Para la extracción de datos se ha hecho una conexión de orígen desde Power BI hasta el archivo `marketing_campaign.csv` desde `Inicio > Obtener datos > Texto o CSV`.

(pendiente de introducir imagen)

#### Transformación
Después de seleccionar el archivo `marketing_campaign.csv` se ha realizado todo el proceso de `Transformar datos` en el editor de **Power Query** para limpiar y modificar todos los datos que no aportaban ningún valor deseado. Así como la creación de una tabla de hechos y distintas dimensiones para utilizar un esquema de estrella.

#### Carga
Una vez aplicados todos los pasos necesarios para obtener los datos con los que se va a trabajar y se ha creado la tabla de hechos y las dimensiones lo pasamos todo a Power BI desde `Inicio > Cerrar y aplicar`.

---
## Esquema de estrella
