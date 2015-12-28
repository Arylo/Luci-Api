# Class `luci.model.ipkg`

LuCI IPKG/OPKG call abstraction library

## Functions

|                                                    |                                                            |
| -                                                  | -                                                          |
| [info](#info-pkg) (pkg)                            | Return information about installed and available packages. |
| [install](#install) (...)                          | Install one or more packages.                              |
| [installed](#installed-pkg) (pkg)                  | Determine whether a given package is installed.            |
| [list_all](#list_all-pat-cb) (pat, cb)             | List all packages known to opkg.                           |
| [list_installed](#list_installed-pat-cb) (pat, cb) | List installed packages.                                   |
| [overlay_root](#overlay_root) ()                   | Determines the overlay root used by opkg.                  |
| [remove](#remove) (...)                            | Remove one or more packages.                               |
| [status](#status-pkg) (pkg)                        | Return the package status of one or more packages.         |
| [update](#update) ()                               | Update package lists.                                      |
| [upgrade](#upgrade) ()                             | Upgrades all installed packages.                           |

## Functions

### info (pkg)

Return information about installed and available packages.

**Parameters**

- pkg: Limit output to a (set of) packages

**Return value:**

Table containing package information

---
### install (...)

Install one or more packages.

**Parameters**

- ...: List of packages to install

**Return values:**

+ Boolean indicating the status of the action
+ IPKG return code

---
### installed (pkg)

Determine whether a given package is installed.

**Parameters**

- pkg: Package

**Return value:**

Boolean

---
### list_all (pat, cb)

List all packages known to opkg.

**Parameters**

- pat: Only find packages matching this pattern, nil lists all packages
- cb: Callback function invoked for each package, receives name, version and description as arguments

**Return value:**

nothing

---
### list_installed (pat, cb)

List installed packages.

**Parameters**

- pat: Only find packages matching this pattern, nil lists all packages
- cb: Callback function invoked for each package, receives name, version and description as arguments

**Return value:**

nothing

---
### overlay_root ()

Determines the overlay root used by opkg.

**Return value:**

String containing the directory path of the overlay root.

---
### remove (...)

Remove one or more packages.

**Parameters**

- ...: List of packages to install

**Return values:**

+ Boolean indicating the status of the action
+ IPKG return code

---
### status (pkg)

Return the package status of one or more packages.

**Parameters**

- pkg: Limit output to a (set of) packages

**Return value:**

Table containing package status information

---
### update ()

Update package lists.

**Return values:**

+ Boolean indicating the status of the action
+ IPKG return code

---
### upgrade ()

Upgrades all installed packages.

**Return values:**

+ Boolean indicating the status of the action
+ IPKG return code
