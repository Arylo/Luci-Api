# Class luci.asterisk

## Functions

|                                                         |                                                                             |
| -                                                       | -                                                                           |
| [cbifill](#cbifill-field) (field)                       | Populate given CBI field with CC codes.                                     |
| [cc](#cc-country) (country)                             | Lookup the CC code(s) for the given country.                                |
| [country](#country-country) (country)                   | Lookup the country name for the given CC code.                              |
| [idd](#idd-cc) (cc)                                     | Lookup the international dialing code for the given CC code.                |
| [version](#version) ()                                  | Retrive version string.                                                     |
| [parse](#parse-plan) (plan)                             | Parse a dialplan section                                                    |
| [plan](#plan-name) (name)                               | Get a specific dial plan                                                    |
| [plans](#plans) ()                                      | Get a list of known dial plans                                              |
| [parse](#parse-zone) (zone)                             | Parse a dialzone section                                                    |
| [ucisection](#ucisection-idx) (idx)                     | Find uci section hash for given zone number                                 |
| [zone](#zone-name) (name)                               | Get a specific dial zone                                                    |
| [zones](#zones) ()                                      | Get a list of known dial zones                                              |
| [cbifill](#cbifill-field) (field)                       | Populate given CBI field with IDD codes.                                    |
| [cc](#cc-country) (country)                             | Lookup the country code for the given IDD code.                             |
| [country](#country-country) (country)                   | Lookup the country name for the given IDD code.                             |
| [idd](#idd-idd) (idd)                                   | Lookup the IDD code(s) for the given country.                               |
| [exec](#exec-command) (command)                         | Execute command and return output                                           |
| [execi](#execi-command) (command)                       | Execute command and return an iterator that returns one line per invokation |
| [execl](#execl-command-callback) (command, callback)    | Execute command and invoke given callback for each readed line              |
| [in_dialplan](#in_dialplan-plan) (plan)                 | Find all meetme rooms within the given dialplan                             |
| [parse](#parse-room) (room)                             | Parse a meetme section                                                      |
| [remove](#remove-room-ctx) (room, ctx)                  | Remove meetme room and associated extensions from config                    |
| [room](#room-number) (number)                           | Get a specific meetme room                                                  |
| [rooms](#rooms) ()                                      | Get a list of known meetme rooms                                            |
| [peer](#peer-peer) (peer)                               | Get informations of given SIP peer                                          |
| [peers](#peers) ()                                      | Get a list of known SIP peers                                               |
| [hyperlinks](#hyperlinks-list-url-sep) (list, url, sep) | Convert given list to a collection of hyperlinks                            |
| [parse_list](#parse_list-val) (val)                     | Convert given value to a list of tokens.                                    |
| [uci_resync](#uci_resync-) ()                           | LuCI Asterisk - Resync uci context                                          |
| [box](#box-number) (number)                             | Get a specific voicemailbox                                                 |
| [boxes](#boxes) ()                                      | Get a list of known voicemail boxes                                         |
| [in_dialplan](#in_dialplan-plan) (plan)                 | Find all voicemailboxes within the given dialplan                           |
| [parse](#parse-zone) (zone)                             | Parse a voicemail section                                                   |
| [remove](#remove-box-ctx) (box, ctx)                    | Remove voicemailbox and associated extensions from config                   |


## Functions

### cbifill (field)
Populate given CBI field with CC codes.

**Parameters**

- field: CBI option object

**Return value:**

(nothing)

---
### cc (country)
Lookup the CC code(s) for the given country.

**Parameters**

- country: String containing the country name

**Return value:**

Table containing the CC code(s)

---
### country (country)
Lookup the country name for the given CC code.

**Parameters**

- country: String containing CC code

**Return value:**

String containing the country name

---
### idd (cc)
Lookup the international dialing code for the given CC code.

**Parameters**

- cc: String containing CC code

**Return value:**

String containing IDD code

---
### version ()
Retrive version string.

**Return value:**

String containing the reported asterisk version

---
### parse (plan)
Parse a dialplan section

**Parameters**

- plan: Table containing the plan info

**Return value:**

Table with parsed information

---
### plan (name)
Get a specific dial plan

**Parameters**

- name: Name of the dial plan

**Return value:**

Table containing plan information

---
### plans ()
Get a list of known dial plans

**Return value:**

Associative table of plans and table of plan names

---
### parse (zone)
Parse a dialzone section

**Parameters**

- zone: Table containing the zone info

**Return value:**

Table with parsed information

---
### ucisection (idx)
Find uci section hash for given zone number

**Parameters**

- idx: Zone number

**Return value:**

String containing the uci hash pointing to the section

---
### zone (name)
Get a specific dial zone

**Parameters**

- name: Name of the dial zone

**Return value:**

Table containing zone information

---
### zones ()
Get a list of known dial zones

**Return value:**

Associative table of zones and table of zone names

---
### cbifill (field)
Populate given CBI field with IDD codes.

**Parameters**

- field: CBI option object

**Return value:**

(nothing)

---
### cc (country)
Lookup the country code for the given IDD code.

**Parameters**

- country: String containing IDD code

**Return value:**

Table containing the country code(s)

---
### country (country)
Lookup the country name for the given IDD code.

**Parameters**

- country: String containing IDD code

**Return value:**

String containing the country name

---
### idd (idd)
Lookup the IDD code(s) for the given country.

**Parameters**

- idd: String containing the country name

**Return value:**

Table containing the IDD code(s)

---
### exec (command)
Execute command and return output

**Parameters**

- command: String containing the command to execute

**Return value:**

String containing the command output

---
### execi (command)
Execute command and return an iterator that returns one line per invokation

**Parameters**

- command: String containing the command to execute

**Return value:**

Iterator function

---
### execl (command, callback)
Execute command and invoke given callback for each readed line

**Parameters**

- command: String containing the command to execute
- callback: Function to call back for each line

**Return value:**

Always true

---
### in_dialplan (plan)
Find all meetme rooms within the given dialplan

**Parameters**

- plan: Dialplan name or table

**Return value:**

Associative table containing extensions mapped to room info

---
### parse (room)
Parse a meetme section

**Parameters**

- room: Table containing the room info

**Return value:**

Table with parsed information

---
### remove (room, ctx)
Remove meetme room and associated extensions from config

**Parameters**

- room: Voicemailbox number or table
- ctx: UCI context to use (optional)

**Return value:**

Boolean indicating success

---
### room (number)
Get a specific meetme room

**Parameters**

- number: Number of the room

**Return value:**

Table containing room information

---
### rooms ()
Get a list of known meetme rooms

**Return value:**

Associative table of rooms and table of room numbers

---
### peer (peer)
Get informations of given SIP peer

**Parameters**

- peer: String containing the name of the SIP peer

---
### peers ()
Get a list of known SIP peers

**Return value:**

Table containing each SIP peer

---
### hyperlinks (list, url, sep)
Convert given list to a collection of hyperlinks

**Parameters**

- list: Table of tokens
- url: String pattern or callback function to construct urls (optional)
- sep: String containing the seperator (optional, default is ", ")

**Return value:**

String containing the html fragment

---
### parse_list (val)
Convert given value to a list of tokens. Split by white space.

**Parameters**

- val: String or table value

**Return value:**

Table containing tokens

---
### uci_resync ()
LuCI Asterisk - Resync uci context

---
### box (number)
Get a specific voicemailbox

**Parameters**

- number: Number of the voicemailbox

**Return value:**

Table containing mailbox information

---
### boxes ()
Get a list of known voicemail boxes

**Return value:**

Associative table of boxes and table of box numbers

---
### in_dialplan (plan)
Find all voicemailboxes within the given dialplan

**Parameters**

- plan: Dialplan name or table

**Return value:**

Associative table containing extensions mapped to mailbox info

---
### parse (zone)
Parse a voicemail section

**Parameters**

- zone: Table containing the mailbox info

**Return value:**

Table with parsed information

---
### remove (box, ctx)
Remove voicemailbox and associated extensions from config

**Parameters**

- box: Voicemailbox number or table
- ctx: UCI context to use (optional)

**Return value:**

Boolean indicating success
