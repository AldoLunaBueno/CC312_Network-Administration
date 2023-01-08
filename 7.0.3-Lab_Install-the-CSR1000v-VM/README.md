# Instalación de la VM CSR-1000v (router virtual)

Guía: 

https://itexamanswers.net/7-0-3-lab-install-the-csr1000v-vm-answers.html

## Parte 1. Instalar la VM CSR1000v en VirtualBox

![](pics_gifs/2023-01-07-23-32-40.png)

![](pics_gifs/2023-01-07-23-40-31.png)

![](pics_gifs/2023-01-07-23-41-26.png)

![](pics_gifs/2023-01-07-23-52-07.png)

En esta fase el proceso de instalación demora bastante. No tocamos nada hasta que dejan de llegar nuevos mensajes:

![](pics_gifs/2023-01-07-23-59-17.png)

Lo único que hay que hacer presionar la tecla enter. Nos saldrá una línea de comandos. Introducimos el comando `enable`:


![](pics_gifs/2023-01-08-00-09-42.png)

## Parte 2. Verificando comunicaciones a la VM CSR1000v

```
show ip interface brief
```

![](pics_gifs/2023-01-08-00-20-33.png)