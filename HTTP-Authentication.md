### Authentication Scheme:
 - Is an auth module that implements the way a client should connect to a dataStore. 
 - Such as Basic Auth Scheme or Bearer Auth Scheme. 
 - www-authentication: Desribes the way the cient should connect to the dataStore. 
 
### Basic HTTP : 
 - HTTP "Hyper Text Transfer protocol" is a michanism to link content on a page to other content on same or another page. 
 - Basic is an Auth Scheme that transmits credentials as username/pass pairs. encoded using Base64. 
 - To aviod passing userid/password in clear test through the network. 
 - It can be decoded. So it suggested to be used on conjunction with HTTPS/TLS
 - However this sheme should not be used to protect sensative info. 
```diff
Example 
QUhNQUQ6QUhNQUQxMjM=
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
Example: If your app is not requesting public readOnly info. Then you need authentication.
- Now i have an account in a website called imgur 
   --> https://imgur.com/user/AhmadAlKhaldi/posts
   --> https://ahmadalkhaldi.imgur.com/all
- I want to access all my posts from postman application.
- I need to register the app that is trying to access the users info. @ https://api.imgur.com/oauth2/addclient
  --> postMan callback URL https://www.getpostman.com/oauth2/callback
  --> Now imgur will redirect auth code to above callBack URL. 
 
- Once you register your app you get 
  --> clientID 463e4f1a446d62e
  --> clientSecret 7913a008116963551f57bb049f115bec15755940
  
- Your app needs to contact Auth-URL and Access token URL.
   - Auth-URL:-  https://api.imgur.com/oauth2/authorize
   - Access Token URL:- https://api.imgur.com/oauth2/token
 
- You will request access token and get it. You will also get refresh token. 
     - At 4e6d1f6196fd3f1aea63898b6e7b1efd82db9e62
     - RT 9dac554d93fca22ecdd4ad3012afcdaf5285f7e0
    
 - Now if postman tries to access useraccount it will ask you for permissions to access. 
 
 - Another way to get access token 
 https://api.imgur.com/oauth2/authorize?client_id=463e4f1a446d62e&response_type=token&state=round-trips
```

### SCRAM : Salted Challenge Reponse Authentication machanism. 
 - Better than basic encoded Or clearText(Digest) password with TLS.
 - Why: The authentication information stored in the authentication database is not sufficient by itself. The information is salted to make it harder to do a pre-stored dictionary attack if the database is stolen.
 - How: 
   - Client possession of username/password encoded or solatedPass. --> Sends to server.
   - Server retrieves the corresponding authentication information: a salt, StoredKey, a ServerKey, and an iteration count 
   - Server sends the salt and the iteration count to the client.
   - Client computes the following values and sends a ClientProof to the server. The Formila that only the cient and server know about 
   
```diff
      SaltedPassword  := Hi(Normalize(password), salt, i)
      ClientKey       := HMAC(SaltedPassword, "Client Key")
      StoredKey       := H(ClientKey)
      AuthMessage     := client-first-message-bare + "," +
                         server-first-message + "," +
                         client-final-message-without-proof
      ClientSignature := HMAC(StoredKey, AuthMessage)
      ClientProof     := ClientKey XOR ClientSignature
      ServerKey       := HMAC(SaltedPassword, "Server Key")
      ServerSignature := HMAC(ServerKey, AuthMessage)
```
 
  -  Server authenticates the client by computing the ClientSignature,exclusive-ORing that with the ClientProof to recover the ClientKey, and verifying the correctness of the ClientKey by applying the hash function and comparing the result to the StoredKey.  If the ClientKey . is correct, this proves that the client has access to the user's
exclusive-ORing that with the ClientProof to recover the ClientKey, password.

 -   Client authenticates the server by computing the ServerSignature and comparing it to the value sent by the server.  If the two are equal, this proves that the server had access to the user's ServerKey.

 - ReadMore https://tools.ietf.org/html/rfc7804#section-3

 

