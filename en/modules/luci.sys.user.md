# Class `luci.sys.user`

LuCI system utilities / user related functions.

## Functions

|                                                                |                                                                        |
| -                                                              | -                                                                      |
| [getuser](#getuser-uid) (uid)                                  | Retrieve user informations for given uid.                              |
| [checkpasswd](#checkpasswd-username-pass) (username, pass)     | Test whether given string matches the password of a given system user. |
| [getpasswd](#getpasswd-username) (username)                    | Retrieve the current user password hash.                               |
| [setpasswd](#setpasswd-username-password) (username, password) | Change the password of given user.                                     |

## Functions

### getuser (uid)

Retrieve user informations for given uid.

**Parameters**

- uid: Number containing the Unix user id

**Return value:**

Table containing the following fields: { "uid", "gid", "name", "passwd", "dir", "shell", "gecos" }

---
### checkpasswd (username, pass)

Test whether given string matches the password of a given system user.

**Parameters**

- username: String containing the Unix user name
- pass: String containing the password to compare

**Return value:**

Boolean indicating wheather the passwords are equal

---
### getpasswd (username)

Retrieve the current user password hash.

**Parameters**

- username: String containing the username to retrieve the password for

**Return value:**

String containing the hash or nil if no password is set.

---
### setpasswd (username, password)

Change the password of given user.

**Parameters**

- username: String containing the Unix user name
- password: String containing the password to compare

**Return value:**

Number containing 0 on success and >= 1 on error
