# Proyecto_5 : COMPETICIÓN DE KAGGLE - PREDICCIÓN DEL SALARIO DE LOS TRABAJOS DE DATA

🎯 **OBJETIVO** 🎯

Predecir el sueldo de los trabajadores de data con el menor error posible haciendo uso de los conocimientos adquiridos en la última semana.

📊 **DATOS** 📊

Contamos con los siguientes archivos para lograr nuestro objetivo:

- muestra.csv - Ejemplo de entrega en el formato correcto
- salaries_data.csv - Datos a trabajar
- testeo.csv - Datos para predecir

▸ **PASOS SEGUIDOS** ▸

Antes de realizar cualquier modificación sobre nuestra base de datos, creamos nuestra 'y', que en este caso sería la columna de 'salary_in_usd'.

 -- *LIMPIEZA DE DATOS* --
 
   1. Una vez importados 'salaries_data.csv' y 'testeo.csv', comenzamos la limpieza de datos. Concatenamos ambos ya que, cualquier cambio que se realizara    debía estar en ambas tablas.
   
   2. Quitamos outliers.
   
   3. Borramos las columnas 'salary_currency', 'salary' y 'employee_residence' puesto que no nos daban ninguna información relevante.
   
   4. Revisamos todos los tipos de dato de las tablas, dándonos cuenta de que había varias columnas categóricas. En este caso, decidimos utilizar la      función de Pandas 'get_dummies' para todas las columnas excepto 'remote_ratio' y 'work_year' porque ya eran numéricas. De esta forma, pasaríamos a tener  tantas columnas como categorías hubiera en las anteriores con '0' en el caso donde no se cumpliera y '1' en los que sí.
    
   5. Una vez teniendo todos los datos numéricos, normalizamos las columnas 'work_year' y 'remote_ratio', para que estuvieran en la misma escala que el        resto de columnas. 
   
   6. Ya estando todos los datos limpios, separamos testeo para probar primero a predecir con el dataframe que se nos había proporcionado y,      posteriormente, predecir con testeo y subir los resultados a Kaggle.
 
  -- *PREDICCIONES* --
  
  1. Para saber qué modelo era el mejor para predecir el salario en función de la limpieza que habíamos realizado, creé una función donde se probaban todos los modelos aprendidos y retornaba el que tuviera el menor MSE (error cuadrático medio), que es la metrica en la que se basaba el ranking de la  competición. 
  
  2. Antes de utilizar la función, separamos los datos en X_train, X_test, y_train e y_test. X_train e y_train para entrenar nuestro modelo, y X_test e   y_test para predecir y calcular el mse. 
  
  3. Una vez hecha la separación, utilizamos la función para que nos diga el modelo que debemos utilizar, siendo este la regresión lineal **Ridge** con un mse de 34207.94432400609.
  
  4. Predecimos de nuevo pero con testeo y subimos los resultados en un dataframe con la estructura del archivo 'muestra.csv' a Kaggle, obteniendo la siguiente posición:
  
<img width="1094" alt="posición_ranking" src="https://user-images.githubusercontent.com/115650089/205660432-0489406c-8d6a-455a-adaf-25d4d2b23b11.png">
  
  

