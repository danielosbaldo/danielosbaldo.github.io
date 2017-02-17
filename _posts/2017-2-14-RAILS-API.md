Crear una API con Ruby on Rails  5 !
===================


Que onda! en el presente tutorial veremos como crear un  *Api**[^Apis].  Con ROR, utilizaremos la version 5 de el framework en el siguinte tutorial veremos como conectar REACT con esta API.

Antes de continuar es importante que se tenga conocimiento de lo que son las API y SOA Service Oriented Architectura


### Primero :¿Que es un APi?
un API por sus siglas en ingles Aplication Programming Interface 

### SOA: Arquitectura basada en servicios
[SOA](http://www.epicor.com/lac/solutions/soa.aspx) es una metodo de diseño de arquitectura de software



[Las API'S](http://www.ticbeat.com/tecnologias/que-es-una-api-para-que-sirve/) La interfaz de programación de aplicaciones, abreviada como API del inglés: Application Programming Interface, es un conjunto de subrutinas, funciones y procedimientos (o métodos, en la programación orientada a objetos) que ofrece cierta biblioteca para ser utilizado por otro software como una capa de abstracción.

## Comencemos:
para iniciar lo primero que tenemos que hacer es asegurarnos de que todo este instalado y listo esto no es para principiantes en el ambiente rails si es su caso primero visiten instalacion aqui enlaces para cada plataforma:
###WINDOWS:
hay 2 rutas la mas facil y rapida es con [RailsInstaller](http://railsinstaller.org/en) Pero en lo personal no me agrada.
La segunda es [Vagrant](https://www.vagrantup.com/) el cual te permite manejar maquinas virtuales de manera rapida y sencilla apate de combinarlo con [Chef](https://www.chef.io/chef/) para la preinstalacion de todos los componentes. Vagrant es increible permite tener todas las bondades de linux en windows y con un consumo minimo de recursos Definitivamente lo recomiendo para los que deseen utilizar windows

### Linux:
Recomiendo seguir esta Guia por [Go Rails](https://gorails.com/setup/ubuntu/16.04)
explica exelente el proceso OJO hay que leer a detalle
## A lo que truje chencha
para iniciar la aplicacion en modo API es necesario correr el siguiente comando
```shell
rails new api_app_name --api
```
nos movemos al directorio que creamos
```shell
 cd nombre_del_api
 bundle install
 bin/rake db:setup
```
Despues configuramos RSPEC para el Testeo con:
[Rspec](http://rspec.info/)
en nuesto gemfile en la secion de desarrollo y testeo se agrega rspec-rails
```shell

```
