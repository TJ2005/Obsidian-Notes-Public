### **EXPERIMENT 1: 64-bit vs 32-bit Operating Systems**

**Q) What do you mean by 64-bit operating system and how does it differ from 32-bit operating systems in various aspects like performance and timing?**

1. **Memory Addressing:**
    
    - A **32-bit OS** can address a maximum of **2^32** memory locations, equating to **4 GB** of RAM (although certain systems may limit this further).
    - A **64-bit OS** can theoretically address **2^64** memory locations, or **18.4 million TB** of RAM, offering a massive increase in memory addressability.
2. **Performance:**
    
    - With a **64-bit OS**, memory-intensive applications (like large databases, virtual machines, and advanced video editing software) can run more efficiently, as there is more addressable memory available.
    - In a **32-bit OS**, once the system runs out of addressable memory, performance significantly degrades, and applications may crash or fail to execute properly.
3. **Data Processing:**
    
    - A **32-bit processor** can handle **32 bits of data at once**, limiting the amount of data processed in a single clock cycle, thereby constraining performance, especially for complex applications.
    - A **64-bit processor** can handle **64 bits of data at once**, enabling faster execution of instructions and improved processing for large datasets.
4. **Clock Cycles:**
    
    - In a **32-bit OS**, the processor handles smaller chunks of data, meaning operations may take more clock cycles to complete.
    - In a **64-bit OS**, the processor can handle larger chunks of data in one cycle, reducing the number of clock cycles for certain operations, though the exact effect depends on the application.

---

### **Commands to Execute in CMD:**

Here are the steps and associated commands for the task list:

1. **Create a directory or folder, change directory**:
    
    - Command to create a folder:
        
        ```cmd
        mkdir NewFolder
        ```
        
    - Command to change directory:
        
        ```cmd
        cd NewFolder
        ```
        
2. **Create a file in the above folder**:
    
    - Command to create a file:
        
        ```cmd
        echo.> file.txt
        ```
        
3. **Type some data in the file created**:
    
    - Command to edit the file:
        
        ```cmd
        notepad file.txt
        ```
        
4. **Read the data**:
    
    - Command to read the file:
        
        ```cmd
        type file.txt
        ```
        
5. **Rename the file and folder**:
    
    - Command to rename a file:
        
        ```cmd
        ren file.txt newfile.txt
        ```
        
    - Command to rename a folder:
        
        ```cmd
        ren NewFolder NewFolderRenamed
        ```
        
6. **Create second folder and copy file from first folder to the second folder**:
    
    - Command to create a second folder:
        
        ```cmd
        mkdir SecondFolder
        ```
        
    - Command to copy file:
        
        ```cmd
        copy newfile.txt SecondFolder\
        ```
        
7. **Delete folder**:
    
    - Command to delete a folder:
        
        ```cmd
        rmdir NewFolderRenamed
        ```
        
8. **Open an application**:
    
    - Command to open Notepad:
        
        ```cmd
        start notepad
        ```
        
9. **Close an application**:
    
    - Command to close an application (for Notepad):
        
        ```cmd
        taskkill /IM notepad.exe
        ```
        
10. **Access different drives**:
    

- Command to switch drives:
    
    ```cmd
    D:   (for drive D)
    ```
    

11. **Create 2 files and compare them (FC: File Compare)**:

- Command to create two files:
    
    ```cmd
    echo Hello > file1.txt
    echo Hello > file2.txt
    ```
    
- Command to compare them:
    
    ```cmd
    fc file1.txt file2.txt
    ```
    

12. **Network troubleshooting (IPCONFIG)**:

- Command to display IP configuration:
    
    ```cmd
    ipconfig
    ```
    

13. **NETSTAT command in CMD**:

- Command to view network connections:
    
    ```cmd
    netstat
    ```
    

14. **PING command**:

- Command to ping an address:
    
    ```cmd
    ping www.google.com
    ```
    

15. **TRACERT nmims.edu**:

- Command for trace route:
    
    ```cmd
    tracert nmims.edu
    ```
    

16. **SYSTEMINFO**:

- Command to display system information:
    
    ```cmd
    systeminfo
    ```
    

17. **SFC (System File Checker)**:

- Command to check for system file integrity:
    
    ```cmd
    sfc /scannow
    ```
    

18. **Tasklist command**:

- Command to list running tasks:
    
    ```cmd
    tasklist
    ```
    

19. **Shutdown using CMD**:

- Command to shutdown the system:
    
    ```cmd
    shutdown /s
    ```
    

---

![[IMG-20250730000528879.png]]