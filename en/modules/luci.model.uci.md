# Object Instance `luci.model.uci`

LuCI UCI model library. The typical workflow for UCI is:  Get a cursor instance from the cursor factory, modify data (via Cursor.add, Cursor.delete, etc.), save the changes to the staging area via Cursor.save and finally Cursor.commit the data to the actual config files. LuCI then needs to Cursor.apply the changes so deamons etc. are reloaded.

## Functions

|                                                                                                 |                                                                  |
| -                                                                                               | -                                                                |
| [Cursor:add](#cursor-add-config-type) (config, type)                                             | Add an anonymous section.                                        |
| [Cursor:apply](#cursor-apply-configlist-command) (configlist, command)                           | Applies UCI configuration changes                                |
| [Cursor:changes](#cursor-changes-config) (config)                                                | Get a table of saved but uncommitted changes.                    |
| [Cursor:commit](#cursor-commit-config) (config)                                                  | Commit saved changes.                                            |
| [Cursor:delete](#cursor-delete-config-section-option) (config, section, option)                  | Deletes a section or an option.                                  |
| [Cursor:delete_all](#cursor-delete_all-config-type-comparator) (config, type, comparator)        | Delete all sections of a given type that match certain criteria. |
| [Cursor:foreach](#cursor-foreach-config-type-callback) (config, type, callback)                  | Call a function for every section of a certain type.             |
| [Cursor:get](#cursor-get-config-section-option) (config, section, option)                        | Get a section type or an option                                  |
| [Cursor:get_all](#cursor-get_all-config-section) (config, section)                               | Get all sections of a config or all values of a section.         |
| [Cursor:get_bool](#cursor-get_bool-config-section-option) (config, section, option)              | Get a boolean option and return it's value as true or false.     |
| [Cursor:get_confdir](#cursor-get_confdir) ()                                                     | Get the configuration directory.                                 |
| [Cursor:get_first](#cursor-get_first-config-type-option-default) (config, type, option, default) | Get the given option from the first section with the given type. |
| [Cursor:get_list](#cursor-get_list-config-section-option) (config, section, option)              | Get an option or list and return values as table.                |
| [Cursor:get_savedir](#cursor-get_savedir) ()                                                     | Get the directory for uncomitted changes.                        |
| [Cursor:load](#cursor-load-config) (config)                                                      | Manually load a config.                                          |
| [Cursor:revert](#cursor-revert-config) (config)                                                  | Revert saved but uncommitted changes.                            |
| [Cursor:save](#cursor-save-config) (config)                                                      | Saves changes made to a config to make them committable.         |
| [Cursor:section](#cursor-section-config-type-name-values) (config, type, name, values)           | Create a new section and initialize it with data.                |
| [Cursor:set](#cursor-set-config-section-option-value) (config, section, option, value)           | Set a value or create a named section.                           |
| [Cursor:set_confdir](#cursor-set_confdir-directory) (directory)                                  | Set the configuration directory.                                 |
| [Cursor:set_list](#cursor-set_list-config-section-option-value) (config, section, option, value) | Set given values as list.                                        |
| [Cursor:set_savedir](#cursor-set_savedir-directory) (directory)                                  | Set the directory for uncommited changes.                        |
| [Cursor:substate](#cursor-substate) ()                                                           | Create a sub-state of this cursor.                               |
| [Cursor:tset](#cursor-tset-config-section-values) (config, section, values)                      | Updated the data of a section using data from a table.           |
| [Cursor:unload](#cursor-unload-config) (config)                                                  | Discard changes made to a config.                                |
| [cursor](#cursor-) ()                                                                            | Create a new UCI-Cursor.                                         |
| [cursor_state](#cursor-_state) ()                                                                | Create a new Cursor initialized to the state directory.          |

## Functions

### Cursor:add (config, type)

Add an anonymous section.

**Parameters**

- config: UCI config
- type: UCI section type

**Return value:**

Name of created section

---
### Cursor:apply (configlist, command)

Applies UCI configuration changes

**Parameters**

- configlist: List of UCI configurations
- command: Don't apply only return the command

---
### Cursor:changes (config)

Get a table of saved but uncommitted changes.

**Parameters**

- config: UCI config

**Return value:**

Table of changes

**See also:**

- [Cursor:save](#cursor-save-config)

---
### Cursor:commit (config)

Commit saved changes.

**Parameters**

- config: UCI config

**Return value:**

Boolean whether operation succeeded

**See also:**

- [Cursor:revert](#cursor-revert-config)
- [Cursor:save](#cursor-save-config)

---
### Cursor:delete (config, section, option)

Deletes a section or an option.

**Parameters**

- config: UCI config
- section: UCI section name
- option: UCI option (optional)

**Return value:**

Boolean whether operation succeeded

---
### Cursor:delete_all (config, type, comparator)

Delete all sections of a given type that match certain criteria.

**Parameters**

- config: UCI config
- type: UCI section type
- comparator: Function that will be called for each section and returns a boolean whether to delete the current section (optional)

---
### Cursor:foreach (config, type, callback)

Call a function for every section of a certain type.

**Parameters**

- config: UCI config
- type: UCI section type
- callback: Function to be called

**Return value:**

Boolean whether operation succeeded

---
### Cursor:get (config, section, option)

Get a section type or an option

**Parameters**

- config: UCI config
- section: UCI section name
- option: UCI option (optional)

**Return value:**

UCI value

---
### Cursor:get_all (config, section)

Get all sections of a config or all values of a section.

**Parameters**

- config: UCI config
- section: UCI section name (optional)

**Return value:**

Table of UCI sections or table of UCI values

---
### Cursor:get_bool (config, section, option)

Get a boolean option and return it's value as true or false.

**Parameters**

- config: UCI config
- section: UCI section name
- option: UCI option

**Return value:**

Boolean

---
### Cursor:get_confdir ()

Get the configuration directory.

**Return value:**

Configuration directory

---
### Cursor:get_first (config, type, option, default)

Get the given option from the first section with the given type.

**Parameters**

- config: UCI config
- type: UCI section type
- option: UCI option (optional)
- default: Default value (optional)

**Return value:**

UCI value

---
### Cursor:get_list (config, section, option)

Get an option or list and return values as table.

**Parameters**

- config: UCI config
- section: UCI section name
- option: UCI option

**Return value:**

UCI value

---
### Cursor:get_savedir ()

Get the directory for uncomitted changes.

**Return value:**

Save directory

---
### Cursor:load (config)

Manually load a config.

**Parameters**

- config: UCI config

**Return value:**

Boolean whether operation succeeded

**See also:**

- [Cursor:save](#cursor-save-config)
- [Cursor:unload](#cursor-unload-config)

---
### Cursor:revert (config)

Revert saved but uncommitted changes.

**Parameters**

- config: UCI config

**Return value:**

Boolean whether operation succeeded

**See also:**

- [Cursor:commit](#cursor-commit-config)
- [Cursor:save](#cursor-save-config)

---
### Cursor:save (config)

Saves changes made to a config to make them committable.

**Parameters**

- config: UCI config

**Return value:**

Boolean whether operation succeeded

**See also:**

- [Cursor:load](#cursor-load-config)
- [Cursor:unload](#cursor-unload-config)

---
### Cursor:section (config, type, name, values)

Create a new section and initialize it with data.

**Parameters**

- config: UCI config
- type: UCI section type
- name: UCI section name (optional)
- values: Table of key - value pairs to initialize the section with

**Return value:**

Name of created section

---
### Cursor:set (config, section, option, value)

Set a value or create a named section.

**Parameters**

- config: UCI config
- section: UCI section name
- option: UCI option or UCI section type
- value: UCI value or nil if you want to create a section

**Return value:**

Boolean whether operation succeeded

---
### Cursor:set_confdir (directory)

Set the configuration directory.

**Parameters**

- directory: UCI configuration directory

**Return value:**

Boolean whether operation succeeded

---
### Cursor:set_list (config, section, option, value)

Set given values as list.

**Parameters**

- config: UCI config
- section: UCI section name
- option: UCI option
- value: UCI value

**Return value:**

Boolean whether operation succeeded

---
### Cursor:set_savedir (directory)

Set the directory for uncommited changes.

**Parameters**

- directory: UCI changes directory

**Return value:**

Boolean whether operation succeeded

---
### Cursor:substate ()

Create a sub-state of this cursor. The sub-state is tied to the parent curser, means it the parent unloads or loads configs, the sub state will do so as well.

**Return value:**

UCI state cursor tied to the parent cursor

---
### Cursor:tset (config, section, values)

Updated the data of a section using data from a table.

**Parameters**

- config: UCI config
- section: UCI section name (optional)
- values: Table of key - value pairs to update the section with

---
### Cursor:unload (config)

Discard changes made to a config.

**Parameters**

- config: UCI config

**Return value:**

Boolean whether operation succeeded

**See also:**

- [Cursor:load](#cursor-load-config)
- [Cursor:save](#cursor-save-config)

---
### cursor ()

Create a new UCI-Cursor.

**Return value:**

UCI-Cursor

---
### cursor_state ()

Create a new Cursor initialized to the state directory.

**Return value:**

UCI cursor
