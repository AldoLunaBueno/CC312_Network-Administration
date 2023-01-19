# Laboratorio 4a. Explorando REST API con API Simulator y Postman

## Parte 2. Explorar la documentación API usando el simuldaor de API

http://library.demo.local/

![](pics_gifs/2023-01-18-23-10-35.png)

### GET /books

![](pics_gifs/2023-01-18-22-13-05.png)

Establecemos el parámetro _includeISBN_ en True para que aparezca en los resultados.

![](pics_gifs/2023-01-18-22-18-08.png)

![](pics_gifs/2023-01-18-22-17-14.png)

### POST /loginViaBasic

Con esta API nos autenticamos para usar las API bloqueadas (las que tienen un candadito a la derecha).

![](pics_gifs/2023-01-18-23-14-37.png)

En los resultados obtuvimos un token de autorización:

_cisco|CfYnXV6oZ3hf6_K7PCPnjVw32XGsoBhBRL28eFbLFfM_

![](pics_gifs/2023-01-18-23-19-38.png)



![](pics_gifs/2023-01-18-23-18-18.png)

### POST /books

![](pics_gifs/2023-01-18-23-27-53.png)

![](pics_gifs/2023-01-18-23-28-08.png)

Vemos el código 200 de HTTP, lo que nos indica que la publicación fue exitosa. También podemos comprobar que el libro se publicó viendo la sección «Our books» de la página principal.

![](pics_gifs/2023-01-18-23-36-04.png)

