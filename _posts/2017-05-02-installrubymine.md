---
layout: post
title: Instalar Ruby Mine En Ubuntu
---

Que onda! checaremos la instalación de rubymine, primero nos descargamos el tar.gz de la pagina official de [rubymine](https://www.jetbrains.com/ruby/download/#section=linux)
una vez descargado procederemos a instalarlo

#Primero lo descomprimimos
```shell
  tar -xzf RubyMine-tuversionaqui.tar.gz
```
#hacemos un directorio para RubyMine
```shell
  mkdir -p /opt/rubymine
```
#movemos el rubymine a este directorio
``` shell
  mv ~/Downloads/RubyMine-tuversionaqui /opt/rubymine
```
#Creamos un link symbolico
``` shell
  ln -nfs /opt/rubymines/RubyMine-X.Y.Z /opt/rubymine
```
para iniciar el rubymine tenemos que ejecular el sh del direcctorio /opt/rubymine/bin/rubymine.sh
#ahora lo haremos attachable a un dock o a el menu de software de ubuntu
en rubymine vamos a Tools -> Create Desktop Entry
esto creara un atajo para el menu de el sistema
cierren rrubymine y arranquenlo desde el menu del sistema o buscador de applicaciones

y listo ya tienes rubymine
