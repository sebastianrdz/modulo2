# Portafolio de Implementación

## Introducción
En este repositorio se presentan todas las evidencias del _Portafolio de Implementación_.
Hay una carpeta nombrada _datasets_ la cual contiene los datos utilizados en cada una de las soluciones.
Se presentan 3 documentos de Google Colab en donde se presentan las soluciones implementadas de cada evidencia.
1. Módulo 1 Construcción de un modelo estadístico base. Archivo: _"Modulo1_Peces&Mercurio.ipynb"_
2. Módulo 2 Implementación de una técnica de aprendizaje máquina sin el uso de un framework. Archivo: _"Modulo2_RegresionLineal(Algoritmo).ipynb"_
3. Módulo 2 Uso de framework o biblioteca de aprendizaje máquina para la implementación de una solución. Archivo: _"Modulo2_NeuralNetwork(Framework).ipynb"_

A continuación se presentan los análisis y conclusiones realizados de cada evidencia.
<br><br>



---
## Módulo 1 Construcción de un modelo estadístico base.
> Archivo: _"Modulo1_Peces&Mercurio.ipynb"_

### Preguntas
- ¿Hay evidencia para suponer que la concentración promedio de mercurio en los lagos es dañina para la salud humana? Considera que las normativas de referencia para evaluar los niveles máximos de Hg (Reglamento 34687-MAG y los reglamentos internacionales CE 1881/2006 y Codex Standard 193-1995) establecen que la concentración promedio de mercurio en productos de la pesca no debe superar los 0.5 mg de Hg/kg.
  > En promedio se presenta una concentración de 0.4mg de Hg/kg. en los productos de pesca, lo cual puede ser considerado seguro para el consumo de las personas. Sin embargo, se presentan la otra mitad de los datos productos de pesca que van del rango de 0.6mg de Hg/kg hasta los 1.2mg de Hg/kg los que pudieran ser considerados excesivamente peligrosos.

- ¿Habrá diferencia significativa entre la concentración de mercurio por la edad de los peces?
  > Sí, la edad tiene gran relación en los niveles de mercurio. En una gráfica presentada previamente podemos ver que la mayor cantidad de peces jóvenes tienden a tener niveles de mercurio más bajos que no superan los 0.4mg. Por otro lado podemos ver que hay pescados adultos que presentan mayores niveles de mercurio superando los 0.5mg como límite.

- Si el muestreo se realizó lanzando una red y analizando los peces que la red encontraba ¿Habrá influencia del número de peces encontrados en la concentración de mercurio en los peces?
  > Considerando únicamente una zona, no tendría mucha influencia ya que sería una variable más controlada para determinar de manera aleatoria los niveles de mercurio en una prueba.

- ¿Las concentraciones de alcalinidad, clorofila, calcio en el agua del lago influyen en la concentración de mercurio de los peces?
  > No tanto, mejor dicho, estas variables se ven distorsionadas a causa de las diferentes concentraciones a través de los productos de pesca.


### Conclusión
- H0: No hay ninguna relación entre los factores analizados y los niveles de mercurio encontrados en los peces.
- H1: Sí hay una relación entre los factores analizados y los niveles de mercurio encontrados en los peces.

Primero que nada, es importante aclarar que no podemos tomar en cuenta todos los datos dado a que hay unos que son similares entre sí lo que siempre nos retorna una correlación, Por ejemplo el mercurio promedio y el mercurio máximo. Estos dos atributos miden lo mismo, por lo que no podemos hacer una relación adecuada entre estos a pesar de tener gran correlación entre sí. Por esta razón, dentro del modelo únicamente se toman en cuenta las variables de alcalinidad, PH, calcio, clorofila y edad (indicador de pescado). Dentro de esta práctica se uno un modelo de de regresion lineal y correlación con el propósito de analizar cómo cada atributo definido anteriormente afecta o tiene relación con base al nivel de mercurio que se encuentra en el pescado.

