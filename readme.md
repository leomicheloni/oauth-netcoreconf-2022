![](./img/oauthlogo.png)

![](./img/ejemploaccesoyelp.png)
![](./img/ejemploaccesofacebook.png)
![](./img/ejemploaccesoria.png)

# Autorización, Tokens, Flujos, oAuth y OIDC para todo el mundo

# Leonardo Micheloni

@leomicheloni

## La necesidad

Existen muchos escenarios en los que necesitamos acceder a un recurso de un tercero desde nuestra aplicación.
Por ejemplo si estamos desarrollando una aplicación para gestionar la cuenta de Twitter de los usuarios necesitaremos acceso a la información de su cuenta, su timeline y hasta permisos para publicar en su nombre.
 También podemos tener la necesidad de crear una aplicación que simplemente busque los TT en Twitter y haga algo con eso.
 Otro ejemplo podría ser necesitar acceder a la información de Google maps, un conjunto de recursos de una plataforma de terceros, etc.
 O acceder los contactos de Gmail de una persona para invitarlos a participar de nuestra propia plataforma.

 En el pasado ha habido métodos para lograr esto los cuales han llegado a ser incluso proveer nuestro usuario y password de Gmail para que Yelp acceda a nuestra cuenta y recupere la información de nuestros contactos.

 ## El problema

El problema es encontrar un método para otorgar acceso a algún recurso propio a un tercero sin necesidad de otorgar nuestras credenciales.
Métodos de este tipo, no solo que comprometen nuestras credenciales sino que también dan acceso a todos los recusos que tenemos acceso, el tiempo que se otorga este acceso a ilimitado y, además, finalmente quien obtenga en acceso a fines prácticos actúa como si fuera nosotros mismos ya que tiene las credenciales.

El escenario ideal sería:
 - Otorgar acceso sin exponer nuestras credenciales
 - Que este acceso sea limitado a un grupo de recursos
 - Que el tiempo de duración de este acceso sea limitado
 - Que en caso de comprometerse ese método de acceso el daño sea el menor posible
 
 ## oAuth

 ### Introducción
 Es un protocolo standard de autorización que se encuentra muy extendido, principalmente su versión 2.0.
 

### Autorización vs autenticación
Autorización es la capacidad de acceder a un recurso, estar autorizado para acceder, es equivalente a poseer una entrada para un recital, no importa quién soy ni como la obtuve, si se comprueba que la entrada es válida y para el recitarl correcto, en la fecha, hora y lugar correctos el solo hecho de poseer esta entrada me permite obtener acceso, me autoriza.

Autenticación es la capacidad de verificar la identidad el sujeto, por ejemplo por medio de un pasaporte, en él figuran mis datos y se puede verificar quién soy ya que el documento indica datos propios.

oAuth es un protocolo de autorización.

## Autorización
--- 

![](./img/ticket.jpg)

## Autenticación
---

![](./img/passport.jpg)

---

## Terminología

Para el mismo caso de Yelp queriendo acceder a nuestros contactos de Gmail vamos a cambiar un poco la terminología para que sea más parecida a la que utiliza oAuth

![](./img/diagramaaccesoyelp.png)

- Tiene acceso a todos mis recursos
- Por tiempo indefinido
- De hecho, para Yahoo es yo mismo

Esto también es trasladable a nuestra aplicación.