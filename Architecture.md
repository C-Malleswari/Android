
#  Linux Architecture:

![Linux Architecture](/Images/linux_architecture.jpg)

---

##  **1. Applications**

Programs that users directly interact with.
Applications are user programs that perform tasks for the user. They run in **User Space** (outside the kernel).

###  **Examples:**

- Firefox: Web browser  
- VLC Player: Media Player  
 

###  **Where It Runs:**

User Space → Uses system calls to request Kernel services.

---

##  **2. Services (Daemons)**

Background processes that run continuously and provide core services.
These are **system services** (often called **daemons**) that start at boot time or on demand and provide features to applications and users.

###  **Examples:**

- sshd: Secure Shell (SSH) remote login service  
- systemd: Initializes and manages system services 
- udevd:  Manages device nodes in /dev

###  **Where It Runs:**

User Space (Background processes), interacts with Kernel & Hardware via system calls.

---

##  **3. Libraries**

Shared code that applications and services use.
Libraries offer **pre-written functions** so programs don’t need to rewrite common functionalities.

###  **Examples:**

- glibc: Standard C Library (memory, math, string functions)    
- libm: Math Library  
- libpthread: POSIX Threads (multithreading)  

###  **Where It Runs:**

User Space (linked at runtime or compile time).

---

##  **4. Drivers (Kernel Modules)**

Programs that help the OS communicate with hardware devices.
Device drivers are part of the **Kernel**. They provide control and communication with hardware components.

###  **Examples:**
  
- Wi-Fi driver
- USB driver 
- Bluetooth driver

###  **Where It Runs:**

Kernel Space (can be loaded/unloaded as modules).

---

## **5. Kernel**

Core part of the OS; manages hardware, memory, processes, and system calls.
The Kernel is the **heart** of the operating system. It controls everything from process management to memory and hardware communication.

###  **Examples of Kernel Features:**

- Process Management: Task scheduling, process creation (fork)  
- Memory Management: RAM allocation, virtual memory, paging  
- File System: Handling file systems  
- Networking Stack: Managing TCP/IP communication  

###  **Where It Runs:**

Kernel Space (highest privilege level).

---
## Interview Questions:
```
Question: What is the role of glibc/system libraries in Linux Architecture?
 
Answer:  
System libraries like glibc act as a bridge between user programs and the Linux kernel.  
They provide ready-made functions (APIs) so that developers don’t have to directly use complex system calls. 
Instead of writing low-level code to talk to the kernel, programmers can use easy functions like printf() or scanf() from glibc.
Example:
When you use `printf()` in C, it internally uses the `write()` system call to print to the screen.
```

```
Question: What is User Space and Kernel Space?
Answer: 
- User Space is where user applications run (like your shell, browser, or text editor).  
- Kernel Space is where the core of the operating system runs — it manages CPU, memory, and hardware devices.
Why it matters:
This separation keeps the system safe and stable — user applications cannot directly access or crash the hardware.
Example:
When an app wants to read a file:  
→ It makes a system call  
→ The request goes to the kernel  
→ The kernel uses the driver to access the hardware  
→ Data is returned to the app safely.


```

```
Question: What is a Shell in Linux?
Answer: 
A shell is a command-line interface that allows users to interact with the Linux system by entering commands.
Example:  
- bash is the most common shell in Linux.  
- Commands like `ls`, `cd`, or `mkdir` are typed into the shell, and the shell runs those programs.

```
---


