# <h1 align=center>**`Cryptocurrency Data Analytics`**</h1>
## **Contexto**
En los últimos años, el mercado de las criptomonedas ha experimentado un crecimiento exponencial y una creciente adopción a nivel mundial. La aparición del Bitcoin en 2009 marcó el inicio de una revolución financiera que ha llevado a la creación de miles de criptomonedas diferentes con diversas funcionalidades y tecnologías subyacentes.

Con el aumento del interés en el mercado de criptomonedas, cada vez más inversores, empresas y entusiastas buscan comprender mejor el comportamiento y la evolución de estos activos digitales. Sin embargo, la naturaleza altamente volátil y compleja de las criptomonedas presenta desafíos significativos para aquellos que desean tomar decisiones

_En este proyecto se analiza el mercado de criptomonedas en el periodo 2018-2023 con data extraída de la API CoinGecko que busca explicar el comportamiento y las tendencias de sus precios, volúmenes de negociación y capitalizaciones de mercado._ 
<p align="center">
<img src="https://www.telefonica.com/es/wp-content/uploads/sites/4/2022/08/pexels-rodnae-productions-8370752.jpg"  height=300>
</p>

## Contenido

- [Comenzando](#Comenzando)
- [Reporte](#reporte)
- [Extracción, transformación y carga de los datos](#Extracción,-transformación-y-carga-de-los-datos)
- [Análisis y Visualización](#Análisis-y-Visualización)
- [Conclusiones](#Conclusiones)

## **Comenzando** 🚀
El repositorio cuenta con los siguientes archivos: 
1. [`Datasets`](https://github.com/MBernal6/Cryptocurrency_Data_Analytics/tree/main/datasets): Carpeta donde se encuentran los datasets de las criptomonedas analizadas.
2. [`ETL.ipynb`](https://github.com/MBernal6/Cryptocurrency_Data_Analytics/blob/main/ETL.ipynb): Notebook con el proceso de extracción, transformación y carga de datos.
3. [`EDA.ipynb`](https://github.com/MBernal6/Cryptocurrency_Data_Analytics/blob/main/EDA.ipynb): Notebook con el proceso de exploración y análisis de los datos.

_A continuación se detallan los requisitos e instrucciones que te permitirán obtener una copia del proyecto en funcionamiento._
### **Lenguaje y librerias necesarias**
- Python (versión 3.10.)
- Bibliotecas de Python: pandas, matplotlib, seaborn,plotly, pycoingecko

### **Cómo usar el proyecto localmente**

1. Clona este repositorio en tu máquina local.
2. Ejecuta el script de Python para realizar el proceso ETL y EDA en los datos de CoinGecko.
3. Explora los análisis y visualizaciones generadas para comprender el mercado de criptomonedas.
4. Para poder visualizar los gráficos dinamicos hechos con la libreria plotly borra "png" del código de ploteo:
   ```python
   #Asi se encuentra actualmente
   plt.show("png")
   #Asi debe estar
   plt.show()
# **Reporte**
_A continuación se detalla como fue elaborado el proyecto, que criptomonendas se análizaron y las principales conclusiones a las que se llegó tras la exploración de los datos._

## **I. Extracción, transformación y carga de los datos** :wrench:
Con el objetivo de realizar un análisis de las criptomonedas se utilizo la API de ['Coingecko'](https://www.coingecko.com/en/api/documentation) para obtener la data historica del mercado y prepararla para su uso, el proceso realizado 
se encuentra detallado en el archivo [`ETL.ipynb`](https://github.com/MBernal6/Cryptocurrency_Data_Analytics/blob/main/ETL.ipynb) y sigue la siguiente estructura:
### **Extracción de los datos:**
1. Para el presente proyecto se decidio trabajar con 12 criptomonedas y se seleccionaron en base a las siguientes premisas:
- Una demanda continua asegurando la existencia de un mercado, lo cual se verá con el posicionamiento de actual del trade market en coingecko, escogiendo las 10 primeras de este ranking.
- Una estimación de las cryptos con mejor proyección de crecimiento o se catalogan con mejor futuro, las cuales son detalladas en articulo de la página Investing llamado ["Las criptomonedas con más futuro"](https://es.investing.com/academy/crypto/criptomonedas-con-mas-futuro/), de las cuales se escogeran 2.
2. Las criptomonedas escogidas fueron: Bitcoin, Ethereum, Tether, Binancecoin, Ripple, USD-Coin, Staked-ether, Cardano, Solana, Dogecoin, Algorand, Cosmos.
3. Se extrajo los id, precios, volumenes de negociación, capitalización de mercado y fechas diarias de las 12 criptomonedas escogidas en un periodo de 5 años, desde el 15 de Agosto del 2018 al 15 de Agosto del 2023. Este proceso se realizo con la ayuda de la libreria pycoingecko, se encapsularon en diccionarios y posteriormente se transformaron en dataframes para cada moneda.
### **Transformación de los datos y carga de datos:** 
A continuación se detalla el proceso de transformación que se realizo en los dataframes que resultaron del proceso de extracción:
1. Los datos extraidos venian compactados de forma que las columnas Id, Precios, Volumen y Market_Cap tenian como valores listas que compartian las fechas, por lo que se desanido estos datos.
2. Con la idea de poder consolidar los datos en un solo dataframe se añadio la columna ID en cada dataframe.
3. La fecha extraida de CoinGecko venia en formato timestamp por que lo que transformo a formato DateTime.
4. Se consolido toda la información en un solo dataframe. 
5. Para trabajar posteriormente el EDA y poder realizar el Dashboard con Power Bi se crearon los datasets necesarios que se encuentran en [`Datasets`](https://github.com/MBernal6/Cryptocurrency_Data_Analytics/tree/main/datasets).

## **II. Análisis y Visualización** :mag_right:
Durante nuestro análisis, se realizo los siguientes pasos:

1. **Recopilación de Datos:** Carga y exploraración inicial del conjunto de datos que contiene información sobre el precio, volumen y capitalización de mercado de 12 criptomonedas a lo largo de 5 años. Se analizarán valores nulos, valores duplicados y que los datos tengan en formato correcto para su análisis.
<p align="center">
  <img src= "https://github.com/MBernal6/Cryptocurrency_Data_Analytics/assets/115516183/d2beef63-16ca-4ac3-9823-5cf856c99210" height=300>
</p>

2. **Estadísticas Descriptivas:** Cálculo de las estadísticas básicas para cada columna, como la media, mediana y desviación estándar, para tener una visión general de los valores en nuestros datos.

3. **Visualización de Datos:** Para representar los datos de manera efectiva se utiliza gráficos y visualizaciones. Esto incluye gráficos de líneas, histogramas, detección de valores atípicos.
<p align="center">
  <img src= "https://github.com/MBernal6/Cryptocurrency_Data_Analytics/assets/115516183/fb0c1fdf-186b-496b-a57e-9db00d9d17d1" height=300>
</p>

4. **Análisis bivariado, Correlación y Relaciones:** Análisis de las relaciones entre dos variables, la correlación entre las mismas y entre las criptomonedas y se exploró posibles relaciones entre ellas.

## **III. Principales indicadores**
Los indicadores o KPI´s en los cuales se enfoca este proceso de análisis son: 
1. Variación Porcentual del Precio diario: Con este KPI se busca obtener información sobre como fue el comportamiento del precio de una criptomoneda en relación al precio al momento de la evaluación.
2. Volumen Promedio Diario de Negociación: El volumen de negociación diario puede indicar el nivel de actividad y liquidez en el mercado para una criptomoneda específica.
3. Ratio Precio/Capitalización de Mercado: Este KPI puede ayudar a evaluar si una criptomoneda está sobrevalorada, subvalorada o valorada en línea con su capitalización de mercado en comparación con otras monedas en el mercado.

## **Conclusiones**
- El análisis de las desviaciones estandar de los precios de las criptomonedas las califica como activos de alta volatilidad y por lo tanto riesgosos. Sin embargo, sumamente rentables en el largo tiempo. 
- De acuerdo a las desviaciones estandar del volúmen y la capitalización de mercado las criptomonedas muestran un comportamiento con mucha variabilidad, posteriormente en los gráficos se puede apreciar que estos cambios suelen ser estacionales y siguen la tendencia de las criptomonedas más influyentes. 
- Las stablecoins Tether y USD-Coin no siguen el comportamiento volatil en precios, debido a su parida de 1:1 con el dolar. 
- Las distribuciones de las criptomomendas se muestran sesgadas a la derecha con una gran acumulación de sus datos al lado izquierdo de la misma. En las stablecoins sus distribuciones son más simetricas con variaciones de precios tanto a la derecha como la izquierda. 
- Las criptomonedas que no tienen valores **atípicos** en el cohorte realizado son: Bitcoin, Binance coin y Staked-Ether. 
- Ethereum, Ripple, Cardano, Solana, Cosmos, Algorand y DogeCoin muestran varios outliers en sus precios para el lado superior del diagrama. Estos estan explicados por el comportamiento "natural" de las criptomonedas y son reflejados en una tendencia común del mercado que ya fue explicada en en análisis univariado del precio. Es por ello que no serán excluidos a pesar de afectar en la media y desviación estandar.
- Respecto al volúmen de negociación todas las criptomonedas presentan valores atípicos, lo cual es normal entendiendo el dinamismo del mercado. 
- Las variables que muestran mayor correlación entre si son los precios y la capitalización de mercado. 
- Bitcoin y Ethereum muestran correlaciones en todas su variables con el resto de monedas, esto las posiciona como las monedas que requieren mayor vigilancia.
-------------------------------------
## Construido con 🛠️

_Las herramientas para la creación del proyecto fueron las siguientes:_

* [Visual Studio Code](https://code.visualstudio.com/) - IDE.
* [Python](https://www.python.org/) - Lenguaje de programación.
* [Pandas](https://pandas.pydata.org/) - Libreria para análisis de datos.
* [Coingecko](https://www.coingecko.com/en/api/documentation) - API para obtención de datos.
* [Investing](https://www.investing.com/) - Plataforma de noticias financieras.


## Autor ✒️

* **Mauricio Bernal** - *Proyecto Individual N°02-Labs HENRY* - [MBernal6](https://github.com/MBernal6)
* Puedes contactarme a través de [Linkedin](https://www.linkedin.com/in/mauricio-bernal-portocarrero/)
  
## Expresiones de Gratitud 🎁

* Agradecimientos al bootcamp [HENRY](https://www.soyhenry.com/). 
---
⌨️ por [MBernal6](https://github.com/MBernal6) 