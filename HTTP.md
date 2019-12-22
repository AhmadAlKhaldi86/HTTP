# HTTP
-  HTTP "Hyper Text Transfer protocol" is a michanism to link content on a page to other content on same or another page. 
- Fetch a resource/ Get Data. 
- Client-Server Communication . Request - Response. 
- Proxies set between Client and server Can be 
  -  The user-agent is any tool that acts on the behalf of the user. postMan or a webpage 
- The server, which serves the document as requested by the client.

### HTTP Responsibility:
- Authentication 
- Chaching 
- Proxy and tunneling 

### HTTP Flow:
- The Client Opens a TCP Connection or Connections or reuse an connection. 
- Clinet send a message to the server. 
```diff
Request 
Method --> GET 
URL EndPoint -->  / 
Headers --> Accept-Lang  fr
 Headers have additinal info to the server. https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers
HTTP Version Protocol --> HTTP/1.1


Reponse can be
StatusCode --> HTTP/1.1 200 OK
Date: Sat, 09 Oct 2010 14:28:02 GMT
Server: Apache
Last-Modified: Tue, 01 Dec 2009 20:18:22 GMT
ETag: "51142bc1-7449-479b075b2891b"
Accept-Ranges: bytes
Content-Length: 29769
Content-Type: text/html


```


  
  
  

