# backendComics

Creación de un servidor con express para la solicitud a la API  REST xkcd y asi evitar los errores CORS.

## ¿Qué son los errores CORS?

El Intercambio de Recursos de Origen Cruzado (CORS (en-US)) es un mecanismo que utiliza cabeceras HTTP 
adicionales para permitir que un user agent (en-US) obtenga permiso para acceder a recursos seleccionados 
desde un servidor, en un origen distinto (dominio) al que pertenece. Un agente crea una petición HTTP de 
origen cruzado cuando solicita un recurso desde un dominio distinto, un protocolo o un puerto diferente al
del documento que lo generó.
información encontrada en: https://developer.mozilla.org/es/docs/Web/HTTP/CORS

##Solución al problema

Para solucionar el error y poder acceder a la data, la opción era acceder desde el servidor haciendo uso de
express y este hiciera la petición en vez de nuestra aplicación de frontend.

Para esto salimos del directorio de nuestro proyecto y creamos una carpeta donde iniciamos nuestro proyecto
express con npm init y con el comando npm install express node-fetch cors instalamos express y algunas
dependencias, creamos un archivo server.js y alli hacemos nuestra peticion con fetch en un puerto diferente 
al de nuestro proyecto frontend en nuestro caso configuramos nuestro puesto a 5000 en vez que al 3000 que es
el puerto por defecto de nuestra aplicacion frontend.

Luego configuramos que las solicitudes del localhost:3000 pueda acceder a la información del localhost:5000,
entonces como la solicitud se realiza a través del servidor no genera el error CORS y se devuelve una
respuesta con el metodo json().

En nuestro proyecto en vez de hacer la llamada a https://xkcd.com/json.html, hacemos la llamada a 
localhost:5000 que es donde configuramos el puerto en el servidor y finalmente levantamos el servidor express
con node server.js para luego refrescar el navegador de nuestro proyecto de comics y pudimos ver el objeto con
toda la informacion presentada en la API RES.


El proyecto frontend completo lo puedes visualizar en https://github.com/nelidita/comicspruebatecnica/tree/master
