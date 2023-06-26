# SPARQL: Lenguaje de consulta para RDF.

- **¿Qué es SPARQL?**: SPARQL se utiliza para formular consultas para buscar patrones y realizar operaciones complejas en grafos RDF. Permite consultas flexibles y poderosas sobre los datos RDF, acceder a diferentes fuentes de datos y obtener resultados precisos y relevantes.

- **¿Por qué se necesita un lenguaje de consulta de grafos?**: El ejemplo de buscar bailarines de ballet en Google, que devolvería una lista de páginas relacionadas con el tema. Sin embargo, si queremos una lista completa de bailarines de ballet en todo el mundo, esta información se encuentra en bases de datos RDF como DBPEDIA. SPARQL puede recuperar un conjunto de recursos que cumplen ciertas condiciones.

- **¿Para qué sirve SPARQL?**: SPARQL nos permite obtener un subgrafo con los datos que buscamos al aplicar condiciones en el grafo que contiene la información en formato RDF. También nos permite combinar grafos de diferentes bases RDF para obtener información más completa y precisa, integrando múltiples fuentes de información.

- **Conceptos básicos, constructores y patrones de consulta**: El documento explica el patrón de consulta básico en SPARQL, que es una conjunción de triples donde los sujetos, predicados y objetos pueden ser variables. También discute diferentes tipos de consultas SPARQL, incluyendo SELECT, CONSTRUCT, ASK y DESCRIBE.

- **Patrones complejos, filtros, modificadores y otros tipos de consulta**: SPARQL permite patrones de consulta complejos, que introducen variaciones en las condiciones de búsqueda. Los filtros se utilizan para restringir los resultados de una consulta, y los modificadores permiten organizar los resultados de la consulta de diferentes maneras.

- **Extensiones**: La extensión SPARQL 1.1, introducida en 2013, añade nuevas funcionalidades al lenguaje SPARQL, como expresiones en el SELECT, asignación de valores (bind values), agregaciones, subconsultas, property paths y negación.

- **Integración de grafos locales y remotos**: En la web semántica, los grafos nombrados permiten organizar conjuntos de grafos RDF dentro de un RDF Dataset. Un RDF Dataset consta de un grafo por defecto y varios grafos nombrados, donde cada grafo nombrado está identificado por una IRI.
