# Class `luci.http.protocol`

LuCI http protocol class. This class contains several functions useful for http message- and content decoding and to retrive form data from raw http messages.

## Functions

|                                                                                       |                                                                                                                                                                         |
| -                                                                                     | -                                                                                                                                                                       |
| [header_source](#header_source-sock) (sock)                                           | Creates a ltn12 source from the given socket.                                                                                                                           |
| [mimedecode_message_body](#mimedecode_message_body-src-msg-filecb) (src, msg, filecb) | Decode a mime encoded http message body with multipart/form-data Content-Type.                                                                                          |
| [parse_message_body](#parse_message_body-src-msg-filecb) (src, msg, filecb)           | Try to extract and decode a http message body from the given ltn12 source.                                                                                              |
| [parse_message_header](#parse_message_header-src) (src)                               | Try to extract an http message header including information like protocol version, message headers and resulting CGI environment variables from the given ltn12 source. |
| [urldecode](#urldecode-str-no_plus) (str, no_plus)                                    | Decode an urlencoded string - optionally without decoding the "+" sign to " " - and return the decoded string.                                                          |
| [urldecode_message_body](#urldecode_message_body-src-msg) (src, msg)                  | Decode an urlencoded http message body with application/x-www-urlencoded Content-Type.                                                                                  |
| [urldecode_params](#urldecode_params-url-tbl) (url, tbl)                              | Extract and split urlencoded data pairs, separated bei either "&" or ";" from given url or string.                                                                      |
| [urlencode](#urlencode-str) (str)                                                     | Encode given string to x-www-urlencoded format.                                                                                                                         |
| [urlencode_params](#urlencode_params-tbl) (tbl)                                       | Encode each key-value-pair in given table to x-www-urlencoded format, separated by "&".                                                                                 |

## Functions

### header_source (sock)

Creates a ltn12 source from the given socket. The source will return it's data line by line with the trailing \r\n stripped of.

**Parameters**

- sock: Readable network socket

**Return value:**

Ltn12 source function

---
### mimedecode_message_body (src, msg, filecb)

Decode a mime encoded http message body with multipart/form-data Content-Type. Stores all extracted data associated with its parameter name in the params table withing the given message object. Multiple parameter values are stored as tables, ordinary ones as strings. If an optional file callback function is given then it is feeded with the file contents chunk by chunk and only the extracted file name is stored within the params table. The callback function will be called subsequently with three arguments: o Table containing decoded (name, file) and raw (headers) mime header data o String value containing a chunk of the file data o Boolean which indicates wheather the current chunk is the last one (eof)

**Parameters**

- src: Ltn12 source function
- msg: HTTP message object
- filecb: File callback function (optional)

**Return values:**

+ Value indicating successful operation (not nil means "ok")
+ String containing the error if unsuccessful

**See also:**

- [parse_message_header](#parse_message_header-src)

---
### parse_message_body (src, msg, filecb)

Try to extract and decode a http message body from the given ltn12 source. This function will examine the Content-Type within the given message object to select the appropriate content decoder. Currently the application/x-www-urlencoded and application/form-data mime types are supported. If the encountered content encoding can't be handled then the whole message body will be stored unaltered as "content" property within the given message object.

**Parameters**

- src: Ltn12 source function
- msg: HTTP message object
- filecb: File data callback (optional, see mimedecode_message_body())

**Return values:**

+ Value indicating successful operation (not nil means "ok")
+ String containing the error if unsuccessful

**See also:**

- [parse_message_header](#parse_message_header-src)

---
### parse_message_header (src)

Try to extract an http message header including information like protocol version, message headers and resulting CGI environment variables from the given ltn12 source.

**Parameters**

- src: Ltn12 source function

**Return value:**

HTTP message object

**See also:**

- [parse_message_body](#parse_message_body-src-msg-filecb)

---
### urldecode (str, no_plus)

Decode an urlencoded string - optionally without decoding the "+" sign to " " - and return the decoded string.

**Parameters**

- str: Input string in x-www-urlencoded format
- no_plus: Don't decode "+" signs to spaces

**Return value:**

The decoded string

**See also:**

- [urlencode](#urldecode-str-no_plus)

---
### urldecode_message_body (src, msg)

Decode an urlencoded http message body with application/x-www-urlencoded Content-Type. Stores all extracted data associated with its parameter name in the params table withing the given message object. Multiple parameter values are stored as tables, ordinary ones as strings.

**Parameters**

- src: Ltn12 source function
- msg: HTTP message object

**Return values:**

+ Value indicating successful operation (not nil means "ok")
+ String containing the error if unsuccessful

**See also:**

- [parse_message_header](#parse_message_header-src)

---
### urldecode_params (url, tbl)

Extract and split urlencoded data pairs, separated bei either "&" or ";" from given url or string. Returns a table with urldecoded values. Simple parameters are stored as string values associated with the parameter name within the table. Parameters with multiple values are stored as array containing the corresponding values.

**Parameters**

- url: The url or string which contains x-www-urlencoded form data
- tbl: Use the given table for storing values (optional)

**Return value:**

Table containing the urldecoded parameters

**See also:**

- [urlencode_params](#urlencode_params-tbl)

---
### urlencode (str)

Encode given string to x-www-urlencoded format.

**Parameters**

- str: String to encode

**Return value:**

String containing the encoded data

**See also:**

- [urldecode](#urldecode-str-no_plus)

---
### urlencode_params (tbl)

Encode each key-value-pair in given table to x-www-urlencoded format, separated by "&". Tables are encoded as parameters with multiple values by repeating the parameter name with each value.

**Parameters**

- tbl: Table with the values

**Return value:**

String containing encoded values

**See also:**

- [urldecode_params](#urldecode_params-url-tbl)
