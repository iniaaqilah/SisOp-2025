Nama: Aqilah Salamatuddin  
Kelas: D3 IT B  
NRP: 312450054  

---

## Practice Exercises  

### 1.1. What are the three main purposes of an operating system?  
**Answer:**  
The three main purposes of an operating system are to:  
1. **Manage resources**:  
   - Process management (the OS manages the order of processes that run on the system hardware).  
   - Memory management (the OS allocates and deallocates memory to programs as they are executed).  
   - File management (the OS organizes and manages files on storage devices).  
   - Device management (the OS controls and manages input and output devices).  
2. **Establish a user interface**:  
   - The OS provides a user interface that allows users to interact with the computer.  
3. **Run applications**:  
   - The OS executes and provides services for applications software.  

---

### 1.2. When is it appropriate for the operating system to forsake efficiency and "waste" resources? Why is such a system not really wasteful?  
**Answer:**  
In single-user systems, the primary goal is to maximize the user's experience. For example, a graphical user interface (GUI) might consume additional CPU cycles, but it enhances the user's interaction with the system, making it more intuitive and user-friendly. Therefore, while it may appear to waste resources, it ultimately optimizes the overall user experience, making the system more effective in meeting the user's needs.  

---

### 1.3. What is the main difficulty that a programmer must overcome in writing an operating system for a real-time environment?  
**Answer:**  
The main difficulty is keeping the operating system within the fixed time constraints of a real-time system.  

---

### 1.4. Should the operating system include applications such as web browsers and mail programs? Argue both sides.  
**Answer:**  
- **It should not include applications**: Applications like web browsers and email programs are not part of the core functionality of the OS, which is to manage hardware resources and run continuously. Embedding applications within the OS can introduce security risks, system bloat, and blur the line between the OS and applications.  
- **It should include applications**: Including applications can improve performance and user convenience by optimizing the use of kernel features. However, it is generally better to keep such applications separate, allowing users to install and manage them as needed, while the OS focuses on its primary role as the interface between hardware and the user.  

---

### 1.5. How does the distinction between kernel mode and user mode function as a rudimentary form of protection (security)?  
**Answer:**  
The separation between kernel mode and user mode serves as a basic form of protection in the following ways:  
- Specific instructions can only be executed when the CPU is in kernel mode.  
- Hardware devices can only be accessed, and interrupts can only be enabled or disabled, when the CPU is operating in kernel mode.  
- In user mode, the CPU's capabilities are significantly restricted, ensuring the protection of critical system resources.  

---

### 1.6. Which of the following instructions should be privileged?  
a. Set value of timer  
b. Read the clock  
c. Clear memory  
d. Issue a trap instruction  
e. Turn off interrupts  
f. Modify entries in device-status table  
g. Switch from user to kernel table  
h. Access I/O device  

**Answer:**  
The following operations need to be privileged:  
- a (Set value of timer)  
- c (Clear memory)  
- e (Turn off interrupts)  
- f (Modify entries in device-status table)  
- h (Access I/O device)  

---

### 1.7. What are two difficulties that could arise from placing the OS in a memory partition that cannot be modified by the user or the OS itself?  
**Answer:**  
1. The data required by the operating system (passwords, access controls, accounting information, etc.) would have to be stored in or passed through unprotected memory, making it accessible to unauthorized users.  
2. The OS would be unable to update or modify its own code, limiting its ability to adapt to new requirements or fix bugs.  

---

### 1.8. What are two possible uses of multiple modes of operation in CPUs?  
**Answer:**  
1. **Fine-grained security policies**: Different types of user modes could be established, allowing users within the same group to execute each other's code.  
2. **Specialized kernel modes**: Specific modes could allow certain drivers (e.g., USB device drivers) to operate without requiring a full switch to kernel mode, maintaining efficiency and security.  

---

### 1.9. How could timers be used to compute the current time?  
**Answer:**  
Timers can be used to compute the current time by counting the number of timer interrupts that have occurred since a known starting point. Each interrupt represents a fixed time interval, allowing the system to calculate the elapsed time and determine the current time.  

---

### 1.10. Why are caches useful? What problems do they solve? What problems do they cause?  
**Answer:**  
- **Usefulness**: Caches act as intermediate-speed buffers between components operating at different speeds, reducing wait times for faster devices.  
- **Problems solved**: They address speed mismatches between components, improving overall system performance.  
- **Problems caused**: Maintaining cache consistency (ensuring data in the cache matches the data in the components) can be challenging, especially in multiprocessor systems.  
- **Why not replace devices with caches?**: A cache can replace a device only if:  
  a. The cache and the component have the same state-saving capability.  
  b. The cache is cost-effective, as faster storage is typically more expensive.  

---

### 1.11. Distinguish between the client-server and peer-to-peer models of distributed systems.  
**Answer:**  
- **Client-server model**:  
  - Centralized structure with distinct roles: clients request services, and servers provide them.  
  - Easier to manage and secure but can face scalability issues and single points of failure.  
  - Example: Web servers like Apache serving web pages to client browsers.  
- **Peer-to-peer (P2P) model**:  
  - Decentralized structure where all nodes (peers) act as both clients and servers.  
  - More scalable, resilient, and fault-tolerant but harder to manage due to its distributed nature.  
  - Example: File-sharing systems like BitTorrent and blockchain networks like Bitcoin.  
