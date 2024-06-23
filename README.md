# DH Marketing Consultants

[![Power BI](https://img.shields.io/badge/Power%20BI-2.0%2B-yellow.svg)](https://powerbi.microsoft.com/)
[![DAX Studio](https://img.shields.io/badge/DAX%20Studio-3.0%2B-blue.svg)](https://daxstudio.org/)
[![Bravo](https://img.shields.io/badge/Bravo-1.0%2B-red.svg)](https://bravo.bi/)

![DH1](images/DH1.png)

El objetivo es explorar y analizar una serie de datos del departamento de marketing de DH Marketing Consultants utilizando la herramienta `Power BI` y los lenguajes `DAX` y `M` para la creación de un reporte. El director de marketing necesita generar valor a través de estos datos y pide un análisis. El análisis debe basarse en los diferentes factores que podemos medir del dataset. La empresa requiere los datos organizados por fechas, campañas y productos.

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
4. [Medidas](#medidas)
5. [Conclusión](#conclusión)
6. [Autor](#autor)

---
## Dataset
Los datos proporcionados contienen información relacionada con los distintos perfiles de clientes, las campañas de marketing, el montante obtenido por productos vendidos y las plataformas de venta utilizadas junto con otros datos de gran interés que ofrecen un potencial significativo para extraer una gran cantidad de información valiosa.

Los datos han sido obtenidos desde [kaggle](https://www.kaggle.com/datasets/rodsaldanha/arketing-campaign). El contexto se basa en la necesidad de crear un modelo de respuesta que proporcione un impulso significativo a la eficiencia de una campaña de marketing al aumentar las respuestas o reducir los gastos. Pudiendo prever quiénes responderán a una oferta de producto o servicio en base a un perfil, lo cual puede optimizar la estrategia de marketing y maximizar los recursos invertidos en la campaña.


### Clasificación de datos
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

### Extracción
Para la extracción de datos se ha hecho una conexión de orígen desde Power BI hasta el archivo `marketing_campaign.csv` desde `Inicio > Obtener datos > Texto o CSV`.

### Transformación
Después de seleccionar el archivo `marketing_campaign.csv` se ha realizado todo el proceso de `Transformar datos` en el editor de **Power Query** para limpiar y modificar todos los datos que no aportaban ningún valor deseado. Así como la creación de una tabla de hechos y distintas dimensiones para utilizar un esquema de estrella.

### Carga
Una vez aplicados todos los pasos necesarios para obtener los datos con los que se ha trabajado y se han creado la tabla de hechos y las dimensiones, todo ha sido trasladado a Power BI desde `Inicio > Cerrar y aplicar`.

---
## Esquema de estrella
El reporte está estructurado en una tabla de hechos (fact table) que contiene los datos para realizar el análisis, rodeada de las distintas tablas de dimensiones. Obteniendo así una relación 1:* (uno a muchos), donde cada tabla de dimensión tiene una clave primaria simple y la tabla de hechos tiene las claves principales.

### Tabla de hechos
En este caso nuestra tabla de hechos es `fact_Campañas`, donde tenemos todas las claves principales con los datos medibles que han sido utilizados para la creación de las fórmulas `DAX`.

### Tablas de dimensiones
Para las tablas de dimensiones se han creado las siguientes tablas para establecer orden y rango a los datos: `dim_Edad`, `dim_Educación`, `dim_EstadoCivil`, `dim_Hijos`, `dim_Calendario`, `dim_ComprasWeb`, `dim_VisitasWeb`, `dim_ComprasCatálogo`, `dim_Ingresos`, `dim_ÚltimaCompra`, `dim_ComprasDescuento`, `dim_ComprasTienda`.

---
## Medidas
Para la creación de las visualizaciones de datos con gráficos de líneas, gráficos de barras, gráficos de anillos, etc., de cada una de las campañas así como la comparación entre ellas, las compras por producto, las plataformas más utilizadas, etc. se ha creado la tabla `DAX_Medidas`. En esta tabla podemos encontrar los cálculos como la aceptación y la negación de cada una de las campañas realizadas, el total del montante de cada producto, el total de clientes y el salario medio de los clientes, entre otros cálculos.

---
## Conclusión
Como resultado final hemos obtenido un reporte estructurado en tres hojas. Con las siguientes características para cada una de ellas, así como la pisibilidad de filtrar los datos por año, por rango de edad y de ingresos entre otros. 
- **General**: Cuenta con información general acerca del número de clientes y de quejas, el ingreso medio que tienen los clientes y la cantidad total obtenida y la mensual.
- **Campañas**: Información más detallada acerca de cada una de las campañas, con una comparación total entre todas ellas, así como una comparación individual de cada una con la campaña actual.
- **Productos**: Para este hoja tenemos dos visualizaciones totalmente distintas, donde la primera nos permite conocer toda la información acerca del gasto realizado para cada producto y el total de todos ellos. La segunda nos detalla los datos para cada una de las plataformas de venta.

![Logo_DH](images/logo_DH_Marketing.png)

---
## Autor
[Rafel Castelló Fiol (raficadev)](https://github.com/raficadev) - Desarrollador principal
![Banner](https://github.com/raficadev/GESTEC/blob/main/images/CDDDFB2D-7176-4772-A71D-4D6F3BADC7BB.jpeg)
