Para la primera pregunta, las serializaciones de RDF son:

- JSON/LD
- RDF/XML
- N-Triples

RDF es un marco estándar para intercambiar datos entre diferentes aplicaciones de datos en la web. JSON-LD, RDF/XML, y N-Triples son todas serializaciones de RDF que se utilizan para representar información en diferentes formatos. UNICODE, XML Schema y XSLT no son serializaciones de RDF, aunque son formatos de codificación y descripción de datos que pueden ser utilizados en diferentes contextos.

Para la segunda pregunta, las notaciones correctas para la información "Tom knows Bob" considerando el prefijo dado son:

- ex:Tom ex:knows ex:Bob .
- <http://example.org/Tom> <http://example.org/knows> <http://example.org/Bob> .

Estas son declaraciones en RDF que dicen que el recurso ex:Tom conoce al recurso ex:Bob. La declaración se compone de un sujeto (ex:Tom), un predicado (ex:knows) y un objeto (ex:Bob).

La notación "ex:Tom" ex:knows "ex:Bob" es incorrecta porque en RDF no se utilizan comillas para rodear las URIs.

La notación [ a ex:Tom; ex:knows ex:Bob ] también es incorrecta. Esta notación generalmente se utiliza para las declaraciones de Blank Nodes (nodos anónimos) en RDF, y en este caso específico, no tiene sentido ya que estamos declarando que algún recurso anónimo es del tipo ex:Tom y conoce a ex:Bob, lo que es diferente de decir que ex:Tom conoce a ex:Bob.