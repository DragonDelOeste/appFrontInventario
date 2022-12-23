# appFrontInventario

Aplicacion Front para Proyecto Curso MongoDB que consiste en un pequeño mantenedor de productos con sus CRUD correspondientes. La Base de datos se encuentra alojada
en el cloud de mongo Atlas. Las credenciales se encuentran en el repositorio: https://github.com/DragonDelOeste/appInventario
se inicia en el puerto 8100 de forma automatica, el front fue creado con IONIC el cual se inicia con el comando ionic serve en el terminal,  si se encuentra ocupado aumenta en 1 . http://localhost:8100/tabs
![image](https://user-images.githubusercontent.com/41128203/209310411-afe5912c-fb0e-46ee-a820-22e25cc08243.png)
se ingresa un producto nuevo como en el siguiente ejemplo:
![image](https://user-images.githubusercontent.com/41128203/209310581-2b0fc3fc-2f95-44bb-bb5a-82758ff91b55.png)
![image](https://user-images.githubusercontent.com/41128203/209310798-6f073c2a-b7cc-4c50-96b0-508df0f976df.png)
![image](https://user-images.githubusercontent.com/41128203/209310894-cd69ecde-6610-4e87-a406-7002444f0e77.png)
Ademas permite modificar el producto al presionar el icono azul del lado derecho. como se visualiza en la imagen, ingresando una nueva informacion.
![image](https://user-images.githubusercontent.com/41128203/209311278-c72d42a9-3fb2-4c58-9a54-0db735eb3998.png)
![image](https://user-images.githubusercontent.com/41128203/209311378-5aa06e67-cb56-4bec-a337-3cfed79dc786.png)
Cabe mencionar que por tiempo quedo con insersion la informacion por lo que crea un nuevo producto con los nuevos datos, manteniendo el producto anterior
![image](https://user-images.githubusercontent.com/41128203/209313510-120913b4-3be8-4deb-b073-6cd43d879187.png)
El cual se procede a eliminar el producto que no se actualizo.
![image](https://user-images.githubusercontent.com/41128203/209313696-c7e1de43-1c22-4b31-b72d-7f22affa9104.png)
![image](https://user-images.githubusercontent.com/41128203/209313846-153c6f17-b8f4-46e0-b5b3-3bbe0c21423f.png)
![image](https://user-images.githubusercontent.com/41128203/209313909-44bf366c-dfad-4f2f-a1da-44e1009197e7.png)
![image](https://user-images.githubusercontent.com/41128203/209314029-7c5d0d32-106d-4d56-a7dc-4c5f6975bcac.png)
se agrega la agregacion $sort con el orden de la fecha de creacion de forma descendente y $count para contar la cantidad de documento que tiene la coleccion,
![image](https://user-images.githubusercontent.com/41128203/209314976-c482b3e3-0608-40b6-9ecf-d4f6711a49bb.png)
Actualmente contiene 3 indexes el predeterminado (_id), el de fecha de creacion y nombre producto para futuras busquedas
![image](https://user-images.githubusercontent.com/41128203/209315236-5505961a-35a0-4cc6-b200-4c09a1ef8454.png)

Para la estrategia de Backup y replica, como es una base de datos pequeña al comienzo se esperara a los 2 TB de datos para fragmentar el cluster y por lo mismo se
utilizaria el Revovery Point Objective(RPO) ya que en un negocio de inventario necesito que la menor perdida de datos en un tiempo no muy prolongado y con la opcion de
oplog tener 3 nodos como minimo o 4 recomendado para poder realizar la replica de informacion al resto de los nodos ya que se necesitan 3 para que pueda existir 
nodo primario y el resto secundario, y en caso que se apaque 1 queden 3 disponibles para que la operacion pueda continuar trabajando, y replicando informacion la
informacion de forma asincrona.

Kevin Rodriguez.
Marco Liberona.
