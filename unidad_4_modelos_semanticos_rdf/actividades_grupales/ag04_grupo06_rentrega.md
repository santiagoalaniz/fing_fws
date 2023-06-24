# AG4 - RDF(s)

## Integrantes Grupo 06:

* Santiago Alaniz
* Bruno De Simone
* Javier Gómez

## Descrición del Problema

El 19 de junio del 2023, la Profesora de FWS Edelweis Roher se comunico con nosotros via mail para solicitar una rentrega de la AG04. A grandes rasgos, la rentrega de la AG04 consiste en:

- Parte 1. Corregir la definicion de las relaciones entre las clases modeladas en esta actividad.
- Parte 2 a) y b). Reformular las respuestas dado que no se cumplio con el enunciado de la actividad.

## Descripción de la Solución

### Parte 1
***~ver archivo ag04_grupo06_renetrega.ttl para acceder al RDF schema con la realidad modelada~***

Cambios Notables:

Si bien ambas versiones son muy similares, hay algunas diferencias notables:

1. En la sección de las Clases-RDF de Agroproductos específicos:
   - En la versión antigua, solo existe la clase `PESTICIDA` y se usa una propiedad `tipo_pesticida` para distinguir entre pesticidas químicos y orgánicos.
   - En la versión re-entregada, se distinguen dos subclases de Pesticida: `PESTICIDA_QUIMICO` y `PESTICIDA_ORGANICO`.

2. En las relaciones entre clases:
   - En la versión antigua, las relaciones entre las etapas de producción y los productores se representan mediante la propiedad `transitaPorEtapa`.
   - En la versión re-entregada, las relaciones entre Productores y Etapas, son explícitas y diferenciadas.

3. En la versión proporcionada, se han añadido relaciones adicionales:
   - La relación `"En las diferentes etapas se aplican agroproductos"` se añade para relacionar las etapas de producción con los agroproductos que se utilizan en cada etapa.
   - Se añaden las relaciones `"Algunos pesticidas quimicos afectan a algunos productos"` y `"En la etapa PREPARACION_TIERRA se aplican pesticidas, es importante distinguirlos por tipo"` para representar las interacciones entre los pesticidas y los productos, y cómo se aplican los pesticidas en la etapa de preparación de la tierra.

Ademas, se tienen en cuenta los comentarios realizados por la profesora, para la re-definicion de las relaciones en rdfs.


### Parte 2

#### a. Los fertilizantes pueden ser orgánicos o químicos.

En RDF(s), se podria modelar los fertilizantes de forma similar que lo hicimos con los pesticidas:

```turtle
ex:FERTILIZANTE a rdfs:Class ;
  rdfs:subClassOf ex:AGROPRODUCTO ;
  rdfs:comment "Fertilizante utilizado en la producción agrícola" ;
  rdfs:label "Fertilizante".

ex:FERTILIZANTE_QUIMICO a rdfs:Class ;
  rdfs:subClassOf ex:FERTILIZANTE ;
  rdfs:comment "Fertilizante químico utilizado en la producción agrícola" ;
  rdfs:label "Fertilizante químico".

ex:FERTILIZANTE_ORGANICO a rdfs:Class ;
  rdfs:subClassOf ex:FERTILIZANTE ;
  rdfs:comment "Fertilizante orgánico utilizado en la producción agrícola" ;
  rdfs:label "Fertilizante orgánico".
```

Sin embargo, RDF(s) no permite definir restricciones sobre las propiedades de las clases, por lo que no se puede definir una propiedad `tipo_fertilizante` que distinga entre fertilizantes químicos y orgánicos. Lo que es mas, no se puede expresar la nocion de `exclusion mutua`, es decir, que un fertilizante no puede ser químico y orgánico al mismo tiempo y ademas la `totalidad`, es decir, que todo fertilizante debe ser químico u orgánico.

#### b. En las etapas de siembra(1) y mantenimiento(3) solo se aplican fertilizantes orgánicos.

En primera instancia esta relacion se parece mucho a la descrita en el punto anterior con los pesticidas, sin embargo, hay una diferencia sutil que imposibilita la construccion de la relacion. Pero primero hagamos una distincion sobre la que **si podemos** construir la relacion:

-`En la etapa de siembra (1) Es importante distinguir la aplicacion de pesticidas organicos de la de cualquier pesticida.`

Esto se puede construir en RDF(s) porque se trata de una espicificacion modelada a partir de la definicion de clases y subclases, pero no hay ninguna otra restriccion.

```turtle
  :aplicaPesticidaQuimicoPreparacion a rdf:Property .
    rdfs:domain :PREPARACION_TIERRA .
    rdfs:range :PESTICIDA_QUIMICO .
```

Por eso, aunque suenen similares, la relacion de la parte b introduce una restriccion de `cardinalidad exclusiva` sobre el rango de la propiedad, es decir, que las instancias de agroproductos aplicados sean solo de una subclase especifica. Esta restricción implica una regla condicional en la que ciertas propiedades solo pueden tener ciertos valores en determinadas condiciones. Esto es algo que no se puede expresar en RDF o RDFS.