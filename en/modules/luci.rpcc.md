# Object Instance `luci.rpcc`

LuCI RPC Client.

## Functions

|||
|-|-|
|[Client:proxy](#client-proxy-prefix) (prefix)|Create a transparent RPC proxy.|
|[Client:request](#client-request-method-params-notification) (method, params, notification)|Request an RP call and get the response.|

## Functions

### Client:proxy (prefix)
Create a transparent RPC proxy.

**Parameters**

- prefix: Method prefix

**Return value:**

RPC Proxy object

---
### Client:request (method, params, notification)
Request an RP call and get the response.

**Parameters**

- method: Remote method
- params: Parameters
- notification: Notification only?

**Return value:**

response
