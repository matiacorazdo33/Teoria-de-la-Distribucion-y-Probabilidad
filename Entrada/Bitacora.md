# Bitácora de Aprendizaje y Autoevaluación — Unidad 2

**Materia:** Teoría de la Distribución y Probabilidad  
**Estudiante:** Matias Sebastian Labanda Pineda  
**Curso:** Computación (2do Ciclo "A")  
**Proyecto:** Inferencia Estadística en los Cantones de Loja  

---

## Lo que aprendí en esta unidad

En esta segunda unidad dimos el salto de solo graficar y sacar promedios a utilizar la inferencia estadística para tomar decisiones con datos reales de la provincia. Con el trabajo en los laboratorios me di cuenta de que las librerías de Python no funcionan como cajas negras que lanzan números al azar, sino que siguen reglas matemáticas bastante estrictas.

Al trabajar con el Teorema del Límite Central y las técnicas de remuestreo, vi cómo los datos de habitantes sin alcantarillado en Loja, que originalmente eran muy asimétricos, se van normalizando a nivel de medias muestrales gracias al código. Luego, con las pruebas de hipótesis unimuestrales, entendí por qué era obligatorio elegir la distribución T de Student; al tener una muestra pequeña de solo 16 cantones y no conocer la varianza real de toda la población, los grados de libertad funcionan como una especie de ajuste matemático por la falta de información general.

Finalmente, en la parte de comparación de grupos, comprendí el riesgo de inflar la probabilidad de cometer un Error Tipo I si nos poníamos a hacer varias pruebas T por separado para comparar las zonas norte, centro y sur. El ANOVA de 1 factor nos solucionó la vida al evaluar la igualdad de medias en un solo bloque de código, y la prueba post-hoc de Tukey nos terminó de aclarar en qué sectores específicos se encuentran las diferencias reales de infraestructura.

---

## Problemas que tuve y cómo los solucioné

Uno de los primeros inconvenientes que encontré fue la ingesta del archivo `datos_loja.csv` en el entorno de Google Colab, ya que quería evitar meter los datos de forma manual o fija en el script. Lo solucioné usando el módulo nativo de subida de archivos de Colab para que el notebook sea dinámico y cargue el DataFrame directamente con Pandas cada vez que se corre el código.

Otro reto fue la segmentación de los cantones en subgrupos geográficos. Hacer los filtros uno por uno en Pandas me causaba errores de indexación y advertencias en la terminal. Para dejar el script limpio, preferí construir un diccionario con el mapa de las zonas norte, centro y sur, aplicándolo directamente sobre la columna de los cantones con la función map.

Por último, me costó un poco asimilar que no se puede ejecutar un ANOVA a ciegas sin verificar los datos antes. Tuve que revisar la documentación de las funciones de SciPy para implementar las pruebas previas de Shapiro-Wilk para el supuesto de normalidad y la prueba de Levene para comprobar que las varianzas de los grupos fueran homogéneas antes de avanzar con el test paramétrico.

---

## Mi autoevaluación

A nivel teórico me siento bastante claro, sobre todo al entender el impacto que tendrían los errores de inferencia en la práctica. Por ejemplo, cometer un Error Tipo I significaría gastar presupuesto en obras sanitarias en zonas que no lo necesitan, mientras que un Error Tipo II causaría que ignoremos una crisis local por guiarnos solo de un promedio general. 

En la parte de programación considero que mejoré bastante, ya que ahora puedo combinar el formateo de ecuaciones en LaTeX con scripts muy bien comentados usando statsmodels y scipy.stats. Como punto a mejorar, me queda repasar más la personalización de los gráficos de sensibilidad y el manejo de escalas logarítmicas con matplotlib para que las visualizaciones queden más profesionales.

---
[Volver a contenidos](../Entrada/Contenidos.md)
