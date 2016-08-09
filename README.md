RAML Example 3: Documentation
=======================

Explanation
-----------

This example shows an API definition with two user document. One was included by inline method and the other was included using external link. The text to include must be compatible with markdown.

###### global.raml

```yaml
#%RAML 0.8
title: Dummy API
version: 1
baseUri: https://api.intraway.com
documentation:
  - title: Custom 1
    content: |
      _Lorem ipsum_ dolor sit amet, consectetur adipiscing elit. Mauris non neque dolor. In laoreet mauris non orci auctor, non gravida urna fringilla. Vestibulum ac nibh et risus suscipit aliquam eget ullamcorper magna. Morbi placerat consectetur nunc, a commodo lorem commodo sit amet. Sed bibendum ullamcorper orci nec efficitur. Integer non lacinia neque. Aliquam placerat, turpis a vulputate maximus, erat sem ullamcorper nisl, vel tempor lorem lacus ac orci. Suspendisse potenti. Fusce sit amet massa quam. Sed ac placerat massa, vel finibus lacus. Nam nec dolor ac enim varius cursus.
  - title: Custom 2
    content: !include custom2.md
```

###### custom2.md

```md
_Lorem ipsum_ dolor sit amet, **consectetur** adipiscing elit. Mauris non neque dolor. In laoreet mauris non orci auctor, non gravida urna fringilla. Vestibulum ac nibh et risus suscipit aliquam eget ullamcorper magna. Morbi placerat *consectetur nunc*, a commodo lorem commodo sit amet. Sed bibendum ullamcorper orci nec efficitur. Integer non lacinia neque. Aliquam placerat, turpis a vulputate maximus, erat sem ullamcorper nisl, vel tempor lorem lacus ac orci. Suspendisse potenti. Fusce sit amet massa quam. Sed ac placerat massa, vel finibus lacus. Nam nec dolor ac enim varius cursus.
```

If want learn more about this, go to [RAML - User Documentation](https://github.com/raml-org/raml-spec/blob/master/versions/raml-08/raml-08.md#user-documentation)

License
-------

The document is released under the GPL-3.0 license. See the [LICENSE](https://github.com/irgalieri/raml_examples/blob/master/LICENSE) for more information.
