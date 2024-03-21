# Análisis de Datos Titanic 🛳️

![Imagen titanic](https://github.com/AleDV89/An-lisis_Data_Titanic/blob/main/titanic_foto1.jpg)

### 📝 Resumen:

Se realiza un análisis exploratorio con Data Set del Titanic con el objetivo de extraer, analizar y visualizar los datos con Python 3.x. en Visual Studio con Jupyter Notebook. 

### 🧪 Requisitos: 

`pandas` , `numpy` , `seaborn`, `plt`, `os`, `requests` , `PyPDFLoader` , ` Chroma` ,
` ChatOpenAI` , `StrOutputParser` , `RunnablePassthrough` , `gr`, `PdfFileReader`, `BeautifulSoup`

### 🔍 Obtención de Datos:

[Archivo](https://github.com/AleDV89/An-lisis_Data_Titanic/blob/main/titanic.csv)

📚 PDFS:

[PDFS](https://github.com/AleDV89/An-lisis_Data_Titanic/tree/main/'PDFS)

### 🕵️‍♂️ Estructura del proyecto
El proyecto Titanic está compuesto por:
* Procesamiento de datos.
* Limpieza de datos.
* Análisis Exploratorio de Datos (EDA).
* Interpretación de escenarios.

  
#### 📊 Procesamiento de los Datos

* Los datos se cargan en un DataFrame de Pandas y se procede a la lectura del mismo.
 Se inspeccionan los datos y se verifican los nulos con `seaborn`

![NULOS](https://github.com/AleDV89/An-lisis_Data_Titanic/blob/main/'GRAFICOS/HEATMAP.png)

* Verificación de los nulos en %
```python
df.isnull().sum()/len(df)*100

```
El resultado señala: 20% en 'Age' y 77% en 'Cabin'

* Verificación de tipos de datos
```python
df.dtypes
```

* Verificación de datos duplicados
```python
df.duplicated().sum()
```

Resultado = 0 , no existen archivos duplicados.

* Cantidad de filas y columnas
```python
df.shape
```

#### 🧹 Limpieza de Datos

La columna 'Cabin' cuenta con 77% de nulos por lo que se procederá a eliminarse. En cambio la columna 'Age' 19,8% y se procede a repararlo 

(ver codigos aqui) 

#### Análisis Exploratorio de Datos (EDA)

La primera interrogante del análisis fue averiguar quienes eran los pasajeros a bordo del Titanic.
Por ello, se realiza la primera pregunta: 

* Cuantos bebes había a bordo del titanic?
```python
bebes = df_copia[df_copia['Age'] < 1]
```
```python
total_bebes = len(bebes)
```

El resultado es igual a 7 bebés. 

La segunda pregunta fue: 
Cuantos niños había a bordo del titanic?

Para determinar cuántos niños había a bordo del Titanic, es importante establecer la definición de "niño" 
según las normas y costumbres de la época, que pueden diferir de las definiciones contemporáneas.

Se extrae la información mediante `WEB SCRAPING`
```python
response = requests.get(URL)
if response.status_code == 200:
    soup = BeautifulSoup(response.text, "html.parser")
content_div = soup.find('div', {'id': 'mw-content-text'})
paragraphs = content_div.find_all('p')[3]

for paragraph in paragraphs:
        print(paragraph.text)

else:
    print('No se pudo acceder a la página de Wikipedia')

```

La respuesta: Comenzaban a trabajar a una edad muy temprana, entre 7 y 8 años. Normalmente realizan labores específicas como vigilar el correcto funcionamiento de las máquinas (portadores de bobinas, devanadores de tramas), engrasar las máquinas.

Por lo que se procede  a considerar a niños desde 1 a 7 años y adultos a partir de 8 años de edad. 

![niños_bebes](https://github.com/AleDV89/An-lisis_Data_Titanic/blob/main/'GRAFICOS/ni%C3%B1os%20y%20bebes%20a%20bordo.png)

En el gráfico se observa la cantidad de niños y bebés a bordo.

* Otros datos:
- La persona más grande de edad tenia 80 años.
- El promedio de edad de los 891 pasajeros era de 29 años.
- El número de mujeres a bordo era de 288.
- Mientras que el hombres era: 549.

![Grafico_pasajeros](https://github.com/AleDV89/An-lisis_Data_Titanic/blob/main/'GRAFICOS/grafico_pasajeros.png)

#### También se analizaron los sobrevivientes

Los datos extraidos sobre los sobrevivientes son:

- Sobrevivieron en total: 342 personas
- No sobrevivieron: 549

* Se inicia comparación de datos internos y externos.
  Para ello, se utiliza 
```python
llm = ChatOpenAI(model="gpt-3.5-turbo-1106", temperature=0)
```

(Ver más en el NB)

Se importan los pdfs y se hace la primera consulta 
```python
ans = chain.invoke("cuantos pasajeros sobrevivieron?")

print(ans)
```

La respuesta es: 
¡Hola! Según los informes, el Carpathia rescató a 705 sobrevivientes del Titanic. Trágicamente, se perdieron 1,502 vidas en el desastre. Por lo tanto, el número de pasajeros que sobrevivieron fue de 705.

Fuentes:
- https://nieonline.com/sentinel/downloads/curricula/titanic.pdf
- https://www.titanicinquiry.org/downloads/USInq.pdf

💡Contamos con información interna proporcionada por nuestra base de datos, así como también hemos consultado fuentes externas, como documentos fiables, para obtener información adicional.

Siguiendo con el análisis, tambien se verifica cuantas mujeres y cuantos hombres sobrevivieron. 
![Grafico_myh](https://github.com/AleDV89/An-lisis_Data_Titanic/blob/main/'GRAFICOS/sobrevivintes_por_sexo.png)

y además, se le consulta en los PDFS la misma información. 

```python

ans = chain.invoke("Quienes sobrevivieron? Más hombres o mujeres?")

print(ans)

```

¡Hola! Según los documentos proporcionados, hubo un total de 750 personas salvadas del Titanic, de las cuales 210 pertenecían a la tripulación. De esos 210, solo 15 eran mujeres. Además, de los pasajeros de primera clase, sobrevivieron 131 mujeres y 68 hombres. De los pasajeros de segunda clase, sobrevivieron 106 mujeres y niños, y 12 hombres. Y de los pasajeros de tercera clase, sobrevivieron 93 mujeres y 85 hombres. Por lo tanto, en general, sobrevivieron más mujeres que hombres. 

Fuentes:
- https://www.titanicinquiry.org/downloads/USInq.pdf (páginas 555, 428, 21, 1003)
 Se confirma que fueron más mujeres las que sobrevivieron. 

### Mapa de los tres puertos

![Mapa](https://github.com/AleDV89/An-lisis_Data_Titanic/blob/main/'GRAFICOS/mapa_puertos.png)

 El Titanic zarpó de tres puertos en su primer y único viaje.
⚫ En los puntos negros se observa los dos puertos: Southampton en Gran Bretaña y Queenstown en Irlanda.
🔵 En este punto se observa el puerto Cherbourg en Francia.

### Conclusión: 


