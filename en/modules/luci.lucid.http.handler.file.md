# Object Instance `luci.lucid.http.handler.file`

File system handler

## Functions

|                                                                       |                                             |
| -                                                                     | -                                           |
| [Simple:getfile](#simple-getfile-uri) (uri)                            | Translate path and return file information. |
| [Simple:handle_GET](#simple-handle_get-request) (request)              | Handle a GET request.                       |
| [Simple:handle_HEAD](#simple-handle_head-request) (request)            | Handle a HEAD request.                      |
| [Simple:parse_range](#simple-parse_range-request-size) (request, size) | Parse a range request.                      |

## Functions

### Simple:getfile (uri)

Translate path and return file information.

**Parameters**

- uri: Request URI

**Return value:**

physical file path, file information

---
### Simple:handle_GET (request)

Handle a GET request.

**Parameters**

- request: Request object

**Return value:**

status code, header table, response source

---
### Simple:handle_HEAD (request)

Handle a HEAD request.

**Parameters**

- request: Request object

**Return value:**

status code, header table, response source

---
### Simple:parse_range (request, size)

Parse a range request.

**Parameters**

- request: Request object
- size: File size

**Return value:**

offset, length, range header or boolean status
