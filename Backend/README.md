## Backend

API creada para la conexión a la base de datos SQL, desarrollada en pyhton.

Hay un archivo IotDB.sql para crear la base de datos.
Un archivo IotPA.sql para los procedimientos almacenados.
Y un archivo inputEjemplos.sql para llenar la base de datos.

Para obtener informacion de la API se debe de realizar una peticion GET hacia cualquiera de las rutas disponibles con sus respectivos parametros:

#Administrador / Usuarios

###### /login?username=&contrasena=
###### /insert?name=&email=&username=&password=&date_register=&admin=
###### /delete?username= 
###### /modify?username=&name=&email=&status=
###### /search?username=
###### /showAllUser

#Espacios

Stage
###### /insertStage?id_stage=&name=&user=&admin=
###### /deleteStage?id_stage= 
###### /searchStage?id_stage=
###### /modifyStage?id_stage=&name=
###### /showAllStage

Floor
###### /insertFloor?id_floor=&name=&id_stage=
###### /deleteFloor?id_floor= 
###### /searchFloor?id_floor=
###### /modify?id_floor=&name=
###### /showAllFloor

Room
###### /insertRoom?id_room=&name=&id_floor=&id_scenario=
###### /deleteRoom?id_room= 
###### /searchRoom?id_room=
###### /modify?id_room=&name=&id_scenario=
###### /showAllRoom

#Dispositvos

###### /insertProduct?id_product=&name=&description=&os=&id_device=&status=&brand=&model=&x=&y=&id_room=

###### /insertSensor?id_sensor=&type=&firmware=&clasification=&id_device=&status=&brand=&model=&x=&y=&id_room=

###### /deleteDevice?id_device=
###### /searchDevice?id_device=
###### /type?type_device=
###### /modifyDevice?id_device=&brand=&model=&x=&y=
###### /showAllDevice

Regresa un flask.Response() y un status code 200. Se puede convertir en un JSON con JSON.parse(); la estructura de la respuesta depende de los parametros que se den.

En la parte login se usa una llave para la encriptación de las contraseñas es "asdfghjkl", mientras que el método de encriptación es salt.