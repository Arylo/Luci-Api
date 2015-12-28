# Class `luci.lucid.rpc.ruci`

Remote UCI functions.

## Functions

|                                                                                          |                                   |
| -                                                                                        | -                                 |
| [cursor](#cursor-session) (session, ...)                                                 | Generate a new RUCI cursor.       |
| [cursor_state](#cursor_state-session) (session, ...)                                     | Generate a new RUCI state cursor. |
| [foreach](#foreach-session-inst-config-sectiontype) (session, inst, config, sectiontype) | Custom foreach function.          |

## Functions

### cursor (session, ...)

Generate a new RUCI cursor.

**Parameters**

- session: Session object
- ...: Parameters passed to the UCI constructor

**Return value:**

RUCI instance

---
### cursor_state (session, ...)

Generate a new RUCI state cursor.

**Parameters**

- session: Session object
- ...: Parameters passed to the UCI constructor

**Return value:**

RUCI instance

---
### foreach (session, inst, config, sectiontype)

Custom foreach function.

**Parameters**

- session: Session object
- inst: RUCI instance
- config: UCI config
- sectiontype: UCI sectiontype

**Return value:**

section data
