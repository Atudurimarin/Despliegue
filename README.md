# Despliegue

(Nota: AL final y después de tener problemas con mi grupo del proyecto, he hecho el despliegue con el .war y la base de datos del grupo de Dani Valcarce y Toni Feliu)

## Introducción

Vamos a utilizar docker compose que nos permitirá arrancar los contenedores en los que se encuentrán la base de datos, el Tomcat y PHP para realizar el despliegue de nuestra aplicacíon.<br><br>

## 1. ## 
Lo primero que vamos a hacer es crear un directorio dónde pondremos nuestro archivo yml de configuración, el script SQL de la base de datos y el archivo war de nuestra aplicación. En mi caso lo he llamado compose.

![image](https://user-images.githubusercontent.com/91564326/172449715-205a1257-d18b-4312-8804-f137aa104a49.png)

![image](https://user-images.githubusercontent.com/91564326/172449889-2a51f937-ee86-4615-a83e-b70b9d66c426.png)

Usaré la carpeta mysql-dump para guardar el script SQL y la carpeta target para guardar el archivo .war . 

## 2. ##
El siguiente paso va a ser configurar (con el bloc de notas en mi caso) el archivo .yml con la ubicación de los archivos de nuestra aplicación y su configuración (password y usuario).

![yamal1](https://user-images.githubusercontent.com/91564326/172454369-9cc243c6-aff3-4f7f-a7d6-a339e7af9d2c.png)

![yamal2](https://user-images.githubusercontent.com/91564326/172454417-715989f2-c7ea-47d8-a31b-03d38fa9b758.png)

## 3. ##
Con los archivos en nuestra carpeta y el archivo .yml debidamente configurado hacemos un docker-compose -d para que Docker comience a descargar las imagenes necesarias:<br>
![comp1](https://user-images.githubusercontent.com/91564326/172456061-70c7c3ef-ad57-43e6-bc9a-01c564de58e0.png)<br>
comienza a descargar la imagen de Mysql
<br>
![comp2](https://user-images.githubusercontent.com/91564326/172456101-ddef6e6a-ca50-4241-be04-12f21dbb7a5a.png)<br>
Una vez acabada la descarga de Mysql, comienza a descargar PHPmyAdmin
<br>
![comp3](https://user-images.githubusercontent.com/91564326/172456128-3f322d5b-8f65-44f3-a8d3-806f655d208a.png)<br>
Finalmente acaba descargando la imagen de Tomcat.
<br><br>

## 4. ##
Llegados a este punto la aplicación ya estaría desplegada y como hemos configurado, deberíamos ser capaces de ver nuestra web accediendo a localhost:8080/publicClassHamburguesa. En mi caso no me funcionaba y me daba un error 404 por problemas con el Tomcat. Al final resulta que el error estaba en un fallo en la escritura del nombre del proyecto, una vez subsanado la aplicación estaba desplegada y funcionando.



![comp4](https://user-images.githubusercontent.com/91564326/172458633-00048f4b-a985-4b52-b7c7-5e58ac244369.png)

 
![COMP6](https://user-images.githubusercontent.com/91564326/172458632-02c8685b-f90c-40e0-9e7f-8cb868ad65ff.png)

## Conclusiones ##
El despliegue se ha realizado con éxito, aunque he tenido problemas para construir la imagen y hacer el push.

