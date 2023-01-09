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

Hasta aquí llegamos, porque no es posible hacerle ping, como se ve en la siguiente sección.

## Problemas

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