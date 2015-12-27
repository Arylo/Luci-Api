# Class `luci.ltn12.filter`

LTN12 Filter constructors

## Functions

|                                                 |                                                                                                                          |
| -                                               | -                                                                                                                        |
| [chain](#chain) (...)                           | Chain a bunch of filters together.                                                                                       |
| [cycle](#cycle-low-ctx-extra) (low, ctx, extra) | Return a high level filter that cycles a low-level filter by passing it each chunk and updating a context between calls. |

## Functions

### chain (...)

Chain a bunch of filters together. (thanks to Wim Couwenberg)

**Parameters**

- ...: filters to be chained

**Return value:**

LTN12 filter

---
### cycle (low, ctx, extra)

Return a high level filter that cycles a low-level filter by passing it each chunk and updating a context between calls.

**Parameters**

- low: Low-level filter
- ctx: Context
- extra: Extra argument passed to the low-level filter

**Return value:**

LTN12 filter
