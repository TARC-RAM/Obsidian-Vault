# Operating System
- A program that acts as an intermediary between the user of a computer and the computer hardware.
- It is part of the computing system that manages all of the hardware and all of the software which controls every file, device, section of main memory and every nanosecond of processing time.
- Provide isolation and protection (allocate different parts of memory to different applications so that applications don't overwrite other memory locations).

![[Pasted image 20260202210809.png]]
The most important software in the computer system, running at all times. and manages all the hardware (I/O devices, CPU, Memory, storages) and controls all software that runs in the systems.
## Common operating system platforms include:
- Windows
- Linux
- Embedded Linux
- RIOT
# 1.1. FUNCTIONS OF AN OPERATING SYSTEM
- Make the computer system convenient to use.
- Use the computer hardware in an efficient manner
- Allocate resources (e.g CPU time, memory space, file storage space, I/O devices.) to specific programs - thus increasing efficiency of computer system.
- Controls the execution of user programs and the operations of I/O devices.
# 1.2 CHARACTERISTICS OF AN ON OPERATING SYSTEM
- **Concurrency** - To ensure that two or more processes / application can run at the same time
- **Sharing** - To ensure different processes or users can **SHARE** the same resources (CPU, memory I/O devices or file)
- **Long-term storage** - To allow users the convenience of keeping their programs or data permanently in the computer rather than on some external medium.
- **Non determinacy** - An operating system must be determinate in the sense that the same program that runs today or tomorrow with the same data, should produce the same results. It respond to events which will occur in an unpredictable manner. These events include resource requests, run-time errors in programs and interrupts from peripheral devices.
# 1.3 COMPUTER SYSTEM COMPONENTS
- **Hardware** - Provides basic computing resources (CPU, memory, I/O devices)
- **Operating system** - Controls and coordinates use of hardware among various applications and users.
- **Applications Program / Application Software** - Define the ways in which the system resources are used to solve the computing problems of the users (compilers, database systems, video games, business programs)
- **Users** - Include people, machines and other computers.
# 1.4 CLASSIFICATION OF OPERATING SYSTEMS
## 1.4.1 Non-Networked operating system
![[Pasted image 20260213153131.png]]

### Tasks Performed by Each Subsystem
- Monitor Its resources continously
- Enforce the policies that determine who gets what, when and how much.
- Allocate/deallocate the resource when appropriate.
## 1.4.2 Networked Operating System
Networked systems have a Network Manager that assumes responsibility for networking tasks while working harmoniously with every other manager.
![[Pasted image 20260213153342.png]]
![[Pasted image 20260213153433.png]]
### Essential Managers Of Operating System
**Processor Manager**
- Allocates CPU time
- Keeps track of each process status - waiting, executing
- Sets up necessary registers and tables
- Reclaims processor when job is finished and/or time for job has expired
- Providing mechanisms for process synchronization, process communication and deadlock handling
- Two levels of responsibility
	- Accepts or rejects the incoming jobs (handled by **Job Scheduler**)
	- Decides which process gets the CPU and for how long (Handled by the Process Scheduler) 
**Memory Manager**
- Checks validity of each request for memory space and if it is a legal request, allocates a portion of memory that isn't already in use
- Sets up a table to keep track of who is using which section of memory
- Deallocates memory block once program completes execution.
- Protects OS memory space so that it cannot be altered by other programs.
**Device Manager**
- Monitors every device and control unit
- Allocate system's devices in the most efficient manner (e.g printers, devices, ports, disk drives) based on a scheduling policy chosen by the system's designers
- Functions include:
	- Allocation of devices
	- Starting operation of devices
	- Deallocation of devices once job completes.
**File Manager**
- Keeps track of each file in the system (e.g data files, program files, compilers, application programs)
- Allocate resources (e.g opening files) and deallocate resources (e.g closing files)
- Uses predetermined access policies to enforce restrictions on who has access to which files
- Example:
	- Restrictions on each file - System only, user only, group only, general access
	- User restriction - read only, read/write only, allowed to create file, allowed to delete file
## 1.4.3 Types of Operating Systems
**Batch Systems
- A batch system of similar jobs processed serially without user interaction.
- The main objective is to execute a large number of jobs as efficiency as possible. Efficiency is measured in throughput i.e the number of jobs completed in a given amount of time (e.g 550 jobs per hour)
- The Jobs are executed in the first-come-first-served (FCFS) manner.
- Multi programming organizes jobs (code and data) so CPU always has one to execute.
- Access to file is serial, so simple file management and memory management.
- Example:
	- Well suited for applications that have a long execution time and do not need any quick response E.g Payroll, forecasting, statistical analysis and large scientific application

**Time-sharing systems
- An extension of multi programming system that supports interactive users and provides a quick response time
- The main objective is to minimize the response time by sharing the computer resources among several users
- The CPU switches jobs so frequently that users can interact with each job while it is running, creating interactive computing.
- Most time-sharing systems make use of  round-robin scheduling in which each program is given a system-defined time-slice for its execution. A context switch occurs each time after the time slice of currently running process is over.
- More sophisticated memory management is needed to provide separation and protection of multiple users programs
- File management must provide advanced protection, access controls and concurrency control methods
- Example:
	- Air traffic control system used by the airport authority robotics, weapon, undersea exploration

**Hybrid Systems
- A combination of batch and interactive systems.
- Appear to be interactive because individual users can access the system and get fast responses but actually accepts and runs batch programs in background when the interactive load is light
- Takes advantage of the free time between high-demand usage of the system and low-demand times.
- Many large computer systems are hybrids.

**Embedded Systems
- Embedded systems are computers placed inside other products to add features and capabilities
- Example:
	- In automobiles, embedded computers can help with engine performance, braking and navigation.
## 1.5 OPERATING SYSTEM OPERATIONS
- Bootstrap program - simple code to initialize the system, load the kernel
- Kernel loads
- Starts system daemons (services provided outside of the kernel)
- Kernel interrupt driven (hardware and software)
	- Hardware interrupt by one of the devices
	- Software interrupt (exception or trap):
		- Software error (e.g division by zero)
		- Request for operating system service - **system call**
		- Other process problems include infinite loop, process modifying each other or the operating system.
# 1.6 SYSTEM CALLS, INTERRUPTS AND INTERRUPTS HANDLING
## 1.6.1 Dual Mode Operations in Operating System
- Dual-mode operation allows OS to protect itself and other system components. OS needs to function in the dual mode because the Kernel Level programs perform all the bottom level functions of the OS like process management, Memory management, etc. If the user alters these, then this can cause an entire system failure. So, for specifying the access to the users only to the tasks of their use, Dual Mode is necessary for an OS.
- The OS has two modes of operation to ensure it works correctly:
	- User mode - Execution done on behalf of a user
	- Kernel mode (supervisor mode, system mode or privileged mode) - Execution done on behalf of OS.
- Mode bit is added to the hardware to indicate the current mode : kernel (0) or user (1)
  ![[Pasted image 20260213174021.png]]
- When the computer system executes on behalf of a user application, the system is in user mode.
- However, when a user application requests a service from the OS via a **system call**, it must transition from user to kernel mode to fulfill the request
- At system boot time, the hardware starts in kernel mode. The OS is then loaded and starts user process in user mode.
- Whenever a trap (software interrupt) or interrupt occurs, the hardware switches from user mode to kernel mode.
- The system always switches to user mode before passing control to a user program.
- This protection is accomplished by designating some machine instructions as privileged instruction. The hardware allows privileged instruction to be executed only in kernel mode.
- If an attempt is made to execute a privileged instruction in user mode, the hardware does not execute the instruction but treats the instruction as illegal and traps to the OS.
- E.g halt instruction, turn off interrupt
## 1.6.2 Use of System Call to perform I/O
- System call is a programming interface to the services provided by an OS.
- Typically written in a high-level language (C or C++)
- Mostly accessed by programs via a Application Programming Interface (API) rather than direct system call use. API is a set of protocols, routines, functions that allow exchanging data among various applications and devices while a system call is a method that allows a program to request services from the kernel.
- Three most common APIs are Win32 API for Windows, POSIX API for POSIX-based systems (including virtually all versions of UNIX, Linux and Mac OS X) and java API for the Java virtual machine (JVM)
- There are hundred system calls which can be grouped into 6 categories there are:

| Task                    | Commands                   |
| ----------------------- | -------------------------- |
| Process Control         | fork (); exit(); wait();   |
| File Manipulation       | open(); read(); write();   |
| Device Manipulation     | ioctl(); read(); write();  |
| Information Maintenance | ioctl(); read(); write();  |
| Communication           | pipe(); shmget(); mmap();  |
| Protection              | chmod(); umask(); chown(); |
![[Pasted image 20260213175637.png]]
![[Pasted image 20260213175711.png]]
## 1.6.3 Interrupts
- Interrupt is a signal which has highest priority from hardware or software which CPU should process its signal immediately.
- Almost all computers provide a mechanism by which other components may interrupt the normal processing of the CPU.
- The difference between a software interrupt (often called a trap) and a hardware interrupt is a trap that is triggered by a user program to invoke OS functionality. Still, an hardware interrupt is triggered by a hardware device to allow CPU to execute the corresponding interrupt service routine.
## 1.6.4 Interrupt Handling
- An interrupt service routine (ISR) is provided that is responsible for dealing with the interrupt
- When the OS detects event is interrupted, the interrupt handler typically follows this sequence:
	- Interrupt type described and stored (passed to user as an error message)
	- Interrupted process state saved (value of the program counter and contents of all registers)
	- Control is then transferred to the ISR, generally through the interrupt vector. Interrupt is processed
		- Non-Recoverable interrupt
			- Job processing is terminated
			- Resources allocated to the job are released
			- An error message is sent to the user.
		- Recoverable
		- I/O interrupt - The job is moved to the I/O queue.
		- Time quantum interrupt - The job is moved to the ready queue
	- Processor resumes normal operation
![[Pasted image 20260213181246.png]]