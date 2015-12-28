# Object Instance `luci.lucid.rpc.server`

RPC daemom.

## Functions

|                                                                                |                                                     |
| -                                                                              | -                                                   |
| [Method:call](#methodcall-session-argv) (session, argv)                        | Standard call the associated function.              |
| [Method:extended](#methodextended-method-description) (method, description)    | Create an extended wrapped RPC method.              |
| [Method:process](#methodprocess-session-request-argv) (session, request, argv) | Process a given request and create a JSON response. |
| [Method:xcall](#methodxcall-session-argv) (session, argv)                      | Extended call the associated function.              |
| [Module:add](#moduleadd-k-v) (k, v)                                            | Add a handler.                                      |
| [Module:checkrestricted](#modulecheckrestricted-request) (request)             | Enforce access restrictions.                        |
| [Module:process](#moduleprocess-session-request-argv) (session, request, argv) | Process a request.                                  |
| [Module:register](#moduleregister-m-descr) (m, descr)                          | Register a handler, submodule or function.          |
| [Module:restrict](#modulerestrict-restriction) (restriction)                   | Add an access restriction.                          |
| [Server:get_root](#serverget_root) ()                                          | Get the associated root module.                     |
| [Server:process](#serverprocess-client-env) (client, env)                      | Handle a new client connection.                     |
| [Server:reply](#serverreply-jsonrpc-id-res-err) (jsonrpc, id, res, err)        | Create a JSON reply.                                |
| [Server:set_root](#serverset_root-root) (root)                                 | Set a new root module.                              |

## Functions

### Method:call (session, argv)

Standard call the associated function.

**Parameters**

- session: Session storage
- argv: Request parameters

**Return value:**

function call response

---
### Method:extended (method, description)

Create an extended wrapped RPC method.

**Parameters**

- method: Lua function
- description: Method description

**Return value:**

Wrapped RPC method

---
### Method:process (session, request, argv)

Process a given request and create a JSON response.

**Parameters**

- session: Session storage
- request: Requested method
- argv: Request parameters

---
### Method:xcall (session, argv)

Extended call the associated function.

**Parameters**

- session: Session storage
- argv: Request parameters

**Return value:**

function call response

---
### Module:add (k, v)

Add a handler.

**Parameters**

- k: key
- v: handler

---
### Module:checkrestricted (request)

Enforce access restrictions.

**Parameters**

- request: Request object

**Return value:**

nil or HTTP statuscode, table of headers, response source

---
### Module:process (session, request, argv)

Process a request.

**Parameters**

- session: Session storage
- request: Request object
- argv: Request parameters

**Return value:**

JSON response object

---
### Module:register (m, descr)

Register a handler, submodule or function.

**Parameters**

- m: entity
- descr: description

**Return value:**

Module (self)

---
### Module:restrict (restriction)

Add an access restriction.

**Parameters**

- restriction: Restriction specification

---
### Server:get_root ()

Get the associated root module.

**Return value:**

Root module

---
### Server:process (client, env)

Handle a new client connection.

**Parameters**

- client: client socket
- env: superserver environment

---
### Server:reply (jsonrpc, id, res, err)

Create a JSON reply.

**Parameters**

- jsonrpc: JSON-RPC version
- id: Message id
- res: Result
- err: Error

---
### Server:set_root (root)

Set a new root module.

**Parameters**

- root: Root module
