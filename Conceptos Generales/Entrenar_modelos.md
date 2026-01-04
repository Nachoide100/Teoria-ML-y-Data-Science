## ENTRENAR MODELOS

1. **What Linear Regression training algorithm can you use if you have a training set
with millions of features?**

La solución directa para el cáculo de los parámetros óptimos del modelo de Regresión Lineal (Ecuación Normal), es terriblemente lenta cuando el número de características es grande. Por ello, será mejor utilizar los algoritmos de Descenso Gradiente, en concreo el “Stochastic” o el “Mini - Batch” si el data set también es muy grande en términos de instancias. 

1. **Suppose the features in your training set have very different scales. What algo‐
rithms might suffer from this, and how? What can you do about it?**

Los algoritmos que utilizan Descenso Gradiente son los más afectados puesto que si las características tienen escalas muy diferentes, la función de costo cambiar de forma, haciendo que el algoritmo no vata directamente hacia el mínimo global, si no en una dirección casi ortogonal y terminando en un valle largo y casi plao, lo que hace que la convergencia sea mucho más lenta. 

Por otro lado, los modelos lineales regularizados (como el Ridge Regression) también se ven afectados. Si las características no están escaladas, aquellas con valores grandes se verán mayor penalizadas, lo que sesgará el modelo. 

La solución a este problema es asegurarse que todas las características tenga una escala similar, ya sea a través del mecanismo de Normalización o Estandarización.

1. **Can Gradient Descent get stuck in a local minimum when training a Logistic
Regression model?**

Esto no puede pasar ya que la función de la Regresión Logística es convexa, lo que asegura que solo tiene un mínimo global.

1. **Do all Gradient Descent algorithms lead to the same model provided you let
them run long enough?**

No, mientras que el el Batch converge exactamente en la solución óptima (mínimo), tanto el “Stochastic” como el “Mini_batch”, al utilizar solo una instancia o pequeños subconjuntos aleatorios nunca convergerán en el mínimo, sino que rebotarán continuamente alrededor de él. Para conseguir que convergiesen, habría que reducir gradualmente el “learning rate” a lo largo del tiempo.

1. **Suppose you use Batch Gradient Descent and you plot the validation error at
every epoch. If you notice that the validation error consistently goes up, what is
likely going on? How can you fix this?**

A priori, lo que está ocurriendo es que la tasa de aprendizaje es demasiado alta, lo que provoca que el algoritmo salte repetidamente al otro lado del valle de la función de costo, divergiendo y terminando cada vez más lejos de la solución óptima. Por tanto, la solución más directa sería reducir la tasa de aprendizaje.

1. **Is it a good idea to stop Mini-batch Gradient Descent immediately when the vali‐
dation error goes up?**

En este tipo de algoritmo no es buena idea. La razón reside en que este algoritmo funciona seleccionando un subconjunto de datos aletatorios en cada paso de optimización, haciendo que el error de validación rebote continuamente alrededor del mínimo óptimo. Si detenemos el entrenamiento inmediatamente en el primer aumento del error, es muy probable que estemos deteniendo el algoritmo prematuramente debido a un rebote temporal causado por el ruido, sin haber alcanzado una solución cercada al óptimo.

1. **Which Gradient Descent algorithm (among those we discussed) will reach the
vicinity of the optimal solution the fastest? Which will actually converge? How
can you make the others converge as well?**

Los más rápidos son (en orden) el Stochastic y el Min - Batch. El que converge es el Batch, puesto que es él único que utiliza todo el set de datos en cada paso. Para hacer conveger los dos primeros deberemos disminuir su tasa de aprendizaje, para lograr que se asienten en el mínimo global 

1. **Suppose you are using Polynomial Regression. You plot the learning curves and
you notice that there is a large gap between the training error and the validation
error. What is happening? What are three ways to solve this?**

Una brecha entre un error de entrenamiento bajo y un error de validación alto supone un sobreajuste. Esto ocurre porque el modelo es demasiado complejo en relación a la cantidad o ruido de los datos de entrenamiento. Para solucionarlo podemos: 

- Simplificar el modelo
- Regularizar el modelo.
- Obtener más datos de entrenamiento.
1. **Suppose you are using Ridge Regression and you notice that the training error
and the validation error are almost equal and fairly high. Would you say that the
model suffers from high bias or high variance? Should you increase the regulari‐
zation hyperparameter α or reduce it?**

Estamos antes un claro ejemplo de sesgo alto. Cuando el error de entrenamiento y el error de validación son casi iguales y ambos son altos, es un indicador de que el modelo es demasiado simple y no ha logrado capturar la estructura subyacente de los datos → Underfitting. 

Para solucionarlo hay que reducir por tanto el hiperparámetros de regularización, puesto que nuestro objetivos es hacer el modelo más completo, aumentando la varianza pero disminuyendo el sesgo. 

1. **Why would you want to use:**
- **Ridge Regression instead of plain Linear Regression (i.e., without any regulari‐
zation)?**
    
    Casi siempre es preferible usar un poco de regularización para restringir el modelo y asi reducir el riesgo de overfitting. 
    
- **Lasso instead of Ridge Regression?**
    
    Si se sospecha que solo unas pocas características son realmente útiles el modelo Lasoo tiende a eliminar su peso completamente, por lo que será más óptimo que el Ridge Regression.
    
- **Elastic Net instead of Lasso?**
    
    En general, se prefiere la Elastic Net porque Lasso puede comportarse de manera errática si el número de carácteristicas es mayor que el número de instancias del entrenamiento o cuadno varias características están fuertemente correlacionadas. 
    
1. **Suppose you want to classify pictures as outdoor/indoor and daytime/nighttime.
Should you implement two Logistic Regression classifiers or one Softmax Regres‐
sion classifier?**

Debemos implementar dos clasificadores Logísticos puesto que las dos tareas de clasificación (exterior / interior y diurno / nocturno) no son mutuamente excluyente. La regresión Softmax está diseñada para la clasificación multiclase dónde cada insgtancia debe pertenecer a una sola clase.