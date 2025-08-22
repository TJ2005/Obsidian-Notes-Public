---
Title: "File Management"
Status: 
marker: 
tags: 
Date: "2025.05.09"
Time: "15:28"
---
# File Management
the file system is the most visible aspect of a general-purpose operating system
It provides a mechanism for accessing the data to the end user. 
It has two distinct parts
- Storing the files that are related together
- Directory

Most file Systems live on storage devices

## File Concept
The operating system abstracts from the physical properties of its storage devices to define a logical storage unit, the fil.??
Files are mapped by the operating system onto physical devices.

These are usually
- Non Volatile
- Rebooting keeps data persistent.

A file can be called a collection of related information that's stored on secondary storage.
From a dumb users perspective the smallest unit should be a file.
So a file is needed to read or write data to secondary storage. It can be in any form that the user defines it to be in. Thus we have multiple file extensions.

Data files may be numeric, alphabetic, alphanumeric, or binary. Files may be free form, such as text files, or may be formatted rigidly. In general, a file is a sequence of bits, bytes, lines, or records, the meaning of which is defined by the file’s creator and user

 Because files have been the way to store the data for the user and the applications its meaning has been twisted and it has been doing so much more than its general purpose.

Unix and Linux provide a proc File Systems now.

The type of information stored in a file can be defined by its creator. For example xlsx only stores data in tabular form.
There can be many types of information stored in the file.
- text data
- photo
- video
- music
- etc

A **Text File** is a sequence of characters organized into lines or pages possibly. Whereas a **source file** is a file that stores functions each of which are organized as per the syntax with declarations. Where as executable can be code that can be loaded on and readily be executed.

## File Attributes
A **file** is a named collection of related information stored on secondary storage. It is referred to by its **name**, typically a string like `example.c`. Some systems are case-sensitive in naming (`File.txt` ≠ `file.txt`), while others are not. Once named, a file becomes independent of the process, user, or system that created it. For example, a user may create `example.c`, another may edit it, and it may be copied or shared (USB, email, network) while retaining the same name. Without synchronization, copies become separate and can be changed independently.

### Common File Attributes
- **Name**: Human-readable symbolic file name.
- **Identifier**: Unique, non-human-readable tag (usually a number) identifying the file in the file system.
- **Type**: Indicates file type (if the OS supports it).
- **Location**: Pointer to device and physical location on the device.
- **Size**: Current file size (in bytes/words/blocks); may include max allowed size.
- **Protection**: Access control (who can read/write/execute).
- **Timestamps/User ID**: Metadata for creation, modification, last access; useful for security and monitoring.

Some newer file systems also support extended file attributes, including character encoding of the file and security features such as a file checksum. Figure

## 13.1.2 File Operations (Summary)

A **file** is an abstract data type. The operating system provides system calls for managing files through a minimal set of **seven basic operations**:
###  Basic File Operations
1. **Create**  
   - Allocate space in the file system.  
   - Add an entry in the directory.

2. **Open**  
   - Required before most operations (except create/delete).  
   - Checks access permissions and returns a **file handle** (index to the open-file table).  
   - Eliminates need to repeatedly search directory.

3. **Write**  
   - Uses file handle and data to be written.  
   - Maintains a **write pointer** to the current position, updated after each write.

4. **Read**  
   - Uses file handle and memory location to load data.  
   - Maintains a **read pointer** (shared with write as **current-file-position pointer**).

5. **Reposition (seek)**  
   - Changes current-file-position pointer.  
   - No actual I/O involved.

6. **Delete**  
   - Searches for file in directory.  
   - Frees file space and removes/marks directory entry.  
   - If multiple hard links exist, content is deleted only after last link is removed.

7. **Truncate**  
   - Empties file contents while keeping attributes.  
   - Sets length to zero and releases file space.

### Additional Operations
- **Append**: Add to the end of a file.
- **Rename**: Change file name.
- **Copy**: Combine create, read, and write.
- **Get/Set attributes**: Read/set metadata (e.g., length, owner).

### Directory & Open-File Table
- Frequent directory access is avoided by requiring `open()` before use.
- OS maintains an **open-file table**:
  - Stores metadata for each open file (one entry per file).
  - File handle (index) is used for all further operations.

### System Design: Two-Level Table
1. **Per-process table**  
   - Tracks files opened by a specific process.  
   - Stores access rights, accounting info, and current file pointer.

2. **System-wide table**  
   - Stores shared info: file location, size, timestamps.  
   - One entry per open file across all processes.
   - Includes an **open count** 

### Main File Attributes
- **File Pointer** : In systems that do not track file offset in `read()` and `write()` System Calls the file system must track the last read location and write location. The pointer is unique to each process operating on the file and are separate than the on disk attributes. 
- **File Open Count :** When Files are closed the operating system must reuse its open file table entries or it could run out of the space inb the table When multiple processes have opened a file the system must wait for the last file to close before removing the open file table entry it tracks the number of opened files and when its 0 it can be removed. 
- **Location of the file:** Whenever the System needs to locate a file for a process id on a mass storage it's address is stored on RAM to kept in frequently accessed memory table so the access speed increases. decreases.
- **Access Rights:** 
- 
- . The file-open count tracks the number of opens and closes and reaches zero on the last close. The system can then remove the entry. • Location of the fil . Most file operations require the system to read or write data within the file. The information needed to locate the file (wherever it is located, be it on mass storage, on a file server across the network, or on a RAM drive) is kept in memory so that the system does not have to read it from the directory structure for each operation. • Access rights. Each process opens a file in an access mode. This information is stored on the per-process table so the operating system can allow or deny subsequent I/O requests.


# References


###### Information
- date: 2025.05.09
- time: 15:28