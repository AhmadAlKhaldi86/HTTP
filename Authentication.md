### Authentication Scheme:
 - Is an auth module that implements the way a client should connect to a dataStore. 
 - Such as Basic Auth Scheme or Bearer Auth Scheme. 
 
### Basic HTTP : 
 - HTTP "Hyper Text Transfer protocol" is a michanism to link content on a page to other content on same or another page. 
 - Basic is an Auth Scheme that transmits credentials as username/pass pairs. encoded using Base64. 
 - To aviod passing userid/password in clear test through the network. 
 - It can be decoded. So it suggested to be used on conjunction with HTTPS/TLS
 - However this sheme should not be used to protect sensative info. 
```diff
Example 
```

### Bearer HTTP
- Bearer Tokens to access an OAUTH protected resource. 
- Oauth is just an industry security standard that enables apps to get LIMITED access to an http resource. 
![](https://github.com/AhmadAlKhaldi86/Security/blob/master/assets/Oauth%20FrameWork.png)
- Tokens represent specific scopes and durations of access.
- Refresh tokens are credentials used to obtain access tokens.  Refresh tokens are issued to the client by the authorization
server and are used to obtain a new access token when the current access token becomes invalid or expires.
![](https://github.com/AhmadAlKhaldi86/Security/blob/master/assets/RefreshTokens.png)
- transport-layer security should always be used. 
- Continue reading here https://oauth.net/2/
- https://aaronparecki.com/oauth-2-simplified/#roles

```diff
Example:
- Now i have an account in a website called imgur 
   --> https://imgur.com/user/AhmadAlKhaldi/posts
   --> https://ahmadalkhaldi.imgur.com/all
- I want to access all my posts from postman application.

```


### Resource 
 - https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization

