# File System

* File system allows to access both data and programs of operating system. File system hides the physical aspects of storage device and defines a logical storage unit, the files.
* A file system manily have two parts,
  1. File: for storing related data.
  2. Directory: which orgnizes and provides information about files.
 
### 1. File 
*  A file is a named collection of related information that is recordeed  on secondary storage(the inforamtion in file is defined by its creator).
*  **File Attributes:** A file is named only for the convience of human users.
  1. Name
  2. Indetifier: a unique tag, used to identify the file in file system; it is the name given by file system.
  3. Type: This defines the use of data stored in files.
  4. Location: This information is a pointer to the exact physical, logical, or network address of the file on a storage device.
  5. Size
  6. Protection: Access control for the different user.
  7. Timestamp: may be used for creation date, last modified, last use.
* Some file system supporst many other attirbutes such as file checksum, character encoding.
* **File Operation**
  1. Creating a file
  2. Opening a file
  3. Writing a file
  4. Reading a file
  5. Deleting a file
  6. REpositiong within a file
  7. Truncating a file: erase the content of file but keep its attributes.
 
Most of the file operation involve searching the directory for the entry associated with the named file,  to avoid ths many system opens the file, the OS keeps a table, called _open-file table_, containing nformation about all open files. When a file operation is requested the file is specified via an index into this table, so no searching is required. When the file is no longer being acivly used it is closed by the process and OS remove its entry from the table potentially releasing the locks(For delete and wirte).

<div></div>

File Types: A common technique for implementing file types is to include the type as part of the file name. The name is split into two parts — a name and an extension.

### 2. Director
* This stores the inforamtion about files kept in the director, typically a director entry consists of the file's name and its unique identifier.
