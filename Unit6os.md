### UNIT-VI: I/O Systems

### Short & Easy Exam Notes

### 1\. I/O Hardware

I/O hardware is used to connect input and output devices with the computer.

* Input devices: Keyboard, mouse, scanner.

* Output devices: Monitor, printer.

* I/O controller: Controls communication between CPU and I/O devices.

### 2\. Polling

Polling is a method where the CPU continuously checks whether an I/O device is ready.

* CPU checks the device status repeatedly.

* If the device is ready, data transfer starts.

* It wastes CPU time.

Example: CPU repeatedly checking whether the keyboard has a key pressed.

### 3\. Interrupts

An interrupt is a signal sent by an I/O device to inform the CPU that it needs attention.

* CPU can perform other tasks.

* Device sends an interrupt when ready.

* CPU stops its current work and handles the interrupt.

Example: Keyboard sends an interrupt when a key is pressed.

### 4\. DMA (Direct Memory Access)

DMA transfers data directly between I/O devices and memory without continuous CPU involvement.

* CPU initializes the DMA controller.

* DMA transfers data directly.

* CPU is free to perform other tasks.

Example: Transferring a file from a disk to memory.

### 5\. Polling vs Interrupts vs DMA

| Method    | Simple meaning                                    |
| --------- | ------------------------------------------------- |
| Polling   | CPU repeatedly checks device                      |
| Interrupt | Device informs CPU                                |
| DMA       | Data transfers directly between device and memory |

### Protection

### 6\. Goals of Protection

Protection ensures that system resources are accessed only by authorized users.

Main goals:

* Prevent unauthorized access.

* Protect data and programs.

* Allow controlled sharing of resources.

* Improve system security.

### 7\. Principles of Protection

Principles of protection are rules used to design a secure system.

* Least privilege: Give users only the permissions they need.

* Separation of privilege: Important tasks require proper permissions.

* Fail-safe default: Deny access unless permission is given.

* Complete mediation: Check permission every time a resource is accessed.

### 8\. Access Matrix

An access matrix is a table that shows which user can access which resource and what operations they can perform.

* Rows represent users or domains.

* Columns represent objects.

* Entries represent permissions.

Example:

| User   | File A | Printer   |
| ------ | ------ | --------- |
| User 1 | Read   | Print     |
| User 2 | Write  | No access |

### 9\. Implementation of Access Matrix

Access matrix can be implemented using different methods:

* Global table: Stores user, object and permission together.

* Access Control List (ACL): Stores permissions with each object.

* Capability List: Stores permissions with each user.

* Lock and key: Objects have locks and users have matching keys.

### 10\. Access Control List (ACL)

ACL is a list attached to an object that shows which users can access it.

* Specifies users and their permissions.

* Permissions may include read, write and execute.

* Easy to check who can access a particular file.

Example: File A → User 1: Read, User 2: Write.

Remember: ACL = Object → Users and permissions.

### 11\. Capability List

A capability list stores the objects and permissions available to a particular user.

* Specifies which objects a user can access.

* Contains permissions such as read, write and execute.

* Helps control user access.

Example: User 1 → File A: Read, File B: Write.

Remember: Capability List = User → Objects and permissions.

### ACL vs Capability List

| ACL                  | Capability List            |
| -------------------- | -------------------------- |
| Attached to object   | Attached to user           |
| Shows who can access | Shows what user can access |
| Object-based         | User-based                 |

### 12\. Program Threats

Program threats are attacks that misuse programs to damage the system or access data without permission.

| Threat          | Simple meaning                                          |
| --------------- | ------------------------------------------------------- |
| Trojan Horse    | Harmful code hidden inside a useful program.            |
| Trapdoor        | Secret way to access a program without normal security. |
| Logic Bomb      | Code that runs when a specific condition occurs.        |
| Virus           | Malicious code that attaches to files and spreads.      |
| Buffer Overflow | Writing more data than a memory buffer can hold.        |
| Stack Smashing  | Overwriting stack memory to change program execution.   |

### Easy examples to remember

* Trojan Horse: Fake useful software containing harmful code.

* Trapdoor: Secret entry into a program.

* Logic Bomb: Activates on a particular date or condition.

* Virus: Infects other files.

* Buffer Overflow: Data exceeds memory space.

### Last-Minute Revision

Remember these one-line definitions:

* Polling: CPU checks device repeatedly.

* Interrupt: Device informs CPU.

* DMA: Direct data transfer between device and memory.

* Protection: Prevents unauthorized access.

* Access Matrix: Table of users, objects and permissions.

* ACL: Object stores user permissions.

* Capability List: User stores object permissions.

* Trojan Horse: Harmful code hidden in useful software.

* Trapdoor: Secret access method.

* Logic Bomb: Executes when a condition is met.

* Virus: Malicious code that spreads.

* Buffer Overflow: Data exceeds buffer capacity.


