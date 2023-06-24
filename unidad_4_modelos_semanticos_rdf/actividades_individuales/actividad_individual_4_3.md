# Modelo abstracto rdf.

## ¿Cuáles son los elementos de una tripla RDF en orden correcto?

La respuesta correcta es:

- Sujeto - Propiedad - Objeto

## ¿Qué es lo que un nodo en blanco no tiene?

La respuesta correcta es:

- un identificador único global

## ¿Cómo puede ser un nodo blanco dereferenciado?

La respuesta correcta es:

- por su id de nodo – sólo desde el mismo grafo

## ¿Cómo pueden representarse varios datos ordenados de una misma relación en RDF?

Las respuestas correctas son:

- introduciendo nodos blancos, los cuales enlazan a los valores relacionados
- todos los valores pueden ser listados en un recurso rdf:Seq

La afirmación "dando el mismo tipo de datos a los valores relacionados" no necesariamente representa datos ordenados. La afirmación "relaciones multivaluadas pueden ser determinadas por el orden de las triplas en el dataset" es falsa, ya que RDF no garantiza ningún orden específico de las triplas.