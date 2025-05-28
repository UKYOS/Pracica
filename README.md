
# Predicción de Préstamos Digitales en Clientes Peruanos 🇵🇪

Este proyecto tiene como objetivo aplicar técnicas de regresión lineal y redes neuronales para predecir el monto de préstamos digitales de clientes peruanos, utilizando Python y herramientas de ciencia de datos.

## 🎯 Objetivo General

Aplicar técnicas de regresión lineal y redes neuronales artificiales para predecir el monto de préstamos digitales.

## ✅ Objetivos Específicos

- Implementar un modelo de regresión lineal simple.
- Desarrollar una red neuronal para predecir montos basándose en múltiples variables.
- Manipular datos con Pandas y NumPy.
- Visualizar resultados con Matplotlib.
- Aplicar estructuras de programación en Python.
- Usar GitHub como sistema de control de versiones.

## 📁 Dataset

- Fuente: Kaggle - Préstamos Digitales - Perú
- Variables comunes:
  - `cliente`, `genero`, `procedencia`, `trxDigitalUm`, `promSaldoBanco3Um`, `ventaPrestDig`, entre otras.

✅ Variables disponibles
Variable	          Descripción
mes	                Año y mes en formato yyyymm
cliente	            ID del cliente
estadoCliente	      Estado del cliente (A, B, etc.)
rngEdad	            Rango de edad (ej: <35-45])
genero	            M o F
rngSueldo	          Rango de sueldo
procedencia	        Ciudad (ej: lima)
operDigital	        Estado de operación digital (NN, etc.)
trxDigitalUm	      Número de transacciones digitales
promTrxDig3Um	      Promedio de transacciones digitales
recCamp	            Participación en campaña (0/1)
frecCamp	          Frecuencia en campañas
tenTarjeta	        Tipo de tarjeta (ej: TC-TD)
promConsBanco3Um  	Promedio consumo banco 3 últimos meses
promSaldoBanco3Um	  Promedio saldo banco 3 últimos meses
promSaldoTc3Um    	Promedio saldo tarjeta 3 últimos meses
promSaldoPrest3Um 	Promedio saldo préstamo 3 últimos meses
sowTcUm           	Participación tarjeta
sowPrestUm	        Participación préstamo
ventaPrestDig	      Monto del préstamo digital (target)

## 🧪 Librerías Utilizadas

- pandas
- numpy
- matplotlib
- scikit-learn
- tensorflow / keras

## 🔢 Modelos Implementados

  Regresión Lineal Simple

  Red Neuronal (Keras)



## 📊 Visualizaciones

- Gráfico de regresión lineal.
- Evolución del error de entrenamiento de la red neuronal (Loss vs Epochs).
- Comparación entre valores reales y predichos.

## 🔁 Lógica de Programación

El proyecto incluye:
- Uso de bucles (`for`)
- Condicionales (`if`)
- Diccionarios y listas para análisis personalizados



## 📌 Conclusiones

- La regresión lineal mostró una tendencia, aunque limitada, de correlación.
- La red neuronal logró mejores resultados ajustando múltiples variables.
- Las técnicas de Machine Learning son útiles para entender el comportamiento de préstamos digitales.

## 🚀 Cómo Ejecutar

1. Abre el notebook en Google Colab.
2. Sube el archivo `dataBasePrestDigital.csv` al entorno.
3. Ejecuta todas las celdas paso a paso.

## 🔗 Respuesta a las preguntas 

Pregunta 1 

¿Qué criterio utilizaste para seleccionar la variable independiente en la regresión lineal simple? ¿Por qué crees que esa variable influye en el monto del préstamo?

Para el experimento de regresión lineal simple que analizamos en detalle con su gráfico y métricas, la variable independiente seleccionada fue promSaldoBanco3Um . La decisión de usar esta variable se tomó como parte de la exploración para entender cómo diferentes características individuales se relacionaban linealmente con el monto del préstamo (promSaldoPrest3Um) en los datos filtrados (donde el monto del préstamo era mayor a cero).

¿Por qué se podría pensar que promSaldoBanco3Um influye en el monto del préstamo?
La hipótesis sería que el saldo promedio que una persona maneja en sus cuentas bancarias podría ser un indicador de su comportamiento financiero general, su capacidad de endeudamiento o su propensión a utilizar otros productos crediticios.

Pregunta 2:
¿Qué significa el error MSE (Mean Squared Error) y qué te indica sobre el rendimiento del modelo?

El MSE (Error Cuadrático Medio) es una métrica que se usa para medir el rendimiento de un modelo de regresión. Se calcula así:

Para cada predicción, se toma la diferencia entre el valor real y el valor predicho.
Esta diferencia (el error) se eleva al cuadrado.
Se suman todos estos errores al cuadrado.
Finalmente, se calcula el promedio de esta suma.

¿Qué indica sobre el rendimiento del modelo?

