# Análisis de Datos Titanic 🛳️

![Imagen titanic](https://github.com/AleDV89/An-lisis_Data_Titanic/blob/main/titanic_foto1.jpg)

### 📝 Resumen:

En este análisis exploratorio, se utilizó la Base de datos del Titanic con el objetivo de extraer, analizar y visualizar los datos utilizando Python 3.x en Visual Studio con Jupyter Notebook. Mediante técnicas de exploración de datos, se buscó comprender mejor la información contenida en el conjunto de datos del Titanic y obtener insights significativos que pudieran contribuir a una comprensión más profunda de este histórico acontecimiento.

### 🧪 Requisitos: 

`pandas` , `numpy` , `seaborn`, `plt`, `os`, `requests` , `PyPDFLoader` , ` Chroma` ,
` ChatOpenAI` , `StrOutputParser` , `RunnablePassthrough` , `gr`, `PdfFileReader`, `BeautifulSoup`

### 🔍 Obtención de Datos:

[Archivo](https://github.com/AleDV89/An-lisis_Data_Titanic/blob/main/titanic.csv)

📚 PDFS:

[PDF1](https://e00-elmundo.uecdn.es/aula/laminas/titanic.pdf)
[PDF2](https://nieonline.com/sentinel/downloads/curricula/titanic.pdf)
[PDF3](https://www.senate.gov/artandhistory/history/resources/pdf/TitanicReport.pdf)
[PDF4](https://www.titanicinquiry.org/downloads/USInq.pdf)

### 🕵️‍♂️ Estructura del proyecto

El proyecto Titanic está compuesto por:
* Procesamiento de datos.
* Limpieza de datos.
* Análisis Exploratorio de Datos (EDA).
* Interpretación de escenarios.

  
#### 📊 Procesamiento de los Datos

* Los datos se cargan en un DataFrame de Pandas y se procede a la lectura del mismo.
 Se inspeccionan los datos y se verifican los nulos con `seaborn`



#### Análisis Exploratorio de Datos (EDA)

La primera interrogante del análisis fue averiguar quienes eran los pasajeros a bordo del Titanic.
Por ello, se realiza la primera pregunta: 

El resultado es igual a 7 bebés. 

La segunda pregunta fue: 
Cuantos niños había a bordo del titanic?

Para determinar cuántos niños había a bordo del Titanic, es importante establecer la definición de "niño" 
según las normas y costumbres de la época, que pueden diferir de las definiciones contemporáneas.

Se extrae la información mediante `WEB SCRAPING`

La respuesta: Comenzaban a trabajar a una edad muy temprana, entre 7 y 8 años. Normalmente realizan labores específicas como vigilar el correcto funcionamiento de las máquinas (portadores de bobinas, devanadores de tramas), engrasar las máquinas.

Por lo que se procede  a considerar a niños desde 1 a 7 años y adultos a partir de 8 años de edad. 


* Otros datos:
- La persona más grande de edad tenia 80 años.
- El promedio de edad de los 891 pasajeros era de 29 años.
- El número de mujeres a bordo era de 288.
- Mientras que el hombres era: 549.

#### También se analizaron los sobrevivientes

Los datos extraidos sobre los sobrevivientes son:

- Sobrevivieron en total: 342 personas
- No sobrevivieron: 549

📝 Ver notebook completo aqui:
[notebook](https://github.com/AleDV89/An-lisis_Data_Titanic/blob/main/Titanic_proy.ipynb)

Fuentes:
- https://nieonline.com/sentinel/downloads/curricula/titanic.pdf
- https://www.titanicinquiry.org/downloads/USInq.pdf

💡Contamos con información interna proporcionada por nuestra base de datos, así como también hemos consultado fuentes externas, como documentos fiables, para obtener información adicional.
Para ello, se ha incoporado instancias de clases dentro de la biblioteca OpenAI para crear un asistente de IA que nos busque información dentro de los pdfs

### Conclusión: 
Al analizar detenidamente los datos del Titanic, destacan varios aspectos intrigantes. En particular, llama la atención la definición de 'niño' en esa época, donde incluso a partir de los 7 años algunos ya trabajaban en fábricas, lo que plantea cuestiones sobre la percepción histórica de la niñez. Nuestra base de datos revela que, en el desafortunado evento, sobrevivieron un número significativo de niños de diversas clases: 2 de primera clase, 15 de segunda clase y 17 de tercera clase. Sin embargo, contrastando con los datos de los PDFs consultados, donde se estima que solo sobrevivieron aproximadamente 4 niños, surge una notable discrepancia. Además, resalta el hecho de que las mujeres fueron el grupo con mayor índice de supervivencia, subrayando posibles prioridades en la evacuación. Estos descubrimientos arrojan luz sobre la complejidad y las divergencias en la narrativa de la tragedia del Titanic, subrayando la importancia de una evaluación exhaustiva de múltiples fuentes para obtener una comprensión más completa de los eventos históricos.






