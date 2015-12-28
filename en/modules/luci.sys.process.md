# Class `luci.sys.process`

LuCI system utilities / process related functions.

## Functions

|                                      |                                                         |
| -                                    | -                                                       |
| [info](#info) ()                     | Get the current process id.                             |
| [list](#list) ()                     | Retrieve information about currently running processes. |
| [setgroup](#setgroup-gid) (gid)      | Set the gid of a process identified by given pid.       |
| [setuser](#setuser-uid) (uid)        | Set the uid of a process identified by given pid.       |
| [signal](#signal-pid-sig) (pid, sig) | Send a signal to a process identified by given pid.     |

## Functions

### info ()

Get the current process id.

**Return value:**

Number containing the current pid

---
### list ()

Retrieve information about currently running processes.

**Return value:**

Table containing process information

---
### setgroup (gid)

Set the gid of a process identified by given pid.

**Parameters**

- gid: Number containing the Unix group id

**Return values:**

+ Boolean indicating successful operation
+ String containing the error message if failed
+ Number containing the error code if failed

---
### setuser (uid)

Set the uid of a process identified by given pid.

**Parameters**

- uid: Number containing the Unix user id

**Return values:**

+ Boolean indicating successful operation
+ String containing the error message if failed
+ Number containing the error code if failed

---
### signal (pid, sig)

Send a signal to a process identified by given pid.

**Parameters**

- pid: Number containing the process id
- sig: Signal to send (default: 15 [SIGTERM])

**Return values:**

+ Boolean indicating successful operation
+ Number containing the error code if failed
