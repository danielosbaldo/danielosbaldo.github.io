---
layout: post
title: Debug Golang runtime
---

Que onda! El dia de hoy vamos a ver como debugear dolang con [delve](https://github.com/derekparker/delve) una poderosa herramienta, un poco parecida a lo que ruby ofrece con [pry](https://github.com/pry/pry)

para seguir estos ejemplos es necesario que conoscas un poco de [golang](https://github.com/golang/go) ó Go como Gustes llamarlo

# Primero lo instalaremos
aqui no hay que quitarle credito a la buena documentacion de delve sige estos [pasos](https://github.com/derekparker/delve/tree/master/Documentation/installation) depediendo de tu plataforma

# lo sigiente es situar un [breakpoint](https://en.wikipedia.org/wiki/Breakpoint) 

en nuestro codigo lo haremos con lo siguiente 
```go
  runtime.Breakpoint()
```

# Agregamos a los importes el runtime

```go
    import (
	_ "github.com/go-sql-driver/mysql"
	"fmt"
	"time"
	"runtime" //esto es lo importante
)
```

# para ejecutar el codigo y continuar con el in

``` shell
  dlv debug [nombredelarchivo]
```

 listo para saber mas como debugear hay que leer la documentacion de [delve](https://github.com/derekparker/delve)