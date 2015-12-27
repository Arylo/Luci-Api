# Class `luci.lucid.tcpserver`

## Functions

|                                                                                                     |                                                              |
| -                                                                                                   | -                                                            |
| [accept](#accept-polle) (polle)                                                                     | Accept a new TCP connection.                                 |
| [prepare_daemon](#prepare_daemon-config-server) (config, server)                                    | Prepare a daemon and allocate its resources.                 |
| [prepare_socket](#prepare_socket-family-host-port-opts-backlog) (family, host, port, opts, backlog) | Prepare a TCP server socket.                                 |
| [prepare_tls](#prepare_tls-tlskey) (tlskey)                                                         | Prepare a TLS server context and load keys and certificates. |

## Functions

### accept (polle)

Accept a new TCP connection. (server callback)

**Parameters**

- polle: Poll descriptor

**Return value:**

handler process id or nil, error code, error message

---

### prepare_daemon (config, server)

Prepare a daemon and allocate its resources. (superserver callback)

**Parameters**

- config: configuration table
- server: LuCId basemodule

**Return value:**

binary data

---

### prepare_socket (family, host, port, opts, backlog)

Prepare a TCP server socket.

**Parameters**

- family: protocol family ["inetany", "inet6", "inet"]
- host: host
- port: port
- opts: table of socket options
- backlog: socket backlog

**Return value:**

socket, final socket family

---

### prepare_tls (tlskey)

Prepare a TLS server context and load keys and certificates. May invoke px5g to create keys and certificate on demand if available.

**Parameters**

- tlskey: TLS configuration identifier

**Return value:**

TLS server conext or nil
