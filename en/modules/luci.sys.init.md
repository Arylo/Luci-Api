# Class `luci.sys.init`

LuCI system utilities / init related functions.

## Functions

|                                 |                                               |
| -                               | -                                             |
| [disable](#disable-name) (name) | Disable the given init script                 |
| [enable](#enable-name) (name)   | Enable the given init script                  |
| [enabled](#enabled-name) (name) | Test whether the given init script is enabled |
| [index](#index-name) (name)     | Get the index of he given init script         |
| [names](#names) ()              | Get the names of all installed init scripts   |

## Functions

### disable (name)

Disable the given init script

**Parameters**

- name: Name of the init script

**Return value:**

Boolean indicating success

---
### enable (name)

Enable the given init script

**Parameters**

- name: Name of the init script

**Return value:**

Boolean indicating success

---
### enabled (name)

Test whether the given init script is enabled

**Parameters**

- name: Name of the init script

**Return value:**

Boolean indicating whether init is enabled

---
### index (name)

Get the index of he given init script

**Parameters**

- name: Name of the init script

**Return value:**

Numeric index value

---
### names ()

Get the names of all installed init scripts

**Return value:**

Table containing the names of all inistalled init scripts
