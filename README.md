infoURL
=======

Programa en Ruby que nos dará información sobre una URL

***

Este código viene a partír de una práctica sobre Ruby (de un [seminario](http://jj.github.io/IV/documentos/seminarios/ruby) de [Infraestructuras Virtuales](http://jj.github.io/IV/) de la [ETSIIT, Granada](http://etsiit.ugr.es/)).

***

###Crearemos una serie de funciones usando Ruby instanciadas con un URL que devuelvan información sobre esta: fecha de envio de petición, tipo MIME y servidor de la web.

Usaremos la cabecera HTTP de respuesta, y escogeremos los campos de la fecha de envio de petición (date), tipo MIME (content-type) y servidor de la web (server). El programa sería:


```

#!/usr/bin/ruby
# -*- coding: utf-8 -*-

require 'net/http'

    def fecha()
        response = Net::HTTP.get_response(ARGV[0],'/')     
        return response['date'].to_s
    end

    def contenido()
        response = Net::HTTP.get_response(ARGV[0],'/')     
        return response['content-type'].to_s
    end

    def servidor()
        response = Net::HTTP.get_response(ARGV[0],'/')     
        return response['server'].to_s
    end

    url = ARGV[0]
    puts "URL introducida: " << url
    puts "Fecha de envío de petición: " << fecha()
    puts "Contenido del tipo MIME: " << contenido()
    puts "Servidor: " << servidor()

```

Donde podemos ver la salida del programa pasándole de entrada "www.google.es"

![imagen](http://i.imgur.com/50TieXT.png)


Puedes ver también el código en este [mismo repositorio]().


***

Autor:
J. Cristóbal López Zafra, @JCristobal en GitHub y con correo de contacto tobas92@gmail.com
