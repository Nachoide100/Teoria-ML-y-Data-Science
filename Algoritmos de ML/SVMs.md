## SUPPORT VECTOR MACHINES

1. **What is the fundamental idea behind Support Vector Machines?**

La idea central de una SVM es la clasificación de margen amplio, que, a diferencia de otros modelos que solo buscan una línea que separe las clases, la SVM intenta ajustar la “calle” más ancha posible entre ellas. Su objetivo es enconttar un límite de decisión que no solo separe los datos correctamente, sino que también se mantenga lo más lejos posible de las instancias de entrenamiento más cercanas, lo que permitirá una mejor generalización, ya que ofrece un “rango de seguridad” para nuevas instancias que no fueron vistas durante el entrenamiento. 

2. **What is a support vector?**

Los “support vector” son las instancias de entrenamiento que se encuentran exactamente al borde de la “calle” y son por tanto, lo valores que definen el límite de decisión de una SVM.

3. **Why is it important to scale the inputs when using SVMs?**

Es importante porque las SVM son extremadamente sensibles a las escalas de las característias. Si una característica tiene una escala mucho mayor que la otra, los límites de decisión se verán afectados, puesto que se tenderá a ignorar la importancia de las características con escala pequeña. 

4. **Can an SVM classifier output a confidence score when it classifies an instance?
What about a probability?**

Los SVM classifiiers si otorgan una función de confianza, la cual se obtiene a través de la función de decisión, cuyo valor representa la distancia de una instancia específica al límite de decisión. 

Por el contrario, los clasificadores SVM no proporcionan probabilidad de clase de forma natural aunque si podemos configurar Scikit - learn (probability = True) para que las estime, pero esta opción ralentizará considerablemente el entrenamiento del modelo y la generación de predicciones. 

5. **Should you use the primal or the dual form of the SVM problem to train a model
on a training set with millions of instances and hundreds of features?**

Para conjuntos de millones de instancias, debemos utilizar la forma primal del problema de optimización ya que en la forma dual su complejidad computacional se encuentra entre 

*O*(*m*2×*n*) **y** *O*(*m*3×*n*), lo que haría que el tiempo de entrenamiento se volviera inmanejable. 

6. **Say you trained an SVM classifier with an RBF kernel. It seems to underfit the
training set: should you increase or decrease γ (gamma)? What about C?**

Si el modelo sufre de “underfitting”, significa que es demasiado simple para capturar la estructura de los datos por tanto tendremos que aumentar tanto y (estrechamiento de la campana de la función de similitud) como C (disminución del número de violaciones del margen).