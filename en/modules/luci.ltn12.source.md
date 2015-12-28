# Class `luci.ltn12.source`

LTN12 Source constructors

## Functions

|                                              |                                                            |
| -                                            | -                                                          |
| [cat](#cat) (...)                            | Create a source that produces contents of several sources. |
| [chain](#chain-src-f) (src, f)               | Chain a source and a filter together.                      |
| [empty](#empty) ()                           | Create an empty source.                                    |
| [error](#error-err) (err)                    | Return a source that just outputs an error.                |
| [file](#file-handle-io_err) (handle, io_err) | Create a file source.                                      |
| [rewind](#rewind-src) (src)                  | Creates rewindable source.                                 |
| [simplify](#simplify-src) (src)              | Turn a fancy source into a simple source.                  |
| [string](#string-s) (s)                      | Create a string source.                                    |

## Functions

### cat (...)

Create a source that produces contents of several sources. Sources will be used one after the other, as if they were concatenated (thanks to Wim Couwenberg)

**Parameters**

- ...: LTN12 sources

**Return value:**

LTN12 source

---
### chain (src, f)

Chain a source and a filter together.

**Parameters**

- src: LTN12 source
- f: LTN12 filter

**Return value:**

LTN12 source

---
### empty ()

Create an empty source.

**Return value:**

LTN12 source

---
### error (err)

Return a source that just outputs an error.

**Parameters**

- err: Error object

**Return value:**

LTN12 source

---
### file (handle, io_err)

Create a file source.

**Parameters**

- handle: File handle ready for reading
- io_err: IO error object

**Return value:**

LTN12 source

---
### rewind (src)

Creates rewindable source.

**Parameters**

- src: LTN12 source to be made rewindable

**Return value:**

LTN12 source

---
### simplify (src)

Turn a fancy source into a simple source.

**Parameters**

- src: fancy source

**Return value:**

LTN12 source

---
### string (s)

Create a string source.

**Parameters**

- s: Data

**Return value:**

LTN12 source
