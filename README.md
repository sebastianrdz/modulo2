# Portafolio de Implementacion
## Momento de Retroalimentación: Módulo 1 Construcción de un modelo estadístico base (Portafolio Implementación)
### Mercurio
Preguntas
<br>
¿Hay evidencia para suponer que la concentración promedio de mercurio en los lagos es dañino para la salud humana? Considera que las normativas de referencia para evaluar los niveles máximos de Hg (Reglamento 34687-MAG y los reglamentos internacionales CE 1881/2006 y Codex Standard 193-1995) establecen que la concentración promedio de mercurio en productos de la pesca no debe superar los 0.5 mg de Hg/kg.
- En promedio se presenta una concentración de 0.4mg de Hg/kg. en los productos de pesca, lo cual puede ser considerado seguro para el consumo de las personas. Sin embargo, se presentan la otra mitad de los datos productos de pesca que van del rango de 0.6mg de Hg/kg hasta los 1.2mg de Hg/kg los que pudieran se considerados excesivamente peligrosos.

¿Habrá diferencia significativa entre la concentración de mercurio por la edad de los peces?
- Sí, la edad tiene gran relación en los niveles de mercurio. En una grafica presentada previamente podemos ver que la mayor cantidad de peces jóvenes tienden a tener niveles de mercurio mas bajos que no superan los 0.4mg. Por otro lado podemos ver que hay pescados adultos que presentan mayores niveles de mercurio superando los 0.5mg como limite.

Si el muestreo se realizó lanzando una red y analizando los peces que la red encontraba ¿Habrá influencia del número de peces encontrados en la concentración de mercurio en los peces?
- Considerando únicamente una zona, no tendría mucha influencia ya que seria una variable más controlada para determinar de manera aleatoria los niveles de mercurio en una prueba.

¿Las concentraciones de alcalinidad, clorofila, calcio en el agua del lago influyen en la concentración de mercurio de los peces?
- No tanto, mejor dicho, estas variables se ven distorsionadas a causa de las diferentes concentraciones a través de los productos de pesca.


Conclusión
- H0: No hay ninguna relación entre los factores analizados y los niveles de mercurio encontrados en los peces.
- H1: Sí hay una relación entre los factores analizados y los niveles de mercurio encontrados en los peces.
<br>

Podemos concluir que uno de los factores que mayor impacto tiene en la concentración de los pescados es la edad del pescado tal cual. Una me las más grandes correlaciones que puede identificar fue que en su mayoría, los pescados jóvenes tienen una menor concentración de mercurio en comparación de los pescados adultos. Esto puede indicar que los pescados jóvenes han estado en menor contacto con factores externos (Clorofila, calcio, etc.) en comparación a los adultos. Así mismo puede ser algún otro factor de la anatomía del pescado que trasciende en medida en que envejecen.
<br> 

Ahora bien, analizando las relaciones de los datos, nuestra hipótesis nula (H0) es rechazada y nuestra hipótesis alternativa aceptada. Esto dado a que debido a las correlaciones analizadas en la parte superior, podemos ver que hay cuatro factores que afectan los niveles de mercurio en un rango moderado. Estos son la alcalinidad, PH, calcio y clorofila. Estos cuatro factores tienen una correlación moderada entre 0.4 y 0.6 al compararla con el promedio de mercurio encontrado en los peces. Esto indica que estas variables, mientras que no en su totalidad, afectan los niveles de mercurio. Importante notar que son dependencias negativas, indicando que a medida en que estos factores diminuyen, los niveles de mercurio incrementan.

<br><br>

## Momento de Retroalimentación: Módulo 2 Implementación de una técnica de aprendizaje máquina sin el uso de un framework. (Portafolio Implementación)
### Regresion Lineal
Dentro de este documento se puede ver la implementación de el modelo de regresión lineal. De este modo implementamos un alpha muy bajo de 0.000001 y un theta de estable [1,1] para proceder a entrenar los datos. Los datos procedentes son del menu de comida de McDonalds, del cual comparamos las calorías totales de cada comida individual, con las calorías procedentes únicamente de la proteína. Esto nos permite visualizar la relación entre las calorías y la proteína si es que hay una presente. y por lo visto en el análisis, sí hay una gran relación entre estas dos variables.
<br>
Tras Analizar esta base de datos y correr diferentes escenarios por mi cuenta, pude concluir que sí hay una relación entre las calorías y las proteínas de cada comida de manera individual. Dicho esto, no es exactamente lineal, por lo que para unas comidas, las proteínas pueden representar el 60% de las calorías, en otras puede representar menos de 10% de las calorías.

<br><br>

## Momento de Retroalimentación: Módulo 2 Uso de framework o biblioteca de aprendizaje máquina para la implementación de una solución. (Portafolio Implementación)
### Modelo
Dentro de Este modelo se implemento la librería Sklearn para para llevar acabo el modelo nombrado _Neural Network Multi-layer Perceptron classifier_, el cual nos permite modelar con un formato a e conexiones neuronales para hacer predicciones.
<br>

Así mismo, se utilizo el data set ya definido en este curso de _wines.csv_ para correr las predicciones dentro de este. Como métrica de desempeño se considero la clase a la que pertenece cada alcohol (1, 2 o 3). 
<br>

Para definir los valores de entrenamiento, y los valores de prueba, utilize una librería igualmente de Sklearn para dividir los datos de manera aleatoria. Esto nos da nuestros valores Y y X de entrenamiento al igual que nuestros valores Y y X de prueba. Teniendo nuestros valores inicializamos el modelo ya definido por Sklearn, y lo entrenamos por medio de la función _fit()_ en donde le pasamos nuestros valores X de entrenamiento y prueba. Teniendo esto hacemos una predicción con base a nuestras classes para ajustar el modelo con base a las X.
<br>

Teniendo esta predicción acabamos! Podemos visualizar los resultados de dos maneras:
- "confusion_matrix" para representar cómo es que se distribuyen los datos través de las 3 classes que tenemos presentes.
- "classification_report" para representar la correlaciones y el grado de confiabilidad del modelo con base a los datos proporcionados.

En las pruebas realizadas arriba, se puede visualizar que con los datos de entrenamiento obtuvimos un grado de confianza y certeza de 1.00 (100%)
Si embargo en la pruebas realizadas con los datos de prueba, obtuvimos un 0.97 (97%) de certeza.
<br>

Dicho esto, una limitación de esta prueba considero es el tamaño de la muestra. Wines tiene un conjunto de 178 campos por columna. Teniendo mas datos a los que analizar se pudiera realizar un mejor ajuste del modelo y posiblemente una mejor predicción al final.
