# Class `luci.lucid.rpc.system`

Internal system functions.

## Functions

|||
|-|-|
|[authenticate](#authenticate-session-type-entity-key) (session, type, entity, key)|Create or use a new authentication token.|
|[echo](#echo-object) (object)|Simple echo test function.|
|[multicall](#multicall-session) (session)|Accumulate different requests and execute them.|
|[void](#void) ()|Simple void test function.|

## Functions

### authenticate (session, type, entity, key)

Create or use a new authentication token.

**Parameters**

- session: Session object
- type: Authentication type
- entity: Authentication enttity (username)
- key: Authentication key (password)

**Return value:**

boolean status

---
### echo (object)

Simple echo test function.

**Parameters**

- object: to be echoed object

**Return value:**

echo object

---
### multicall (session)

Accumulate different requests and execute them.

**Parameters**

- session: Session object

**Return value:**

overall response object

---
### void ()

Simple void test function.
