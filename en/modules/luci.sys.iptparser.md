# Object Instance `luci.sys.iptparser`

LuCI iptables parser and query library

## Functions

|||
|-|-|
|[IptParser](#iptparser-family) (family)|Create a new iptables parser object.|
|[IptParser:chain](#iptparserchain-table-chain) (table, chain) |Return the given firewall chain within the given table name.|
|[IptParser:chains](#iptparserchains-table) (table) |Find the names of all chains within the given table name.|
|[IptParser:find](#iptparserfind) () |Find all firewall rules that match the given criteria.|
|[IptParser:is_custom_target](#iptparseris_custom_target-target) (target) |Test whether the given target points to a custom chain.|
|[IptParser:resync](#iptparserresync) () |Rebuild the internal lookup table, for example when rules have changed through external commands.|
|[IptParser:tables](#iptparsertables) () |Find the names of all tables.|

## Functions

### IptParser (family)

Create a new iptables parser object.

**Parameters**

- family: Number specifying the address family. 4 for IPv4, 6 for IPv6

**Return value:**

IptParser instance

---
### IptParser:chain (table, chain)

Return the given firewall chain within the given table name.

**Parameters**

- table: String containing the table name
- chain: String containing the chain name

**Return value:**

Table containing the fields "policy", "packets", "bytes" and "rules". The "rules" field is a table of rule tables.

---
### IptParser:chains (table)

Find the names of all chains within the given table name.

**Parameters**

- table: String containing the table name

**Return value:**

Table of chain names in the order they occur.

---
### IptParser:find ()

Find all firewall rules that match the given criteria. Expects a table with search criteria as only argument. If args is nil or an empty table then all rules will be returned.  The following keys in the args table are recognized: 

- table		 - Match rules that are located within the given table 
- chain		 - Match rules that are located within the given chain 
- target		 - Match rules with the given target 
- protocol	 - Match rules that match the given protocol, rules with protocol "all" are always matched 
- source		 - Match rules with the given source, rules with source "0.0.0.0/0" (::/0) are always matched 
- destination - Match rules with the given destination, rules with destination "0.0.0.0/0" (::/0) are always matched 
- inputif	 - Match rules with the given input interface, rules with input	interface "*" (=all) are always matched 
- outputif	 - Match rules with the given output interface, rules with output	interface "*" (=all) are always matched 
- flags		 - Match rules that match the given flags, current supported values are "-f" (--fragment) and "!f" (! --fragment) 
- options	 - Match rules containing all given options 

The return value is a list of tables representing the matched rules. Each rule table contains the following fields:

- index		 - The index number of the rule 
- table		 - The table where the rule is located, can be one of "filter", "nat" or "mangle" 
- chain		 - The chain where the rule is located, e.g. "INPUT" or "postrouting_wan" 
- target		 - The rule target, e.g. "REJECT" or "DROP" 
- protocol		The matching protocols, e.g. "all" or "tcp" 
- flags		 - Special rule options ("--", "-f" or "!f") 
- inputif	 - Input interface of the rule, e.g. "eth0.0" or "*" for all interfaces 
- outputif	 - Output interface of the rule,e.g. "eth0.0" or "*" for all interfaces 
- source		 - The source ip range, e.g. "0.0.0.0/0" (::/0) 
- destination - The destination ip range, e.g. "0.0.0.0/0" (::/0) 
- options	 - A list of specific options of the rule, e.g. { "reject-with", "tcp-reset" } 
- packets	 - The number of packets matched by the rule 
- bytes		 - The number of total bytes matched by the rule 

Example: 

`ip = luci.sys.iptparser.IptParser() result = ip.find( { target="REJECT", protocol="tcp", options={ "reject-with", "tcp-reset" } } )`

This will match all rules with target "-j REJECT", protocol "-p tcp" (or "-p all") and the option "--reject-with tcp-reset".

**Return value:**

Table of matching rule tables

---
### IptParser:is_custom_target (target)

Test whether the given target points to a custom chain.

**Parameters**

- target: String containing the target action

**Return value:**

Boolean indicating whether target is a custom chain.

---
### IptParser:resync ()

Rebuild the internal lookup table, for example when rules have changed through external commands.

**Return value:**

nothing

---
### IptParser:tables ()

Find the names of all tables.

**Return value:**

Table of table names.
