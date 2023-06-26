# Modelos Semanticos Rdf(s)

## **Limitaciones de XML para la Web de Datos**: 
El documento discute las limitaciones de XML (eXtensible Markup Language) en el contexto de la Web de Datos. Estas limitaciones incluyen verbosidad, falta de semántica, ausencia de relaciones directas, esquemas de validación, dificultad para mezclar vocabularios y procesamiento.

## **Grafos de Conocimiento**: 
Los grafos de conocimiento son estructuras de datos que representan información en forma de entidades (nodos) y relaciones (aristas) entre estas entidades. Permiten modelar y almacenar conocimientos de una manera flexible y semánticamente rica.

## **Base de datos SQL o Grafo de Datos?**: 
El documento discute las consideraciones para elegir entre un modelo de datos relacional o un grafo de datos. Depende de los requisitos de la aplicación para el soporte de transacciones, consistencia y operaciones con datos estructurados y tabulares, o la necesidad de capacidad de búsqueda, accesibilidad, interoperabilidad y reutilización de datos altamente relacionados y complejos.

## **Diferencias entre un Grafo de Conocimientos y un Grafo de Datos**: 
Un grafo de conocimientos es un grafo estructurado que representa bases de conocimientos que almacenan información factual en forma de relaciones entre entidades. Un grafo de datos se ajusta a un modelo de datos basado en un grafo, como un grafo dirigido con aristas etiquetadas.

## **RDF: Un Tipo de Grafo de Conocimientos**: 
El documento discute cómo nombrar datos en la web usando URLs o IRIs, e introduce RDF, sus conceptos, sintaxis y semántica. Explica cómo representar tablas relacionales en RDF y discute las serializaciones de RDF.

## **Esquema RDF / Vocabulario RDF**: 

El Marco de Descripción de Recursos (RDF, por sus siglas en inglés) es un estándar del World Wide Web Consortium (W3C) que proporciona un modelo de datos para representar información en la web. RDF se utiliza para describir relaciones entre recursos en términos de triplas, que constan de un sujeto, un predicado y un objeto.

Aquí hay algunos aspectos clave del RDF que se discuten en el documento:

1. **Nombrar datos en la web**: Para identificar recursos globalmente, RDF utiliza URLs o IRIs (Identificadores de Recursos Internacionalizados). Los IRIs generalizan los URI (Identificadores de Recursos Uniformes), admitiendo caracteres internacionales. Al usar IRI con HTTP, se pueden vincular grafos RDF con entidades relacionadas en la Web, creando datos vinculados o enlazados (Linked Data).

2. **Definición del modelo abstracto**: En RDF, una tripla es una tupla <s,p,o> del conjunto (I U B) X I X (I U B U L), donde I representa IRIs, B representa nodos en blanco, y L representa nodos literales. 's' es el sujeto, 'p' es el predicado y 'o' es el objeto. Un conjunto de triplas forma un grafo RDF.

3. **Serializaciones RDF**: Existen varios formatos de sintaxis para escribir grafos RDF, incluyendo RDFa, RDF/XML, Turtle, N-Triples, JSON-LD y N-Quads. Estos formatos permiten representar y compartir grafos RDF de manera efectiva en diferentes contextos y aplicaciones.

4. **Representaciones con RDF**: En RDF, las relaciones se representan generalmente como relaciones binarias (entre dos elementos) usando triplas. Para representar relaciones n-arias (relaciones que involucran a n elementos) en RDF, es necesario introducir nodos intermedios y reestructurar la relación en una serie de relaciones binarias.

5. **Reificación en RDF**: La reificación en RDF es un proceso que permite representar información adicional sobre una tripla o una relación en el grafo RDF. A menudo, es necesario representar metadatos sobre una declaración, como la fuente de la información, la confiabilidad o el tiempo en el que se hizo la declaración.

6. **RDF Schema / RDF Vocabulary**: RDF Schema (RDFs) es un lenguaje de vocabulario que permite definir características semánticas de los datos RDF. Ayuda a establecer restricciones y relaciones entre clases y propiedades en el grafo RDF, facilitando la comprensión e interpretación de los datos por parte de los sistemas informáticos.