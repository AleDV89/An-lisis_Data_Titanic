# Análisis de Datos Titanic 🛳️

![Imagen titanic](https://github.com/AleDV89/An-lisis_Data_Titanic/blob/main/titanic_foto1.jpg)

### 📝 Resumen:

Se realiza un análisis exploratorio con Data Set del Titanic con el objetivo de extraer, analizar y visualizar los datos con Python 3.x.

### 🧪 Requisitos: 

`pandas` , `numpy` , `seaborn`, `plt`, `os`, `requests` , `PyPDFLoader` , ` Chroma` ,
` ChatOpenAI` , `StrOutputParser` , `RunnablePassthrough` , `gr`, `PdfFileReader`, `BeautifulSoup`

### 🔍 Obtención de Datos:

![Archivo](https://github.com/AleDV89/An-lisis_Data_Titanic/blob/main/titanic.csv)
📚 PDFS:
![PDFS](https://github.com/AleDV89/An-lisis_Data_Titanic/tree/main/'PDFS)

### 📊 Procesamiento de los Datos

* Los datos se cargan en un DataFrame de Pandas y se procede a la lectura del mismo.
 Se inspeccionan los datos y se verifican los nulos con `seaborn`

![NULOS](https://github.com/AleDV89/An-lisis_Data_Titanic/blob/main/'GRAFICOS/HEATMAP.png)

* Verificación de los nulos en %

  ```python
df.isnull().sum()/len(df)*100


``

El resultado señala: 20% en 'Age' y 77% en 'Cabin'



