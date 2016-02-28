# Object Instance `luci.lucid.http.server`

HTTP Daemon

## Functions

|                                                                         |                                                                      |
| -                                                                       | -                                                                    |
| [Handler:checkrestricted](#handler-checkrestricted-request) (request)    | Enforce access restrictions.                                         |
| [Handler:failure](#handler-failure-code-msg) (code, msg)                 | Create a failure reply.                                              |
| [Handler:process](#handler-process-request-sourcein) (request, sourcein) | Process a request.                                                   |
| [Handler:restrict](#handler-restrict-restriction) (restriction)          | Add an access restriction.                                           |
| [Server:error](#server-error-client-code-msg) (client, code, msg)        | Send a fatal error message to given client and close the connection. |
| [Server:get_vhosts](#server-get_vhosts) ()                               | Get a list of registered virtual hosts.                              |
| [Server:parse_headers](#server-parse_headers-source) (source)            | Parse the request headers and prepare the environment.               |
| [Server:process](#server-process-client-env) (client, env)               | Handle a new client connection.                                      |
| [Server:set_vhost](#server-set_vhost-name-vhost) (name, vhost)           | Register a virtual host with a given name.                           |
| [VHost:get_handlers](#vhost-get_handlers) ()                             | Get a list of registered handlers.                                   |
| [VHost:process](#vhost-process-request) (request, ...)                   | Process a request and invoke the appropriate handler.                |
| [VHost:set_handler](#vhost-set_handler-handler) (handler)                | Register handler with a given URI prefix.                            |

## Functions

### Handler:checkrestricted (request)

Enforce access restrictions.

**Parameters**

- request: Request object

**Return value:**

nil or HTTP statuscode, table of headers, response source

---
### Handler:failure (code, msg)

Create a failure reply.

**Parameters**

- code: HTTP status code
- msg: Status message

**Return value:**

status code, header table, response source

---
### Handler:process (request, sourcein)

Process a request.

**Parameters**

- request: Request object
- sourcein: Request data source

**Return value:**

HTTP statuscode, table of headers, response source

---
### Handler:restrict (restriction)

Add an access restriction.

**Parameters**

- restriction: Restriction specification

---
### Server:error (client, code, msg)

Send a fatal error message to given client and close the connection.

**Parameters**

- client: Client socket
- code: HTTP status code
- msg: status message

---
### Server:get_vhosts ()

Get a list of registered virtual hosts.

**Return value:**

Table of virtual hosts

---
### Server:parse_headers (source)

Parse the request headers and prepare the environment.

**Parameters**

- source: line-based input source

**Return value:**

Request object

---
### Server:process (client, env)

Handle a new client connection.

**Parameters**

- client: client socket
- env: superserver environment

---
### Server:set_vhost (name, vhost)

Register a virtual host with a given name.

**Parameters**

- name: Hostname
- vhost: Virtual host object

---
### VHost:get_handlers ()

Get a list of registered handlers.

**Return value:**

Table of handlers

---
### VHost:process (request, ...)

Process a request and invoke the appropriate handler.

**Parameters**

- request: Request object
- ...: Additional parameters passed to the handler

**Return value:**

HTTP statuscode, table of headers, response source

---
### VHost:set_handler (handler)

Register handler with a given URI prefix.

**Parameters**

- handler: Handler object
