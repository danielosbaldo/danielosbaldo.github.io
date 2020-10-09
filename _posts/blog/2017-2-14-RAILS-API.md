---
layout: post
title: Crear una API con Ruby on Rails  5 !
---

Que tal! en el presente tutorial veremos como crear un  *Api**[^Apis].  Con ROR, utilizaremos la version 5 de el framework en el siguiente tutorial veremos como conectar REACT con esta API.

Antes de continuar es importante que se tenga conocimiento de lo que son las API y SOA Service Oriented Architecture


### Primero :¿Que es un API?
un API por sus siglas en ingles Aplicación Programming Interface

### SOA: Arquitectura basada en servicios
[SOA](http://www.epicor.com/lac/solutions/soa.aspx) es una método de diseño de arquitectura de software



[Las API'S](http://www.ticbeat.com/tecnologias/que-es-una-api-para-que-sirve/) La interfaz de programación de aplicaciones, abreviada como API del inglés: Application Programming Interface, es un conjunto de subrutinas, funciones y procedimientos (o métodos, en la programación orientada a objetos) que ofrece cierta biblioteca para ser utilizado por otro software como una capa de abstracción.

## Comencemos:
Para iniciar lo primero que tenemos que hacer es asegurarnos de que todo este instalado y listo esto no es para principiantes en el ambiente rails si es su caso primero visiten instalación aquí enlaces para cada plataforma:

###WINDOWS:
hay 2 rutas la mas fácil y rápida es con [RailsInstaller](http://railsinstaller.org/en) Pero en lo personal no me agrada.
La segunda es [Vagrant](https://www.vagrantup.com/) el cual te permite manejar maquinas virtuales de manera rápida y sencilla a parte de combinarlo con [Chef](https://www.chef.io/chef/) para la preinstalación de todos los componentes. Vagrant es increíble permite tener todas las bondades de Linux en windows y con un consumo mínimo de recursos Definitivamente lo recomiendo para los que deseen utilizar windows.
otra opción para los usuarios de Windows 10 es el uso de WSL ó WLS2. en otro post explicare mas a detalle este Feature [WSL](https://danielvalenzuela.website/).

### Linux:
Recomiendo seguir esta Guía por [Go Rails](https://gorails.com/setup/ubuntu/16.04)
explica excelente el proceso OJO hay que leer a detalle
## A lo que truje chencha
para iniciar la aplicación en modo API es necesario correr el siguiente comando
```shell
rails new api_app_name --api
```
nos movemos al directorio que creamos
```shell
 cd nombre_del_api
 bundle install
 bin/rake db:setup
```
#Ahora a hablar de configuramos
CORS Cross-Origin Http Request es un estándar que permite realizar request desde varios orígenes http para leer mas del tema aquí un enlace de Mozilla [CORS](https://developer.mozilla.org/es/docs/Web/HTTP/Access_control_CORS)

en esta ocasión veremos CORS en rails y se relazara por la gema rack-cors para usarla hay que habilitarla en el Gemfile
```ruby
# Use Rack CORS for handling Cross-Origin Resource Sharing (CORS), making cross-origin AJAX possible
gem 'rack-cors'

```
ahora ingresamos Bundle install

```shell
bundle install
```

ahora nos moveremos a el archivo de configuración `config/initializers/cors.rb` una vez dentro verán todo comentado este archivo hay que editarlo pueden usar las configuraciones que están en [RackCors Github](https://github.com/cyu/rack-cors/)

la mía se ve de la siguiente manera
```ruby

Rails.application.config.middleware.insert_before 0, Rack::Cors do
  allow do
    origins 'example.com'

    resource '*',
      headers: :any,
      methods: [:get, :post, :put, :patch, :delete, :options, :head]
  end
end

```

nota CORS Es recomendado por la [W3C](https://www.w3.org/)


#Serializacion
utilizaremos una gema para serializar active_model_serializers
para mas información blog [serializer](https://www.sitepoint.com/active-model-serializers-rails-and-json-oh-my/)
agregamos al Gemfile
```ruby
gem 'active_model_serializers', '~> 0.10.0'
```
y corremos bundle
```shell

bundle install

```
creamos el archivo `config/initializers/active_model_serializers.rb` y escribimos lo siguiente
```ruby
ActiveModel::Serializer.config.adapter = :json_api
```

#Versionar
Veremos Como versionar las api en ruby se pueden usar gemas pero en este caso les dire como hacerlo desde cero.



Despues configuramos RSPEC para el Testeo con:
[Rspec](http://rspec.info/)
en nuestro gem file en la sección de desarrollo y testeo se agrega rspec-rails

```ruby
group :development, :test do

  # Use RSpec for specs
  gem 'rspec-rails', '>= 3.5.0'

  # Use Factory Girl for generating random test data
  gem 'factory_girl_rails'
end

```

actualizamos bundle

y correemos el instalador

```shell
rails g rspec:install

```
