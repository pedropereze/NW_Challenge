# NeuralWork Challenge


Como se pide trabajar con una base de datos, creé una en MySQL con las siguientes credenciales
Host: 'localhost'
User_name : 'root'
password : 'NW_server_pw'

Aquí creé la tabla con los datos entregados en el .csv y luegó utlicé la información en MySQL como fuente para la ingesta de datos en Python.

En el archivo NW_DS_Challenge.ipynb está la resolución de los distintos problemas mencionados.


### Problema 1

Para el problema 1 realicé k-means para agrupar viajes por origen-destino y a partir del histograma de distribución de las horas de cada viaje generé las etiquetas por hora. Luego junté ambas etiquetas para poder agrupar los viajes por origen-destino-hora similares según lo pedido. Además, creé una función que permite etiquetar nuevos viajes y agregarlos al DataFrame creado con los viajes agrupados.


### Problema 2

Para el problema 2, creé la función weekly_mean que recibe las coordenadas x1,y1,x2,y2 que definene el bounding box y la región y calcula los viajes semanales dentro del bounding box en la región entregada.
Luego, para saber el estado de la ingesta de datos, creé triggers para saber cuando se actualiza, ingresa o borra nueva data en la base de datos de MySQL, lo que guardan el tipo de acción que se realizó en una segunda tabla llamada cambios. Esta segunda tabla me permite saber con una consulta simple el estado de la ingesta de datos. La función que entrega el estado de la ingesta de datos se llama ingest_status y depende del largo de la tabla cambios en la última ingesta de datos realizada.

### Comentarios generales

Se me entregó una base de datos de 100 entradas, la que cargué a MySQL, luego todas las funciones y procedimientos que realicé, son en base a los datos ingeridos desde el MySQL, por lo que es independiente del tamaño de la base de datos. Y además, se crearon funciones para trabajar con datos ingresados posterior a la primera carga de datos en SQL como generalización del trabajo.

Por el momento, no tengo experiencia en GCP, por lo que no entrego lo pedido en el punto 5 del desafío.

Desde ya, muchas gracias por la oportunidad de participar de este proceso.
