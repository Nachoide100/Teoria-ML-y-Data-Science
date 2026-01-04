## PREGUNTAS GENERALES 

1. **How would you define Machine Learning?**

El Machine Learning es la ciencia que permite programar los ordenadores para que aprendan sobre una expriencia (E) con respecto a una tarea (T) y una medida de rendimiento (P), si su rendimiento en T, medido por P, mejora con la experiencia. 

2. **Can you name four types of problems where it shines?**
- Problemas para los que las soluciones existentes requieren mucho ajuste manual o largas listas de reglas: un algoritmo de aprendizaje automático puede simplificar el código y funcionar mejor.
- Problemas complejos para los que no hay buena solución en absoluto utilizando un enfoque tradicional: las mejores técnicas de aprendizaje automático pueden encontrar una solución.
- Entornos fluctuantes: un sistema de aprendizaje automático puede adaptarse a los nuevos datos.
- Análisis de problemas complejos y grandes cantidades de datos.
  
3. **What is a labeled training set?**

Es un cojunto de ejemplos de datos usados para entrenar un algoritmo de ML, donde cada ejemplo incluye la solución deseada o la respuesta correcta. Por ejemplo, quieres predecir el valor de una casa y el dataset presenta una columna con el valor real de cada casa. 

4.  **What are the two most common supervised tasks?**

Clasificaión (ej. Filtro de Spam) y Predicción de un valor número dado un set de features llamadas predictores (ej. Predecir el precio de un coche dado su marca, año, potencia…). 

5. **Can you name four common unsupervised tasks?**

Las 4 tareas comunes en esta categoría son: 

- Clustering: detectar puntos de datos que son similares entre sí.
- Detección de anomalías: identificar instancias que se desvían significativamente de la norma o patrón esperado.
- Reducción de dimensionalidad: simplificar los datos sin perder demasiada información
- Visualización: generar una representación en 2D o 3D de una gran cantidad de datos complejos.
6. **What type of Machine Learning algorithm would you use to allow a robot to walk in various unknown terrains?**

Utilizaría el Reinforcemente Learning, el sistema capaz de observar el entorno, seleccionar acciones y obtener recompensas (positivas o negativas) según la selección de sus acciones, guiando su estrategia para obtener la mejor recompensa a lo largo del tiempo. 

7. **What type of algorithm would you use to segment your customers into multiple groups?**

Utilizaría el algoritmo de clustering, ya que es el que nos va a permitir detectar grupos de clientes similares.  En ningún momento le dices al algoritmo a qué grupo pertenece un cliente:  encuentra esas conexiones sin tu ayuda. 

8. **Would you frame the problem of spam detection as a supervised learning problem or an unsupervised learning problem?** 

El problema de la detección de spam lo afrontaría con un modelo de aprendizaje supervisado. Esto se debe a que este tipo de modelos trabaja con datos de entrenamiento en los que las soluciones deseadas (labels) están incluidas, como es nuestro caso → El modelo se entrena con un dataset de ejemplos de correos electrónicos en los que ya está determinada su clase (”spam” o “correo normal”). 

9. **What is an online learning system?**

En el aprendizaje en línea, se entrena al sistema de forma incremental mediante la alimentación de instancias de datos secuencialmente, ya sea individualmente o por pequeños grupos llamados mini-lotes. Cada paso de aprendizaje es rápido y barato, por lo que el sistema puede aprender sobre los nuevos datos en el momento en que llegan. Permite ir evolucionando el modelo según van entrando datos nuevos. 

10. **What is out-of-core learning?**

Está técnica se utiliza para entrenar sistemas en conjunto de datos tan grandes que no caben por completo en la memoria principal de una sola máquina. Para ello, este tipo de algoritmos son capaces de aprender de forma incremental: 

- Se hace una carga parcial de datos en la memoria.
- Se entrena el modelo en ese subset de datos.
- Se repite este proceso (cargar + entrenar) hasta completar el conjunto de datos.
11. **What type of learning algorithm relies on a similarity measure to make predictions?**

El tipo de algoritmo de ML que depende de una medida de similitud para hacer predicciones es el Aprendizaje Basado en Instancias. Trabaja de la siguiente manera: 

- Memoriza los ejemplos.
- Generaliza por comparación
- Usa una medida de similitud como forma de clasificar.
12.  **What is the difference between a model parameter and a learning algorithm’s hyperparameter?**

Los parámetros del modelo son las variables internas que definen la capacidad predictiva del modelo. Son los valores que el modelo busca que se ajusten lo mejor posible a los datos de entrenamiento. Ej. En un modelo de regresión lineal, los parámetros son los coeficientes que definen la línea de predicción.

Los hiperparámetros son los parámetros del algoritmo de aprendizaje, no del modelo en sí mismo. Permiten ajustar la complejidad del modelo o la velocidad con la que aprender. Ej. Tasa de aprendizaje del Descenso de Gradiente o El factor de regularización.

13. **What do model-based learning algorithms search for? What is the most common strategy they use to succeed? How do they make predictions?**

Los algoritmos de aprendizaje basado en modelos buscan construir una representación generalilzada de los datos o una fórmula, a la que llamamos modelo. Este modelo luego se usa para predecir datos nunca vistos. 
Estos algoritmos buscan encontrar los valores de parámetros del modelo a través de su entrenamiento. Una vez el algoritmo a encontrado sus mejores parámetros a través del entrenamiento, este se aplica para hacer predicciones sobre nuevos casos (inferencia).
