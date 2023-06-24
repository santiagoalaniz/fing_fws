Aquí están las respuestas a tus preguntas:

1. XML es acrónimo de:
   - Respuesta: **b. eXtensible Markup Language**

2. ¿Cuál de las siguientes afirmaciones es verdadera?
   - Respuesta: **b. Los Namespaces de XML evitan el problema de homonimia.**

3. ¿Qué es una instancia XML?
   - Respuesta: **a. Un documento XML**

4. ¿Es este un documento XML "bien formado"?
   ```xml
   <?xml version="1.0"?>
   <note>
   <to>Tove</to>
   <from>Jani</from>
   <heading>Reminder</heading>
   <body>Don't forget me this weekend!</body>
   </note>
   ```
   - Respuesta: Verdadero

5. ¿Es este un documento XML "bien formado"?
   ```xml
   <?xml version="1.0"?>
   <to>Tove</to>
   <from>Jani</from>
   <heading>Reminder</heading>
   <body>Don't forget me this weekend!</body>
   </note>
   ```
   - Respuesta: Falso (El elemento raíz no está cerrado correctamente)

6. ¿Es este un documento XML Schema?
   ```xml
   <?xml version="1.0"?>
   <xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
   <xs:element name="note">
   <xs:complexType>
   <xs:sequence>
   <xs:element name="to" type="xs:string"/>
   <xs:element name="from" type="xs:string"/>
   <xs:element name="heading" type="xs:string"/>
   <xs:element name="body" type="xs:string"/>
   </xs:sequence>
   </xs:complexType>
   </xs:element>
   </xs:schema>
   ```
   - Respuesta: Verdadero

7. ¿Cuál de las siguientes afirmaciones es verdadera?
   - Respuesta: **a. Un XML Schema describe la estructura de un documento XML.**

8. ¿Para qué se usa un documento XML Schema?
   - Respuesta: **b. Para validar un documento XML**
   - Respuesta: **d. Para definir un tipo de documento XML**