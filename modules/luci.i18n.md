# Class `luci.i18n`

LuCI translation library.

## Functions

|                                                   |                                                                                                                      |
| -                                                 | -                                                                                                                    |
| [clear](#clear) ()                                | Clear the translation table.                                                                                         |
| [load](#load-file-lang-force) (file, lang, force) | Load a translation and copy its data into the translation table.                                                     |
| [loadc](#loadc-file-force) (file, force)          | Load a translation file using the default translation language.                                                      |
| [setlanguage](#setlanguage-lang) (lang)           | Set the context default translation language.                                                                        |
| [string](#string-key) (key)                       | Return the translated value for a specific translation key and ensure that the returned value is a Lua string value. |
| [stringf](#stringf-key) (key, ...)                | Return the translated value for a specific translation key and use it as sprintf pattern.                            |
| [translate](#translate-key) (key)                 | Return the translated value for a specific translation key.                                                          |
| [translatef](#translatef-key) (key, ...)          | Return the translated value for a specific translation key and use it as sprintf pattern.                            |

## Functions

### clear ()

Clear the translation table.

---
### load (file, lang, force)

Load a translation and copy its data into the translation table.

**Parameters**

- file: Language file
- lang: Two-letter language code
- force: Force reload even if already loaded (optional)

**Return value:**

Success status

---
### loadc (file, force)

Load a translation file using the default translation language. Alternatively load the translation of the fallback language.

**Parameters**

- file: Language file
- force: Force reload even if already loaded (optional)

---
### setlanguage (lang)

Set the context default translation language.

**Parameters**

- lang: Two-letter language code

---
### string (key)

Return the translated value for a specific translation key and ensure that the returned value is a Lua string value. This is the same as calling `tostring(translate(...))`

**Parameters**

- key: Default translation text

**Return value:**

Translated string

---
### stringf (key, ...)

Return the translated value for a specific translation key and use it as sprintf pattern. Ensure that the returned value is a Lua string value. This is the same as calling `tostring(translatef(...))`

**Parameters**

- key: Default translation text
- ...: Format parameters

**Return value:**

Translated and formatted string

---
### translate (key)

Return the translated value for a specific translation key.

**Parameters**

- key: Default translation text

**Return value:**

Translated string

---
### translatef (key, ...)

Return the translated value for a specific translation key and use it as sprintf pattern.

**Parameters**

- key: Default translation text
- ...: Format parameters

**Return value:**

Translated and formatted string
