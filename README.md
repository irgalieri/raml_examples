RAML Example 6: Security
========================

Explanation
-----------

**SecuritySchemes** property is declared at the API's root level.

The next example shows two security schema, OAuth 1.0 and OAuth 2.0. And in the resource **'/users/{userid}/packages'** implement 3 security. anonymous, OAuth 1.0 and OAuth 2.0.

###### global.raml

```yaml
#%RAML 0.8
title: Dummy API
version: v3
baseUri: https://api.intraway.com
securitySchemes:
    - oauth_2_0:
        description: |
          Dummy API supports OAuth 2.0 for authenticating all API requests.
        type: OAuth 2.0
        describedBy:
            headers:
                Authorization:
                    description: |
                       Used to send a valid OAuth 2 access token.
                    type: string
            responses:
                401:
                    description: |
                        Bad or expired token. This can happen if the user
                        revoked or expired an access token. To fix, you should re-
                        authenticate the user.
                403:
                    description: |
                        Bad OAuth request (wrong consumer key, bad nonce, expired
                        timestamp...). Unfortunately, re-authenticating the user won't help here.
        settings:
          authorizationUri: https://www.intraway.com/sso/oauth2/authorize
          accessTokenUri: https://api.intraway.com/sso/oauth2/token
          authorizationGrants: [ code, token ]
          scopes: [ ADMINISTRATOR ]
    - oauth_1_0:
        description: |
            OAuth 1.0 continues to be supported for all API requests, but OAuth 2.0 is now preferred.
        type: OAuth 1.0
        settings:
          requestTokenUri: https://api.intraway.com/sso/oauth/request_token
          authorizationUri: https://www.intraway.com/sso/oauth/authorize
          tokenCredentialsUri: https://api.intraway.com/sso/oauth/access_token
/users/{userid}/packages:
    get:
        securedBy: [null, oauth_1_0, oauth_2_0]
        description: |
            List the authenticated user’s packages.
```

If want learn more about this, go to [RAML - Security](https://github.com/raml-org/raml-spec/blob/master/versions/raml-08/raml-08.md#security)

License
-------

The document is released under the GPL-3.0 license. See the [LICENSE](https://github.com/irgalieri/raml_examples/blob/master/LICENSE) for more information.
