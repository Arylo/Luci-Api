# Object Instance `luci.json`

LuCI JSON-Library

## Functions

|                                                                                 |                                                                           |
| -                                                                               | -                                                                         |
| [ActiveDecoder](#activedecoder-customnull) (customnull)                         | Create a new Active JSON-Decoder.                                         |
| [ActiveDecoder:get](#activedecoderget) ()                                       | Fetches one JSON-object from given source                                 |
| [Decoder](#decoder-customnull) (customnull)                                     | Create a new JSON-Decoder.                                                |
| [Decoder:get](#decoderget) ()                                                   | Get the decoded data packets after the rawdata has been sent to the sink. |
| [Decoder:sink](#decodersink) ()                                                 | Create an LTN12 sink from the decoder object which accepts the JSON-Data. |
| [Encoder](#encoder-data-buffersize-fastescape) (data, buffersize, fastescape) | Create a new JSON-Encoder.                                                |
| [Encoder:source](#encodersource) ()                                             | Create an LTN12 source providing the encoded JSON-Data.                   |
| [decode](#decode-json) (json)                                                   | Directly decode a JSON string                                             |
| [encode](#encode-obj) (obj)                                                     | Direcly encode a Lua object into a JSON string.                           |
| [null](#null) ()                                                                | Null replacement function                                                 |

## Functions

### ActiveDecoder (customnull)

Create a new Active JSON-Decoder.

**Parameters**

- customnull: Use luci.json.null instead of nil for decoding null

**Return value:**

Active JSON-Decoder

---
### ActiveDecoder:get ()

Fetches one JSON-object from given source

**Return value:**

Decoded object

---
### Decoder (customnull)

Create a new JSON-Decoder.

**Parameters**

- customnull: Use luci.json.null instead of nil for decoding null

**Return value:**

JSON-Decoder

---
### Decoder:get ()

Get the decoded data packets after the rawdata has been sent to the sink.

**Return value:**

Decoded data

---
### Decoder:sink ()

Create an LTN12 sink from the decoder object which accepts the JSON-Data.

**Return value:**

LTN12 sink

---
### Encoder (data, buffersize, fastescape)

Create a new JSON-Encoder.

**Parameters**

- data: Lua-Object to be encoded.
- buffersize: Blocksize of returned data source.
- fastescape: Use non-standard escaping (don't escape control chars)

**Return value:**

JSON-Encoder

---
### Encoder:source ()

Create an LTN12 source providing the encoded JSON-Data.

**Return value:**

LTN12 source

---
### decode (json)

Directly decode a JSON string

**Parameters**

- json: JSON-String

**Return value:**

Lua object

---
### encode (obj)

Direcly encode a Lua object into a JSON string.

**Parameters**

- obj: Lua Object

**Return value:**

JSON string

---
### null ()

Null replacement function

**Return value:**

null
