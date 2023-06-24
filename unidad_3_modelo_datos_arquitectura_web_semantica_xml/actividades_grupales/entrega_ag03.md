# AG3 - XML SCHEMA

## Integrantes Grupo 06:

* Santiago Alaniz
* Bruno De Simone
* Javier Gómez

## Descripcion del Problema.

La actividad consiste en establecer un sistema de registro y seguimiento de la producción y venta de los productos agrícolas de los productores de la cooperativa COOPGRAN, así como el registro de los insumos que adquieren de las empresas proveedoras. Para esto, los productores deben enviar mensualmente a la administración de la cooperativa los productos vendidos, la cantidad vendida de cada uno y el número de documento del cliente que lo compró, así como los insumos comprados, la cantidad adquirida de cada uno y el RUT de la empresa proveedora. Toda esta información se almacena en un documento XML que cumple con ciertos estándares. La cooperativa realiza una conciliación para detectar errores en los datos recibidos y garantizar la integridad de la información. 

Se pide:
 * Especificar el formato del documento XML a utilizar 
 * Crear tres documentos XML que sean instancias válidas del esquema creado.

## Solucion.

### Parte 1: Especificar el formato del documento XML a utilizar.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="productor">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="identificacion" type="xs:string"/>
        <xs:element name="nombre" type="xs:string"/>
        <xs:element name="fecha" type="xs:date"/>
        <xs:element name="productos_vendidos">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="producto" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="identificador" type="xs:string"/>
                    <xs:element name="cantidad_kg" type="xs:decimal"/>
                    <xs:element name="nro_documento_cliente" type="xs:string"/>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
        <xs:element name="insumos_comprados">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="insumo" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="identificador" type="xs:string"/>
                    <xs:element name="cantidad_kg" type="xs:decimal"/>
                    <xs:element name="RUT_empresa_proveedora" type="xs:string"/>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:sequence>
      <xs:attribute name="id" type="xs:string" use="required"/>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

Este Schema XML es adecuado para representar la información que se desea almacenar. El esquema define el elemento raíz como "productor" y establece las subestructuras necesarias para representar los productos vendidos y los insumos comprados por cada productor, incluyendo la identificación del productor, el nombre, la fecha y los identificadores de producto e insumo, la cantidad en kg y los números de documento y RUT correspondientes.

### Parte 2: Crear tres documentos XML que sean instancias válidas del esquema creado.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<productor id="P01">
    <identificacion>123456789</identificacion>
    <nombre>Juan Perez</nombre>
    <fecha>2022-03-31</fecha>
    <productos_vendidos>
        <producto>
            <identificador>PROD001</identificador>
            <cantidad_kg>10.5</cantidad_kg>
            <nro_documento_cliente>12345</nro_documento_cliente>
        </producto>
        <producto>
            <identificador>PROD002</identificador>
            <cantidad_kg>7.2</cantidad_kg>
            <nro_documento_cliente>67890</nro_documento_cliente>
        </producto>
    </productos_vendidos>
    <insumos_comprados>
        <insumo>
            <identificador>INS001</identificador>
            <cantidad_kg>50.0</cantidad_kg>
            <RUT_empresa_proveedora>123456789</RUT_empresa_proveedora>
        </insumo>
    </insumos_comprados>
</productor>
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<productor id="P02">
    <identificacion>987654321</identificacion>
    <nombre>Maria Rodriguez</nombre>
    <fecha>2022-02-28</fecha>
    <productos_vendidos>
        <producto>
            <identificador>PROD003</identificador>
            <cantidad_kg>12.0</cantidad_kg>
            <nro_documento_cliente>45678</nro_documento_cliente>
        </producto>
        <producto>
            <identificador>PROD004</identificador>
            <cantidad_kg>5.5</cantidad_kg>
            <nro_documento_cliente>90123</nro_documento_cliente>
        </producto>
        <producto>
            <identificador>PROD005</identificador>
            <cantidad_kg>8.3</cantidad_kg>
            <nro_documento_cliente>45678</nro_documento_cliente>
        </producto>
    </productos_vendidos>
    <insumos_comprados>
        <insumo>
            <identificador>INS002</identificador>
            <cantidad_kg>20.0</cantidad_kg>
            <RUT_empresa_proveedora>234567890</RUT_empresa_proveedora>
        </insumo>
        <insumo>
            <identificador>INS003</identificador>
            <cantidad_kg>10.0</cantidad_kg>
            <RUT_empresa_proveedora>345678901</RUT_empresa_proveedora>
        </insumo>
    </insumos_comprados>
</productor>
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<productor id="P03">
    <identificacion>111111111</identificacion>
    <nombre>Pablo Sanchez</nombre>
    <fecha>2022-01-31</fecha>
    <productos_vendidos>
        <producto>
            <identificador>PROD006</identificador>
            <cantidad_kg>15.5</cantidad_kg>
            <nro_documento_cliente>34567</nro_documento_cliente>
        </producto>
    </productos_vendidos>
    <insumos_comprados>
        <insumo>
            <identificador>INS004</identificador>
            <cantidad_kg>30.0</cantidad_kg>
            <RUT_empresa_proveedora>456789012</RUT_empresa_proveedora>
        </insumo>
        <insumo>
            <identificador>INS005</identificador>
            <cantidad_kg>12.0</cantidad_kg>
            <RUT_empresa_proveedora>567890123</RUT_empresa_proveedora>
        </insumo>
    </insumos_comprados>
</productor>
```

