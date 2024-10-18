---
Title: Computer Networks Lab 2
Status: true
marker:
  - "[[btech]]"
  - "[[networking]]"
  - "[[Computer Networks]]"
  - "[[Linux]]"
  - "[[Package Manager]]"
tags: 
Date: 22-07-2024
Time: 08:12
---
# Computer Networks Lab 2
## Index
- [Content](#content)
  - [Installing Packages](#installing-packages)
  - [Using gedit](#using-gedit)
  - [Writing and Running a Hello World C Program](#writing-and-running-a-hello-world-c-program)
  - [Updating Applications](#updating-applications)
  - [Using Ping](#using-ping)
  - [Using Ipconfig](#using-ipconfig)
  - [Saving Output to a Text File](#saving-output-to-a-text-file)
- [References](#references)

## Content

### Installing Packages
To install packages on a Debian-based system like Ubuntu, you can use the `apt-get` command with `sudo` to gain administrative privileges. The general syntax is:

```bash
sudo apt-get install package_name
```

For example, to install the `curl` package, you would use:

```bash
sudo apt-get install curl
```

### Updating Applications
To keep your system and applications up to date, you can use the `apt-get` commands:

1. **Update the package lists:**

```bash
sudo apt-get update
```

2. **Upgrade the installed packages to their latest versions:**

```bash
sudo apt-get upgrade
```

3. **For a more comprehensive upgrade that handles changing dependencies:**

```bash
sudo apt-get dist-upgrade
```

For an advanced guide checkout [[Package Managers]].

### Using gedit
`gedit` is a simple text editor for the GNOME desktop environment. You can use it to create and edit text files. To open `gedit`, use the following command:

```bash
gedit filename
```

If the file does not exist, `gedit` will create it for you. For example, to create or edit a file named `example.txt`:

```bash
gedit example.txt
```


### Writing and Running a Hello World C Program
You can write and compile a simple C program using the terminal. Follow these steps:

1. **Create the C program file:**

```bash
gedit hello.c
```

2. **Write the Hello World program:**

```c
#include %3Cstdio.h%3E

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

Save and close the file.

3. **Compile the program using `gcc`:**

```bash
gcc hello.c -o hello
```

4. **Run the compiled program:**

```bash
./hello
```

You should see the output:

```
Hello, World!
```


### Using Ping
`ping` is a network utility used to test the reachability of a host on an IP network. It sends ICMP Echo Request messages and listens for ICMP Echo Reply messages.

To ping a host, use the command:

```bash
ping hostname_or_ip
```

For example, to ping Google's DNS server:

```bash
ping 8.8.8.8
```

### Using Ipconfig
On Unix-based systems, the equivalent of `ipconfig` on Windows is `ifconfig` or `ip`. These commands display the network configuration.

- **Using `ifconfig`:**

```bash
ifconfig
```

- **Using `ip`:**

```bash
ip addr show
```

### Saving Output to a Text File
You can save the output of any command to a text file using the `>` or `>>` operators.

- `>` will overwrite the file with the new content.
- `>>` will append the new content to the end of the file.

For example, to save the output of `ifconfig` to `network_info.txt`:

```bash
ifconfig > network_info.txt
```

To append the output of `ping` to the same file:

```bash
ping 8.8.8.8 >> network_info.txt
```

## References
- [Ubuntu Documentation](https://help.ubuntu.com)
- [GNU Compiler Collection Documentation](https://gcc.gnu.org)
- [gedit Documentation](https://help.gnome.org/users/gedit/stable/)
- [Linux man-pages project](https://man7.org/linux/man-pages/)

Add the rest of to the unix book guide