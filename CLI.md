#  ~ <a href="https://www.zsh.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/Zsh-art/logo/main/png/white_vertical_icon.png" alt="zsh" height="30"/></a> **CLI Basics (macOS) ~**

### **Basic Command Line Interface (CLI) Terminologies**

---

#### **CLI Basics**
- **Command Line Interface (CLI)**: A text-based interface to interact with your operating system.
- **Shell**: A program that processes commands (e.g., Bash, Zsh).
- **Terminal**: A program to access the CLI (e.g., Terminal on macOS).
- **Command**: An instruction given to the CLI to perform a task.

---

#### **File System**
- **Directory**: A folder that contains files or other directories.
- **Path**: The location of a file or directory in the filesystem.
  - **Absolute Path**: Full path from the root directory (e.g., `/Users/yourname/Desktop`).
  - **Relative Path**: Path relative to the current directory (e.g., `./Documents`).
- **Root Directory**: The top-most directory in the filesystem (`/` on Unix-based systems).

---

#### **Common Symbols**
- `~`: Refers to the home directory (e.g., `/Users/yourname`).
- `.`: Represents the current directory.
- `..`: Represents the parent directory.
- `/`: Directory separator in Unix-based systems.
- `*`: Wildcard to match multiple files (e.g., `*.txt` matches all `.txt` files).

---

#### **Key Processes**
- **Command**: An executable program or script.
- **Options/Flags**: Modifiers for commands (e.g., `ls -l`).
- **Arguments**: Data or paths passed to a command (e.g., `cat file.txt`).

---

#### **Navigation and Directory Management**  
```bash
ls                      # List directory contents
ls -la                  # List all files, including hidden files, with details
cd [folder_name]        # Move into a specified folder
cd ..                   # Move back to the parent directory
cd ~                    # Navigate to the home directory
cd /                    # Navigate to the root directory
pwd                     # Print the current working directory
mkdir [folder_name]     # Create a new directory
mkdir -p [parent/child] # Create nested directories
```

---

#### **File Management**  
```bash
touch [file_name]       # Create a new, empty file
mv [source] [destination]  # Move or rename files/folders
cp [source] [destination]  # Copy files/folders
cp -r [source_folder] [destination_folder]  # Copy folders recursively
rm [file_name]          # Remove files
rm -r [folder_name]     # Remove folders recursively
rm -rf [folder_name]    # Forcefully remove folders/files without confirmation
```

---

#### **Viewing and Editing Files**  
```bash
cat [file_name]         # Display the contents of a file
less [file_name]        # View file content one screen at a time
nano [file_name]        # Open a text editor for modifying files
open [file_name]        # Open a file in the default macOS application
head [file_name]        # Show the first 10 lines of a file
tail [file_name]        # Show the last 10 lines of a file
echo [text] > [file_name]   # Write text to a file (overwrite)
echo [text] >> [file_name]  # Append text to a file
```

---

#### **Permissions**  
```bash
chmod [permissions] [file_name]     # Change file permissions
chmod 755 file.sh                  # Give owner full access, others read/execute access
chmod +x file.sh                   # Add execute permissions
chown [user:group] [file_name]     # Change ownership of a file/directory
```

---

#### **Process Management**  
```bash
ps                      # Display running processes
ps aux                  # Show detailed information about all processes
kill [PID]              # Terminate a process by its Process ID (PID)
top                     # Display real-time system resource usage and processes
ctrl + c                # Stop a running program in the terminal
```

---

#### **Searching**  
```bash
find [directory] -name [file_name]  # Search for files by name
grep [pattern] [file_name]          # Search for a specific pattern in a file
grep -r [pattern] [directory]       # Search recursively in all files within a directory
```

---

#### **Archiving and Compression**  
```bash
tar -cvf archive.tar [files/directories]  # Create a tar archive
tar -xvf archive.tar                     # Extract a tar archive
zip -r archive.zip [folder_name]         # Compress a folder into a ZIP file
unzip archive.zip                        # Extract a ZIP file
```

---

#### **Networking and Downloads**  
```bash
ping [domain]            # Send network packets to check connectivity
curl [URL]               # Fetch content from a URL
curl -O [URL]            # Download a file from a URL
wget [URL]               # Download files from a URL (requires `brew install wget`)
```

---

#### **System Information**  
```bash
whoami                   # Display the current logged-in user
hostname                 # Display the system’s hostname
df -h                    # Show disk space usage in a human-readable format
du -sh [folder_name]     # Display the size of a directory
sw_vers                  # Display macOS version details
```

---

#### **Shortcuts**  
```bash
ctrl + l                # Clear the terminal screen
!!                      # Repeat the last command
ctrl + r                # Search the command history
cmd + k                 # Clear the terminal screen (Mac-specific)
```

---


#### *Additionally, it is important to note that there are two types of Shells.*

*The two primary types of shells are based on the operating system they serve:*

---

#### *A. Unix-Based Shells* 
- *Platforms: macOS, Linux, and other Unix-based systems.*
- *Popular Shells: Bash (default on many Linux distros), Zsh (default on macOS since Catalina), Fish (known for its user-friendly syntax).*
- *Features:* 
  - *Case-sensitive commands.*  
  - *Consistent use of forward slashes `/` for file paths.*  
  - *Built-in support for scripting and automation.*

---

#### *B. Windows Shells* 
- *Platforms: Windows OS.*  
- *Popular Shells: CMD (Command Prompt) and PowerShell (more advanced, supports scripting and object manipulation).*
- *Features:*
  - *Commands are not case-sensitive.*  
  - *Uses backslashes `\` for file paths.*  
  - *PowerShell introduces object-based command handling, making it more powerful than CMD.*  

---

### *Key Differences*    

| **Aspect**               | **Unix-Based Shells**                          | **Windows Shells**                          |
|--------------------------|-----------------------------------------------|---------------------------------------------|
| **File Paths**            | Use forward slashes `/` (e.g., `/home/user`) | Use backslashes `\` (e.g., `C:\Users\User`) |
| **Case Sensitivity**      | Case-sensitive (e.g., `file.txt` ≠ `File.txt`) | Not case-sensitive (`file.txt` = `File.txt`)|
| **Default Shell**         | Bash, Zsh, or other POSIX-compliant shells   | CMD or PowerShell                           |
| **Command Syntax**        | Simpler, shorter commands (e.g., `ls`, `cp`) | Longer, often verbose (e.g., `dir`, `copy`) |
| **Script Support**        | Supports shell scripting (Bash scripts)      | PowerShell supports advanced scripting      |
| **Environment Variables** | Accessed with `$` (e.g., `$HOME`)            | Accessed with `%` (e.g., `%USERPROFILE%`)   |
| **Output Handling**       | Text-based                                  | Object-based (PowerShell only)              |
| **Tools and Utilities**   | Extensive set of Unix-based tools (e.g., `grep`, `sed`) | Limited, requires third-party tools for some functionalities |
| **File Permissions**      | Built-in with `chmod` and `chown`            | Limited; uses GUI or ACL for permissions    |
| **Default Behavior**      | Designed for multi-user environments         | Primarily designed for single-user setups   |
| **Portability**           | Commands work across most Unix-like systems  | Commands are mostly Windows-specific        |  
| **Error Redirection**     | Consistently handled with `>`, `>>`, `2>`    | More complex syntax for redirection         |

---  