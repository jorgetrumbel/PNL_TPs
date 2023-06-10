# PNL_TPs
## Repositorio de entrega de TPs de PNL
En este repositorio se presentan los Desafios de la materia Procesamiento del Lenguaje Natural. Se exploran distintos algorítmos relacionados con esta disciplina y se construyen interfaces para cada uno.

## Desafío 1 (TP1):
Este desafío encara temas introductorios del Procesamiento del Lenguaje Natural. Se exploran temas relacionados con la vectorización de términos, es decir, cómo describir matemáticamente las palabras o términos en un documento para poder utilizarlo en un algorítmo de aprendizaje. Entre las técnicas utilizadas están:
  
  -> One Hot Encoding
  
  -> Vectores de frecuencia
  
  -> TF-IDF
  
Cada una de estas técnicas tiene sus ventajas y desventajas. La forma en que se computan puede verse en este Notebook.
Finalmente, este Desafío presenta una manera simple de comparar 2 documentos utilizando la similitud del coseno.

## Desafío 2 (TP2):
En este Notebook se construye un Bot de mensajería pensado para atender un negocio (por ejemplo un restaurante). Este bot recibe un mensaje del usuario y responde con la información solicitada. Está pensado para funcionar como un sistema de menúes en el cual es usuario es guíado a la información que necesita.

En este trabajo se exploran temáticas de preprocesamiento del texto, como la extracción de caracteres especiales del corpus y la tokenización de los términos utilizando las librerías de Stanza en español. También se realiza la Vectorización con Bag of Words y One Hot Encoding

Para el funcionamiento del Bot, se utiliza un diccionario, donde se establecen ciertas respuestas pre-establecidas a partir de patrones de texto introducidos de forma manual. El Bot se entrena utilizando una DNN simple, obteniendo un buen entrenamiento. La performance es muy buena si se utilizan los términos del diccionario. Si otros términos son utilizados, el Bot responde de forma aleatoria.
