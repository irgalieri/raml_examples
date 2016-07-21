RAML Example 2: Named Parameters
================================

Explanation
-----------

This RAML Specification describes collections of named parameters for the following properties: URI parameters, query string parameters, form parameters, request bodies (depending on the media type), and request and response headers. And in this example you can see form parameters. This example content one parameter with multiple type.

###### global.raml

```yaml
#%RAML 0.8
title: Dummy API
version: 1
baseUri: https://api.intraway.com
/:
  post:
    description: The POST operation adds an new entity.
    body:
      application/x-www-form-urlencoded:
        formParameters:
          EntityId:
            displayName: Entity Identifier
            description: Entity numeric identifier.
            type: number
          Name:
            description: Entity name.
            type: string
          Desc:
            - type: string
              description: Text content. The text content must be the last field in the form.
            - type: file
              description: File to upload. The file must be the last field in the form.

```

To learn more about [RAML - Named Parameters](https://github.com/raml-org/raml-spec/blob/master/versions/raml-08/raml-08.md#named-parameters).

License
-------

The document is released under the GPL-3.0 license. See the [LICENSE](https://github.com/irgalieri/raml_examples/blob/master/LICENSE) for more information.
