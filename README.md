RAML Example 1: Including Files
===============================

Explanation
-----------

As usual, we must start our RAML file with Markup language definition in this case we use RAML 0.8 so:

```yaml
#%RAML0.8
```

In this example we have two files **global.raml** and **secondary.md**. The first file include the last one file.

###### global.raml

```yaml
#%RAML 0.8
title: My API
documentation:
  - title: My API
    content: !include secondary.md
```

###### secondary.md

```md
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla felis augue, commodo nec ornare quis, blandit eget tortor. Nullam feugiat efficitur condimentum. Aenean mattis vitae nulla non ullamcorper. Mauris ut metus velit. Vestibulum malesuada nisi eget diam tincidunt, nec dignissim nulla pulvinar. Donec elementum non lacus in pretium. In faucibus dictum sem, at rhoncus augue. Proin porttitor nisl eget ultrices convallis. Duis vestibulum cursus ornare. Mauris id tortor a turpis hendrerit placerat cursus in nunc.
```

To learn more about [RAML Include](https://github.com/raml-org/raml-spec/blob/master/versions/raml-08/raml-08.md#includes)

License
-------

The driver is released under the GPL-3.0 license. See the [LICENSE](https://github.com/irgalieri/raml_examples/blob/master/LICENSE) for more information.
