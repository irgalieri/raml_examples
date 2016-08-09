RAML Example 5: Resource Types and Traits
=========================================

Explanation
-----------

**Resource Type**: is a partial resource definition that, like a resource, can specify a description and methods and their properties. Resources that use a resource type inherit its properties, such as its methods.

**Trait**: is a partial method definition that, like a method, can provide method-level properties such as description, headers, query string parameters, and responses. Methods that use one or more traits inherit those traits' properties.

The next example shows one *resourceType* and two *traits*. All have parameters like *queryParamName* or *tokenName*, you could use this to replace a word or a parameter name.

###### global.raml

```yaml
#%RAML 0.8
title: Dummy API
version: v1
baseUri: https://api.intraway.com
resourceTypes:
  - searchableCollection:
      get:
        queryParameters:
          <<queryParamName>>:
            description: Return <<resourcePathName>> that have their <<queryParamName>> matching the given value
          <<fallbackParamName>>:
            description: If no values match the value given for <<queryParamName>>, use <<fallbackParamName>> instead
traits:
  - secured:
      queryParameters:
        <<tokenName>>:
          description: A valid <<tokenName>> is required
    paged:
      queryParameters:
        numPages:
          description: The number of pages to return, not to exceed <<maxPages>>
/books:
  type: { searchableCollection: { queryParamName: title, fallbackParamName: digest_all_fields } }
  get:
    is: [ secured: { tokenName: access_token}, paged: { maxPages: 10 } ]
```

If want learn more about this, go to [RAML - Resource Types and Traits](https://github.com/raml-org/raml-spec/blob/master/versions/raml-08/raml-08.md#resource-types-and-traits)

License
-------

The document is released under the GPL-3.0 license. See the [LICENSE](https://github.com/irgalieri/raml_examples/blob/master/LICENSE) for more information.
