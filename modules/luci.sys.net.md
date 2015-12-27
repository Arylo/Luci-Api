# Class `luci.sys.net`

LuCI system utilities / network related functions.

## Functions

|                                    |                                                                 |
| -                                  | -                                                               |
| [arptable](#arptable) ()           | Returns the current arp-table entries as two-dimensional table. |
| [conntrack](#conntrack) ()         | Returns conntrack information                                   |
| [defaultroute](#defaultroute) ()   | Determine the current IPv4 default route.                       |
| [defaultroute6](#defaultroute6) () | Determine the current IPv6 default route.                       |
| [deviceinfo](#deviceinfo) ()       | Return information about available network interfaces.          |
| [devices](#devices) ()             | Determine the names of available network interfaces.            |
| [pingtest](#pingtest-host) (host)  | Tests whether the given host responds to ping probes.           |
| [routes](#routes) ()               | Returns the current kernel routing table entries.               |
| [routes6](#routes6) ()             | Returns the current ipv6 kernel routing table entries.          |

## Functions

### arptable ()

Returns the current arp-table entries as two-dimensional table.

**Return value:**

Table of table containing the current arp entries. The following fields are defined for arp entry objects: { "IP address", "HW address", "HW type", "Flags", "Mask", "Device" }

---
### conntrack ()

Returns conntrack information

**Return value:**

Table with the currently tracked IP connections

---
### defaultroute ()

Determine the current IPv4 default route. If multiple default routes exist, return the one with the lowest metric.

**Return value:**

Table with the properties of the current default route. The following fields are defined: { "dest", "gateway", "metric", "refcount", "usecount", "irtt", "flags", "device" }

---
### defaultroute6 ()

Determine the current IPv6 default route. If multiple default routes exist, return the one with the lowest metric.

**Return value:**

Table with the properties of the current default route. The following fields are defined: { "source", "dest", "nexthop", "metric", "refcount", "usecount", "flags", "device" }

---
### deviceinfo ()

Return information about available network interfaces.

**Return value:**

Table containing all current interface names and their information

---
### devices ()

Determine the names of available network interfaces.

**Return value:**

Table containing all current interface names

---
### pingtest (host)

Tests whether the given host responds to ping probes.

**Parameters**

- host: String containing a hostname or IPv4 address

**Return value:**

Number containing 0 on success and >= 1 on error

---
### routes ()

Returns the current kernel routing table entries.

**Return value:**

Table of tables with properties of the corresponding routes. The following fields are defined for route entry tables: { "dest", "gateway", "metric", "refcount", "usecount", "irtt", "flags", "device" }

---
### routes6 ()

Returns the current ipv6 kernel routing table entries.

**Return value:**

Table of tables with properties of the corresponding routes. The following fields are defined for route entry tables: { "source", "dest", "nexthop", "metric", "refcount", "usecount", "flags", "device" }
