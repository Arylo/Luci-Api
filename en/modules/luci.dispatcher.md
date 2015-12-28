# Class `luci.dispatcher`

## Functions

|                                                                                 |                                                                                            |
| -                                                                               | -                                                                                          |
| [alias](#alias) (...)                                                           | Create a redirect to another dispatching node.                                             |
| [arcombine](#arcombine-trg1, trg2) (trg1, trg2)                                 | Create a combined dispatching target for non argv and argv requests.                       |
| [assign](#assign-path, clone, title, order) (path, clone, title, order)         | Clone a node of the dispatching tree to another position.                                  |
| [build_url](#build_url) (...)                                                   | Build the URL relative to the server webroot from given virtual path.                      |
| [call](#call-name) (name, ...)                                                  | Create a function-call dispatching target.                                                 |
| [cbi](#cbi-model) (model)                                                       | Create a CBI model dispatching target.                                                     |
| [createindex](#createindex) ()                                                  | Generate the dispatching index using the best possible strategy.                           |
| [createindex_fastindex](#createindex_fastindex-path, suffixes) (path, suffixes) | Generate the dispatching index using the fastindex C-indexer.                              |
| [createindex_plain](#createindex_plain-path, suffixes) (path, suffixes)         | Generate the dispatching index using the native file-cache based strategy.                 |
| [createtree](#createtree) ()                                                    | Create the dispatching tree from the index.                                                |
| [dispatch](#dispatch-request) (request)                                         | Dispatches a LuCI virtual path.                                                            |
| [entry](#entry-path, target, title, order) (path, target, title, order)         | Create a new dispatching node and define common parameters.                                |
| [error404](#error404-message) (message)                                         | Send a 404 error code and render the "error404" template if available.                     |
| [error500](#error500-message) (message)                                         | Send a 500 error code and render the "error500" template if available.                     |
| [form](#form-model) (model)                                                     | Create a CBI form model dispatching target.                                                |
| [get](#get) (...)                                                               | Fetch or create a dispatching node without setting the target module or enabling the node. |
| [httpdispatch](#httpdispatch-request) (request)                                 | Dispatch an HTTP request.                                                                  |
| [modifier](#modifier-func, order) (func, order)                                 | Register a tree modifier.                                                                  |
| [node](#node) (...)                                                             | Fetch or create a new dispatching node.                                                    |
| [rewrite](#rewrite-n) (n, ...)                                                  | Rewrite the first x path values of the request.                                            |
| [template](#template-name) (name)                                               | Create a template render dispatching target.                                               |

## Functions

### alias (...)

Create a redirect to another dispatching node.

**Parameters**

- ...: Virtual path destination

---
### arcombine (trg1, trg2)

Create a combined dispatching target for non argv and argv requests.

**Parameters**

- trg1: Overview Target
- trg2: Detail Target

---
### assign (path, clone, title, order)

Clone a node of the dispatching tree to another position.

**Parameters**

- path: Virtual path destination
- clone: Virtual path source
- title: Destination node title (optional)
- order: Destination node order value (optional)

**Return value:**

Dispatching tree node

---
### build_url (...)

Build the URL relative to the server webroot from given virtual path.

**Parameters**

- ...: Virtual path

**Return value:**

Relative URL

---
### call (name, ...)

Create a function-call dispatching target.

**Parameters**

- name: Target function of local controller
- ...: Additional parameters passed to the function

---
### cbi (model)

Create a CBI model dispatching target.

**Parameters**

- model: CBI model to be rendered

---
### createindex ()

Generate the dispatching index using the best possible strategy.

---
### createindex_fastindex (path, suffixes)

Generate the dispatching index using the fastindex C-indexer.

**Parameters**

- path: Controller base directory
- suffixes: Controller file suffixes

---
### createindex_plain (path, suffixes)

Generate the dispatching index using the native file-cache based strategy.

**Parameters**

- path: Controller base directory
- suffixes: Controller file suffixes

---
### createtree ()

Create the dispatching tree from the index. Build the index before if it does not exist yet.

---
### dispatch (request)

Dispatches a LuCI virtual path.

**Parameters**

- request: Virtual path

---
### entry (path, target, title, order)

Create a new dispatching node and define common parameters.

**Parameters**

- path: Virtual path
- target: Target function to call when dispatched.
- title: Destination node title
- order: Destination node order value (optional)

**Return value:**

Dispatching tree node

---
### error404 (message)

Send a 404 error code and render the "error404" template if available.

**Parameters**

- message: Custom error message (optional)

**Return value:**

false

---
### error500 (message)

Send a 500 error code and render the "error500" template if available.

**Parameters**

- message: Custom error message (optional)#

**Return value:**

false

---
### form (model)

Create a CBI form model dispatching target.

**Parameters**

- model: CBI form model tpo be rendered

---
### get (...)

Fetch or create a dispatching node without setting the target module or enabling the node.

**Parameters**

- ...: Virtual path

**Return value:**

Dispatching tree node

---
### httpdispatch (request)

Dispatch an HTTP request.

**Parameters**

- request: LuCI HTTP Request object

---
### modifier (func, order)

Register a tree modifier.

**Parameters**

- func: Modifier function
- order: Modifier order value (optional)

---
### node (...)

Fetch or create a new dispatching node.

**Parameters**

- ...: Virtual path

**Return value:**

Dispatching tree node

---
### rewrite (n, ...)

Rewrite the first x path values of the request.

**Parameters**

- n: Number of path values to replace
- ...: Virtual path to replace removed path values with

---
### template (name)

Create a template render dispatching target.

**Parameters**

- name: Template to be rendered
