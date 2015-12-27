# Class `luci.sys.wifi`

LuCI system utilities / wifi related functions.

## Functions

|                                         |                                                   |
| -                                       | -                                                 |
| [channels](#channels-iface) (iface)     | Get available channels from given wireless iface. |
| [getiwconfig](#getiwconfig) ()          | Get iwconfig output for all wireless devices.     |
| [getiwinfo](#getiwinfo-ifname) (ifname) | Get wireless information for given interface.     |
| [iwscan](#iwscan) ()                    | Get iwlist scan output from all wireless devices. |

## Functions

### channels (iface)

Get available channels from given wireless iface.

**Parameters**

- iface: Wireless interface (optional)

**Return value:**

Table of available channels

---
### getiwconfig ()

Get iwconfig output for all wireless devices.

**Return value:**

Table of tables containing the iwconfing output for each wifi device

---
### getiwinfo (ifname)

Get wireless information for given interface.

**Parameters**

- ifname: String containing the interface name

**Return value:**

A wrapped iwinfo object instance

---
### iwscan ()

Get iwlist scan output from all wireless devices.

**Return value:**

Table of tables contaiing all scan results
