# Class `luci.fs`

LuCI filesystem library.

## Functions

|                                                           |                                                                                                             |
| -                                                         | -                                                                                                           |
| [access](#access-str) (str)                               | Test for file access permission on given path.                                                              |
| [basename](#basename-path) (path)                         | Return the last element - usually the filename - from the given path with the directory component stripped. |
| [chmod](#chmod-path-perm) (path, perm)                    | Set permissions on given file or directory.                                                                 |
| [dir](#dir-path) (path)                                   | Return a table containing all entries of the specified directory.                                           |
| [dirname](#dirname-path) (path)                           | Return the directory component of the given path with the last element stripped of.                         |
| [glob](#glob-filename) (filename)                         | Evaluate given shell glob pattern and return a table containing all matching file and directory entries.    |
| [isdirectory](#isdirectory-dirname) (dirname)             | Checks wheather the given path exists and points to a directory.                                            |
| [isfile](#isfile-filename) (filename)                     | Checks wheather the given path exists and points to a regular file.                                         |
| [link](#link-path1-path2-symlink) (path1, path2, symlink) | Create a hard- or symlink from given file (or directory) to specified target file (or directory) path.      |
| [mkdir](#mkdir-path-recursive) (path, recursive)          | Create a new directory, recursively on demand.                                                              |
| [mtime](#mtime-path) (path)                               | Get the last modification time of given file path in Unix epoch format.                                     |
| [readlink](#readlink-path) (path)                         | Retrieve target of given symlink.                                                                           |
| [rmdir](#rmdir-path) (path)                               | Remove the given empty directory.                                                                           |
| [stat](#stat-path) (path)                                 | Get information about given file or directory.                                                              |
| [unlink](#unlink-path) (path)                             | Remove the given file.                                                                                      |
| [utime](#utime-path-mtime-atime) (path, mtime, atime)     | Set the last modification time  of given file path in Unix epoch format.                                    |

## Functions

### access (str)

Test for file access permission on given path.

**Parameters**

- str: String value containing the path

**Return values:**

+ Number containing the return code, 0 on sucess or nil on error
+ String containing the error description (if any)
+ Number containing the os specific errno (if any)

---
### basename (path)

Return the last element - usually the filename - from the given path with the directory component stripped.

**Parameters**

- path: String containing the path to strip

**Return value:**

String containing the base name of given path

**See also:**

- [dirname](#dirname-path)

---
### chmod (path, perm)

Set permissions on given file or directory.

**Parameters**

- path: String containing the path of the directory
- perm: String containing the permissions to set ([ugoa][+-][rwx])

**Return values:**

+ Number with the return code, 0 on sucess or nil on error
+ String containing the error description on error
+ Number containing the os specific errno on error

---
### dir (path)

Return a table containing all entries of the specified directory.

**Parameters**

- path: String containing the path of the directory to scan

**Return values:**

+ Table containing file and directory entries or nil on error
+ String containing the error description on error
+ Number containing the os specific errno on error

---
### dirname (path)

Return the directory component of the given path with the last element stripped of.

**Parameters**

- path: String containing the path to strip

**Return value:**

String containing the directory component of given path

**See also:**

- [basename](#basename-path)

---
### glob (filename)

Evaluate given shell glob pattern and return a table containing all matching file and directory entries.

**Parameters**

- filename: String containing the path of the file to read

**Return values:**

+ Table containing file and directory entries or nil if no matches
+ String containing the error description (if no matches)
+ Number containing the os specific errno (if no matches)

---
### isdirectory (dirname)

Checks wheather the given path exists and points to a directory.

**Parameters**

- dirname: String containing the path of the directory to test

**Return value:**

Boolean indicating wheather given path points to directory

---
### isfile (filename)

Checks wheather the given path exists and points to a regular file.

**Parameters**

- filename: String containing the path of the file to test

**Return value:**

Boolean indicating wheather given path points to regular file

---
### link (path1, path2, symlink)

Create a hard- or symlink from given file (or directory) to specified target file (or directory) path.

**Parameters**

- path1: String containing the source path to link
- path2: String containing the destination path for the link
- symlink: Boolean indicating wheather to create a symlink (optional)

**Return values:**

+ Number with the return code, 0 on sucess or nil on error
+ String containing the error description on error
+ Number containing the os specific errno on error

---
### mkdir (path, recursive)

Create a new directory, recursively on demand.

**Parameters**

- path: String with the name or path of the directory to create
- recursive: Create multiple directory levels (optional, default is true)

**Return values:**

+ Number with the return code, 0 on sucess or nil on error
+ String containing the error description on error
+ Number containing the os specific errno on error

---
### mtime (path)

Get the last modification time of given file path in Unix epoch format.

**Parameters**

- path: String containing the path of the file or directory to read

**Return values:**

+ Number containing the epoch time or nil on error
+ String containing the error description (if any)
+ Number containing the os specific errno (if any)

---
### readlink (path)

Retrieve target of given symlink.

**Parameters**

- path: String containing the path of the symlink to read

**Return values:**

+ String containing the link target or nil on error
+ String containing the error description on error
+ Number containing the os specific errno on error

---
### rmdir (path)

Remove the given empty directory.

**Parameters**

- path: String containing the path of the directory to remove

**Return values:**

+ Number with the return code, 0 on sucess or nil on error
+ String containing the error description on error
+ Number containing the os specific errno on error

---
### stat (path)

Get information about given file or directory.

**Parameters**

- path: String containing the path of the directory to query

**Return values:**

+ Table containing file or directory properties or nil on error
+ String containing the error description on error
+ Number containing the os specific errno on error

---
### unlink (path)

Remove the given file.

**Parameters**

- path: String containing the path of the file to remove

**Return values:**

+ Number with the return code, 0 on sucess or nil on error
+ String containing the error description on error
+ Number containing the os specific errno on error

---
### utime (path, mtime, atime)

Set the last modification time  of given file path in Unix epoch format.

**Parameters**

- path: String containing the path of the file or directory to read
- mtime: Last modification timestamp
- atime: Last accessed timestamp

**Return values:**

+ 0 in case of success nil on error
+ String containing the error description (if any)
+ Number containing the os specific errno (if any)
