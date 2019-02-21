# Talleres de ciencia de datos y aprendizaje automático para el aula de software libre (ASL)

Este repositorio contiene una serie de material sobre un breve tutorial sobre ``scikit-learn`` en Python. Está basado en el tutorial de ``scikit-learn`` realizado en la conferencia Scipy2017 (ver referencias).

## Conseguir el material para el tutorial

Si tienes una cuenta de Github, la forma más conveniente de bajar el material es realizar un clone del repositorio GitHub o hacer un fork. Puedes clonar el repositorio con el comando:
```bash
git clone https://github.com/ayrna/taller-sklearn-asl-2019.git

```

Si no estás familiarizado con GitHub o no tienes cuenta, también puedes bajar todo el repositorio como un archivo `.zip`, accediendo a ``Clone or download`` en la cabecera del [repositorio](https://github.com/ayrna/taller-sklearn-asl-2019) y pulsando sobre ``Download ZIP``.

![](images/download-repo.png)

Por favor, ten en cuenta que los contenidos del repositorio pueden cambiar a última hora, así que recomendamos que intentes actualizar los contenidos antes de cada sesión. Si tienes una cuenta de GitHub y has clonado el repositorio, solo tienes que usar el comando:
```bash
git pull origin master
```
En otro caso, tendrás que descargar de nuevo el `.zip` cada vez que quieras actualizar los ficheros.


## Notas de instalación

Este tutorial requiere tener instalaciones lo más recientes posibles de:

- [NumPy](http://www.numpy.org)
- [SciPy](http://www.scipy.org)
- [matplotlib](http://matplotlib.org)
- [pandas](http://pandas.pydata.org)
- [pillow](https://python-pillow.org)
- [scikit-learn](http://scikit-learn.org/stable/)
- [IPython](http://ipython.readthedocs.org/en/stable/)
- [Jupyter Notebook](http://jupyter.org)


Este último es importante. Si lo tienes correctamente instalado, deberías poder teclear:
```bash
    jupyter notebook
```
en tu terminal de comandos y ver el panel de carga de libros de notas en tu navegador web. Intenta abrir y ejecutar cualquiera de los libros que contiene este curso, para ver si funciona todo correctamente.

### Instalación en equipos personales

Para aquellos usuarios que no tengan las dependencias instaladas, una forma relativamente sencilla de conseguirlas es utilizar una distribución de Python como [Anaconda](https://www.anaconda.com/distribution/), que incluye los paquetes de Python más relevantes para ciencia, matemáticas, ingeniería y análisis de datos. Anaconda puede descargarse e instalarse de forma libre, incluyendo el uso comercial y la redistribución. Los códigos incluidos en este tutorial deberían ser compatibles con Python 2.7 y Python 3.7. Suponiendo que tengas Anaconda instalado, los siguientes comandos crean un entorno nuevo llamado `sklearn-env` e instalan todas las dependencias:
```bash
conda update conda
conda update anaconda
conda create --prefix ~/sklearn-env scikit-learn
source activate sklearn-env
conda install matplotlib
conda install ipython
conda install pandas
conda install Pillow
```

### Preparación de equipos en la UCO (ThinkStation)

Los equipos de la UCO están provistos de todo el material necesario para crear un entorno donde trabajaremos durante todas las sesiones de los talleres. Con el comando `pip` instalamos las bibliotecas necesarias para trabajar:
```bash
$ pip install --user --upgrade scikit-learn pandas
```
Como puedes observamos, instalamos las librerías con la opción ``--user``, ya que si no requeriríamos permisos de administración. Si tienes algún tipo de problema durante la instalación, puedes limpiar la carpeta ``$HOME/.local/lib/python2.7/site-packages``, pero vigila previamente que no tengas librerías que quieras mantener. Si os quedáis sin espacio durante la instalación, también podéis vaciar el directorio ``$HOME/.cache/pip``. Esta última carpeta puede borrarse tras la instalación.

En algunas instalaciones de Linux hemos visto que la dependencia ``argparse`` no se instala automáticamente, puedes arreglarlo así:
```bash
$ pip install --user --upgrade argparse
```



## Revisión de una correcta instalación

Tras obtener el material, **recomendamos encarecidamente** abrir y ejecutar el libro de notas ``check_env.ipynb``, que se encuentra en la raíz del repositorio. Para ello, ejecuta el comando:
```bash
jupyter notebook check_env.ipynb
```
Una vez dentro del libro, ejecuta la única celda de código pulsando sobre el botón "Run Cells", tal y como muestra esta figura:

![](images/check_env-1.png)

Si tu entorno satisface todos los requisitos para el tutorial, el código ejecutado debería mostrar una salida como la siguiente:
```bash
Using python in /usr/local
2.7.11 (default, Feb 11 2016, 10:11:51) 
[GCC 5.3.0]

[ OK ] PIL version 1.1.7
[ OK ] matplotlib version 2.1.2
[ OK ] scipy version 1.2.1
[ OK ] IPython version 4.0.0
[ OK ] numpy version 1.16.1
[ OK ] pandas version 0.24.1
[ OK ] sklearn version 0.20.2
```
Aunque no sea un requisito, te recomendamos actualizar los paquetes Python a su ultima versión, para así asegurar la mejor compatibilidad con el material didáctico. Puedes actualizar los paquetes con los comandos:
```bash
pip install [package-name] --upgrade
```


## Descarga de las bases de datos

Los datos para este tutorial no están incluidos en el repositorio. Vamos a utilizar varios datasets: muchos vienen en scikit-learn, el cuál descarga y guarda los datos.

Debido a que la red puede fallar, sería una buena idea descargar algunos de los datasets (los más pesados) antes de las clases. Por favor, ejecuta:
```bash
python fetch_data.py
```
para descargar estos datasets.

El tamaño de la descarga de los ficheros es, aproximadamente, 280MB y, una vez extraídos en disco ocuparán unos 480MB de tu disco duro.


## Sesiones y temas

Para cargar cualquier sesión debes iniciar ``jupyter notebook``.


### 1. Visualización, aprendizaje supervisado y métodos de evaluación (jueves 21 febrero)

-  1.01\. Introducción a aprendizaje automático en Python [[notebook](talleres_inov_docente/1-01-introduccion_aprendizaje_automatico.ipynb)][[html](https://rawgit.com/ayrna/tutorial-sklearn/master/talleres_inov_docente/1-01-introduccion_aprendizaje_automatico.html)]
- 1.02\. Herramientas científicas en Python [[notebook](talleres_inov_docente/1-02-herramientas_cientificas_python.ipynb)][[html](https://rawgit.com/ayrna/tutorial-sklearn/master/talleres_inov_docente/1-02-herramientas_cientificas_python.html)]
- 1.03\. Representación y visualización de datos [[notebook](talleres_inov_docente/1-03-representacion_datos_aa.ipynb)][[html](https://rawgit.com/ayrna/tutorial-sklearn/master/talleres_inov_docente/1-03-representacion_datos_aa.html)]
- 1.04\. Aprendizaje supervisado: entrenamiento y test [[notebook](talleres_inov_docente/1-04-entrenando_y_generalizando.ipynb)][[html](https://rawgit.com/ayrna/tutorial-sklearn/master/talleres_inov_docente/1-04-entrenando_y_generalizando.html)]
- 1.05\. Aprendizaje supervisado: clasificación [[notebook](talleres_inov_docente/1-05-aprendizaje_supervisado_clasificacion.ipynb)][[html](https://rawgit.com/ayrna/tutorial-sklearn/master/talleres_inov_docente/1-05-aprendizaje_supervisado_clasificacion.html)]
- 1.06\. Aprendizaje supervisado: regresión [[notebook](talleres_inov_docente/1-06-aprendizaje_supervisado_regresion.ipynb)][[html](https://rawgit.com/ayrna/tutorial-sklearn/master/talleres_inov_docente/1-06-aprendizaje_supervisado_regresion.html)]
- 1.07\. Caso de estudio - Supervivencia en el Titanic [[notebook](talleres_inov_docente/1-07-caso_estudio_titanic.ipynb)][[html](https://rawgit.com/ayrna/tutorial-sklearn/master/talleres_inov_docente/1-07-caso_estudio_titanic.html)]
- 1.08\. Validación cruzada y métodos de evaluación de rendimiento [[notebook](talleres_inov_docente/1-08-validacion_cruzada.ipynb)][[html](https://rawgit.com/ayrna/tutorial-sklearn/master/talleres_inov_docente/1-08-validacion_cruzada.html)]
- 1.09\. Selección de parámetros, validación y test [[notebook](talleres_inov_docente/1-09-complejidad_modelos_busqueda_grid.ipynb)][[html](https://rawgit.com/ayrna/tutorial-sklearn/master/talleres_inov_docente/1-09-complejidad_modelos_busqueda_grid.html)]

### 2. Aprendizaje no supervisado (jueves 14 marzo)

Nota: Mantenemos la numeración de los cuadernos con el [curso original de sklearn](https://github.com/pagutierrez/tutorial-sklearn) para quién quiera hacer la versión completa del curso.

- 2.02\. Aprendizaje no supervisado: agrupamiento [[notebook](talleres_inov_docente/2-02-aprendizaje_no_supervisado_agrupamiento.ipynb)][[html](https://rawgit.com/ayrna/tutorial-sklearn/master/talleres_inov_docente/2-02-aprendizaje_no_supervisado_agrupamiento.html)]
- 2.01\. Aprendizaje no supervisado: transformación [[notebook](talleres_inov_docente/2-01-aprendizaje_no_supervisado_transformaciones.ipynb)][[html](https://rawgit.com/ayrna/tutorial-sklearn/master/talleres_inov_docente/2-01-aprendizaje_no_supervisado_transformaciones.html)]
- 2.05\. Encadenamiento con tuberías [[notebook](talleres_inov_docente/2-05-encadenando_con_tuberias.ipynb)][[html](https://rawgit.com/ayrna/tutorial-sklearn/master/talleres_inov_docente/2-05-encadenando_con_tuberias.html)]
- 3.01\. Extracción de características de un texto mediante *Bag-of-Words* (bolsas de palabras) [[notebook](talleres_inov_docente/3-01-extraccion_caracteristicas_texto.ipynb)][[html](https://rawgit.com/ayrna/tutorial-sklearn/master/talleres_inov_docente/3-01-extraccion_caracteristicas_texto.html)]
- 3.02\. Caso de estudio - Clasificación de texto para detección de spam en SMS [[notebook](talleres_inov_docente/3-02-caso_estudio_deteccion_spam_SMS.ipynb)][[html](https://rawgit.com/ayrna/tutorial-sklearn/master/talleres_inov_docente/3-02-caso_estudio_deteccion_spam_SMS.html)]
- 3.05\. Aprendizaje supervisado: árboles de decisión y bosques aleatorios [[notebook](talleres_inov_docente/3-05-arboles_y_bosques.ipynb)][[html](https://rawgit.com/ayrna/tutorial-sklearn/master/talleres_inov_docente/3-05-arboles_y_bosques.html)]
- 3.06\. Selección de características [[notebook](talleres_inov_docente/3-06-seleccion_caracteristicas.ipynb)][[html](https://rawgit.com/ayrna/tutorial-sklearn/master/talleres_inov_docente/3-06-seleccion_caracteristicas.html)]

# Referencias
Este tutorial es una versión reducida del [tutorial original de sklearn por Pedro A. Gutiérrez](https://github.com/pagutierrez/tutorial-sklearn), que a su vez se baja en el tutorial de Alex Gramfort y Andreas Mueller [[Github]](https://github.com/amueller/scipy-2017-sklearn)[[Youtube1]](https://www.youtube.com/watch?v=2kT6QOVSgSg)[[Youtube2]](https://www.youtube.com/watch?v=WLYzSas511I)

Se recomiendan los siguientes tutoriales adicionales para aprender más sobre el manejo de la librería:
- *An introduction to machine learning with scikit-learn*. Documentación oficial de `scikit-learn`. [http://scikit-learn.org/stable/tutorial/basic/tutorial.html](http://scikit-learn.org/stable/tutorial/basic/tutorial.html).
- *A tutorial on statistical-learning for scientific data processing*. Documentación oficial de `scikit-learn`. [http://scikit-learn.org/stable/tutorial/statistical_inference/index.html](http://scikit-learn.org/stable/tutorial/statistical_inference/index.html).

Por último, para aprender la sintaxis básica de Python en menos de 13 horas, se recomienda el siguiente curso de *CodeAcademy*:
- Curso de Python de CodeAcademy. [https://www.codecademy.com/es/learn/python](https://www.codecademy.com/es/learn/python)
