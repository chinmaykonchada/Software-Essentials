# 5 Types of Programming Languages
1. Procedural programming languages
    - A procedural language follows a sequence of statements or commands in order to achieve a desired output. 
        - example: C and C++, Java, Pascal.

2. Functional programming languages
    - Rather than focusing on the execution of statements, functional languages focus on the output of mathematical functions and evaluations. Each function–a reusable module of code–performs a specific task and returns a result.

3. Object-oriented programming languages (OOP)
    - This type of language treats a program as a group of objects composed of data and program elements, known as attributes and methods. Objects can be reused within a program or in other programs. 
        - Java, Python, PHP, C++, Ruby.
4. Scripting languages
    - Programmers use scripting languages to automate repetitive tasks, manage dynamic web content, or support processes in larger applications.
        - PHP, Ruby, Python, bash, Perl, Node.js.
5. Logic programming languages
    - Instead of telling a computer what to do, a logic programming language expresses a series of facts and rules to instruct the computer on how to make decisions.

# Statically typed languages vs Dynamically typed languages

    Statically typed languages
    - Data types are defined during compile time and cannot change during runtime. This is because of static type checking, which occurs before the code is executed. Statically typed languages include Java, C++, and C#. In these languages, you need to explicitly specify the data type of variables when you declare them. This helps ensure that you can't assign an object of a different type to a given reference. Statically typed languages offer more optimized code with less flexibility.
    
    Dynamically typed languages    
    - Data types can change during runtime, which is why type checking occurs while the code is being executed. Dynamically typed languages include Python, Ruby, and JavaScript. In these languages, errors that would prevent the script from running properly can still cause the language to compile. Dynamically typed languages offer more flexibility, but with less optimized code.

# Int Range
int can store from [-2^31, 2^31 - 1] because:
- there 32 bits for int, and highest significant bit is used for storing sign of the number, so if the rest of the bits are filled with 1's then num=2^30+2^29+2^28....+2^0 which is equal to 2^31 - 1 .
- but it is not the case with negative numbers bcz computer store negative numbers in 2's complement form, so -2^31 can be stored as follows: -2^31(1000000...0) is first complemented we get 0111111...1 then we add 1 to least significant bit we get (1000000...0) which is -2^31 . 

# Differences between Module, Library, Package, Framework, API, SDK.
    Real world example:
    Module = Your fingers
    Package= Your hands
    Library = Building your home
    Framework = Buying a home
- Module: It's a reusable piece of software that can be imported and used in other parts of a program.
- Library: A collection of related modules or functions that provide a specific set of functionalities, pre-written code that can be used to avoid writing code from scratch.
    -   Example: React.js, NumPy
- Package: A package is a collection of related modules or libraries bundled together for distribution and deployment.
    - Example: NumPy.
- Framework: A framework is like a structure that provides a base for the application development process. With the help of a framework, you can avoid writing everything from scratch.
    - Example: Express.js
- Api: An API specifies how software components should interact, allowing different software applications to communicate with each other
- Sdk:  A set of development tools that allows you to create applications for a specific platform. It typically includes APIs, libraries, documentation, and other resources.
    - Example: Android sdk.

# 3-way hand shake:
The 3-way handshake is a process used in the Transmission Control Protocol (TCP) to establish a reliable connection between a client and a server before data transmission begins. It ensures that both the client and the server are synchronized and ready to start communication.

Illustration of the 3-Way Handshake Process:
- Client → Server: Sends SYN (Sequence number = x)
- Server → Client: Sends SYN-ACK (Sequence number = y, Acknowledgment = x+1)
- Client → Server: Sends ACK (Acknowledgment = y+1)

here SYN (Synchronize) and ACK (Acknowledge).

**Scenario of the 3-Way Handshake:**
Example: When you type a URL in a web browser, the browser (client) initiates a 3-way handshake with the web server. This ensures that the connection is established before the requested webpage data is transmitted.

# Dynamic Host Configuration Protocol (DHCP)
The Dynamic Host Configuration Protocol (DHCP) is a network management protocol used to automate the process of configuring devices on IP networks. DHCP allows devices to automatically receive an IP address and other necessary network configuration details, such as the default gateway, subnet mask, and DNS servers, without manual intervention.

Examples:
- Device A:
MAC Address: 00:1A:2B:3C:4D:5E
IP Address: 192.168.1.10
- Device B:
    MAC Address: 00:1A:2B:3C:4D:5F
    IP Address: 192.168.1.11

In the example above, each device has a unique MAC address, and within the same local network, they have unique IP addresses. However, if **Device A moves to a different network, its IP address may change (due to DHCP), but its MAC address will remain the same.**