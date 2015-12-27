# Class `luci.util`

LuCI utility functions.

## Functions

|                                                            |                                                                                                               |
| -                                                          | -                                                                                                             |
| [append](#append-src) (src, ...)                           | Appends numerically indexed tables or single objects to a given table.                                        |
| [bigendian](#bigendian) ()                                 | Test whether the current system is operating in big endian mode.                                              |
| [class](#class-base) (base)                                | Create a Class object (Python-style object model).                                                            |
| [clone](#clone-object-deep) (object, deep)                 | Clones the given object and return it's copy.                                                                 |
| [cmatch](#cmatch-str-pattern) (str, pattern)               | Count the occurences of given substring in given string.                                                      |
| [combine](#combine-tbl1-tbl2) (tbl1, tbl2, ...)            | Combines two or more numerically indexed tables and single objects into one table.                            |
| [contains](#contains-table-value) (table, value)           | Checks whether the given table contains the given value.                                                      |
| [copcall](#copcall-f) (f, ...)                             | This is a coroutine-safe drop-in replacement for Lua's "pcall"-function                                       |
| [coxpcall](#coxpcall-f-err) (f, err, ...)                  | This is a coroutine-safe drop-in replacement for Lua's "xpcall"-function                                      |
| [dtable](#dtable) ()                                       | Create a dynamic table which automatically creates subtables.                                                 |
| [dumptable](#dumptable-t-maxdepth) (t, maxdepth)           | Recursively dumps a table to stdout, useful for testing and debugging.                                        |
| [escape](#escape-s-c) (s, c)                               | Escapes all occurrences of the given character in given string.                                               |
| [exec](#exec-command) (command)                            | Execute given commandline and gather stdout.                                                                  |
| [execi](#execi-command) (command)                          | Return a line-buffered iterator over the output of given command.                                             |
| [get_bytecode](#get_bytecode-val) (val)                    | Return the current runtime bytecode of the given data.                                                        |
| [imatch](#imatch-val) (val)                                | Return a matching iterator for the given value.                                                               |
| [instanceof](#instanceof-object-class) (object, class)     | Test whether the given object is an instance of the given class.                                              |
| [keys](#keys-t) (t)                                        | Retrieve all keys of given associative table.                                                                 |
| [kspairs](#kspairs-t) (t)                                  | Return a key, value iterator for the given table.                                                             |
| [libpath](#libpath) ()                                     | Returns the absolute path to LuCI base directory.                                                             |
| [parse_units](#parse_units-ustr) (ustr)                    | Parse certain units from the given string and return the canonical integer value or 0 if the unit is unknown. |
| [pcdata](#pcdata-value) (value)                            | Create valid XML PCDATA from given string.                                                                    |
| [perror](#perror-obj) (obj)                                | Write given object to stderr.                                                                                 |
| [restore_data](#restore_data-str) (str)                    | Restore data previously serialized with serialize_data().                                                     |
| [serialize_data](#serialize_data-val) (val)                | Recursively serialize given data to lua code, suitable for restoring with loadstring().                       |
| [spairs](#spairs-t-f) (t, f)                               | Return a key, value iterator which returns the values sorted according to the provided callback function.     |
| [split](#split-str-pat, max, regex) (str, pat, max, regex) | Splits given string on a defined separator sequence and return a table containing the resulting substrings.   |
| [strip_bytecode](#strip_bytecode-code) (code)              | Strips unnescessary lua bytecode from given string.                                                           |
| [striptags](#striptags-value) (value)                      | Strip HTML tags from given string.                                                                            |
| [threadlocal](#threadlocal) ()                             | Create a new or get an already existing thread local store associated with the current active coroutine.      |
| [trim](#trim-str) (str)                                    | Remove leading and trailing whitespace from given string value.                                               |
| [update](#update-t-updates) (t, updates)                   | Update values in given table with the values from the second given table.                                     |
| [vspairs](#vspairs-t) (t)                                  | Return a key, value iterator for the given table.                                                             |

## Functions

### append (src, ...)

Appends numerically indexed tables or single objects to a given table.

**Parameters**

- src: Target table
- ...: Objects to insert

**Return value:**

Target table

---
### bigendian ()

Test whether the current system is operating in big endian mode.

**Return value:**

Boolean value indicating whether system is big endian

---
### class (base)

Create a Class object (Python-style object model). The class object can be instantiated by calling itself. Any class functions or shared parameters can be attached to this object. Attaching a table to the class object makes this table shared between all instances of this class. For object parameters use the __init__ function. Classes can inherit member functions and values from a base class. Class can be instantiated by calling them. All parameters will be passed to the __init__ function of this class - if such a function exists. The __init__ function must be used to set any object parameters that are not shared with other objects of this class. Any return values will be ignored.

**Parameters**

- base: The base class to inherit from (optional)

**Return value:**

A class object

**See also:**

- [instanceof](#instanceof-object-class)
- [clone](#clone-object-deep)

---
### clone (object, deep)

Clones the given object and return it's copy.

**Parameters**

- object: Table value to clone
- deep: Boolean indicating whether to do recursive cloning

**Return value:**

Cloned table value

---
### cmatch (str, pattern)

Count the occurences of given substring in given string.

**Parameters**

- str: String to search in
- pattern: String containing pattern to find

**Return value:**

Number of found occurences

---
### combine (tbl1, tbl2, ...)

Combines two or more numerically indexed tables and single objects into one table.

**Parameters**

- tbl1: Table value to combine
- tbl2: Table value to combine
- ...: More tables to combine

**Return value:**

Table value containing all values of given tables

---
### contains (table, value)

Checks whether the given table contains the given value.

**Parameters**

- table: Table value
- value: Value to search within the given table

**Return value:**

Boolean indicating whether the given value occurs within table

---
### copcall (f, ...)

This is a coroutine-safe drop-in replacement for Lua's "pcall"-function

**Parameters**

- f: Lua function to be called protected
- ...: Parameters passed to the function

**Return value:**

A boolean whether the function call succeeded and the returns values of the function or the error object

---
### coxpcall (f, err, ...)

This is a coroutine-safe drop-in replacement for Lua's "xpcall"-function

**Parameters**

- f: Lua function to be called protected
- err: Custom error handler
- ...: Parameters passed to the function

**Return value:**

A boolean whether the function call succeeded and the return values of either the function or the error handler

---
### dtable ()

Create a dynamic table which automatically creates subtables.

**Return value:**

Dynamic Table

---
### dumptable (t, maxdepth)

Recursively dumps a table to stdout, useful for testing and debugging.

**Parameters**

- t: Table value to dump
- maxdepth: Maximum depth

**Return value:**

Always nil

---
### escape (s, c)

Escapes all occurrences of the given character in given string.

**Parameters**

- s: String value containing unescaped characters
- c: String value with character to escape (optional, defaults to "\")

**Return value:**

String value with each occurrence of character escaped with "\"

---
### exec (command)

Execute given commandline and gather stdout.

**Parameters**

- command: String containing command to execute

**Return value:**

String containing the command's stdout

---
### execi (command)

Return a line-buffered iterator over the output of given command.

**Parameters**

- command: String containing the command to execute

**Return value:**

Iterator

---
### get_bytecode (val)

Return the current runtime bytecode of the given data. The byte code will be stripped before it is returned.

**Parameters**

- val: Value to return as bytecode

**Return value:**

String value containing the bytecode of the given data

---
### imatch (val)

Return a matching iterator for the given value. The iterator will return one token per invocation, the tokens are separated by whitespace. If the input value is a table, it is transformed into a string first. A nil value will result in a valid interator which aborts with the first invocation.

**Parameters**

- val: The value to scan (table, string or nil)

**Return value:**

Iterator which returns one token per call

---
### instanceof (object, class)

Test whether the given object is an instance of the given class.

**Parameters**

- object: Object instance
- class: Class object to test against

**Return value:**

Boolean indicating whether the object is an instance

**See also:**

- [class](#class-base)
- [clone](#clone-object-deep)

---
### keys (t)

Retrieve all keys of given associative table.

**Parameters**

- t: Table to extract keys from

**Return value:**

Sorted table containing the keys

---
### kspairs (t)

Return a key, value iterator for the given table. The table pairs are sorted by key.

**Parameters**

- t: The table to iterate

**Return value:**

Function value containing the corresponding iterator

---
### libpath ()

Returns the absolute path to LuCI base directory.

**Return value:**

String containing the directory path

---
### parse_units (ustr)

Parse certain units from the given string and return the canonical integer value or 0 if the unit is unknown. Upper- or lower case is irrelevant. Recognized units are: o "y"	- one year   (60*60*24*366) o "m"	- one month  (60*60*24*31) o "w"	- one week   (60*60*24*7) o "d"	- one day    (60*60*24) o "h"	- one hour	 (60*60) o "min"	- one minute (60) o "kb"  - one kilobyte (1024) o "mb"	- one megabyte (1024*1024) o "gb"	- one gigabyte (1024*1024*1024) o "kib" - one si kilobyte (1000) o "mib"	- one si megabyte (1000*1000) o "gib"	- one si gigabyte (1000*1000*1000)

**Parameters**

- ustr: String containing a numerical value with trailing unit

**Return value:**

Number containing the canonical value

---
### pcdata (value)

Create valid XML PCDATA from given string.

**Parameters**

- value: String value containing the data to escape

**Return value:**

String value containing the escaped data

---
### perror (obj)

Write given object to stderr.

**Parameters**

- obj: Value to write to stderr

**Return value:**

Boolean indicating whether the write operation was successful

---
### restore_data (str)

Restore data previously serialized with serialize_data().

**Parameters**

- str: String containing the data to restore

**Return value:**

Value containing the restored data structure

**See also:**

- [serialize_data](#serialize_data-val)
- [get_bytecode](#get_bytecode-val)

---
### serialize_data (val)

Recursively serialize given data to lua code, suitable for restoring with loadstring().

**Parameters**

- val: Value containing the data to serialize

**Return value:**

String value containing the serialized code

**See also:**

- [restore_data](#restore_data-str)
- [get_bytecode](#get_bytecode-val)

---
### spairs (t, f)

Return a key, value iterator which returns the values sorted according to the provided callback function.

**Parameters**

- t: The table to iterate
- f: A callback function to decide the order of elements

**Return value:**

Function value containing the corresponding iterator

---
### split (str, pat, max, regex)

Splits given string on a defined separator sequence and return a table containing the resulting substrings. The optional max parameter specifies the number of bytes to process, regardless of the actual length of the given string. The optional last parameter, regex, specifies whether the separator sequence is interpreted as regular expression.

**Parameters**

- str: String value containing the data to split up
- pat: String with separator pattern (optional, defaults to "\n")
- max: Maximum times to split (optional)
- regex: Boolean indicating whether to interpret the separator pattern as regular expression (optional, default is false)

**Return value:**

Table containing the resulting substrings

---
### strip_bytecode (code)

Strips unnescessary lua bytecode from given string. Information like line numbers and debugging numbers will be discarded. Original version by Peter Cawley (http://lua-users.org/lists/lua-l/2008-02/msg01158.html)

**Parameters**

- code: String value containing the original lua byte code

**Return value:**

String value containing the stripped lua byte code

---
### striptags (value)

Strip HTML tags from given string.

**Parameters**

- value: String containing the HTML text

**Return value:**

String with HTML tags stripped of

---
### threadlocal ()

Create a new or get an already existing thread local store associated with the current active coroutine. A thread local store is private a table object whose values can't be accessed from outside of the running coroutine.

**Return value:**

Table value representing the corresponding thread local store

---
### trim (str)

Remove leading and trailing whitespace from given string value.

**Parameters**

- str: String value containing whitespace padded data

**Return value:**

String value with leading and trailing space removed

---
### update (t, updates)

Update values in given table with the values from the second given table. Both table are - in fact - merged together.

**Parameters**

- t: Table which should be updated
- updates: Table containing the values to update

**Return value:**

Always nil

---
### vspairs (t)

Return a key, value iterator for the given table. The table pairs are sorted by value.

**Parameters**

- t: The table to iterate

**Return value:**

Function value containing the corresponding iterator