Podemos concluir que uno de los factores que mayor impacto tiene en la concentración de los pescados es la edad del pescado tal cual. Una de las más grandes correlaciones que puede identificar fue que en su mayoría, los pescados jóvenes tienen una menor concentración de mercurio en comparación con los pescados adultos. Esto puede indicar que los pescados jóvenes han estado en menor contacto con factores externos (Clorofila, calcio, etc.) en comparación a los adultos. Así mismo puede ser algún otro factor de la anatomía del pescado que trasciende en la medida en que envejecen.

Ahora bien, analizando las relaciones de los datos, nuestra hipótesis nula (H0) es rechazada y nuestra hipótesis alternativa _"Sí hay una relación entre los factores analizados y los niveles de mercurio encontrados en los peces."_ es aceptada. Esto dado a que debido a las correlaciones analizadas en la parte superior, podemos ver que hay cuatro factores que afectan los niveles de mercurio en un rango moderado. Estos son la alcalinidad, PH, calcio y clorofila. Estos cuatro factores tienen una correlación moderada entre 0.4 y 0.6 al compararla con el promedio de mercurio encontrado en los peces. Esto indica que estas variables, mientras que no en su totalidad, afectan los niveles de mercurio. Es importante notar que son dependencias negativas, indicando que a medida en que estos factores disminuyen, los niveles de mercurio se incrementan. Las gráficas de de relaciones presentadas son de gran ayuda para identificar y visualizar cómo se comportan las diferentes variables en comparación. La alcalinidad, PH, calcio y clorofila en particular muestran la correlación negativa que se presentan al compararlas con el nivel de mercurio promedio.
<br><br>



---
## Módulo 2 Implementación de una técnica de aprendizaje máquina sin el uso de un framework.
> Archivo: _"Modulo2_RegresionLineal(Algoritmo).ipynb"_

En esta práctica se implementó un modelo de regresión lineal de manera iterativa sin el uso de una librería externa. Unicamente _Pandas_ utilizada para la manipulación del dataset. Teniendo esto, yo soy una persona apasionada por la comida y la salud. Por ese motivo dentro de esta práctica se utiliza el dataset _mc-donalds-menu.csv_ el cual contiene el desglose de la información nutrimental de las principales 260 comidas disponibles en el menú de McDonald 's.

Para hacer una comparación correcta, se analizan dos datos en específico:
- El campo de Calorías
- El campo de Proteínas * 4 (Conversión de gramos de proteína, a calorías por parte de proteína)
Lo que busco es verificar la relación que hay entre las calorías totales de la comida, y las calorías procedentes de únicamente la proteína, y así comparar las raciones entre estas.

En este modelo se implementó un alpha muy bajo de 0.000001 y un theta de estable [1,1] para proceder a entrenar los datos. Esto con el propósito de tratar y obtener los resultados más exactos partiendo de un theta estándar. Viendo los resultados ya entrenados con el modelo visto en clase, nos retorna un theta aproximado de _[0.99, 0.13]_. Esto nos da entender qué de cada 0.99 calorías, 0.13 calorías son de proteína relativamente. Ahora para entender mejor la relación, por cada 99 calorías, 13 calorías son provenientes de proteína.

Teniendo esto me di a la tarea de graficar los modelos totales, entrenamiento y pruebas. Viendo las gráficas nos muestra la relación que hay entre los datos de entrenamiento y de prueba. Ahora dejando esto de lado, hay dos limitantes que puedo visualizar:
- Cantidad muy baja de datos analizados
- elección de datos de entrenamiento y de prueba

Por un lado considero que 260 datos no son suficientes para generar un modelo adecuado que nos permita generar predicciones con base en las calorías de los alimentos, esto puesto que claramente puede haber muchas variaciones en diferentes sectores, culturas, restaurantes, etc.

