# Object Instance `luci.ip.cidr`

LuCI IP Library / CIDR instances

## Functions

|                                                        |                                                                                |
| -                                                      | -                                                                              |
| [cidr:add](#cidr-add-amount-inplace) (amount, inplace) | Add specified amount of hosts to this instance.                                |
| [cidr:broadcast](#cidr-broadcast) ()                   | Return CIDR containing the broadcast address of this instance.                 |
| [cidr:contains](#cidr-contains-addr) (addr)            | Test whether this instance fully contains the given CIDR instance.             |
| [cidr:equal](#cidr-equal-addr) (addr)                  | Test whether the value of the instance is equal to the given address.          |
| [cidr:higher](#cidr-higher-addr) (addr)                | Test whether the value of the instance is higher then the given address.       |
| [cidr:host](#cidr-host) ()                             | Return a corresponding CIDR representing the host address of this instance.    |
| [cidr:is4](#cidr-is4) ()                               | Test whether the instance is a IPv4 address.                                   |
| [cidr:is4linklocal](#cidr-is4linklocal) ()             | Test whether this instance is an IPv4 link-local address (Zeroconf)            |
| [cidr:is4rfc1918](#cidr-is4rfc1918) ()                 | Test whether this instance is an IPv4 RFC1918 private address                  |
| [cidr:is6](#cidr-is6) ()                               | Test whether the instance is a IPv6 address.                                   |
| [cidr:is6linklocal](#cidr-is6linklocal) ()             | Test whether this instance is an IPv6 link-local address                       |
| [cidr:lower](#cidr-lower-addr address.                 |
| [cidr:mask](#cidr-mask-bits) (bits)                    | Return a corresponding CIDR representing the netmask of this instance.         |
| [cidr:maxhost](#cidr-maxhost) ()                       | Return CIDR containing the highest available host address within the subnet.   |
| [cidr:minhost](#cidr-minhost) ()                       | Return CIDR containing the lowest available host address within this subnet.   |
| [cidr:network](#cidr-network-bits) (bits)              | Return a corresponding CIDR representing the network address of this instance. |
| [cidr:prefix](#cidr-prefix-mask) (mask)                | Return the prefix length of this CIDR instance.                                |
| [cidr:string](#cidr-string) ()                         | Return a corresponding string representation of the instance.                  |
| [cidr:sub](#cidr-sub-amount-inplace) (amount, inplace) | Substract specified amount of hosts from this instance.                        |

## Functions

### cidr:add (amount, inplace)

Add specified amount of hosts to this instance.

**Parameters**

- amount: Number of hosts to add to this instance
- inplace: Boolen indicating whether to alter values inplace (optional)

**Return value:**

CIDR representing the new address or nil on overflow error

**See also:**

- [cidr:sub](#cidr-sub-amount-inplace)

---
### cidr:broadcast ()

Return CIDR containing the broadcast address of this instance.

**Return value:**

CIDR instance containing the netmask, always nil for IPv6

**See also:**

- [cidr:network](#cidr-network-bits)
- [cidr:host](#cidr-host)
- [cidr:mask](#cidr-mask-bits)

---
### cidr:contains (addr)

Test whether this instance fully contains the given CIDR instance.

**Parameters**

- addr: CIDR instance to test against

**Return value:**

Boolean indicating whether this instance contains the given CIDR

---
### cidr:equal (addr)

Test whether the value of the instance is equal to the given address. This function will throw an exception if the given address is a different family than this instance.

**Parameters**

- addr: A luci.ip.cidr instance to compare against

**Return value:**

Boolean indicating whether this instance is equal

**See also:**

- [cidr:lower](#cidr-lower-addr)
- [cidr:higher](#cidr-higher-addr)

---
### cidr:higher (addr)

Test whether the value of the instance is higher then the given address. This function will throw an exception if the given address has a different family than this instance.

**Parameters**

- addr: A luci.ip.cidr instance to compare against

**Return value:**

Boolean indicating whether this instance is higher

**See also:**

- [cidr:lower](#cidr-lower-addr)
- [cidr:equal](#cidr-equal-addr)

---
### cidr:host ()

Return a corresponding CIDR representing the host address of this instance. This is intended to extract the host address from larger subnet.

**Return value:**

CIDR instance containing the network address

**See also:**

- [cidr:network](#cidr-network-bits)
- [cidr:broadcast](#cidr-broadcast)
- [cidr:mask](#cidr-mask-bits)

---
### cidr:is4 ()

Test whether the instance is a IPv4 address.

**Return value:**

Boolean indicating a IPv4 address type

**See also:**

- [cidr:is6](#cidr-is6)

---
### cidr:is4linklocal ()

Test whether this instance is an IPv4 link-local address (Zeroconf)

**Return value:**

Boolean indicating whether this instance is IPv4 link-local

---
### cidr:is4rfc1918 ()

Test whether this instance is an IPv4 RFC1918 private address

**Return value:**

Boolean indicating whether this instance is an RFC1918 address

---
### cidr:is6 ()

Test whether the instance is a IPv6 address.

**Return value:**

Boolean indicating a IPv6 address type

**See also:**

- [cidr:is4](#cidr-is4)

---
### cidr:is6linklocal ()

Test whether this instance is an IPv6 link-local address

**Return value:**

Boolean indicating whether this instance is IPv6 link-local

---
### cidr:lower (addr)

Test whether the value of the instance is lower then the given address. This function will throw an exception if the given address has a different family than this instance.

**Parameters**

- addr: A luci.ip.cidr instance to compare against

**Return value:**

Boolean indicating whether this instance is lower

**See also:**

- [cidr:higher](#cidr-higher-addr)
- [cidr:equal](#cidr-equal-addr)

---
### cidr:mask (bits)

Return a corresponding CIDR representing the netmask of this instance.

**Parameters**

- bits: Override prefix length of this instance (optional)

**Return value:**

CIDR instance containing the netmask

**See also:**

- [cidr:network](#cidr-network-bits)
- [cidr:host](#cidr-host)
- [cidr:broadcast](#cidr-broadcast)

---
### cidr:maxhost ()

Return CIDR containing the highest available host address within the subnet.

**Return value:**

CIDR containing the host address, nil if subnet is too small

**See also:**

- [cidr:minhost](#cidr-minhost)

---
### cidr:minhost ()

Return CIDR containing the lowest available host address within this subnet.

**Return value:**

CIDR containing the host address, nil if subnet is too small

**See also:**

- [cidr:maxhost](#cidr-maxhost)

---
### cidr:network (bits)

Return a corresponding CIDR representing the network address of this instance.

**Parameters**

- bits: Override prefix length of this instance (optional)

**Return value:**

CIDR instance containing the network address

**See also:**

- [cidr:host](#cidr-host)
- [cidr:broadcast](#cidr-broadcast)
- [cidr:mask](#cidr-mask-bits)

---
### cidr:prefix (mask)

Return the prefix length of this CIDR instance.

**Parameters**

- mask: Override instance prefix with given netmask (optional)

**Return value:**

Prefix length in bit

---
### cidr:string ()

Return a corresponding string representation of the instance. If the prefix length is lower then the maximum possible prefix length for the corresponding address type then the address is returned in CIDR notation, otherwise the prefix will be left out.

---
### cidr:sub (amount, inplace)

Substract specified amount of hosts from this instance.

**Parameters**

- amount: Number of hosts to substract from this instance
- inplace: Boolen indicating whether to alter values inplace (optional)

**Return value:**

CIDR representing the new address or nil on underflow error

**See also:**

- [cidr:add](#cidr-add-amount-inplace)
