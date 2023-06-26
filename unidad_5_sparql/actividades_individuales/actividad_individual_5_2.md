Completar lo que falta en la siguiente consulta SPARQL que recupera el nombre y la fecha de fundación de todas las organizaciones y compañías cuya sede se encuentra en Japón y que tienen fecha de fundación anterior a 1950.

Los prefijos referencian a los siguientes namespaces:

rdfs: http://www.w3.org/2000/01/rdf-schema#
dbo: http://dbpedia.org/ontology/
dbp: http://dbpedia.org/property/
dbr: http://dbpedia.org/resource/

```
select ?nombre ?fechaFundacion 
where 
{
    ?x dbo:headquarter ?y.  
    ?y dbo:country  dbr:Japan.
    **?x** dbp:foundation **?fechaFundacion**.
    ?x rdfs:label ?nombre.
    FILTER ( **?fechaFundacion < "1950-01-01"^^xsd:date** )
    {
        {?x rdf:type dbo:Organization.} 
        **UNION**
        {?x rdf:type dbo:Company.}
     }
}
```