Así mismo, considero que la selección de datos entre los datos de entrenamiento y los datos de prueba no fue la más óptima. Dentro de este modelo simplemente se dividieron los datos en dos grupos, sin embargo lo correcto sería agrupar estos datos de manera aleatoria que nos permita hacer una comparación adecuada entre los datos de entrenamiento y los datos de prueba.

<br><br>




<!-- El Github incluye la descripción de la entrega (ya sea en el readme o en un documento) y contiene todos los elementos solicitados (librería utilizada, dataset usado, métrica de desempeño (valor logrado sobre el subset de prueba), predicciones de prueba (entradas, valor esperado, valor obtenido), nombre del archivo a revisar) -->
---
## Módulo 2 Uso de framework o biblioteca de aprendizaje máquina para la implementación de una solución.
> Archivo: _"Modulo2_NeuralNetwork(Framework).ipynb"_ <br>
> Google Colab: https://colab.research.google.com/drive/1pCAcCLgTcQzARZNfbk02lUGaU1QECfdc?usp=sharing

Con esta práctica, lo que se busca es entrenar un modelo con el propósito de definir / clasificar de manera correcta las diferentes Clases. Para entrar mejor en contexto, dentro de esta práctica se utiliza un dataset _wines.csv_ el cual tiene información de 178 vinos diferentes. Todos los vinos corresponden a una "clase" según sus atributos. Dentro de la práctica se entrena un modelo con el propósito de definir la clase a la cual pertenece un dado vino tomando en cuenta sus atributos.

Ahora bien en este modelo se implementó la librería Sklearn para para llevar a cabo el modelo nombrado _Neural Network Multi-layer Perceptron classifier_, el cual nos permite modelar con un formato de conexiones neuronales para hacer predicciones.

Como ya mencione, se utilizó el dataset ya definido en este curso de _wines.csv_ para correr las predicciones dentro de este. Como métrica de desempeño se consideró la clase a la que pertenece cada alcohol (1, 2 o 3). 

Para definir los valores de entrenamiento, y los valores de prueba, utilice una librería igualmente de Sklearn para dividir los datos de manera aleatoria. Esto nos da nuestros valores Y y X de entrenamiento al igual que nuestros valores Y y X de prueba. Teniendo nuestros valores inicializamos el modelo ya definido por Sklearn, y lo entrenamos por medio de la función _fit()_ en donde le pasamos nuestros valores X de entrenamiento y prueba. Teniendo esto hacemos una predicción con base a nuestras clases para ajustar el modelo con base a las X.

Teniendo esta predicción acabamos! Podemos visualizar los resultados de dos maneras:
- "confusion_matrix" para representar cómo es que se distribuyen los datos través de las 3 clases que tenemos presentes.
- "classification_report" para representar la correlaciones y el grado de confiabilidad del modelo con base a los datos proporcionados.

En las pruebas realizadas arriba, se puede visualizar que con los datos de entrenamiento obtuvimos un grado de confianza y certeza de 1.00 (100%). Lo que esto no dice es que para cada vino, el modelo fue capaz de agrupar basándose únicamente en los atributos, la clase a la que pertenece dicho vino. Esto lo verifica con los datos de entrada que son el conjunto de atributos, y basados en estos relaciona correctamente el valor esperado (Clase ya definida en el dataset) con el valor obtenido (clase la cual fue predecida por el modelo).
Sin embargo en la pruebas realizadas con los datos de prueba, obtuvimos un 0.97 (97%) de certeza. De manera similar, el modelo logró realizar las mismas predicciones previamente descritas, solo que con un 97% de nivel de confianza. Lo que esto nos dice es que un 3% de las predicciones no va a coincidir el valor esperado con el valor obtenido.

Dicho esto, una limitación de esta prueba considero es el tamaño de la muestra. Wines tiene un conjunto de 178 campos por columna. Teniendo más datos a los que analizar se pudiera realizar un mejor ajuste del modelo y posiblemente una mejor predicción al final el cual nos ayude reducir el porcentaje de error de 3% en el modelo.


