# Class `luci.sys`

LuCI Linux and POSIX system utilities.

## Functions

|                                                             |                                                                  |
| -                                                           | -                                                                |
| [call](#call) (...)                                         | Execute a given shell command and return the error code          |
| [dmesg](#dmesg) ()                                          | Retrieves the output of the "dmesg" command.                     |
| [exec](#exec-command) (command)                             | Execute a given shell command and capture its standard output    |
| [getenv](#getenv-var) (var)                                 | Retrieve environment variables.                                  |
| [hostname](#hostname-String) (String)                       | Get or set the current hostname.                                 |
| [httpget](#httpget-url-stream-target) (url, stream, target) | Returns the contents of a documented referred by an URL.         |
| [loadavg](#loadavg) ()                                      | Returns the system load average values.                          |
| [mounts](#mounts) ()                                        | Retrieve information about currently mounted file systems.       |
| [reboot](#reboot) ()                                        | Initiate a system reboot.                                        |
| [sysinfo](#sysinfo) ()                                      | Returns the system type, cpu name and installed physical memory. |
| [syslog](#syslog) ()                                        | Retrieves the output of the "logread" command.                   |
| [uniqueid](#uniqueid-bytes) (bytes)                         | Generates a random id with specified length.                     |
| [uptime](#uptime) ()                                        | Returns the current system uptime stats.                         |

## Functions

### call (...)

Execute a given shell command and return the error code

**Parameters**

- ...: Command to call

**Return value:**

Error code of the command

---
### dmesg ()

Retrieves the output of the "dmesg" command.

**Return value:**

String containing the current log buffer

---
### exec (command)

Execute a given shell command and capture its standard output

**Parameters**

- command: Command to call

**Return value:**

String containg the return the output of the command

---
### getenv (var)

Retrieve environment variables. If no variable is given then a table containing the whole environment is returned otherwise this function returns the corresponding string value for the given name or nil if no such variable exists.

**Parameters**

- var: Name of the environment variable to retrieve (optional)

**Return values:**

+ String containg the value of the specified variable
+ Table containing all variables if no variable name is given

---
### hostname (String)

Get or set the current hostname.

**Parameters**

- String: containing a new hostname to set (optional)

**Return value:**

String containing the system hostname

---
### httpget (url, stream, target)

Returns the contents of a documented referred by an URL.

**Parameters**

- url: The URL to retrieve
- stream: Return a stream instead of a buffer
- target: Directly write to target file name

**Return value:**

String containing the contents of given the URL

---
### loadavg ()

Returns the system load average values.

**Return values:**

+ String containing the average load value 1 minute ago
+ String containing the average load value 5 minutes ago
+ String containing the average load value 15 minutes ago

---
### mounts ()

Retrieve information about currently mounted file systems.

**Return value:**

Table containing mount information

---
### reboot ()

Initiate a system reboot.

**Return value:**

Return value of os.execute()

---
### sysinfo ()

Returns the system type, cpu name and installed physical memory.

**Return values:**

+ String containing the system or platform identifier
+ String containing hardware model information
+ String containing the total memory amount in kB
+ String containing the memory used for caching in kB
+ String containing the memory used for buffering in kB
+ String containing the free memory amount in kB
+ String containing the cpu bogomips (number)

---
### syslog ()

Retrieves the output of the "logread" command.

**Return value:**

String containing the current log buffer

---
### uniqueid (bytes)

Generates a random id with specified length.

**Parameters**

- bytes: Number of bytes for the unique id

**Return value:**

String containing hex encoded id

---
### uptime ()

Returns the current system uptime stats.

**Return value:**

String containing total uptime in seconds
