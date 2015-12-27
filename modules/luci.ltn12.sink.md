# Class `luci.ltn12.sink`

LTN12 sink constructors

## Functions

|                                              |                                           |
| -                                            | -                                         |
| [chain](#chain-f-snk) (f, snk)               | Chain a sink with a filter.               |
| [error](#error-err) (err)                    | Create a sink that just returns an error. |
| [file](#file-handle-io_err) (handle, io_err) | Create a file sink.                       |
| [null](#null) ()                             | Create a sink that discards data.         |
| [simplify](#simplify-snk) (snk)              | Turn a fancy sink into a simple sink.     |
| [table](#table-t) (t)                        | Create a sink that stores into a table.   |

## Functions

### chain (f, snk)

Chain a sink with a filter.

**Parameters**

- f: LTN12 filter
- snk: LTN12 sink

**Return value:**

LTN12 sink

---
### error (err)

Create a sink that just returns an error.

**Parameters**

- err: Error object

**Return value:**

LTN12 sink

---
### file (handle, io_err)

Create a file sink.

**Parameters**

- handle: file handle to write to
- io_err: IO error

**Return value:**

LTN12 sink

---
### null ()

Create a sink that discards data.

**Return value:**

LTN12 sink

---
### simplify (snk)

Turn a fancy sink into a simple sink.

**Parameters**

- snk: fancy sink

**Return value:**

LTN12 sink

---
### table (t)

Create a sink that stores into a table.

**Parameters**

- t: output table to store into

**Return value:**

LTN12 sink