El MSE te da una medida de la magnitud promedio de los errores al cuadrado.
Al elevar los errores al cuadrado, el MSE penaliza de forma más significativa los errores grandes. Por ejemplo, un error de 10 unidades contribuye con 100 al MSE, mientras que un error de 2 unidades solo contribuye con 4.
Un valor de MSE más bajo indica un mejor rendimiento del modelo, ya que significa que, en promedio, las predicciones del modelo están más cerca de los valores reales.
La unidad del MSE es la unidad de la variable objetivo al cuadrado. Por esto, a veces se prefiere usar la raíz cuadrada del MSE (RMSE), que está en la misma unidad que la variable objetivo y es más fácil de interpretar directamente.

Pregunta 3:
¿Qué conclusiones sacaste al comparar los valores predichos por el modelo con los valores reales? ¿Hubo sobreajuste o subajuste? ¿Cómo lo detectaste?

Al comparar los valores predichos con los reales, tanto para la regresión lineal simple como para la red neuronal (con las 3 variables seleccionadas), las conclusiones fueron:

Regresión Lineal Simple (con promSaldoBanco3Um):

El R2 fue extremadamente bajo (0.02).
El gráfico de "Valores Reales vs. Predicción" mostró una línea de regresión casi horizontal, indicando que el modelo predecía valores muy similares independientemente del valor real del saldo de la ceunta bancaria.
Esto indica un claro subajuste (underfitting). El modelo era demasiado simple (una línea recta con una sola variable débilmente correlacionada) para capturar la complejidad de los datos y no aprendía bien ni siquiera de los datos de entrenamiento.
Red Neuronal (con 3 variables):

El gráfico de "Evolución del Error (MAE) Durante el Entrenamiento" mostró que las curvas de error de entrenamiento y de validación disminuyeron y luego se estabilizaron en un nivel de MAE relativamente alto (alrededor de 6950-7195).
El gráfico de "Valores Reales vs. Predicciones" mostró que, aunque había más variabilidad en las predicciones que con la regresión lineal, los puntos seguían muy dispersos de la línea de "predicción perfecta", y el modelo tendía a subestimar severamente los montos de préstamo más grandes.
El R2 final de la red neuronal también fue bajo

Detección:

Principalmente subajuste: El MAE alto y el R2 bajo en el conjunto de prueba, junto con curvas de aprendizaje que se estabilizan en un error alto, sugieren que el modelo, a pesar de ser más complejo, seguía subajustando. Las 3 variables seleccionadas no parecían tener suficiente poder predictivo para explicar la variabilidad del monto del préstamo.
No hubo evidencia clara de sobreajuste (overfitting) significativo, ya que la curva de error de validación no empezó a aumentar drásticamente mientras la de entrenamiento continuaba bajando. Ambas se estabilizaron juntas, aunque en un nivel de error no ideal.

¿Qué desafíos encontraste al trabajar con el dataset y cómo los solucionaste (por ejemplo, valores faltantes, codificación de categorías, etc.)?

Durante el trabajo con el dataset, enfrentamos varios desafíos comunes en el preprocesamiento de datos:

Valores Faltantes (NaN):

Desafío: Podrían haber existido después del mapeo de rangos o en otras columnas. Los modelos no pueden procesar NaN.
Solución: Para rngEdad y rngSueldo, después de mapearlos, rellenamos los NaN con la mediana de los valores ya convertidos, lo cual es robusto a valores atípicos. Al final del preprocesamiento general, aplicamos df_processed.fillna(0) para rellenar cualquier NaN restante en el DataFrame con ceros, una estrategia simple para asegurar que no haya faltantes.

Codificación de Variables Categóricas:

Desafío: Variables como rngEdad, rngSueldo (inicialmente texto), genero, estadoCliente, procedencia, operDigital, y tenTarjeta necesitaban ser convertidas a un formato numérico para los modelos.
Solución:
Mapeo Manual: Para rngEdad y rngSueldo, usamos diccionarios para asignar valores numéricos específicos a cada rango.
Conversión Binaria: Para genero, usamos una función lambda para convertir 'M' a 1 y 'F' a 0.
One-Hot Encoding: Para las demás variables categóricas nominales (estadoCliente, procedencia, operDigital, tenTarjeta), utilizamos pd.get_dummies() con drop_first=True para crear nuevas columnas binarias para cada categoría, evitando la trampa de la multicolinealidad.

Luego, convertimos las columnas booleanas resultantes del One-Hot Encoding a enteros (0 y 1).
Alta Proporción de Ceros en la Variable Objetivo (promSaldoPrest3Um):

Desafío: Ya que un alto porcentaje de la variable objetivo eran ceros, lo cual podía sesgar el modelo de regresión y dificultar la predicción de los montos no nulos.
Solución: Adoptamos la estrategia de filtrar los datos, creando un nuevo DataFrame df_no_cero que contenía solo las filas donde promSaldoPrest3Um > 0. Esto permitió que los modelos se enfocaran en predecir el monto cuando este efectivamente existía.
Escalado de Características para la Red Neuronal:

Desafío: Las redes neuronales funcionan mejor cuando las características de entrada están en una escala similar.

Solución: Utilizamos StandardScaler de Scikit-learn para escalar las 3 variables seleccionadas (rngSueldo, promSaldoTc3Um, promConsBanco3Um) antes de entrenar la red neuronal.
## 🔗 Repositorio
https://colab.research.google.com/drive/1qa2BZVXS6xe5kGl0nAFHZv9O60-hKmz5?usp=sharing

