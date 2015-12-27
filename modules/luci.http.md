# Class `luci.http`

LuCI Web Framework high-level HTTP functions.

## Functions

|                                                       |                                                                                       |
| -                                                     | -                                                                                     |
| [build_querystring](#build_querystring-table) (table) | Create a querystring out of a table of key - value pairs.                             |
| [close](#close) ()                                    | Close the HTTP-Connection.                                                            |
| [content](#content) ()                                | Return the request content if the request was of unknown type.                        |
| [formvalue](#formvalue-name-noparse) (name, noparse)  | Get a certain HTTP input value or a table of all input values.                        |
| [formvaluetable](#formvaluetable-prefix) (prefix)     | Get a table of all HTTP input values with a certain prefix.                           |
| [getcookie](#getcookie-name) (name)                   | Get the value of a certain HTTP-Cookie.                                               |
| [getenv](#getenv-name) (name)                         | Get the value of a certain HTTP environment variable or the environment table itself. |
| [header](#header-key-value) (key, value)              | Send a HTTP-Header.                                                                   |
| [prepare_content](#prepare_content-mime) (mime)       | Set the mime type of following content data.                                          |
| [redirect](#redirect-url) (url)                       | Redirects the client to a new URL and closes the connection.                          |
| [setfilehandler](#setfilehandler-callback) (callback) | Set a handler function for incoming user file uploads.                                |
| [source](#source) ()                                  | Get the RAW HTTP input source                                                         |
| [splice](#splice-fp-size) (fp, size)                  | Splice data from a filedescriptor to the client.                                      |
| [status](#status-code-message) (code, message)        | Set the HTTP status code and status message.                                          |
| [write](#write-content-src_err) (content, src_err)    | Send a chunk of content data to the client.                                           |
| [write_json](#write_json-data) (data)                 | Send the given data as JSON encoded string.                                           |

## Functions

### build_querystring (table)
Create a querystring out of a table of key - value pairs.

**Parameters**

- table: Query string source table

**Return value:**

Encoded HTTP query string

---
### close ()
Close the HTTP-Connection.

---
### content ()
Return the request content if the request was of unknown type.

**Return values:**

+ HTTP request body
+ HTTP request body length

---
### formvalue (name, noparse)
Get a certain HTTP input value or a table of all input values.

**Parameters**

- name: Name of the GET or POST variable to fetch
- noparse: Don't parse POST data before getting the value

**Return value:**

HTTP input value or table of all input value

---
### formvaluetable (prefix)
Get a table of all HTTP input values with a certain prefix.

**Parameters**

- prefix: Prefix

**Return value:**

Table of all HTTP input values with given prefix

---
### getcookie (name)
Get the value of a certain HTTP-Cookie.

**Parameters**

- name: Cookie Name

**Return value:**

String containing cookie data

---
### getenv (name)
Get the value of a certain HTTP environment variable or the environment table itself.

**Parameters**

- name: Environment variable

**Return value:**

HTTP environment value or environment table

---
### header (key, value)
Send a HTTP-Header.

**Parameters**

- key: Header key
- value: Header value

---
### prepare_content (mime)
Set the mime type of following content data.

**Parameters**

- mime: Mimetype of following content

---
### redirect (url)
Redirects the client to a new URL and closes the connection.

**Parameters**

- url: Target URL

---
### setfilehandler (callback)
Set a handler function for incoming user file uploads.

**Parameters**

- callback: Handler function

---
### source ()
Get the RAW HTTP input source

**Return value:**

HTTP LTN12 source

---
### splice (fp, size)
Splice data from a filedescriptor to the client.

**Parameters**

- fp: File descriptor
- size: Bytes to splice (optional)

---
### status (code, message)
Set the HTTP status code and status message.

**Parameters**

- code: Status code
- message: Status message

---
### write (content, src_err)
Send a chunk of content data to the client. This function is as a valid LTN12 sink. If the content chunk is nil this function will automatically invoke close.

**Parameters**

- content: Content chunk
- src_err: Error object from source (optional)

**See also:**

- [close](#close)

---
### write_json (data)
Send the given data as JSON encoded string.

**Parameters**

- data: Data to send
