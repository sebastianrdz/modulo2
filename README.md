# Portafolio de Implementacion
## Momento de Retroalimentación: Módulo 1 Construcción de un modelo estadístico base (Portafolio Implementación)
### Mercurio

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
