# Class `luci.http.protocol.mime`

LuCI http protocol implementation - mime helper class. This class provides functions to guess mime types from file extensions and vice versa.

## Functions

|                                         |                                                                                                                                 |
| -                                       | -                                                                                                                               |
| [to_ext](#to_ext-mimetype) (mimetype)   | Return corresponding extension for a given mime type or nil if the given mime-type is unknown.                                  |
| [to_mime](#to_mime-filename) (filename) | Extract extension from a filename and return corresponding mime-type or "application/octet-stream" if the extension is unknown. |

## Tables

|            |                                                             |
| -          | -                                                           |
| MIME_TYPES | MIME mapping table containg extension - mimetype relations. |

## Functions

### to_ext (mimetype)

Return corresponding extension for a given mime type or nil if the given mime-type is unknown.

**Parameters**

- mimetype: The mimetype to retrieve the extension from

**Return value:**

String with the extension or nil for unknown type

---
### to_mime (filename)

Extract extension from a filename and return corresponding mime-type or "application/octet-stream" if the extension is unknown.

**Parameters**

- filename: The filename for which the mime type is guessed

**Return value:**

String containign the determined mime type

## Tables

### MIME_TYPES

MIME mapping table containg extension - mimetype relations.
