# Class `luci.lucid`

## Functions

|
| -                                                                    | -                                                                            |
| [close_pollfds](#close_pollfds) ()                                   | Close all registered file descriptors from main loop.                        |
| [create_process](#create_process-threadcb-waitcb) (threadcb, waitcb) | Create a new child process from a Lua function and assign a destructor.      |
| [daemonize](#daemonize) ()                                           | Daemonize the process.                                                       |
| [get_interfaces](#get_interfaces) ()                                 | Return a list of available network interfaces on the host.                   |
| [prepare](#prepare) ()                                               | Prepares the slaves-daemons and publishers, allocate resources.              |
| [prepare_daemon](#prepare_daemon-config) (config)                    | Prepare a daemon from a given configuration table.                           |
| [prepare_slave](#prepare_slave-name) (name)                          | Prepare a slave.                                                             |
| [register_pollfd](#register_pollfd-polle) (polle)                    | Add a file descriptor for the main loop and associate handler functions.     |
| [register_tick](#register_tick-cb) (cb)                              | Register a tick function that will be called at each cycle of the main loop. |
| [revoke_privileges](#revoke_privileges-user-group) (user, group)     | Revoke process privileges.                                                   |
| [run](#run) ()                                                       | Run the superprocess if prepared before.                                     |
| [running](#running) ()                                               | Returns the PID of the currently active LuCId process.                       |
| [securestate](#securestate) ()                                       | Return a secure UCI cursor.                                                  |
| [start](#start) ()                                                   | Starts a new LuCId superprocess.                                             |
| [stop](#stop) ()                                                     | Stops any running LuCId superprocess.                                        |
| [try_process](#try_process) ()                                       | Tests whether a given number of processes can be created.                    |
| [unregister_pollfd](#unregister_pollfd-polle) (polle)                | Unregister a file desciptor and associate handler from the main loop.        |
| [unregister_tick](#unregister_tick-cb) (cb)                          | Unregister a tick function from the main loop.                               |

## Functions

### close_pollfds ()

Close all registered file descriptors from main loop. This is useful for forked child processes.

---
### create_process (threadcb, waitcb)

Create a new child process from a Lua function and assign a destructor.

**Parameters**

- threadcb: main function of the new process
- waitcb: destructor callback

**Return value:**

process identifier or nil, error code, error message

---
### daemonize ()

Daemonize the process.

**Return value:**

boolean status or nil, error code, error message

---
### get_interfaces ()

Return a list of available network interfaces on the host.

**Return value:**

table returned by nixio.getifaddrs()

---
### prepare ()

Prepares the slaves, daemons and publishers, allocate resources.

---
### prepare_daemon (config)

Prepare a daemon from a given configuration table.

**Parameters**

- config: Configuration data.

**Return value:**

boolean status or nil, error code, error message

---
### prepare_slave (name)

Prepare a slave.

**Parameters**

- name: slave name

**Return value:**

table containing slave module and configuration or nil, error message

---
### register_pollfd (polle)

Add a file descriptor for the main loop and associate handler functions.

**Parameters**

- polle: Table containing: {fd = FILE DESCRIPTOR, events = POLL EVENTS, handler = EVENT HANDLER CALLBACK}

**Return value:**

boolean status

**See also:**

- [unregister_pollfd](#unregister_pollfd-polle)

---
### register_tick (cb)

Register a tick function that will be called at each cycle of the main loop.

**Parameters**

- cb: Callback

**Return value:**

boolean status

**See also:**

[unregister_tick](##unregister_tick-cb)

---
### revoke_privileges (user, group)

Revoke process privileges.

**Parameters**

- user: new user name or uid
- group: new group name or gid

**Return value:**

boolean status or nil, error code, error message

---
### run ()

Run the superprocess if prepared before. This main function of LuCId will wait for events on given file descriptors.

---
### running ()

Returns the PID of the currently active LuCId process.

---
### securestate ()

Return a secure UCI cursor.

**Return value:**

UCI cursor

---
### start ()

Starts a new LuCId superprocess.

---
### stop ()

Stops any running LuCId superprocess.

---
### try_process ()

Tests whether a given number of processes can be created.

**Return value:**

boolean status

---
### unregister_pollfd (polle)

Unregister a file desciptor and associate handler from the main loop.

**Parameters**

- polle: Poll descriptor

**Return value:**

boolean status

**See also:**

- [register_pollfd](#register_pollfd-polle)

---
### unregister_tick (cb)

Unregister a tick function from the main loop.

**Parameters**

- cb: Callback

**Return value:**

boolean status

**See also:**

- [register_tick](#register_tick-cb)
