# Simple-layout  
  Simple-layout es una librería basada en flex-bos y escrita en sass que permite la contrucción rápida de aplicaciones web.
# Tabla de contenido
* [Instalación](#instalación)
* [Uso](#uso) 
* [Elementos](#elementos)
* [Columnas](#columnas)
  * [Columnas en distintos tamaños de pantalla](#columnas-en-distintos-tamaños-de-pantalla)

## Instalación  
`npm i @pixela/simple-layout`

## Uso:
Para hacer uso del paquete se deberá importar donde éste sea necesario.

`@import '~@pixela/simple-layout';`

## Columnas:
Como utilizar columnas:

Se deberá utilizar el mixin `col()`, se podrá utilizar de las siguientes maneras:

* `col()` de esta manera se generá un elemento que ocupa 12 columnas, con un máximo de 12 columnas, es decir el resultado será un elemento que ocupe todo el ancho del contenedor, los valores del número de columnas a ocupar y el máximo de columnas están definidos en las __Variables globales__.

* `col(numero_de_columnas)` también se puede utilizar enviando el número de columnas que ocupará el elemento, por ejemplo `col(4)` generá un elemento que ocupa 4 columnas de un máximo de 12.


#### Columnas en distintos tamaños de pantalla:
  Para los distintos tamaños de pantalla definidos en las __Variables globales__, se pueden utilizar distintas versiones del mixin `col()` las cuales funcionan de la misma manera, las columnas se podrán vizualisar hasta que el tamaño de pantalla sea igual al tamaño definido.

  * `col-sm()` hasta pantallas pequeñas, por defecto tiene un máximo de columnas de 4.
  * `col-md()` hasta pantallas medianas, por defecto tiene un máximo de columnas de 6.
  * `col-lg()` hasta pantallas grandes, por defecto tiene un máximo de columnas de 8.
  * `col-xl()` hasta pantallas extra grandes, por defecto tiene un máximo de columnas de 10.

  * __Ejemplo:__ el objeto cambiará el número de columnas segun el tamaño de la pantalla  
  ```
  .objeto {
      col(6); //ocupara 6 columnas de 12
      col-xl(4); //ocupara 4 columnas de 10
      col-lg(3); //ocupara 3 columnas de 8
      col-md(2); //ocupara 2 columnas de 6
      col-sm(1); //ocupara 1 columnas de 4
  }
  ```
  Todas las versiones anteriores también pueden recibir como parámetros el número de columnas por ejemplo `col-md(numero_de_columnas)`   
  ## Filas:
  Para utilizar filas se deberá utilizar o extender la clase `.row`
  ```
    <div class="row"></div>
  ```

## Elementos:

  * #### Navs:
  Un elemento de tipo nav se utiliza para realizar menús, haciendo uso de links dentro de su estructura. Para utilizar navs existen 2 opciones ya sea utilizando la clase `.nav` en un elemento o utilizando el elemento `<nav></nav>`, ejemplos:
    * ###### utilizando la clase
 ```
 <ul class="nav">
   <li><a href="#">opc1</a></li>
   <li><a href="#">opc2</a></li>
   <li><a href="#">opc3</a></li>
 </ul>
 ```
   * ###### utilizando el elemento
 ```
  <nav>
    <a href="#">opc1</a>
    <a href="#">opc2</a>
    <a href="#">opc3</a>
  </nav>
 ```
  * #### Containers:
  Se utilizan para contener a otros elementos dentro del mismo.
  Para utilizar contenedores se debe extender la clase `%container`, los parámetros de los contenedores como el tamaño máximo y el ancho estan definidos en las __Variables globales__
  ```
  .objeto {
      @extend %container;
  }
  ```

  * #### Sections:
  Se utilizan para diferenciar distintas secciones de un documento, haciendo uso de paddings.
  Para utilizar Secciones se debe utilizar la case `.section` o el elemento  `<section></section>`, los parámetros para modificar los paddings de las secciones estan definidos en las __Variables globales__.
    * ###### utilizando la clase:
  ```
  <div class="section"></div>
  ```
    * ###### utilizando la clase:
  ```
  <section></section>
  ```

## Variables globales:
Todas las variables globales se declararán en el archivo __settings.scss__, para sobreescribir los valores se deberán crear las variables con el mismo nombre y el valor nuevo, las variables que el paquete contiene por defecto son:

* #### Margenes:
 valores de los márgenes para distintos elementos
  * `$global-margin:` Es el valor de todos los márgenes, por defecto es de  16px
  * `$global-padding:` Es el valor de todos los paddings, por defecto es de 16px
  * `$gutter:` Es el valor de los márgenes entre columnas, este es igual a `$global-margin`
  * `$nav-link-margin:` Es el valor de los márgenes de un elemento nav, este es igual a `$global-margin`

* #### Columnas:
  Parámetros para manejar las columnas de un elemento
  * `$cols:` Número de columnas a ocupar por un elemento, su valor es de 12
  * `$max-cols:` Número máximo de columnas de un elemento, su valor es de 12  

* #### Límites de columnas con distintos tamaños de pantalla:
  * `$cols-sm:` Número de columnas a ocupar por un elemento en pantallas pequeñas, su valor es de 4
  * `$max-cols-sm:` Número máximo de columnas de un elemento en pantallas pequeñas, su valor es de 4
  * `$cols-md:` Número de columnas a ocupar por un elemento en pantallas medianas, su valor es de 6
  * `$max-cols-md:` Número máximo de columnas de un elemento en pantallas medianas, su valor es de 6
  * `$cols-lg:` Número de columnas a ocupar por un elemento en pantallas grandes, su valor es de 8
  * `$max-cols-lg:` Número máximo de columnas de un elemento en pantallas grandes, su valor es de 8
  * `$cols-xl:` Número de columnas a ocupar por un elemento en pantallas extra grandes, su valor es de 10
  * `$max-cols-xl:` Número máximo de columnas de un elemento en pantallas extra grandes, su valor es de 10

* #### Tamaños de pantalla:
Distintos tamaños de pantalla a utilizar
  * `$sm-screen:`  Pantalla pequeña 480px
  * `$md-screen:`  Pantalla mediana 760px
  * `$lg-screen:`  Pantalla grande 1024px
  * `$xl-screen:`  Pantalla extra grande 1600px

* #### Tamaños de contenedores:
  Valores para manejo de contenedores
  * `$container-width:` Ancho de contenedor 100%
  * `$max-cont-width:`  Ancho máximo para un conteneror 1200px

* #### Tamaños de padding:
  Valores de padding para aplicar a elementos
  * `$padding-sm:` Padding pequeño 24px
  * `$padding-md:` Padding grande 36px
  * `$padding-lg:` Padding grande 48px
  * `$padding-xl:` Padding extra grande 64px

* #### Colores:
  En este archivo también se definirán los colores a utilizar en el proyecto.  
  __ejemplo:__  
  `$orange: #fe6d0e `
