# Class `luci.ltn12.pump`

LTN12 pump functions

## Functions

|                                           |                                                               |
| -                                         | -                                                             |
| [all](#all-src-snk-step) (src, snk, step) | Pump all data from a source to a sink, using a step function. |
| [step](#step-src-snk) (src, snk)          | Pump one chunk from the source to the sink.                   |

## Functions

### all (src, snk, step)

Pump all data from a source to a sink, using a step function.

**Parameters**

- src: LTN12 source
- snk: LTN12 sink
- step: step function (optional)

**Return values:**

+ 1 if the operation succeeded otherwise nil
+ Error object

---
### step (src, snk)

Pump one chunk from the source to the sink.

**Parameters**

- src: LTN12 source
- snk: LTN12 sink

**Return values:**

+ Chunk of data or nil if an error occured
+ Error object
