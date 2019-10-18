## Network

### OSI - five layers - tcp/ip

 ![img](https://github.com/CyC2018/CS-Notes/raw/master/notes/pics/0fa6c237-a909-4e2a-a771-2c5485cd8ce0.png) 

 ![“tcp/ip”的图片搜索结果](https://cdn.educba.com/academy/wp-content/uploads/2019/07/OSI-Model-vs-TCPIP-Model.png) 



### OSI

#### Layer 7: Application Layer

HTTP/DNS

 High-level [APIs](https://en.wikipedia.org/wiki/API), including resource sharing, remote file access

#### Layer 6: Presentation Layer

 Translation of data between a networking service and an application; including [character encoding](https://en.wikipedia.org/wiki/Character_encoding), [data compression](https://en.wikipedia.org/wiki/Data_compression) and [encryption/decryption](https://en.wikipedia.org/wiki/Encryption) 

#### Layer 5: Session Layer

 Managing communication [sessions](https://en.wikipedia.org/wiki/Session_(computer_science)), i.e. continuous exchange of information in the form of multiple back-and-forth transmissions between two nodes 

#### Layer 4: Transport Layer  (process to process)

 UDP/TCP (socket)

 Reliable transmission of data segments between points on a network, including [segmentation](https://en.wikipedia.org/wiki/Packet_segmentation), [acknowledgement](https://en.wikipedia.org/wiki/Acknowledgement_(data_networks)) and [multiplexing](https://en.wikipedia.org/wiki/Multiplexing) 

#### Layer 3: Network Layer (host to host) (IP)

 The [network layer](https://en.wikipedia.org/wiki/Network_layer) provides the functional and procedural means of transferring variable length [data](https://en.wikipedia.org/wiki/Data) sequences (called [packets](https://en.wikipedia.org/wiki/Network_packet)) from one node to another connected in "different networks". 

 Structuring and managing a multi-node network, including [addressing](https://en.wikipedia.org/wiki/Address_space), [routing](https://en.wikipedia.org/wiki/Routing) and [traffic control](https://en.wikipedia.org/wiki/Network_traffic_control)

#### Layer 2: Data Link Layer (neighbour node)

 The [data link layer](https://en.wikipedia.org/wiki/Data_link_layer) provides [node-to-node data transfer](https://en.wikipedia.org/wiki/Node-to-node_data_transfer)—a link between two directly connected nodes.  

#### Layer 1: Physical Layer 

 The [physical layer](https://en.wikipedia.org/wiki/Physical_layer) is responsible for the transmission and reception of unstructured raw data between a device and a physical [transmission medium](https://en.wikipedia.org/wiki/Transmission_medium). 



### Socket

A socket provides a connection between two applications. Each endpoint of a communication is a socket. 

Socket=IP : Port	(冒号  colon)



### TCP

TCP provides [reliable](https://en.wikipedia.org/wiki/Reliability_(computer_networking)), ordered, and [error-checked](https://en.wikipedia.org/wiki/Error_detection_and_correction) delivery of a stream between applications running on hosts communicating via an IP network. Major internet applications such as the [World Wide Web](https://en.wikipedia.org/wiki/World_Wide_Web), [email](https://en.wikipedia.org/wiki/Email), [remote administration](https://en.wikipedia.org/wiki/Remote_administration), and [file transfer](https://en.wikipedia.org/wiki/File_transfer) rely on TCP. Applications that do not require reliable data stream service may use the [User Datagram Protocol](https://en.wikipedia.org/wiki/User_Datagram_Protocol) (UDP), which provides a [connectionless](https://en.wikipedia.org/wiki/Connectionless_communication) [datagram](https://en.wikipedia.org/wiki/Datagram) service that emphasizes reduced [latency](https://en.wikipedia.org/wiki/Latency_(engineering)) over reliability. 

#### What is function of Router ?

Answer : Router is a device or PC which is used to connect two or more IP networks.

#### What is Default Gateway ？

Answer : Default gateway is the address of router.

#### What is Subnet Mask ?

Answer : Subnet mask is used to differentiate Network ID and Host ID from a given IP address. 

#### Define Bandwidth and Latency? 

Ans:- Performance of network is measured in Bandwidth called throughput and Latency  called Delay. Network bandwidth is the number of bits which can be transmitted over the network over a certain period of time. Latency refers to the time taken by a message to travel from one end of network to another. It is strictly measured in terms of time.

#### TCP Connection Begin -Three-way handshake process

- **Step 1 (SYN) :** In the first step, client wants to establish a connection with server, so it sends a segment with SYN(Synchronize Sequence Number) which informs server that client is likely to start communication and with what sequence number it starts segments with
- **Step 2 (SYN + ACK):** Server responds to the client request with SYN-ACK signal bits set. Acknowledgement(ACK) signifies the response of segment it received and SYN signifies with what sequence number it is likely to start the segments with
- **Step 3 (ACK) :** In the final part client acknowledges the response of server and they both establish a reliable connection with which they will start the actual data transfer

#### TCP Connection Terminated - Four-way handshake

- **Step 1 (FIN From Client) –** Suppose that the client application decides it wants to close the connection. (Note that the server could also choose to close the connection). This causes the client send a TCP segment with the **FIN** bit set to **1** to server and to enter the **FIN_WAIT_1** state. While in the **FIN_WAIT_1** state, the client waits for a TCP segment from the server with an acknowledgment (ACK).
- **Step 2 (ACK From Server) –** When Server received FIN bit segment from Sender (Client), Server Immediately send acknowledgement (ACK) segment to the Sender (Client).
- **Step 3 (Client waiting) –** While in the **FIN_WAIT_1** state, the client waits for a TCP segment from the server with an acknowledgment. When it receives this segment, the client enters the **FIN_WAIT_2** state. While in the **FIN_WAIT_2** state, the client waits for another segment from the server with the FIN bit set to 1.
- **Step 4 (FIN from Server) –** Server sends FIN bit segment to the Sender(Client) after some time when Server send the ACK segment (because of some closing process in the Server).
- **Step 5 (ACK from Client) –** When Client receive FIN bit segment from the Server, the client acknowledges the server’s segment and enters the **TIME_WAIT** state. The **TIME_WAIT** state lets the client resend the final acknowledgment in case the **ACK** is lost. The time spent by client in the **TIME_WAIT** state is depend on their implementation, but their typical values are 30 seconds, 1 minute, and 2 minutes. After the wait, the connection formally closes and all resources on the client side (including port numbers and buffer data) are released.



### Differences between TCP and UDP

| TCP                                                          | UDP                                                          |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| TCP is a **connection-oriented** protocol. Connection-orientation means that the communicating devices should establish a connection before transmitting data and should close the connection after transmitting the data. | UDP is the **Datagram oriented** protocol. This is because there is no overhead for opening a connection, maintaining a connection, and terminating a connection. UDP is efficient for broadcast and multicast type of network transmission. |
| TCP is reliable as it guarantees delivery of data to the destination router. | The delivery of data to the destination cannot be guaranteed in UDP. |
| TCP provides extensive error checking mechanisms. It is because it provides flow control and acknowledgment of data. | UDP has only the basic error checking mechanism using checksums. |
| Sequencing of data is a feature of Transmission Control Protocol (TCP). this means that packets arrive in-order at the receiver. | There is no sequencing of data in UDP. If ordering is required, it has to be managed by the application layer. |
| TCP is comparatively slower than UDP.                        | UDP is faster, simpler and more efficient than TCP.          |
| Retransmission of lost packets is possible in TCP, but not in UDP. | There is no retransmission of lost packets in User Datagram Protocol (UDP). |
| TCP has a (20-80) bytes variable length header.              | UDP has a 8 bytes fixed length header.                       |
| TCP is heavy-weight.                                         | UDP is lightweight.                                          |
| TCP doesn’t supports Broadcasting.                           | UDP supports Broadcasting.                                   |
| UDP is used by DNS, DHCP, TFTP, SNMP, RIP, and VoIP.         |                                                              |



### Routing schemes

#### Unicast

**Unicast** addressing uses a *one-to-one* association between a sender and destination: each destination address uniquely identifies a single receiver endpoint. 

#### Broadcasting

[Broadcast](https://en.wikipedia.org/wiki/Broadcasting_(networking)) uses a *one-to-all* association; a single datagram from one sender is routed to all of the possibly multiple endpoints associated with the broadcast address. The network automatically replicates datagrams as needed to reach all the recipients within the scope of the broadcast, which is generally an entire network subnet. 

#### Multicast

[Multicast](https://en.wikipedia.org/wiki/Multicast) addressing uses a *one-to-many-of-many* or *many-to-many-of-many* association; datagrams are routed simultaneously in a single transmission to many recipients. It differs from broadcast in that the destination address designates a subset, not necessarily all, of the accessible nodes. 





## Computer System

### Process and Thread

#### Difference between Process and Thread

A process is an active program. It is more than the program code as it includes the program counter, process stack, registers, program code etc. Compared to this, the program code is only the text section.

A **thread** of execution is the smallest sequence of programmed instructions that can be managed independently by a [scheduler](https://en.wikipedia.org/wiki/Scheduling_(computing)), which is typically a part of the [operating system](https://en.wikipedia.org/wiki/Operating_system).[[1\]](https://en.wikipedia.org/wiki/Thread_(computing)#cite_note-1) A thread is the component  of  a process.   [Multiple threads](https://en.wikipedia.org/wiki/Thread_(computing)#Multithreading) can exist within one process, executing [concurrently](https://en.wikipedia.org/wiki/Concurrent_computation) and sharing resources such as [memory](https://en.wikipedia.org/wiki/Shared_memory_(interprocess_communication)), while different processes do not share these resources.  A thread shares information like data segment, code segment, files etc. with its peer threads while it contains its own registers, stack, counter etc.

The major differences between a process and a thread are given as follows:

| Comparison Basis       | Process                                                      | Thread                                                       |
| ---------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Definition             | A process is a program under execution.                      | A thread is a lightweight process that can be managed independently by a scheduler. |
| Context switching time | Processes require more time for context switching as they are more heavy. | Threads require less time for context switching as they are lighter than processes. |
| Memory Sharing         | Processes are totally independent and don’t share memory.    | A thread may share some memory with its peer threads.        |
| Communication          | Communication between processes requires more time than between threads. | Communication between threads requires less time than between processes . |
| Resource Consumption   | Processes require more resources than threads.               | Threads generally need less resources than processes.        |
| Dependency             | Individual processes are independent of each other.          | Threads are parts of a process and so are dependent.         |
| Data and Code sharing  | Processes have independent data and code segments.           | A thread shares the data segment, code segment, files etc. with its peer threads. |
| Treatment by OS        | All the different processes are treated separately by the operating system. | All user level peer threads are treated as a single task by the operating system. |
| Time for creation      | Processes require more time for creation.                    | Threads require less time for creation.                      |
| Time for termination   | Processes require more time for termination.                 | Threads require less time for termination.                   |



#### Communication between processes

- **Socket**: Data sent over a network interface, either to a different process on the same computer or to another computer on the network. Stream-oriented ([TCP](https://en.wikipedia.org/wiki/Transmission_Control_Protocol); data written through a socket requires formatting to preserve message boundaries) or more rarely message-oriented ([UDP](https://en.wikipedia.org/wiki/User_Datagram_Protocol), [SCTP](https://en.wikipedia.org/wiki/SCTP)).
-  [Shared memory](https://en.wikipedia.org/wiki/Shared_memory_(interprocess_communication)) : Multiple processes are given access to the same block of [memory](https://en.wikipedia.org/wiki/Memory_(computing)) which creates a shared buffer for the processes to communicate with each other. 
- **Signal** : A system message sent from one process to another, not usually used to transfer data but instead used to remotely command the partnered process.  ( **one process send a signal and the receiver will handle it by its signal handler to implement communication.** )
- Message queue or PIPE or semaphore etc. 



#### Thread synchronization

why:

 Thread synchronization is the concurrent execution of two or more threads that share critical resources. Threads should be synchronized to avoid **critical resource use conflicts**. Otherwise, **conflicts may arise when parallel-running threads attempt to modify a common variable at the same time**. 

 **For example,** suppose that there are three processes, namely 1, 2, and 3. All three of them are concurrently executing, and they need to share a common resource (critical section) as shown in Figure 1. Synchronization should be used here to avoid any conflicts for accessing this shared resource. Hence, when Process 1 and 2 both try to access that resource, it should be assigned to only one process at a time. If it is assigned to Process 1, the other process (Process 2) needs to wait until Process 1 frees that resource (as shown in Figure 2). 

-  Semaphore 
-  Synchronized/Lock 



#### Deadlock

 In an [operating system](https://en.wikipedia.org/wiki/Operating_system), a deadlock occurs when a [process](https://en.wikipedia.org/wiki/Process_(computing)) or [thread](https://en.wikipedia.org/wiki/Thread_(computing)) enters a waiting [state](https://en.wikipedia.org/wiki/Process_state) because a requested [system resource](https://en.wikipedia.org/wiki/System_resource) is held by another waiting process, which in turn is waiting for another resource held by another waiting process. If a process is unable to change its state indefinitely because the resources requested by it are being used by another waiting process, then the system is said to be in a deadlock.[[3\]](https://en.wikipedia.org/wiki/Deadlock#cite_note-os_galvin-3) 



 **Deadlock can arise if following four conditions hold simultaneously (Necessary Conditions)**
***Mutual Exclusion:*** One or more than one resource are non-sharable (Only one process can use at a time)
***Hold and Wait:*** A process is holding at least one resource and waiting for resources.
***No Preemption:*** A resource cannot be taken from a process unless the process releases the resource.
***Circular Wait:*** A set of processes are waiting for each other in circular form. 



#### Process Status

 ![img](https://github.com/CyC2018/CS-Notes/raw/master/notes/pics/ProcessState.png) 

#### Thread Status

 ![线程的状态.jpg-59.9kB](http://static.zybuluo.com/Rico123/ot7o6218591iwj9py999hs1u/%E7%BA%BF%E7%A8%8B%E7%9A%84%E7%8A%B6%E6%80%81.jpg) 



####  **What are the different scheduling algorithms**

- *First-Come, First-Served (FCFS) Scheduling.*
- *Shortest-Job-Next (SJN) Scheduling.*
- *Priority Scheduling.* : Priority scheduling involves priority assignment to every process, and processes with higher priorities are carried out first, whereas tasks with equal priorities are carried out on a first-come-first-served (FCFS) or round robin basis.  
- *Shortest Remaining Time.*  : Round Robin is a [CPU scheduling algorithm](http://quiz.geeksforgeeks.org/gate-notes-operating-system-process-scheduling/) where each process is assigned a fixed time slot in a cyclic way. 
- *Round Robin(RR) Scheduling.* :: Round Robin is a [CPU scheduling algorithm](http://quiz.geeksforgeeks.org/gate-notes-operating-system-process-scheduling/) where each process is assigned a fixed time slot in a cyclic way. 
- *Multiple-Level Queues Scheduling.* : sets several queues with different priorities and a boost algorithm.



### VM

![1571103063767](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\1571103063767.png)

#### Physical addressing 

The main memory of a computer system is organized as an array of M contiguous byte-sized cells
Each byte has a unique physical address (PA)  started from 0

A CPU use physical addresses to access memory



#### Virtual Memory

 **virtual memory** (also **virtual storage**) is a [memory management](https://en.wikipedia.org/wiki/Memory_management_(operating_systems)) technique that provides an "idealized abstraction of the storage resources that are actually available on a given machine".

 The primary benefits of virtual memory include freeing applications from having to manage a shared memory space, increased security due to memory isolation .

#### Virtual addressing

Virtual addresses refer to the virtual store viewed by the process.  

the CPU accesses main memory by a virtual address (VA) which will be converted to PA to sent to main memory.

### Virtual Address

Through the idea of space division multiplexing, the system provides virtual memory for each program. The virtual address means the address in the virtual memory and the program running is depends on it. Virtual address will be translate to physical address by MMU in CPU.



#### Why Virtual Memory (VM)?

- Uses main memory efficiently
  Use DRAM as a cache for the parts of a virtual address space
- Simplifies memory management
  Each process gets the same uniform linear address space
- Isolates address spaces
  One process can’t interfere with another’s memory	
  User program cannot access privileged kernel information

#### Page

 **paging** is a [memory management](https://en.wikipedia.org/wiki/Memory_management) scheme by which a computer stores and retrieves data from [secondary storage](https://en.wikipedia.org/wiki/Computer_data_storage#Secondary_storage)[[a\]](https://en.wikipedia.org/wiki/Paging#cite_note-1) for use in [main memory](https://en.wikipedia.org/wiki/Computer_data_storage#Primary_storage). 

- The data on disk is partitioned into blocks  serve as the transfer units between the disk and the main memory

#### Address Translation

 Hardware converts virtual addresses to physical addresses via an OS-managed lookup table (**page table**)

page table -> physical memory (both in DRAM) ----->(if page fault) ->virtual memory in disk(each PA has a translated VA)

#### Page Faults

Definition:

 A **page fault** is a type of [exception](https://en.wikipedia.org/wiki/Exception_handling) raised by computer hardware when a running program accesses a [memory page](https://en.wikipedia.org/wiki/Memory_page) that is not currently mapped by the [memory management unit](https://en.wikipedia.org/wiki/Memory_management_unit) (MMU) into the [virtual address space](https://en.wikipedia.org/wiki/Virtual_address_space) of a process.  



- Page table entry indicates virtual address not in memory
- OS exception handler invoked to move data from disk into memory,and next time it will read the word from memory normally.(pages are swapped (copied) in and out )current process suspends, others can resumeOS has full control over placement, etc.)

#### Caching

Caching is the processing of utilizing a region of fast memory for a limited data and process. A cache memory is usually much efficient because of its high access speed.

#### Buffer overflow

 a **buffer overflow**  is an [anomaly](https://en.wikipedia.org/wiki/Anomaly_in_software) (异常) where a [program](https://en.wikipedia.org/wiki/Computer_program), while writing [data](https://en.wikipedia.org/wiki/Data_(computing)) to a [buffer](https://en.wikipedia.org/wiki/Buffer_(computer_science)), overruns the buffer's boundary and [overwrites](https://en.wikipedia.org/wiki/Overwrite) adjacent [memory](https://en.wikipedia.org/wiki/Main_memory) locations.  It may lead the process to run a poisonous code segment.



## C++ Feature

### Why C++ fast?

- Firstly, the variables and data structures in cpp is created on the system's stack, only when you use malloc(), you will use the spaces on the system's heap. And it's faster for system to use data on the stack.
- cpp's memory recycling is written by programmer himself, not like java. Thus we can implement this when and how it runs.
- Cpp can directly generate executable files and run them on the system, but languages like java run on JVM, and they will be compiled at runtime as well, which will affect the efficiency of the operation.



###  Polymorphism 

It is one of the property in oop between parent and children classes.

the parent define a virtual function, and the children classes rewrite it and  if we use the func in child's instance , it will act like what we defined in child class.



### Overloading

C++ allows a function or operator in the same scope have multiple definitions, called function overloading and operator overloading.

An overloaded declaration is that the func or operator has been declared in this scope before, but their parameters are not the same.

When you call an overloaded func or overloaded operator, the compiler decides which option to use by comparing the type of parameters you are using with the type of parameters in the definition.



### Memory Leak

Memory leak is when you new a pointer in a function or new a class instance which has a pointer in it, but when you end the life of the function or class instance, you do not delete the pointer, it will cause this part of the memory can not be accessed, but it still exists. . This is a memory leak.



example:

new a pointer but not delete it before the function process die.

new a pointer but get an error before the program delete it.



### Solution

#### RAII

*Resource Acquisition Is Initialization* or RAII, is a C++ programming technique[[1\]](https://en.cppreference.com/w/cpp/language/raii#cite_note-1)[[2\]](https://en.cppreference.com/w/cpp/language/raii#cite_note-2) which binds the life cycle of a resource that must be acquired before use (allocated heap memory, thread of execution, open socket, open file, locked mutex, disk space, database connection—anything that exists in limited supply) to the [lifetime](https://en.cppreference.com/w/cpp/language/lifetime) of an object. 

- ​	encapsulate each resource into a class, where 
  - the constructor acquires the resource and establishes all class invariants or throws an exception if that cannot be done,
  - the destructor releases the resource and never throws exceptions;
-  always use the resource via an instance of a RAII-class that either 
  -  has automatic storage duration or temporary lifetime itself, or 
  -  has lifetime that is bounded by the lifetime of an automatic or temporary object 

#### Shared Pointer (instance of raii)

`std::shared_ptr` is a smart pointer that retains shared ownership of an object through a pointer. Several `shared_ptr` objects may own the same object. The object is destroyed and its memory deallocated when either of the following happens:

- the last remaining `shared_ptr` owning the object is destroyed;
- the last remaining `shared_ptr` owning the object is assigned another pointer via [operator=](https://en.cppreference.com/w/cpp/memory/shared_ptr/operator%3D) or [reset()](https://en.cppreference.com/w/cpp/memory/shared_ptr/reset).



It implements a reference counter to decide when to deallocate the memory.



Circular reference will also cause memory leak.



-> weak_ptr



### Constant

 Constants provide a way to define a variable which cannot be modified by any other part in the code 

– #define: without memory consume .just replace the place.

– const: memory consume 



### Auto

The compiler will check the right value's type and automatically give it to 'auto'.



### Lambda Expression

It is the anonymous function.



### One tool is called Divide and Conquer 

to break up big computations into many little ones 



### Another tool is Abstraction 

Provide a higher-level concept that hides detail 



### Difference Between Cpp Reference vs Pointer

A reference variable can be said as another name for an existing variable. Once this variable is initialized the variable name can be used to refer to another variable. Pointers, on the other hand, are variables that store the address of a variable. Like any variable, these are declared first and then any variable’s address can be stored in them. 

 ![C++ Reference vs Pointers Infographics](https://cdn.educba.com/academy/wp-content/uploads/2018/09/C-Reference-vs-Pointers-1.jpg) 



## Data Structure

### Linked List

- Can grow or shrink in size during program execution.
- Can be made as long as needed. (Until system memory exhausts).
- easy to add and delete at the two ends, O(1) complexity
- hard to index and insert at the middle , O(n)  complexity

### Difference between Array & Linked List

The array is a container which holds the **fixed** number of similar data types. It is stored as n **sequential ** words at memory address.

Linked list relies on **references** where each node consists of the data and the references to the previous and next element. The reference field holds the address of prev and next elements. Thus it can stored randomly in memory.

|       BASIS FOR COMPARISON        |                            ARRAY                             |                         LINKED LIST                          |
| :-------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|               Basic               |   It is a consistent set of a fixed number of data items.    | It is an ordered set comprising a variable number of data items. |
|               Size                |                Specified during declaration.                 |    No need to specify; grow and shrink during execution.     |
|        Storage Allocation         |      Element location is allocated during compile time.      |        Element position is assigned during run time.         |
|       Order of the elements       |                     Stored consecutively                     |                       Stored randomly                        |
|       Accessing the element       | Direct or randomly accessed, i.e., Specify the array index or subscript. | Sequentially accessed, i.e., Traverse starting from the first node in the list by the pointer. |
| Insertion and deletion of element |           Slow relatively as shifting is required.           |                 Easier, fast and efficient.                  |
|             Searching             |               Binary search and linear search                |                        linear search                         |
|          Memory required          |                             less                             |                             More                             |
|        Memory Utilization         |                         Ineffective                          |                          Efficient                           |

### Vector

Vector is a dynamic array in cpp. 

![1571130721138](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\1571130721138.png)

if it's size is almost reach the capasity, vector will move the original data to a larger space

![1571130890877](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\1571130890877.png)







### Queue(dequeue -- double-ended queue) and Stack

one is first in first out, the other is first in last out.

they both can implement by the linked list or array.



### Map and Set

Both are implemented by RB-tree(红黑树),

**Map** is an associative container, stored in the form of key-value pairs, which is convenient for searching. The keyword plays the role of index. The value indicates the data associated with the index. The structure of the red-black tree can be realized. Completed in **O(log n)** time

**Set** is an associative container. Each element in the set contains only one keyword. **The set supports efficient keyword query operations—checking whether each given keyword is in the set**, and the set is a balanced binary search of the red-black tree. The tree structure implements, and supports efficient insertion and deletion. When inserting elements, the structure of the binary tree is automatically adjusted, so that the root node key value of each subtree is greater than the key value of all nodes of the left subtree, and is smaller than the key values of all nodes of the right subtree. In addition, it is necessary to ensure that the heights of the left subtree and the right subtree are equal.

**The balanced binary search tree uses the in-order traversal algorithm.** The retrieval efficiency is higher than that of vectors, deque, list, etc. In addition, the use of the in-order traversal can traverse the key values from small to large.

The main purpose of constructing a set is to retrieve it quickly. You can't modify the key directly.

### Tree

#### Pre-order traversal , in-order traversal , post-order traversal 

(according to the order of the three things of each node to make a distinction)



#### RB-tree

each node in the tree store a color (black or white) , to insure the balance of the tree. after insert or delete , need to do left-rotate or right-rotate to ensure the balance.



### AVL Tree

**An AVL tree is a binary search tree with self – balancing condition. The condition assures that the difference between the height of left and right sub tree cannot be greater than one. This difference between left sub tree and right sub tree is known as Balance Factor.**

using left and right rotation to keep balance



### Graph

### BFS (breadth-first search) & DFS (depth-first search)

BFS: 

 **Breadth-first search** (**BFS**) is an [algorithm](https://en.wikipedia.org/wiki/Algorithm) for traversing or searching [tree](https://en.wikipedia.org/wiki/Tree_data_structure) or [graph](https://en.wikipedia.org/wiki/Graph_(data_structure)) data structures. It starts at the [tree root](https://en.wikipedia.org/wiki/Tree_(data_structure)#Terminology) (or some arbitrary node of a graph, sometimes referred to as a 'search key'[[1\]](https://en.wikipedia.org/wiki/Breadth-first_search#cite_note-1)), and explores all of the neighbor nodes at the present depth prior to moving on to the nodes at the next depth level. 

 can be implemented by queue , and each reached node marked as "visited", add first element into the queue and add its neighbors into the queue and marked as visited.



DFS:

  The algorithm starts at the [root node](https://en.wikipedia.org/wiki/Tree_(data_structure)#Terminology) (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before [backtracking](https://en.wikipedia.org/wiki/Backtracking). 

 can be implemented by **stack**, as long as the stack is not empty, take one element out , find it neighbors. If the element hasn't been visited before, add it in the stack. Then do these actions recursively until the stack is empty.



### Represent

We can **represent the same graph by two different methods**:

1. Adjacency Matrix
2. Adjacency List

#### 1) Adjacency Matrix

A **graph can represent matrix elements**. Initially, all the elements of a matrix are zero. If there is an edge between two vertices (example vertex A and B) then we mark **'1'** to the element at the position MAB and MBA for undirected graph and for a directed graph, we mark **'1'** to the element at the position MAB.

**Example:**

![Graph image 4](https://www.includehelp.com/data-structure-tutorial/images/graph-4.jpg)

#### 2) Adjacency List

A graph can also be represented by a list. We need an array of the list and for each time if there is an edge exist between two vertices then we push one vertex to another vertex list and vice versa. 

![Graph image 5](https://www.includehelp.com/data-structure-tutorial/images/graph-5.jpg)



## Algorithm

### Merge Sort (Bottom-up merge sort) (O(nlogn))

It is a divide and conquer algorithm. For an array, we firstly  divide the input several pairs by its index, then bottom up, compare the size of the number within the pair which product a sorted pair, then merge two neighboring pairs by compare the elements in these two pair,and merge to a new sorted small list. Do the same thing as before. At last, we will get the sorted list.



### Selection Sort (O(n^2))

### Bubble Sort (O(n^2))

Bubble Sort is the simplest sorting algorithm that works by repeatedly swapping the adjacent elements if they are in wrong order.

Each iteration will move one element to the right place.

### Heap Sort (O(nlogn))

O(n) for making a heap of the original list, from [n/2]

O(nlogn) for sorting

First, make the unsorted array into a heap by  satisfying the order property (r_i >= r_2i and r_i >= r_2i+1). Then repeat the two steps until there are no more unsorted  elements.  

● Take the root (maximum) element off the heap by swapping it into its correct place in the array at the end of the unsorted elements.  

● Reheap the remaining unsorted elements. (This puts the next-largest element into the  root position). 



###  Insertion Sort  (O(n^2))

a[0] is used as a guard. A total of 5 operations were performed.
Every operation: first put the element copy content into a[0], and then compare this element with the sorted sequence from the end. Find your location in the sorted sequence and insert it. Or if you can't find it, you will continue until the guard. Means that this element is the smallest and should be placed in a[1] .
Each time, the sorted sequence will add an element. If there are n elements in the sequence, then you can do up to n times.



### Quick Sort (O(nlogn))

Quick sort is a highly efficient sorting algorithm and is based on partitioning of array of data into smaller arrays. A large array is partitioned into two arrays one of which holds values smaller than the specified value, based on which the partition is made and another array holds values greater than the pivot value.

Quick sort partitions an array and then calls itself recursively twice to sort the two resulting subarrays. This algorithm is quite efficient for large-sized data sets as its average and worst case complexity are of Ο(n^2), where **n** is the number of items.

Bad instance: reverse-order array



###  Dynamic Programming 

Dynamic Programming is mainly an optimization over plain [recursion](https://www.geeksforgeeks.org/recursion/). Wherever we see a recursive solution that has repeated calls for same inputs, we can optimize it using Dynamic Programming. The idea is to simply store the results of subproblems, so that we do not have to re-compute them when needed later. This simple optimization reduces time complexities from exponential to polynomial. For example, if we write simple recursive solution for [Fibonacci Numbers](https://www.geeksforgeeks.org/program-for-nth-fibonacci-number/), we get exponential time complexity and if we optimize it by storing solutions of subproblems, time complexity reduces to linear. 





