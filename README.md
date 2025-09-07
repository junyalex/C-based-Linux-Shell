# Project Overview 
This is a C-based Unix shell implementation developed throughout the Winter 2025 semester. 
This project involves building a fully functional shell called mysh that provides a comprehensive range of functionality matching that of other built-in shells.
The shell supports built-in commands, environment variables, file system operations, process management, pipes, and network communication.

# Core Features
- Input validation : Command is limited to 128-characters.
- User interface : Interactive prompt ( $mysh )
- Signal Handling
- Error Management

# Basic Commands
- echo [text] : Display text to stdout
- exit : Terminate the shell

# File System Commands
- ls [path] [--rec] [--d depth] [--f substring] : List directory contents with options
- cd [path] : Change directory (supports ., .., ..., ....)
- cat [file] : Display file contents or read from stdin
- wc [file] : Count words, characters, and lines

# Process Management
- ps : list processes launched by shell
- kill [pid] [signal] : send signals to processes
- Background processes (&)

# Network Commands: Client-server chat system
- start-server [port] : Start a chat server on specified port
- close-server : Terminate the current server
- start-client [port] [hostname] : Connect to a chat server
- send [port] [hostname] [message] : Send message to server

# Advanced Features
- Pipes: Chain commands using "|" operator (Multiple pipes are supported)
```bash
mysh$ cat file.txt | grep hello | wc
```
- Dynamic environment variables: Initialize variables with $var expansion
- Memory Management: Dynamic allocation for variables and processes

# External Commands 
- Any command not implemented as built-in is executed using the underlying Linux system binaries (via exec).
- For example, 
```bash
mysh$ grep keyword file.txt
mysh$ sort data.txt
```

# Installation & Setup
- Operating System : Linux
```bash
 # clone repository
git clone https://github.com/junyalex/Linux-Shell.git

# Navigate to source directory
cd src

# Creates an executable file called "mysh".
make

# Run the shell
./mysh
```
# Compilation 
The project uses the following compiler flags for strict debugging and memory safety. 
```bash
-g -Wall -Wextra -Werror -fsanitize=address,leak,object-size,bounds-strict,undefined -fsanitize-address-use-after-scope
```

