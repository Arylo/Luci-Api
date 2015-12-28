# Class `luci.sauth`

LuCI session library.

## Functions

|                                    |                                                            |
| -                                  | -                                                          |
| [clean](#clean) ()                 | Manually clean up expired sessions.                        |
| [kill](#kill-id) (id)              | Kills a session                                            |
| [prepare](#prepare) ()             | Prepare session storage by creating the session directory. |
| [read](#read-id) (id)              | Read a session and return its content.                     |
| [sane](#sane) ()                   | Check whether Session environment is sane.                 |
| [write](#write-id-data) (id, data) | Write session data to a session file.                      |

## Functions

### clean ()

Manually clean up expired sessions.

---
### kill (id)

Kills a session

**Parameters**

- id: Session identifier

---
### prepare ()

Prepare session storage by creating the session directory.

---
### read (id)

Read a session and return its content.

**Parameters**

- id: Session identifier

**Return value:**

Session data

---
### sane ()

Check whether Session environment is sane.

**Return value:**

Boolean status

---
### write (id, data)

Write session data to a session file.

**Parameters**

- id: Session identifier
- data: Session data
