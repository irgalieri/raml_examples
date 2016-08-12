RAML Example 3: Schemas
=======================

Explanation
-----------

In this example we can see the entity resource, this resource return two kind of data type, JSON and XML. Each response has its own schema. In this case response-xml and response-json.

###### global.raml

```yaml
#%RAML 0.8
title: Dummy API
version: 1
baseUri: https://api.intraway.com
schemas:
  - response-json:      !include ./schemas/entity.xsd
  - response-xml:       !include ./schemas/entity.json
/entity:
  get:
    responses:
      200:
        body:
          application/xml:
            schema: response-xml
          application/json:
            schema: response-json

```

###### entity.json

```json
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "id": "http://jsonschema.net",
  "type": "object",
  "properties": {
    "status": {
      "id": "http://jsonschema.net/status",
      "type": "integer"
    },
    "message": {
      "id": "http://jsonschema.net/message",
      "type": "string"
    },
    "detail": {
      "id": "http://jsonschema.net/detail",
      "type": "string"
    }
  },
  "required": [
    "status",
    "message",
    "detail"
  ]
}
```

###### entity.xsd

```xml
<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="response">
    <xs:complexType>
      <xs:simpleContent>
        <xs:extension base="xs:string">
          <xs:attribute type="xs:short" name="status"/>
          <xs:attribute type="xs:string" name="message"/>
          <xs:attribute type="xs:string" name="detail"/>
        </xs:extension>
      </xs:simpleContent>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

If want learn more about this, go to [RAML - Schemas](https://github.com/raml-org/raml-spec/blob/master/versions/raml-08/raml-08.md#schemas)

License
-------

The document is released under the GPL-3.0 license. See the [LICENSE](https://github.com/irgalieri/raml_examples/blob/master/LICENSE) for more information.
