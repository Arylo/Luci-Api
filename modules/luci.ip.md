# Class `luci.ip`

LuCI IP calculation library.

## Constants

|                 |                                          |
| -               | -                                        |
| `LITTLE_ENDIAN` | Boolean; true if system is little endian |
| `BIG_ENDIAN`    | Boolean; true if system is big endian    |
| `FAMILY_INET4`  | Specifier for IPv4 address family        |
| `FAMILY_INET6`  | Specifier for IPv6 address family        |

## Functions

|                                                                |                                                                                         |
| -                                                              | -                                                                                       |
| [Hex](#hex-hex-prefix-family-swap) (hex, prefix, family, swap) | Transform given hex-encoded value to luci.ip.cidr instance of specified address family. |
| [IPv4](#ipv4-address-netmask) (address, netmask)               | Parse given IPv4 address in dotted quad or CIDR notation.                               |
| [IPv6](#ipv6-address-netmask) (address, netmask)               | Parse given IPv6 address in full, compressed, mixed or CIDR notation.                   |
| [htonl](#htonl-x) (x)                                          | Convert given long value to network byte order on little endian hosts                   |
| [htons](#htons-x) (x)                                          | Convert given short value to network byte order on little endian hosts                  |
| [ntohl](#ntohl-x) (x)                                          | Convert given short value to host byte order on little endian hosts                     |
| [ntohs](#ntohs-x) (x)                                          | Convert given short value to host byte order on little endian hosts                     |

## Functions

### Hex (hex, prefix, family, swap)

Transform given hex-encoded value to luci.ip.cidr instance of specified address family.

**Parameters**

- hex: String containing hex encoded value
- prefix: Prefix length of CIDR instance (optional, default is 32/128)
- family: Address family, either luci.ip.FAMILY_INET4 or FAMILY_INET6
- swap: Bool indicating whether to swap byteorder on low endian host

**Return value:**

luci.ip.cidr instance or nil if given value was invalid

**See also:**

- [IPv4](#ipv4-address-netmask)
- [IPv6](#ipv6-address-netmask)

---
### IPv4 (address, netmask)

Parse given IPv4 address in dotted quad or CIDR notation. If an optional netmask is given as second argument and the IP address is encoded in CIDR notation then the netmask parameter takes precedence. If neither a CIDR encoded prefix nor a netmask parameter is given, then a prefix length of 32 bit is assumed.

**Parameters**

- address: IPv4 address in dotted quad or CIDR notation
- netmask: IPv4 netmask in dotted quad notation (optional)

**Return value:**

luci.ip.cidr instance or nil if given address was invalid

**See also:**

- [IPv6](#ipv6-address-netmask)
- [Hex](#hex-hex-prefix-family-swap)

---
### IPv6 (address, netmask)

Parse given IPv6 address in full, compressed, mixed or CIDR notation. If an optional netmask is given as second argument and the IP address is encoded in CIDR notation then the netmask parameter takes precedence. If neither a CIDR encoded prefix nor a netmask parameter is given, then a prefix length of 128 bit is assumed.

**Parameters**

- address: IPv6 address in full/compressed/mixed or CIDR notation
- netmask: IPv6 netmask in full/compressed/mixed notation (optional)

**Return value:**

luci.ip.cidr instance or nil if given address was invalid

**See also:**

- [IPv4](#ipv4-address-netmask)
- [Hex](#hex-hex-prefix-family-swap)

---
### htonl (x)

Convert given long value to network byte order on little endian hosts

**Parameters**

- x: Unsigned integer value between 0x00000000 and 0xFFFFFFFF

**Return value:**

Byte-swapped value

**See also:**

- [htons](#htons-x)
- [ntohl](#ntohl-x)

---
### htons (x)

Convert given short value to network byte order on little endian hosts

**Parameters**

- x: Unsigned integer value between 0x0000 and 0xFFFF

**Return value:**

Byte-swapped value

**See also:**

- [htonl](#htonl-x)
- [ntohs](#ntohs-x)

---
### ntohl (x)

Convert given short value to host byte order on little endian hosts

**Parameters**

- x: Unsigned integer value between 0x00000000 and 0xFFFFFFFF

**Return value:**

Byte-swapped value

**See also:**

- [htons](#htons-x)
- [ntohl](#ntohl-x)

---
### ntohs (x)

Convert given short value to host byte order on little endian hosts

**Parameters**

- x: Unsigned integer value between 0x0000 and 0xFFFF

**Return value:**

Byte-swapped value

**See also:**

- [htonl](#htonl-x)
- [ntohs](#ntohs-x)
