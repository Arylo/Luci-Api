# Class `luci.http.protocol.date`

LuCI http protocol implementation - date helper class. This class contains functions to parse, compare and format http dates.

## Functions

|                                    |                                                                              |
| -                                  | -                                                                            |
| [compare](#compare-d1-d2) (d1, d2) | Compare two dates which can either be unix epoch times or HTTP date strings. |
| [to_http](#to_http-time) (time)    | Convert the given unix epoch time to valid HTTP date string.                 |
| [to_unix](#to_unix-data) (data)    | Parse given HTTP date string and convert it to unix epoch time.              |
| [tz_offset](#tz_offset-tz) (tz)    | Return the time offset in seconds between the UTC and given time zone.       |

## Functions

### compare (d1, d2)

Compare two dates which can either be unix epoch times or HTTP date strings.

**Parameters**

- d1: The first date or epoch time to compare
- d2: The first date or epoch time to compare

**Return values:**

+ -1  -  if d1 is lower then d2
+ 0   -  if both dates are equal
+ 1   -  if d1 is higher then d2

---
### to_http (time)

Convert the given unix epoch time to valid HTTP date string.

**Parameters**

- time: Unix epoch time

**Return value:**

String containing the formatted date

---
### to_unix (data)

Parse given HTTP date string and convert it to unix epoch time.

**Parameters**

- data: String containing the date

**Return value:**

Unix epoch time

---
### tz_offset (tz)

Return the time offset in seconds between the UTC and given time zone.

**Parameters**

- tz: Symbolic or numeric timezone specifier

**Return value:**

Time offset to UTC in seconds
