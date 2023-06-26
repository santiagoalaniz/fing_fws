Indica cuál de las siguientes consultas SPARQL recupera el nombre, y en caso de existir, la profesión de todas las personas cuyo lugar de nacimiento es Uruguay.
Los prefijos referencian a los siguientes namespaces:

rdf: http://www.w3.org/1999/02/22-rdf-syntax-ns#
dbo: http://dbpedia.org/ontology/
foaf: http://xmlns.com/foaf/0.1/
schema: http://schema.org/
dbp: http://dbpedia.org/property/

Seleccione una:

```
select ?nombre ?profesion  
where 
{
?x rdf:type foaf:Person.
?x dbo:birthPlace  dbr:Uruguay.
?x foaf:name ?nombre.
?x dbp:profession ?profesion.
FILTER EXISTS {?x dbp:profession ?profesion.} 
}


select ?nombre ?profesion  
where 
{
?x schema:sampleType foaf:Person.
?x dbo:birthPlace  dbr:Uruguay.
?x foaf:name ?nombre.
OPTIONAL {?x dbp:profession ?profesion.}
}


select ?nombre ?profesion  
where 
{
?x rdf:type foaf:Person.
?x dbo:birthPlace  dbr:Uruguay.
?x foaf:name ?nombre.
OPTIONAL {?x dbp:profession ?profesion.}
}
```

La tercera opcion es la correcta, Esta consulta SPARQL recupera el nombre, y en caso de existir, la profesión de todas las personas cuyo lugar de nacimiento es Uruguay. La cláusula OPTIONAL se utiliza para obtener la profesión en caso de que exista, pero aún se incluye la persona en el resultado incluso si no tiene un valor para la propiedad de profesión.