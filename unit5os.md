### UNIT V: FILE SYSTEM

### Short Exam Notes

### 1\. File System

A file is a named collection of related information stored on secondary storage. It can contain text, programs, images, audio or other data.

File attributes: Name, identifier, type, location, size, protection, time, date and user identification.

File operations: Create, read, write, reposition, delete and truncate.

### 2\. Types of Files

| File Type  | Extension       | Purpose                   |
| ---------- | --------------- | ------------------------- |
| Executable | .exe, .bin      | Ready-to-run programs     |
| Object     | .obj, .o        | Compiled machine code     |
| Source     | .c, .cpp, .java | Program source code       |
| Batch      | .bat, .sh       | Commands for execution    |
| Text       | .txt, .doc      | Text and documents        |
| Library    | .lib, .dll      | Reusable program routines |
| Archive    | .zip, .tar      | Groups files for storage  |
| Multimedia | .mp3, .mp4      | Audio and video files     |

### 3\. File Access Methods

1\. Sequential Access

* Records are accessed one after another in order.

* Read-next and write-next operations are used.

* File pointer automatically moves after each operation.

* Example: Text editors and compilers.

2\. Direct Access (Random Access)

* File consists of fixed-length logical records or blocks.

* Any block can be accessed directly using its block number.

* Records can be read or written in any order.

* Example: Disk-based databases.

3\. Indexed Access

* An index block contains pointers to the file's data blocks.

* First search the index, then access the required record.

* Supports fast direct access.

* Large files may require multiple levels of indexing.

### 4\. Directory Structures

A directory stores file information such as name, location, size and type.

Directory operations: Search, create, delete, list, rename and traverse files.

| Structure       | Description                                                                                                                   |
| --------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Single-Level    | All files are stored in one directory. Simple, but filename conflicts occur and grouping is not possible.                     |
| Two-Level       | Each user has a separate User File Directory (UFD). Same filenames are allowed for different users, but sharing is difficult. |
| Tree-Structured | Directories contain files and subdirectories. Supports grouping and efficient searching. Uses absolute and relative paths.    |
| Acyclic-Graph   | Allows files or directories to be shared through links. Sharing is possible, but deleting linked files may cause problems.    |

Path names:

* Absolute path: Starts from the root directory.

* Relative path: Starts from the current directory.

### 5\. File Allocation Methods

File allocation determines how disk blocks are assigned to files.

### A. Contiguous Allocation

* Each file occupies consecutive disk blocks.

* Directory stores starting block and file length.

* Supports sequential and direct access.

* Fast access with minimum seek movements.

* Disadvantages: External fragmentation and difficult file expansion.

### B. Linked Allocation

* File blocks are stored anywhere on the disk.

* Each block contains a pointer to the next block.

* Directory stores starting and ending block addresses.

* Advantages: No external fragmentation; files can grow easily.

* Disadvantages: Slow direct access, pointer overhead and more disk seeks.

### Linked Allocation with FAT (File Allocation Table)

* FAT stores the pointers to the next file blocks in a separate table.

* Directory contains the starting block of the file.

* FAT entries form a chain of blocks belonging to the file.

* It makes block-chain information easier to manage than storing pointers inside every data block.

### C. Indexed Allocation

* Each file has a separate index block containing addresses of its data blocks.

* Directory stores the address of the index block.

* Supports direct access and avoids external fragmentation.

* Disadvantages: Index block overhead and wasted space for small files.

* Large files use linked index blocks, multilevel indexing or combined schemes.

### 6\. Disk Scheduling

Disk scheduling determines the order in which disk requests are serviced.

Important terms:

* Seek time: Time taken to move the disk head to the required cylinder.

* Rotational latency: Time waiting for the required sector to rotate under the head.

* Seek distance: Number of cylinders moved by the disk head.

* Disk bandwidth: Total bytes transferred divided by total time taken.

### Disk Scheduling Algorithms

| Algorithm | Working                                                                                                                                                           |
| --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| FCFS      | Services requests in the order they arrive. Simple and fair, but may cause large head movements.                                                                  |
| SSTF      | Services the request closest to the current head. Reduces seek time but may cause starvation.                                                                     |
| SCAN      | Head moves in one direction, services requests, reaches the disk end and reverses. Also called Elevator Algorithm.                                                |
| C-SCAN    | Services requests in one direction, reaches the end and returns to the opposite end without servicing requests on the return. Provides more uniform waiting time. |
| LOOK      | Similar to SCAN, but reverses at the last request instead of reaching the disk end. Reduces unnecessary movement.                                                 |
| C-LOOK    | Similar to C-SCAN, but jumps from the last request in one direction to the first request at the other end without reaching the physical disk ends.                |

### 7\. Disk Scheduling Comparison

| Algorithm | Main Advantage                                 | Main Disadvantage              |
| --------- | ---------------------------------------------- | ------------------------------ |
| FCFS      | Fair, simple                                   | High seek time                 |
| SSTF      | Low average seek time                          | Starvation possible            |
| SCAN      | Good throughput                                | Long waiting for some requests |
| C-SCAN    | Uniform waiting time                           | Extra movement during return   |
| LOOK      | Avoids unnecessary disk-end movement           | Waiting time may vary          |
| C-LOOK    | Uniform service with less unnecessary movement | Circular jump adds movement    |

### 8\. Solving Disk Scheduling Problems

* Identify the initial head position and request queue.

* Note the direction of head movement for SCAN, C-SCAN, LOOK and C-LOOK.

* Arrange requests according to the algorithm.

* Calculate movement between consecutive cylinders.

* Add all movements.

\\text{Total Head Movement}=\\sum |\\text{Next}-\\text{Current}|

Remember: SCAN and C-SCAN travel to disk ends; LOOK and C-LOOK travel only to the last pending request.

### Quick Revision

* File access methods: Sequential, Direct, Indexed.

* Directory structures: Single-Level, Two-Level, Tree, Acyclic-Graph.

* Allocation methods: Contiguous, Linked, Linked with FAT, Indexed.

* Disk scheduling: FCFS, SSTF, SCAN, C-SCAN, LOOK, C-LOOK.

