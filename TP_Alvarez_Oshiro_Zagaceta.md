<hr>

<p align="center">
    <strong>Universidad Peruana de Ciencias Aplicadas</strong><br>
    <img src="https://upload.wikimedia.org/wikipedia/commons/f/fc/UPC_logo_transparente.png"></img><br>
    <strong>Ingeniería de Software - 2024-1</strong><br>
    <strong>Complejidad Algorítmica - WX72</strong><br>
    <br>INFORME DE TRABAJO PARCIAL - PRIMER HITO<br>
</p>

<div style="text-align:center;">
    <h3>Team Members:</h3>
    <table align="center">
        <tr>
            <th style="text-align:center;">Member</th>
            <th style="text-align:center;">Code</th>
        </tr>
        <tr>
            <td>Alvarez Araguache, Samira Jetzabel</td>
            <td>U20211A046</td>
        </tr>
        <tr>
            <td>Oshiro Yamashita, Daiki Oscar </td>
            <td>U20201F846</td>
        </tr>
        <tr>
            <td>Zagaceta Bardales, Rodrigo Enrique</td>
            <td>U202215489</td>
        </tr>
    </table>
</div>

<p align="center">
    <strong>Abril, 2024</strong>
</p>
<br>

## [1. Descripción del problema](#1-descripción-del-problema-1)
## [2. Descripción y visualización del conjunto de datos (Dataset)](#2-descripción-y-visualización-del-conjunto-de-datos-dataset-1)
- [2.1. Descripción del conjunto de datos](#21-descripción-del-conjunto-de-datos)
- [2.2. Visualización del conjunto de datos](#22-visualización-del-conjunto-de-datos)
## [3. Propuesta](#3-propuesta-1)
## [4. Bibliografía](#4-bibliografía-1)
## [5. Anexos](#5-anexos-1)

# 1. Descripción del problema

El problema que abordaremos se centra en la gestión eficiente del tiempo de entrega de productos entre los almacenes de una empresa ubicada en Lima. La empresa busca minimizar el tiempo requerido para entregar los productos entre sus diferentes ubicaciones, teniendo en cuenta las limitaciones de la infraestructura vial y las condiciones variables del tráfico en la ciudad.

Según el Plan de Desarrollo Urbano de Lima Metropolitana al 2035, publicado por la Municipalidad Metropolitana de Lima, se estima que la congestión del tráfico en Lima causa pérdidas económicas significativas, que ascienden a aproximadamente el 3% del PIB de la ciudad. Estas pérdidas incluyen costos asociados con el tiempo perdido en el tráfico, el aumento del consumo de combustible y los impactos negativos en la productividad de las empresas debido a retrasos en la entrega de productos.

La gestión del tiempo de entrega implica encontrar las rutas más eficientes para transportar los productos entre los almacenes, considerando la distancia, las condiciones del tráfico en tiempo real y las características de la red vial de Lima.

Objetivos a lograr:

- Diseñar un sistema de gestión del tiempo de entrega que minimice los tiempos de transporte entre los almacenes de la empresa en Lima, Perú.
- Maximizar la eficiencia en la distribución de productos, asegurando entregas rápidas y consistentes en todo momento.

# 2. Descripción y visualización del conjunto de datos (Dataset)
Mediante el uso de una base de datos en la que se encuentre la ubicación detallada de cada uno de los elementos en el almacén. Obtendremos los datos de la latitud, longitud y número de local o almacén en el que se ubican los objetos. Los datos recolectados son en total de 1500 intersecciones en todos los almacenes.
## 2.1. Descripción del conjunto de datos
Los siguientes datos presentes en el cuadro 1, son los usados para la creación de nuestro mapa del inventario. El primer punto es el identificador del nodo o ID_Nodo, los números son las tiendas ubicadas en la ciudad y las letras los lugares para recoger los materiales para llevarlos a las tiendas, el segundo carácter es la latitud y por último la longitud del grafo. En cuanto al cuadro 2, el cuál está relacionado con las distancias de las aristas entre los nodos del grafo, el primer y segundo carácter están relacionados con los nodos y el último carácter es la distancia presente entre ambos. Todos estos datos están relacionados con la ciudad de Canta.

- Cuadro 1:
  
<img src="img/CUADRON1.png" alt="Descripción Cuadro 1" style="width: 65;"></img>

- Cuadro 2:

<img src="img/CUADRON2.png" alt="Descripción Cuadro 2 Parte 1" style="width: 65;"></img>


## 2.2. Visualización del conjunto de datos
Visualizamos un mapa de toda Lima, imágen 1, el cuál sería la área en la que estará disponible nuestro servicio de búsqueda avanzada para encontrar el mejor camino posible para la gestión de inventarios. En base a nuestros datos, se representa el grafo obtenido según su longitud y latitud asignados a cada uno de los nodos generados. A modo de ejemplo en la imágen 2 se colocó un grafo de una parte de Lima en específico que es en Canta.

- Imagen 1:

<img src="img/visualizacion-imagen1.png" alt="Visualizacion Imagen 1" style="width: 65;"></img>

- Imagen 2:

<img src="img/visualizacion-imagen2.png" alt="Visualizacion Imagen 2" style="width: 65;"></img>

# 3. Propuesta
El propósito principal de este proyecto es crear un sistema que permita reducir los tiempos de transporte entre los almacenes de una empresa con sede en Lima, Perú. Este sistema busca maximizar la eficiencia en la reposición de productos y reducir los tiempos de entrega. Esto contribuirá a mejorar la rentabilidad y la sostenibilidad económica de la empresa a largo plazo, así como mejorar la experiencia del cliente.

<img src="./img/diagrama-bloques.PNG" alt="Diagrama de bloques del programa" style="width: 65;">

Diagrama de bloques de la ruta de los datos en tiempo de ejecución del programa. Inicialmente los datos se introducen en el programa. Luego, se procesan estos datos, para después pasarlos por el algoritmo de Dijsktra. Finalmente, al terminar el algorítmo, se tendrá como resultado la ruta más corta a partir de los datos introducidos inicialmente. Esta ruta se podrá visualizar a través de una interfaz, donde se observarán los vértices que conforman el camino más corto entre el vértice de inicio y el vértice final.

## 3.1. Técnicas

Para lograr estos objetivos, se utilizará el algoritmo de Dijkstra modificado. Dicho algoritmo permite encontrar la ruta más corta con el uso de grafos ponderados. El algoritmo determinará dicha ruta desde un nodo de partida hasta los demás nodos del grafo, siguiendo el camino en las aristas de menor peso. Para ello, se le asigan un peso de 0 al nodo de origen, mientras que al resto se le asigna un peso infinito. Estos nodos son agrupados, para luego ser extraídos según su peso, iniciando desde el menor. Según este nodo, para los nodos adyacentes se calcula el peso desde el vértice de origen. Si este número es menor al peso inicial, se actualiza la distancia y el nodo vecino se añade al grupo. Este proceso tiene 'n' iteraciones, hasta que dicho grupo se encuentre vacío (Jonhsonbaugh, 2005)

La eficacia de Dijkstra en este tipo de casos ha sido demostrada en investigaciones previas con resultados positivos. Por ejemplo, en el estudio de Curo (2016), evidenció mejoras significativas en la reducción del tiempo y la distancia de la distribución de productos entre secciones de un mismo almacén. Además, Ortiz (2019), logró una reducción del 65.07% en el tiempo de respuesta del serenazgo de la zona de Abancay, Apurimac, al estimar la ruta más corta a recorrer por parte de los serenos para atender el llamado de un ciudadano.

## 3.2. Metodología

La metodología a seguir para este proyecto iniciará con la recopilación y generación de las posibles rutas en la ciudad de Lima, así como la ubicación de los almacenes en el mapa, las distancias entre ellos y la división por zonas para facilitar la implementación del algoritmo. Luego, se procederá a modelar el grafo, donde los nodos representarán los almacenes de la empresa y las aristas las rutas entre ellos, mientras que los pesos representarán las distancias entre los vértices. Una vez realizado esto, se pasará a implementar el algoritmo de Dijkstra, segmentado por zonas, lo que nos permitirá encontrar las rutas más cortas entre los almacenes, optimizando así el tiempo de despacho de los productos.

# 4. Diseño del aplicativo

En esta parte haremos el diseño del aplicativo mediante las etapas de la ingeniería de software.

## 4.1 Requisitos del aplicativo

Optimización de Rutas:

- Algoritmo para calcular la ruta más eficiente entre almacenes.
- Ajustes dinámicos de rutas basados en tráfico en tiempo real y condiciones de transporte.

Ubicación de Almacenes:

- El sistema debe permitir la entrada y almacenamiento de las coordenadas GPS de todos los almacenes en Lima.
- Debe proporcionar una interfaz para visualizar la ubicación de los almacenes en un mapa interactivo.

Generación de Rutas:

- El sistema debe permitir la entrada y almacenamiento de posibles rutas entre los almacenes.
- Debe mostrar las rutas en el mapa interactivo para facilitar la visualización y verificación.

Creación del Grafo:

- El sistema debe modelar un grafo donde los nodos representen almacenes y las aristas representen rutas entre ellos.
- Debe asignar pesos a las aristas basados en las distancias calculadas o ingresadas.


## 4.2 Requisitos funcionales

Optimización de Rutas:

F1.1: El sistema debe calcular la ruta más eficiente basada en la distancia y el tráfico en tiempo real.

Simulación de Escenarios:

F2.1: El sistema debe permitir la simulación de diferentes escenarios de transporte para evaluar el impacto de cambios en rutas, volúmenes de carga, horarios, etc.
F2.2: Los usuarios deben poder comparar resultados de diferentes simulaciones para tomar decisiones informadas.

## 4.3 Requisitos no funcionales

Usabilidad:

NF1.1: El sistema debe ser intuitivo y fácil de usar, con una curva de aprendizaje mínima para los operadores.

Fiabilidad:

NF2.1: El sistema debe tener una disponibilidad del 99.9% durante las horas operativas.

Compatibilidad:

NF3.1: El sistema debe ser compatible con los navegadores web más populares (Chrome, Firefox, Safari, Edge).
NF3.2: Debe ser accesible desde dispositivos móviles y tablets con sistemas operativos iOS y Android.

## 4.4 Programación

Bibliotecas implementadas:

<img src="img/bibliotecas.png" alt="Visualizacion Imagen 1" style="width: 65;"></img>

Clase Grafo:

<img src="img/claseGrafo.png" alt="Visualizacion Imagen 1" style="width: 65;"></img>

Función para calcular el peso de las aristas:

<img src="img/funcionPesoA.png" alt="Visualizacion Imagen 1" style="width: 65;"></img>

Algoritmo de Dijkstra:

<img src="img/claseAlgoritmoD.png" alt="Visualizacion Imagen 1" style="width: 65;"></img>

# 5. Validación de resultados y pruebas

A continuación se visualizará los resultados entregados mediante el código previamente mostrado.

<img src="img/resultado.png" alt="Visualizacion Imagen 1" style="width: 65;"></img>

# 6. Conclusiones

En conclusión, gracias al algoritmo de Dijkstra se pudo facilitar la obtención del camino más corto entre los nodos del grafo, que en este caso fueron entre las tiendas y almacenes de Canta.

Se empleó una codificación en el lenguaje de Phyton para el desarrollo de la solución planteada, el cuál es muy utilizado actualmente en el mundo, por lo que este trabajo nos beneficia en este aspecto para el futuro.

# 7. Bibliografía

Curo, F. (2016). *Sistema para la distribución de productos dentro de un almacén de materia prima con el algoritmo Dijkstra alternativo*. [Tesis de licenciatura, Universidad Cesar Vallejo]. https://repositorio.ucv.edu.pe/bitstream/handle/20.500.12692/101819/Curo_HFW-SD.pdf?sequence=4&isAllowed=y 

Jonhsonbaugh, R. (2005). *Matemáticas Discretas Sexta Edición*. https://es.slideshare.net/slideshow/matemticasdiscretas6edijohnsonbaughpdf/264047527 

Ortiz, B. (2019). *Sistema de red de seguridad basada en el algoritmo de Dijkstra para reducir el tiempo de respuesta ante casos de inseguridad ciudadana en Abancay, 2017*. [Tesis de licenciatura, Universidad Nacional Micaela Bastidas de Apurímac] https://repositorio.unamba.edu.pe/bitstream/handle/UNAMBA/767/T_0478.pdf?sequence=1&isAllowed=y 


# 8. Anexos

Link de acceso al repositorio: https://github.com/ComplejAlgorit/primerhito-tp
