# Operating System
- It is a set of system software routines that sits between the application program and the hardware.
- It is part of the computing system that manages all the hardware and all the software which controls every file, device, section of main memory and every nanosecond of processing time
- It is the one program which is always running (all else being application programs).
- Provide isolation and protection (allocate different parts of memory to different applications so that applications don't overwrite other memory locations).
- It is a program that acts as an intermediary between the user of a computer and the computer hardware.
![[Pasted image 20260316181134.png]]
## 1.1 Functions of an Operating System
- Make the computer system convenient to use.
- Use the computer hardware in an efficient manner.
- Allocates resources (e.g CPU time, memory space, file storage space, I/O devices) to specific programs - thus increasing efficiency of computer system.
- Controls the execution of user programs and the operations of I/O devices.
## 1.2 Characteristics of an operating system
### Concurrency
Concurrency is the existence of several simultaneous or parallel activities such as overlapping of I/O operations with computation.
### Sharing
Concurrent activities may be required to share resources or information.
### Long-term storage
The need for sharing of programs and data implies the need for long-term storage of information. Long-term storage allows users the convenience of keeping their programs or data in the computer rather than on some external medium.
### Non determinacy
An operating system must be determinate in the sense that the same program that runs today or tomorrow with the same data, should produce the same results. It responds to events which will occur in an unpredictable manner. These events include resource requests, run-time errors in programs, and interrupts from peripheral devices.
## 1.3 Computer System Components
- Hardware
	- Provides basic computing resources (CPU, memory, Input/Output (I/O) devices).
- Operating System (OS)
	- Controls and coordinates use of hardware among various applications and users.
- Applications programs / Application Software
	- Define the ways in which the system resources are used to solve the computing problems of the users (compilers, database system, video games, business programs).
	- Users
		- Include people, machines and other computers.
## 1.4 Classification Of Operating Systems
### 1.4.1 Non-Networked operating system
The following diagram is an abstract representation of an operating system demonstrating how its major components work together in an non-networked operating system with its four sub-system managers supporting the user command interface.
![[Pasted image 20260316185544.png]]
#### Tasks Performed by Each Subsystem
- Monitor its resources continuously.
- Enforce the policies that determine who gets what, when and how much.
- Allocate/deallocate the resource when appropriate.
### 1.4.2 Networked Operating System
Networked systems have a Network Manager that assumes responsibility for networking tasks while working harmoniously with every other manager.
![[Pasted image 20260316185630.png]]
![[Pasted image 20260316185500.png]]
#### Essential managers of Operating system
##### Processor Manager
- Allocates CPU time.
- Keeps track of each process status - waiting, executing.
- Sets up necessary registers and tables.
- Reclaims processor when job is finished and/or time for job has expired.
- Providing mechanisms for process synchronization, process communication and deadlock handling.
- Two levels of responsiblity
	- Accepts or rejects incoming jobs (handled by Job Scheduler)
	- Decides which process gets the CPU and for how long (Handled by the Process Scheduler)
##### Memory Manager
- Checks validity of each request for memory space and if it is a legal request, allocates a portion of memory that isn't already in use.
- Sets up a table to keep track of who is using which section of memory.
- Deallocates memory blocks once program completes execution.
- Protects OS memory space so that it cannot be altered by other programs
  ![[Pasted image 20260316192003.png]]
##### Device Manager
- Monitors every device and control unit
- Allocate system's devices in the most efficient manner (e.g. printers, devices, ports, disk drives) based on a scheduling policy chosen by the system's designers.
- Function include:
	- Allocation of devices
	- Starting operation of devices
	- Deallocation of devices once job completes.
	  ![[Pasted image 20260316192025.png]]
##### File Manager
- Keeps track of each file in the system (e.g., data files, program files, compilers, application programs)
- Allocate resources (e.g, opening files) and deallocate resources (e.g., closing files)
- Uses predetermined access policies to enforce restrictions on who has access to which files.
- Example:
	- Restrictions on each file - System only, useronly, group only, general access 
	- User restriction - Read only, Write only, Allowed to create file, allowed to delete file.
### 1.4.3 Types of Operating Systems
Type of OS in the context of the level of complexity involved in performing different OS functions such as CPU scheduling, memory management and file management.
##### Batch Systems
- A batch of similar jobs processed serially without user interaction.
- The main objective is to execute a large number of jobs as efficiency as possible. Efficiency is measured in throughput, i.e., the number of jobs completed in a given amount of time (e.g, 550 jobs per hour).
- The Jobs are executed in first-come-first-served (FCFS) manner.
- Multi programming organizes jobs (code and data) so CPU always has one to execute.
- Access to file is serial, so simple file management and memory management.
##### Example:
- Well suited for applications that have a long execution time and do not need any quick response. E.g, Payroll, forecasting, statistical analysis and large scientific application.
#### Time-sharing systems
- An extension of multi programming system