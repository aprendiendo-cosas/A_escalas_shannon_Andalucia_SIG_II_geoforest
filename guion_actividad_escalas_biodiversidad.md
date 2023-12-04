# Guión sobre el efecto de las escalas espaciales en el significado de la diversidad biológica




> + **_Versión_**: 2023-2024
> + **_Asignatura_** : SIG II (Máster GEOFOREST). 
> + **_Autor_**: Curro Bonet-García (fjbonet@uco.es)
> + **_Duración_**: Entre 0.5 y 1 hora (depende de lo intenso del debate...)



## Objetivos

Esta actividad tiene como finalidad última la aplicación del concepto de diversidad (a través del índice de Shannon) a una escala espacial diferente a la que vimos en la [actividad anterior](https://rawcdn.githack.com/aprendiendo-cosas/P_shannon_SIG_II_Geoforest/2023__2024/guion_practica_mapa_biodiversidad.html). Se trata de que los estudiantes infieran o deduzcan una acepción diferente al concepto de diversidad analizado en el ejercicio anterior. Este tipo de ejercicios son muy útiles desde un punto de vista docente porque nos permiten entrenar habilidades cognitivas superiores (trasferir conocimiento de un ámbito a otro, investigar, reflexionar, tomar conciencia del avance en el razonamiento, etc.). Como siempre, los objetivos concretos son de dos tipos:

 + Disciplinares (tienen que ver con la ecología): Se muestran a continuación en orden de complejidad creciente:
   + Fijar los conceptos de diversidad (índice de Shannon) y riqueza (número de especies).
   + Reflexionar sobre los patrones de distribución espaciales de la diversidad en un territorio concreto (Andalucía).
   + Afianzar la conexión entre la identificación del patrón espacial (ej. hay más diversidad al oeste) y las causas que explican dicho patrón (ej. esto se debe a que hacia el oeste llueve más).
   + Comprender que el concepto de diversidad tiene significados diferentes dependiendo de su escala espacial de aplicación.
   + Descubrir un "nuevo" tipo de diversidad a partir de la observación de patrones de aplicación del índice de Shannon a dos escalas: escala de "comunidad pequeña" (cuadrículas de 250 m) y a escala de "paisaje" (espacios protegidos de Andalucía)
 + Instrumentales (tienen que ver con el manejo de herramientas de uso común):
    + Entrenar la capacidad de reflexión ante un problema nuevo partiendo de información incompleta.
    + Poner en práctica lo ya aprendido sobre búsqueda de bibliografía científica.

Antes de detallar en qué consiste esta actividad, lee el siguiente apartado en el que se describe el contexto ecológico planteado.



## Contextualización ecológica

Como sabemos, la cantidad de especies que hay en una comunidad ecológica es importante para entender muchas características estructurales y funcionales de los ecosistemas. En concreto hay dos descriptores importantes en una comunidad ecológica: riqueza de especies y diversidad. La riqueza de especies es fácil de entender: es la cantidad de especies que hay en una comunidad dada. Es un descriptor importante, pero tiene varios problemas para ser usado de manera estándar. Uno de ellos es que depende del esfuerzo de muestreo de especies. Es posible que lugares con muchas especies den valores bajos en este parámetro si no han sido suficientemente muestreados. Para minimizar este problema se usan otros indicadores de diversidad. En nuestro caso trabajamos con el[ índice de Shannon](https://es.wikipedia.org/wiki/%C3%8Dndice_de_Shannon), que tiene en cuenta tanto el número de especies como su abundancia relativa. 

La diversidad biológica se distribuye por la Tierra según una serie de patrones espaciales que vimos en la [actividad anterior](https://rawcdn.githack.com/aprendiendo-cosas/P_shannon_SIG_II_Geoforest/2023__2024/guion_practica_mapa_biodiversidad.html). Dichos patrones ponen de manifiesto cómo se comporta la diversidad frente a ciertos factores ambientales. Por ejemplo:

+ Hay un patrón de distribución de la diversidad en función de la latitud. En el Ecuador hay más diversidad que en los polos. 
+ Heterogeneidad ambiental. Se ha comprobado que los lugares más heterogéneos desde un punto de vista ambiental (más cambios en las condiciones climáticas, por ejemplo), albergan más diversidad.
+ Dureza ambiental. En multitud de ocasiones se ha comprobado que los lugares sometidos a más perturbaciones o más fuentes de estrés, tienen menos diversidad biológica.

[Este](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_SIG_II_geoforest/raw/2023_2024/biblio/biodiversity_patterns.pdf) artículo describe con detalle estos patrones y algunos más. El foco de esta actividad es que, si bien los factores anteriores explican la distribución de la diversidad, lo hacen de forma distinta dependiendo de la escala espacial a la que "observamos". 



## Planteamiento del problema

En el curso 2019-2020, al terminar la práctica sobre el mapa de biodiversidad, una estudiante (Belén, de ciencias ambientales) me hizo la siguiente pregunta: "*Con esto que hemos visto podemos obtener un mapa del índice de Shannon de cada comunidad de Sierra Nevada. Pero, ¿cómo se calcularía el índice de Shannon de todo el espacio protegido?, ¿se calcularía haciendo el promedio de todos los puntos o habría que calcular desde el principio el índice de Shannon considerando que todos los puntos pertenecieran a la misma comunidad?*" No supe contestar en ese momento, pero me comprometí a darle una respuesta más tarde.

Me puse a trabajar e hice lo que Belén propuso. En el proceso aprendí que la diversidad cambia su significado según la escala a la que la midamos. Eso nos permite definir un tipo de diversidad diferente. En este ejercicio trataremos de reproducir el proceso de aprendizaje que yo experimenté. Y como nadie aprende en cabeza ajena, pues te tocará hacerlo a tí para deducir lo mismo que yo deduje :)

En las siguientes secciones se describe cómo procederemos. En primer lugar contaré los pasos que di yo. De ahí podrás descargar información que necesitas para seguir el trabajo.

### Pasos que di yo para responder a Belén

En primer lugar descargué de GBIF todos los datos de presencia de especies de Andalucía.  Esto supone trabajar con una base de datos de 11.448.644 registros. Abajo puedes ver la densidad de puntos de presencia de especies según GBIF en nuestra región.

<img src="https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_SIG_II_geoforest/raw/2023_2024/imagenes/occurrences_gbif.png" alt="Puntos GBIF" style="zoom:50%;" />

A partir de estos datos obtuve dos mapas de distribución del índice de Shannon. En cada uno de ellos la referencia espacial era diferente:

#### Mapa de diversidad a escala de comunidad
Consideré que el tamaño medio de una comunidad ecológica en Andalucía eran unos 250 m. Dividí todo el territorio en cuadrículas de ese tamaño y apliqué el script (programa) de R que vimos en la práctica.  La siguiente imagen muestra la malla anterior y los puntos de presencia de especies. 

<img src="https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_SIG_II_geoforest/raw/2023_2024/imagenes/grid.png" alt="grid" style="zoom:50%;" />

El resultado (tras dos días de procesamiento) se puede ver en la imagen de abajo. Y [aquí](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_SIG_II_geoforest/raw/2023_2024/geoinfo/H_250.tif) puedes descargar la capa en formato raster (para que ocupe menos espacio)

<img src="https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_SIG_II_geoforest/raw/2023_2024/imagenes/shannon_250.png" alt="shannon 250m" style="zoom:50%;" />

#### Mapa de diversidad a escala de paisaje

También apliqué el script de R anterior a la red de espacios protegidos de Andalucía. Es decir, calculé la diversidad de cada espacio protegido: diversidad a escala de paisaje. En este caso cada espacio protegido recibe un único valor del índice de Shannon. Se calcula computando las abundancias relativas de todas las especies presentes en ese espacio protegido.

A continuación puedes ver el resultado. También puedes descargarlo [aquí](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_SIG_II_geoforest/raw/2023_2024/geoinfo/H_natura.tif) en formato raster:

<img src="https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_SIG_II_geoforest/raw/2023_2024/imagenes/shannon_natura_label.png" alt="natura Shannon" style="zoom:100%;" />

***

Los mapas anteriores muestran diferentes patrones en la distribución espacial de la diversidad. Ahí van algunos ejemplos:

+ Fíjate, por ejemplo, en los espacios de Sierra Morena (parte norte de Andalucía. Zona etiquetada como A en el mapa anterior). En esos espacios hay alta diversidad (tonos azules) a escala de comunidad, pero baja a escala de paisaje (tonos anaranjados y rojos). 
+ Otro buen ejemplo de esta discrepancia entre el significado de la diversidad a las dos escalas consideradas es el Parque Natural de Cabo de Gata (extremo suroriental de Andalucía, en la costa). Observa cómo las comunidades de esa zona tienen una diversidad baja (es una zona semidesértica donde la vida es dura...). Sin embargo, la diversidad del espacio en su conjunto es muy alta (aparece coloreado de azul en el mapa).

Recordemos que la pregunta inicial es: ¿se obtendría el mismo valor del índice de Shannon calculando el promedio de la diversidad de las comunidades de un espacio protegido que calculando el índice para dicho espacio en su conjunto? Con las capas anteriores, te toca responder a la pregunta. Te sugiero que procedas de la siguiente forma:

### Pasos que tú tienes que dar...

Por un lado tienes un mapa que muestra el índice de Shannon de cada cuadrícula de 250 m. Y por otro hay otro raster que muestra el índice de Shannon de cada espacio protegido. ¿cómo respondemos la pregunta de Belén? 

Para hacer esto suele ser útil visualizar la forma que tendría el resultado final esperado. En este caso, nos vendría bien tener una tabla en la que asignemos a cada espacio protegido el valor del índice de Shannon a las dos escalas espaciales consideradas (promedio del índice de Shannon de cada comunidad e índice de Shannon de todo el espacio). No es necesario que en esta tabla estén todos los espacios protegidos de Andalucía. Basta con que selecciones algunos. Para elegir con cuál trabajas, observa cómo se distribuyen los dos "tipos de diversidad" de los que estamos hablando...

Con este objetivo en mente, ¿qué se te ocurre que podrías hacer? Ahí va una pista: herramientas de geoprocesamiento que extraen valores de un raster...

Ah, se me olvidaba, además de las dos capas raster anteriores, también necesitarás la delimitación de los espacios protegidos de Andalucía (red Natura 2000). [Aquí](https://github.com/aprendiendo-cosas/A_escalas_shannon_Andalucia_SIG_II_geoforest/raw/2023_2024/geoinfo/red_natura_2000.zip) la tienes en formato shapefile.


## Resultado

En la siguiente presentación hay alguna pista para entender lo que está pasando. No la veas hasta el final :)


<iframe src="https://prezi.com/p/embed/hlzq3rFR88R4Vs84CVly/" id="iframe_container" frameborder="0" webkitallowfullscreen="" mozallowfullscreen="" allowfullscreen="" allow="autoplay; fullscreen" height="516" width="562"></iframe>


Y en el siguiente vídeo está la grabación de la sesión en cuestión :)

<iframe width="560" height="515" src="https://www.youtube.com/embed/ocDYjb-Dkx8?si=K_sbeFqHPCMs62-S" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
