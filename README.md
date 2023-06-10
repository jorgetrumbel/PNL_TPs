# PNL_TPs
## Repositorio de entrega de TPs de PNL
En este repositorio se presentan los Desafios de la materia Procesamiento del Lenguaje Natural. Se exploran distintos algorítmos relacionados con esta disciplina y se construyen interfaces para cada uno.

## Desafío 1 - Vectorización (TP1):
Este desafío encara temas introductorios del Procesamiento del Lenguaje Natural. Se exploran temas relacionados con la vectorización de términos, es decir, cómo describir matemáticamente las palabras o términos en un documento para poder utilizarlo en un algorítmo de aprendizaje. Entre las técnicas utilizadas están:
  
  -> One Hot Encoding
  
  -> Vectores de frecuencia
  
  -> TF-IDF
  
Cada una de estas técnicas tiene sus ventajas y desventajas. La forma en que se computan puede verse en este Notebook.
Finalmente, este Desafío presenta una manera simple de comparar 2 documentos utilizando la similitud del coseno.

## Desafío 2 - Bot conversacional simple (TP2):
En este Notebook se construye un Bot de mensajería pensado para atender un negocio (por ejemplo un restaurante). Este bot recibe un mensaje del usuario y responde con la información solicitada. Está pensado para funcionar como un sistema de menúes en el cual es usuario es guíado a la información que necesita.

En este trabajo se exploran temáticas de preprocesamiento del texto, como la extracción de caracteres especiales del corpus y la tokenización de los términos utilizando las librerías de Stanza en español. También se realiza la Vectorización con Bag of Words y One Hot Encoding

Para el funcionamiento del Bot, se utiliza un diccionario, donde se establecen ciertas respuestas pre-establecidas a partir de patrones de texto introducidos de forma manual. El Bot se entrena utilizando una DNN simple, obteniendo un buen entrenamiento. La performance es muy buena si se utilizan los términos del diccionario. Si otros términos son utilizados, el Bot responde de forma aleatoria.

![TP2_Bot](https://github.com/jorgetrumbel/PNL_TPs/assets/56329158/4dde3ed6-4ab5-4ba9-821f-16d18b39018e)

## Desafío 3 - Embeddings (TP3):
Este desafío presenta un ejemplo de entrenamiento de embeddings custom utilizando la librería Gensim. En este, se utilizó como dataset de entrenamiento uno de Fake News (Noticias falsas) el cual trae un gran número de headlines y texto escritos a modo de noticiero, en inglés.

En este notebook se pueden observar técnicas de preprocesamiento de texto, utilizando tokenizaciones de Keras y entrenamiento de Embeddings utilizando herramientas de Gensim. Una vez entrenados los embeddings se hacen consultas interesantes al modelo, como ver qué términos considera similares. Es interensante notar como el modelo aprende relaciones entre palabras y, en este caso, resulta a veces cómico ver el desempeño de esto con el dataset de noticias falsas. Por último, el notebook también muestra gráficos de dimensionalidad reducida de los embeddings obtenidos, donde las distnacias entre las palabnras indican la similituyd entre los términos.

![Embeddings_baja_dimension_2](https://github.com/jorgetrumbel/PNL_TPs/assets/56329158/cf96bbe9-7ed7-485b-af51-b276ce8a8ec0)

## Desafío 4 - Predicción de próxima palabra (TP4):
En este Notebook se presenta un modelo de predicción de próxima palabra utilizando el mismo dataset de noticias falsas que en el desafío 3. Para esto, se expande sobre el concepto de los embeddings, que nuevamente son entrenados en este notebook, pero se implementa dentro de una red neuronal para poder hacer luego predicciones.

En este notebook se exploran tematicas de preprocesamiento de texto, usando funciones de tokenizado, y también se tratan temas de secuencialidad, utilizados para entrenar el modelo. Estas secuencialidades buscan dar al modelo una noción de contexto de los términos dentro de las frases. También se presentan las capas LSTM, muy populares para problemas de NLP con secuencialidad, que introducen elementos de memoria dentro de las neuronas.

El modelo final obtenido en este ejemplo tiene un desempeño muy pobre. El entrenamiento del modelo es malo y las predicciones que termina realizando son prácticamente aleatorias. Esto empieza a mostrar la complejidad y altos requerimientos computacionales que requiere conseguir un modelo de este tipo que funcione correctamente, y es razón por la cual se suelen emplear embeddings pre entrenados.

![TP4_predicciones](https://github.com/jorgetrumbel/PNL_TPs/assets/56329158/ba9d2c8d-4416-45e4-98e9-cddbdccd479b)

## Desafío 5 - Sentiment analysis (TP5):
En este desafío se construye un modelo de Deep Learning que realiza predicciones de clases a partir de texto para un dataset de evaluación de compradores. Es decir, busca predecir la calificación de un comprador a partir del texto de la reseña. 

En el notebook se exploran temas relacionados con el preprocesamiento del texto (tokenización) y preparación para entrenar con secuencialidad. También se ve como tratar con datos de salida desbalanceados (las clases de las calificaciones están desbalanceadas) y se entrena un modelo utilizando Embeddings que no están pre-entrenados. Así como en el caso del desafío 4, se puede observar que el entrenamiento de embeddings requere de muchos recursos y tiempo, y por lo tanto los resultados obtenidos son pobres. Las métricas de entrenamiento y validación dan bajas, y en especial pareciera que la validación ya esta haciendo over-fitting.

El siguiente gráfico muestra el MSE obtenido en el entrenamiento:
![TP5_train](https://github.com/jorgetrumbel/PNL_TPs/assets/56329158/ab34b472-1807-472b-924a-7b4d69aedcab)

## Desafío 6 - Bot conversacional (TP6):
Este notebook presenta el desafío de mayor complejidad del repositorio e incluye gran parte de lo visto en todos los anteriores. Consta de la construcción de un Bot conversacional de preguntas y respuestas en inglés. En este, el usuario puede hacerle diversas preguntas al Bot, escritas de la manera que el usuario quiera y el Bot dará una respuesta según lo que procese. Se utiliza el dataset del challenge ConvAI2 (Conversational Intelligence Challenge 2) de conversaciones en inglés.

En particular, se ven temas de preprocesamiento de texto (Remoción de caracteres especiales, agregado de caracteres de control, tokenización de términos, secuencialidad). A su vez, se emplea una red neuronal profunda para hacer las predicciones, con la particularidad de que esta utiliza los embeddings pre-entrenados de Glove. Esto genera que los resultados de accuracy obtenidos por el modelo sean siginificativamente mayores a los obtenidos en los desafíos previos. También utiliza capas LSTM para generar memoria de secuencialidad en la red, permitiendo comprender contexto de los términos en un documento.

A continuación se enumeran algunas de las respuestas obtenidas del modelo:

  -> Input: what do you do for a living. Response: i am a student
  
  -> Input: hi. Response: hello how are you
  
  -> Input: Do you have any pet? Response: i am a vegan i am a vegan
  
  -> Input: Where are you from? Response: i am a student
  
  -> Input: How are you? Response: i am fine
  
Si bien las respuestas no parecen ser humanas y el bot responde a veces de forma errática, se puede ver claramente que este logra comprender las oraciones que se dan de input al modelo y da una respuesta razonable en muchos casos. También se destaca que, si bien se utilizaron embeddings pre entrenados, el entrenamiento del modelo igual requirio de mucho tiempo para poder llegar a un resultado razonable.
