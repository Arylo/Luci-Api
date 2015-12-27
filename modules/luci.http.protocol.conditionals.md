# Class `luci.http.protocol.conditionals`

LuCI http protocol implementation - HTTP/1.1 bits. This class provides basic ETag handling and implements most of the conditional HTTP/1.1 headers specified in RFC2616 Sct. 14.24 - 14.28 .

## Functions

|                                                                  |                                                                                                                                                          |
| -                                                                | -                                                                                                                                                        |
| [if_match](#if_match-req-stat) (req, stat)                       | 14.24 / If-Match Test whether the given message object contains an "If-Match" header and compare it against the given stat object.                       |
| [if_modified_since](#if_modified_since-req-stat) (req, stat)     | 14.25 / If-Modified-Since Test whether the given message object contains an "If-Modified-Since" header and compare it against the given stat object.     |
| [if_none_match](#if_none_match-req-stat) (req, stat)             | 14.26 / If-None-Match Test whether the given message object contains an "If-None-Match" header and compare it against the given stat object.             |
| [if_range](#if_range-req-stat) (req, stat)                       | 14.27 / If-Range The If-Range header is currently not implemented due to the lack of general byte range stuff in luci.http.protocol .                    |
| [if_unmodified_since](#if_unmodified_since-req-stat) (req, stat) | 14.28 / If-Unmodified-Since Test whether the given message object contains an "If-Unmodified-Since" header and compare it against the given stat object. |
| [mk_etag](#mk_etag-stat) (stat)                                  | Implement 14.19 / ETag.                                                                                                                                  |

## Functions

### if_match (req, stat)

14.24 / If-Match Test whether the given message object contains an "If-Match" header and compare it against the given stat object.

**Parameters**

- req: HTTP request message object
- stat: A file.stat object

**Return values:**

+ Boolean indicating whether the precondition is ok
+ Alternative status code if the precondition failed

---
### if_modified_since (req, stat)

14.25 / If-Modified-Since Test whether the given message object contains an "If-Modified-Since" header and compare it against the given stat object.

**Parameters**

- req: HTTP request message object
- stat: A file.stat object

**Return values:**

+ Boolean indicating whether the precondition is ok
+ Alternative status code if the precondition failed
+ Table containing extra HTTP headers if the precondition failed

---
### if_none_match (req, stat)

14.26 / If-None-Match Test whether the given message object contains an "If-None-Match" header and compare it against the given stat object.

**Parameters**

- req: HTTP request message object
- stat: A file.stat object

**Return values:**

+ Boolean indicating whether the precondition is ok
+ Alternative status code if the precondition failed
+ Table containing extra HTTP headers if the precondition failed

---
### if_range (req, stat)

14.27 / If-Range The If-Range header is currently not implemented due to the lack of general byte range stuff in luci.http.protocol . This function will always return false, 412 to indicate a failed precondition.

**Parameters**

- req: HTTP request message object
- stat: A file.stat object

**Return values:**

+ Boolean indicating whether the precondition is ok
+ Alternative status code if the precondition failed

---
### if_unmodified_since (req, stat)

14.28 / If-Unmodified-Since Test whether the given message object contains an "If-Unmodified-Since" header and compare it against the given stat object.

**Parameters**

- req: HTTP request message object
- stat: A file.stat object

**Return values:**

+ Boolean indicating whether the precondition is ok
+ Alternative status code if the precondition failed

---
### mk_etag (stat)

Implement 14.19 / ETag.

**Parameters**

- stat: A file.stat structure

**Return value:**

String containing the generated tag suitable for ETag headers
