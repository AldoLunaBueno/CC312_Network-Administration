# Instalación de la VM CSR-1000v (router virtual)

Guía: 

https://itexamanswers.net/7-0-3-lab-install-the-csr1000v-vm-answers.html

## Parte 1. Instalar la VM CSR1000v en VirtualBox

Importamos la VM a VirtualBox:

![](pics_gifs/2023-01-08-20-05-43.png)

![](pics_gifs/2023-01-07-23-40-31.png)

![](pics_gifs/2023-01-07-23-41-26.png)

Ya podemos iniciar la VM. Esta fase del proceso de instalación demora bastante. No tocamos nada hasta que dejan de llegar nuevos mensajes...

![](pics_gifs/2023-01-07-23-52-07.png)

![](pics_gifs/2023-01-07-23-59-17.png)

Lo único que hay que hacer presionar la tecla enter. Nos saldrá una línea de comandos. Introducimos el comando `enable` para poder desbloquear comandos:


![](pics_gifs/2023-01-08-00-09-42.png)

## Parte 2. Verificando comunicaciones a la VM CSR1000v

```
show ip interface brief
```

![](pics_gifs/2023-01-08-20-45-30.png)

En este punto tuvimos un problema que parecía irresoluble. No era posible hacerle ping a CSR1kv. Afortunadamente se resolvió. Se muestra en la sección de dificultades y soluciones.

A continuación probamos la conectividad lanzando un comando ping desde la VM Devasc a nuestra CSR1kv. Vemos que los tres paquetes que enviamos fueron recibidos:

![](pics_gifs/2023-01-09-20-18-40.png)

Habiendo comprabado la conectividad de la red, intentaremos establecer una sesión SSH es Devasc para controlar desde ahí nuestro router virtual CSR1kv.

En Devasc:

```
ssh cisco@<ip_router>
```

La contraseña que usamos es _cisco123!_ Luego salimos con el comando `exit`.

![](pics_gifs/2023-01-09-20-29-51.png)

Ahora nos conectaremos al router por una vía distinta: la interfaz web de Cisco. Solo introlducimos en el navegador web la URL https://\<ip-router> y, si dice que es una conexión insegura, como fue nuestro caso, buscamos la opciones avanzadas para permitirla. 

![](pics_gifs/2023-01-09-20-36-33.png)

Username: cisco

Password: cisco123!

![](pics_gifs/2023-01-09-20-40-36.png)

## Dificultades y soluciones

### Problemas con el adaptador host-only

Máquina Host:

![](pics_gifs/2023-01-08-20-53-00.png)

Devasc (VM):

![](pics_gifs/2023-01-08-21-00-12.png)

Instalé una tercera vez el router virtual y volvió a ocurrir lo mismo.

Aquí está toda la info del sistema:

![](pics_gifs/2023-01-09-00-38-40.png)

![](pics_gifs/2023-01-09-00-39-13.png)

En cuanto a la configuración de la red en Virtual Box, no he tocado nada como dice la guía que seguí. Este es el adaptador host-only que está activado y conectado con la CSR1kv por defecto:

![](pics_gifs/2023-01-09-09-59-13.png)

![](pics_gifs/2023-01-09-10-00-10.png)

La solución fue actualizar Virtual Box. Pasamos de la versión 6.1.38 a la  6.1.40. Y quizás lo que lo cambió todo fue que el adaptador host-only con el que vino cambió:

![](pics_gifs/2023-01-09-19-51-52.png)

Si no hubiera tenido una versión desactualizada, quizás también hubiera tenido el mismo problema, ya que lo que estaba mal al parecer era la configuración de este adaptador.

Con esta configuración pude hacer un ping desde mi máquina host:

![](pics_gifs/2023-01-09-19-54-13.png)