# Comprehensive Linux/Unix Command Guide for IBPS SO IT Officer Exam 2026

This comprehensive guide is meticulously structured for aspirants preparing for the **IBPS SO IT Officer Exam 2026**. In banking exams, the Professional Knowledge section heavily features Linux/Unix architecture, core system operations, and system administration commands. 

Rather than rote memorization (mugging up), this guide breaks down the **Top 100 Linux Commands** into logical, functional categories with intuitive mnemonics, clear syntax, practical exam-oriented examples, and conceptual breakdowns to ensure absolute mastery.

---

## Part 1: Core Linux/Unix Fundamentals for IBPS SO IT

Before diving into commands, you must keep these highly testable concepts in mind:
1. **Case Sensitivity:** Linux commands, flags, and filenames are strictly case-sensitive (`ls` is not the same as `LS`).
2. **Everything is a File:** In Unix/Linux, hardware devices, directories, and regular documents are all treated as files.
3. **The Shell vs. Kernel:** The **Kernel** is the core of the OS interfacing with hardware; the **Shell** is the command-line interpreter translating your commands into kernel actions (e.g., Bash, Sh, Csh).
4. **Standard Streams:** - `stdin` (Standard Input): File Descriptor `0` (Keyboard)
   - `stdout` (Standard Output): File Descriptor `1` (Screen)
   - `stderr` (Standard Error): File Descriptor `2` (Screen error messages)

---

## Part 2: Categorized Top 100 Linux Commands

To make learning systematic, the 100 commands are organized into 8 functional modules:
1. **Directory & Navigation Commands** (1–12)
2. **File Operations & Text Editing** (13–30)
3. **Text Processing & Filtering (The Data Crunchers)** (31–43)
4. **File Permissions & Ownership (Highly Tested)** (44–53)
5. **Process Management & System Monitoring** (54–69)
6. **System Administration & Disk Management** (70–82)
7. **Networking & Troubleshooting** (83–94)
8. **Advanced Utilities & Shell Built-ins** (95–100)

---

### Category 1: Directory & Navigation Commands (1–12)
*Mnemonic for Navigation:* **"People Can Always Make Real Paths"** (**P**wd, **C**d, **A**lways/ls, **M**kdir, **R**mdir, **P**ath/tree).

#### 1. `pwd` (Print Working Directory)
* **What it does:** Tells you exactly which directory you are currently standing in.
* **Mnemonic:** **P**rint **W**orking **D**irectory.
* **Syntax:** `pwd`
* **Example:** ```bash
    $ pwd
    /home/it_officer/documents
    ```
* **Exam Point:** Returns the absolute path starting from the root directory (`/`).

#### 2. `cd` (Change Directory)
* **What it does:** Navigates between directories (folders).
* **Syntax:** `cd [directory_path]`
* **Important Shortcuts:**
    * `cd ~` or just `cd` : Takes you to the Home directory.
    * `cd ..` : Moves up one level to the parent directory.
    * `cd -` : Toggles back to the previous working directory.
* **Example:** Move up to parent directory:
    ```bash
    $ cd ..
    ```

#### 3. `ls` (List)
* **What it does:** Lists the contents (files and subdirectories) of a directory.
* **Syntax:** `ls [options]`
* **Crucial Flags for Exam:**
    * `-a` : Show **all** files (including hidden files starting with a dot `.`).
    * `-l` : Long listing format (shows permissions, owner, size, timestamp).
    * `-lh` : Human-readable sizes (e.g., 2K, 45M).
    * `-R` : **Recursive** listing (shows contents of all subdirectories).
* **Example:** List hidden and detailed files:
    ```bash
    $ ls -al
    ```

#### 4. `mkdir` (Make Directory)
* **What it does:** Creates a new folder/directory.
* **Syntax:** `mkdir [options] directory_name`
* **Crucial Flag:** `-p` (Parents - creates nested subdirectories all at once without throwing an error if they exist).
* **Example:** Create a path `ibps/2026/it_section`:
    ```bash
    $ mkdir -p ibps/2026/it_section
    ```

#### 5. `rmdir` (Remove Directory)
* **What it does:** Deletes an **empty** directory.
* **Syntax:** `rmdir directory_name`
* **Exam Point:** If the directory has even a single file inside it, `rmdir` will fail. For non-empty directories, use `rm -r`.
* **Example:**
    ```bash
    $ rmdir empty_folder
    ```

#### 6. `tree`
* **What it does:** Displays directories and files in a visual depth-indented tree structure.
* **Syntax:** `tree`
* **Example:**
    ```bash
    $ tree
    .
    ├── ibps
    │   └── 2026
    └── notes.txt
    ```

#### 7. `dirname`
* **What it does:** Strips the last level (filename or trailing folder) from a path, giving you only the directory path.
* **Syntax:** `dirname /path/to/file`
* **Example:**
    ```bash
    $ dirname /home/user/docs/report.txt
    /home/user/docs
    ```

#### 8. `basename`
* **What it does:** Strips directory paths and gives you **just** the filename or final folder name.
* **Syntax:** `basename /path/to/file`
* **Example:**
    ```bash
    $ basename /home/user/docs/report.txt
    report.txt
    ```

#### 9. `pushd` (Push Directory)
* **What it does:** Saves the current working directory onto a stack and changes to a new target directory.
* **Syntax:** `pushd /target/directory`

#### 10. `popd` (Pop Directory)
* **What it does:** Removes the top directory from the directory stack and returns you back to it. Useful for automated shell scripting.
* **Syntax:** `popd`

#### 11. `dirs`
* **What it does:** Displays the list of currently remembered directories on the navigation stack managed by `pushd` and `popd`.
* **Syntax:** `dirs`

#### 12. `pathchk`
* **What it does:** Checks whether a specific filename or path is valid and portable across other Unix/Linux systems.
* **Syntax:** `pathchk filename`

---

### Category 2: File Operations & Text Editing (13–30)

#### 13. `touch`
* **What it does:** Creates an empty file or updates the access/modification timestamp of an existing file.
* **Syntax:** `touch filename`
* **Example:**
    ```bash
    $ touch question_bank.txt
    ```

#### 14. `cp` (Copy)
* **What it does:** Copies files or directories from a source to a destination.
* **Syntax:** `cp [options] source destination`
* **Crucial Flags:**
    * `-r` or `-R` : Recursive (mandatory when copying whole folders).
    * `-i` : Interactive (prompts before overwriting an existing file).
* **Example:** Copy a directory recursively:
    ```bash
    $ cp -r /tmp/notes /home/it_officer/
    ```

#### 15. `mv` (Move / Rename)
* **What it does:** Moves a file/directory to a different location, or **renames** it if the destination is in the same directory.
* **Syntax:** `mv source destination`
* **Example (Rename):** `mv old_name.txt new_name.txt`
* **Example (Move):** `mv bank.txt /home/secure/`

#### 16. `rm` (Remove)
* **What it does:** Deletes files or directories permanentely. (Linux has no recycle bin via command line!).
* **Syntax:** `rm [options] filename`
* **Crucial Flags:**
    * `-r` : Recursive (deletes folders and everything inside them).
    * `-f` : Force (deletes without prompting or showing errors).
* **Danger Alert:** `rm -rf /` will wipe out the entire operating system if run as root.

#### 17. `cat` (Concatenate)
* **What it does:** Displays file content on the terminal screen. It can also merge multiple files.
* **Syntax:** `cat filename`
* **Crucial Flags:**
    * `-n` : Displays line numbers along with the content.
* **Example:** `cat -n config.conf`

#### 18. `tac` (Reverse Cat)
* **What it does:** Displays file contents backwards (bottom line first, top line last). It is literally `cat` spelled backwards!
* **Syntax:** `tac filename`

#### 19. `more`
* **What it does:** A page-by-page file viewer. Useful for viewing long text files.
* **Navigation:** Press `Spacebar` to go to the next page, `Enter` to scroll line by line, `q` to quit.
* **Exam Point:** You can only move **forward** in `more`.

#### 20. `less`
* **What it does:** An advanced file viewer that allows both forward and **backward** movement.
* **Famous Unix Saying:** *"Less is more, more or less."* (Because `less` has more features than `more`).
* **Navigation:** Use Arrow keys to move up and down.

#### 21. `head`
* **What it does:** Displays the top/beginning lines of a file.
* **Default behavior:** Shows the first **10 lines**.
* **Crucial Flag:** `-n [number]` (specifies how many lines to show).
* **Example:** Show first 5 lines:
    ```bash
    $ head -n 5 log.txt
    ```

#### 22. `tail`
* **What it does:** Displays the bottom/ending lines of a file.
* **Default behavior:** Shows the last **10 lines**.
* **Crucial Flag:** `-f` (Follow mode: keeps the file open and displays new lines added in real-time. Extensively used by system admins to monitor active system logs).
* **Example:** `tail -f /var/log/syslog`

#### 23. `nano`
* **What it does:** A simple, beginner-friendly terminal-based text editor.
* **Syntax:** `nano filename.txt`

#### 24. `vi` / `vim`
* **What it does:** A highly powerful, standard visual text editor found natively in almost all Unix systems.
* **Exam States/Modes:** `vi` operates in modes:
    1.  **Command Mode:** Default mode when opened. Pressing keys runs commands.
    2.  **Insert Mode:** Used to type text. Enter by pressing `i`. Return to command mode using `Esc`.
    3.  **Last Line/Ex Mode:** Type commands by pressing `:` (e.g., `:wq` to save and quit, `:q!` to quit without saving).

#### 25. `file`
* **What it does:** Examines a file and determines its type (e.g., ASCII text, ELF executable, JPEG image, zip archive).
* **Exam Point:** Linux does not rely on extensions like `.exe` or `.txt` to know what a file is; it reads internal magic numbers. `file` decodes this.
* **Example:** `file script` -> outputs `script: Bourne-Again shell script text executable`.

#### 26. `stat`
* **What it does:** Displays extremely detailed status and metadata of a file, including exact size, inode number, links, and Timestamps (Access, Modify, Change - AMC).
* **Syntax:** `stat filename`

#### 27. `ln` (Link)
* **What it does:** Creates a link (shortcut) to an existing file.
* **Types of links (Extensively asked in IBPS SO):**
    1.  **Hard Link (Default):** Shares the exact same Inode number as the original file. If you delete the original file, the hard link still works. Cannot link directories or cross file systems.
    2.  **Soft Link / Symbolic Link (`-s` flag):** A true pointer shortcut. Has a unique inode. If you delete the original file, the soft link breaks ("dangling link"). Can link directories.
* **Example (Soft Link):** `ln -s original.txt shortcut.txt`

#### 28. `split`
* **What it does:** Splits a large file into smaller chunks based on size or line count.
* **Syntax:** `split -l 1000 bigfile.txt small_chunk_`

#### 29. `csplit` (Context Split)
* **What it does:** Splits a file into sections determined by context lines, matching a specific regular expression pattern rather than fixed sizes.
* **Syntax:** `csplit exam_dump.txt '/Question/' '{*}'`

#### 30. `shred`
* **What it does:** Overwrites a file multiple times with random data before deleting it, making it nearly impossible to recover via forensic tools.
* **Syntax:** `shred -u confidential.dat` (The `-u` removes the file after overwriting).

---

### Category 3: Text Processing & Filtering / The Data Crunchers (31–43)

#### 31. `grep` (Global Regular Expression Print)
* **What it does:** Searches for specific text patterns inside files using regular expressions.
* **Syntax:** `grep [options] "pattern" filename`
* **Crucial Flags (Must remember for exam):**
    * `-i` : Ignore case (treats 'linux' and 'Linux' as identical).
    * `-v` : Invert match (prints lines that **do not** contain the pattern).
    * `-c` : Count (shows only the number of matching lines).
    * `-n` : Print line numbers alongside matching lines.
* **Example:** Find all lines containing "ERROR" case-insensitively:
    ```bash
    $ grep -in "error" server.log
    ```

#### 32. `egrep` & `fgrep`
* **What they do:** Derivatives of grep. 
    * `egrep` is Extended Grep (equivalent to `grep -E`), supporting advanced regex characters like `|`, `+`, `?`.
    * `fgrep` is Fixed/Fast Grep (equivalent to `grep -F`), treats all characters as literal strings (much faster, skips parsing regex syntax).

#### 33. `awk`
* **What it does:** A complete pattern scanning and text processing language. It processes files line-by-line, column-by-column.
* **Exam Core Concept:** It automatically separates data fields/columns using default whitespace. `$1` is column 1, `$2` is column 2, etc.
* **Example:** Print only the username (column 1) from a colon-separated file like `/etc/passwd`:
    ```bash
    $ awk -F: '{print $1}' /etc/passwd
    ```

#### 34. `sed` (Stream Editor)
* **What it does:** Modifies text on the fly (find, replace, insert, delete) without opening the file manually.
* **Core Syntax for Find & Replace:** `sed 's/old_word/new_word/g' file` (`s` stands for substitute, `g` for global).
* **Example:** Replace "2025" with "2026":
    ```bash
    $ sed 's/2025/2026/g' test.txt
    ```

#### 35. `wc` (Word Count)
* **What it does:** Counts lines, words, and characters in a file.
* **Crucial Flags:**
    * `-l` : Count lines.
    * `-w` : Count words.
    * `-c` : Count bytes/characters.
* **Example:** Count how many lines are in a log file:
    ```bash
    $ wc -l transactions.log
    ```

#### 36. `sort`
* **What it does:** Sorts lines of text alphabetically or numerically.
* **Crucial Flags:**
    * `-n` : Sort numerically (otherwise `10` comes before `2` alphabetically).
    * `-r` : Reverse the sort order (descending).
* **Example:** Sort student marks numerically in descending order:
    ```bash
    $ sort -nr marks.txt
    ```

#### 37. `uniq` (Unique)
* **What it does:** Detects and removes adjacent duplicate lines from a file.
* **CRITICAL Exam Rule:** `uniq` **only** removes duplicates that are right next to each other! Therefore, you must almost always run `sort` before piping data into `uniq`.
* **Flags:** `-u` (only show unique lines), `-d` (only show duplicated lines), `-c` (count occurrences).
* **Example:**
    ```bash
    $ sort list.txt | uniq -c
    ```

#### 38. `cut`
* **What it does:** Slices out sections/columns from each line of a file.
* **Flags:** * `-d` : Delimiter (the separator character, e.g., `,` or `:`).
    * `-f` : Field number to extract.
* **Example:** Extract the first and third columns of a CSV file:
    ```bash
    $ cut -d ',' -f 1,3 employees.csv
    ```

#### 39. `paste`
* **What it does:** Merges lines of files sequentially side-by-side (opposite of `cat` which appends files vertically).
* **Syntax:** `paste file1.txt file2.txt`

#### 40. `tr` (Translate)
* **What it does:** Translates, deletes, or squeezes characters from standard input. It does not accept filenames directly; it works only via redirection/pipes.
* **Example:** Convert text to uppercase:
    ```bash
    $ cat file.txt | tr 'a-z' 'A-Z'
    ```

#### 41. `tee`
* **What it does:** Acts like a T-shaped pipe split fitting. It reads standard input and writes it to **both** standard output (the screen) **and** a specified file simultaneously.
* **Example:**
    ```bash
    $ ls -l | tee file_list.txt
    ```

#### 42. `diff` (Difference)
* **What it does:** Compares two files line-by-line and highlights the exact differences between them.
* **Syntax:** `diff file1.txt file2.txt`

#### 43. `comm`
* **What it does:** Compares two sorted files and displays a three-column output: lines unique to file1, lines unique to file2, and lines common to both.
* **Syntax:** `comm file1.txt file2.txt`

---

### Category 4: File Permissions & Ownership / Security (44–53)
*This section is heavily represented in every IBPS SO exam. Understand the math behind permissions.*

> **Concept Refresher:** > When you run `ls -l`, you see permissions like `-rwxr-xr--`. 
> - First character: File type (`-` = regular file, `d` = directory, `l` = symbolic link).
> - Next 9 characters are broken into 3 groups: **User/Owner** (rwx), **Group** (r-x), **Others** (r--).
> - **Octal values:** `r = 4`, `w = 2`, `x = 1`, `- = 0`.

#### 44. `chmod` (Change Mode)
* **What it does:** Changes the read, write, and execute permissions of a file or directory.
* **Syntax (Symbolic):** `chmod u+x file.txt` (Adds execution permission to user).
* **Syntax (Absolute/Numeric):** `chmod 754 file.txt`
    * 7 = 4+2+1 (User gets Read+Write+Execute)
    * 5 = 4+0+1 (Group gets Read+Execute)
    * 4 = 4+0+0 (Others get Read only)
* **Example:** Give full permissions to owner, read/execute to group, nothing to others:
    ```bash
    $ chmod 750 secure_script.sh
    ```

#### 45. `chown` (Change Owner)
* **What it does:** Changes the user ownership of a file or directory. Requires root privileges.
* **Syntax:** `chown new_owner filename`
* **Example:** `chown administrator data.db`

#### 46. `chgrp` (Change Group)
* **What it does:** Changes the group ownership of a file or directory.
* **Syntax:** `chgrp engineering reports.xlsx`

#### 47. `umask` (User Mask)
* **What it does:** Defines the **default** permissions assigned to newly created files and directories.
* **How it works (Exam Math):** * Maximum baseline for directories is `777`, for files is `666`.
    * Default Permission = Baseline minus Umask.
    * *Example:* If `umask` is `022`, a new file gets `666 - 022 = 644` (`rw-r--r--`).
* **Syntax:** `umask` (displays current mask).

#### 48. `chattr` (Change Attribute)
* **What it does:** Changes advanced file attributes on a Linux file system (e.g., making a file completely immutable, even to the root user).
* **Crucial Flag:** `+i` (Immutable attribute: makes the file undeletable and unmodifiable).
* **Example:** Lock system config file:
    ```bash
    $ chattr +i /etc/resolv.conf
    ```

#### 49. `lsattr`
* **What it does:** Lists the specific attributes of a file set by `chattr`.
* **Syntax:** `lsattr filename`

#### 50. `su` (Switch User)
* **What it does:** Switches the current shell session to another user account (usually the Superuser / root account if run without options).
* **Syntax:** `su - username` (The `-` ensures a clean environment login as if they logged in directly).

#### 51. `sudo` (Superuser Do)
* **What it does:** Permits an authorized user to execute a single command with root administrative privileges without switching users completely.
* **Syntax:** `sudo apt update`

#### 52. `passwd`
* **What it does:** Changes the password of a user account.
* **Syntax:** `passwd [username]`

#### 53. `whoami`
* **What it does:** Prints the exact effective username of the current user running the terminal.
* **Syntax:** `whoami`

---

### Category 5: Process Management & System Monitoring (54–69)

#### 54. `ps` (Process Status)
* **What it does:** Captures a static snapshot of currently running active processes.
* **Crucial Flags for Exam:**
    * `ps -ef` or `ps aux` : Lists every running process on the system with user details, Process IDs (PID), and Parent Process IDs (PPID).
* **Example:** Find if the oracle database service is running:
    ```bash
    $ ps -ef | grep oracle
    ```

#### 55. `top`
* **What it does:** Provides a dynamic, interactive real-time view of system processes, CPU usage, memory utilization, and uptime metrics.
* **Exit:** Press `q` to close.

#### 56. `htop`
* **What it does:** An enhanced, color-coded interactive process viewer. It is a visually intuitive version of `top`.

#### 57. `kill`
* **What it does:** Terminates or sends a control signal to a running process using its Process ID (PID).
* **Crucial Signals to Memorize:**
    * `Signal 15 (SIGTERM)` : Default signal. Tells process to clean up and close gracefully.
    * `Signal 9 (SIGKILL)` : Hard kill. Immediately terminates the process without saving work.
* **Example:** Force kill a stuck process with PID 2045:
    ```bash
    $ kill -9 2045
    ```

#### 58. `pkill`
* **What it does:** Terminates processes based on their actual **name** instead of numeric PIDs.
* **Example:** Kill all instances of the chrome browser:
    ```bash
    $ pkill chrome
    ```

#### 59. `killall`
* **What it does:** Kills all processes running a specified command/name precisely. (Similar to `pkill`).

#### 60. `bg` (Background)
* **What it does:** Resumes a suspended/paused job and keeps it running execution in the background.
* **Syntax:** `bg %1`

#### 61. `fg` (Foreground)
* **What it does:** Brings a background or suspended process back into the active foreground terminal control.
* **Syntax:** `fg %1`

#### 62. `jobs`
* **What it does:** Lists all active or suspended command tasks managed under the current terminal shell session.
* **Example:**
    ```bash
    $ jobs
    [1]+  Stopped                 nano notes.txt
    ```

#### 63. `nohup` (No Hang Up)
* **What it does:** Runs a command that will ignore the HUP (Hangup) signal. This ensures the script or process continues executing even after the terminal is closed or user logs out.
* **Example:**
    ```bash
    $ nohup ./backup_script.sh &
    ```
    *(Note: `&` at the end puts the job directly into the background).*

#### 64. `nice`
* **What it does:** Launches a process with a customized priority tier (Niceness value).
* **Niceness Range:** Ranges from `-20` (highest priority, least nice) to `19` (lowest priority, very nice to other processes). Default is `0`.
* **Example:** Run a backup with low priority:
    ```bash
    $ nice -n 10 ./backup.sh
    ```

#### 65. `renice`
* **What it does:** Modifies the scheduling priority/niceness value of an **already running** process using its PID.
* **Syntax:** `renice +5 -p 1234`

#### 66. `uptime`
* **What it does:** Tells you how long the server has been running without a reboot, how many users are logged in, and the system **Load Average** for the past 1, 5, and 15 minutes.
* **Syntax:** `uptime`

#### 67. `free`
* **What it does:** Displays the total amount of free and used physical RAM and Swap space in the system.
* **Crucial Flag:** `-m` (shows data in Megabytes), `-g` (Gigabytes).
* **Example:** `free -m`

#### 68. `vmstat` (Virtual Memory Statistics)
* **What it does:** Reports detailed summaries regarding processes, system memory, paging/swap activities, block IO operations, and CPU activity.
* **Syntax:** `vmstat 2` (updates every 2 seconds).

#### 69. `iostat` (Input/Output Statistics)
* **What it does:** Monitors storage device input/output loading by tracking how long disks are active relative to their data transfer rates.

---

### Category 6: System Administration & Disk Management (70–82)

#### 70. `df` (Disk Free)
* **What it does:** Displays total available and consumed disk space across all mounted storage file systems.
* **Crucial Flag:** `-h` (Human Readable format).
* **Example:** `df -h`

#### 71. `du` (Disk Usage)
* **What it does:** Estimates and counts space utilization of specific individual files and directories.
* **Crucial Flag:** `-sh` (Summary, Human-readable).
* **Example:** Find how much space a folder takes:
    ```bash
    $ du -sh /var/log
    ```

#### 72. `fdisk`
* **What it does:** A command-line menu-driven utility used for viewing, creating, or modifying hard drive storage partition tables.
* **Syntax:** `sudo fdisk -l` (lists all disks and partition details).

#### 73. `mkfs` (Make File System)
* **What it does:** Formats a disk partition with a Linux filesystem (e.g., ext4, xfs). Equivalant to formatting a drive in Windows.
* **Syntax:** `sudo mkfs.ext4 /dev/sdb1`

#### 74. `mount`
* **What it does:** Attaches a physical storage partition or USB drive to a specific directory point in the main Linux directory tree.
* **Syntax:** `mount /dev/sdb1 /mnt/usb`

#### 75. `umount` (Unmount)
* **What it does:** Detaches a mounted file system safely from the directory tree.
* **Exam Point Spelling Check:** Notice there is **no 'n'** after 'u' — it is `umount`, not "unmount".

#### 76. `tar` (Tape Archive)
* **What it does:** Packs multiple files or directories into a single unified archive file (often called a Tarball), and can handle compression.
* **Crucial Flags (Extensively Tested):**
    * `-c` : Create a new archive.
    * `-x` : Extract an archive.
    * `-v` : Verbose (show files being packed/unpacked).
    * `-f` : File name specification (must be the last flag before the file name).
    * `-z` : Compress/Decompress using gzip (produces `.tar.gz`).
* **Example (Create):** `tar -cvzf archive.tar.gz /home/docs`
* **Example (Extract):** `tar -xvzf archive.tar.gz`

#### 77. `gzip` & `gunzip`
* **What they do:** Compress (`gzip`) and decompress (`gunzip`) individual files.
* **Exam Point:** Unlike zip, `gzip` compresses the file directly in-place and appends a `.gz` extension, replacing the original file.

#### 78. `uname` (Unix Name)
* **What it does:** Prints core detailed identification facts about the underlying operating system and Linux kernel version.
* **Crucial Flag:** `-a` (All system details).
* **Example:** `uname -a` -> prints kernel version, architecture (x86_64), OS type.

#### 79. `hostname`
* **What it does:** Shows or configures the network identification name assigned to the server host.

#### 80. `shutdown`
* **What it does:** Shuts down or safely restarts the operating system after a scheduled grace period.
* **Flags:** `-h now` (halt/poweroff immediately), `-r now` (reboot immediately).
* **Example:** `shutdown -r now`

#### 81. `reboot`
* **What it does:** Short-cut instruction command that instantly tells the system to execute a full restart sequence.

#### 82. `init` (Initialization)
* **What it does:** Changes the system **Runlevel** state (Process ID 1 is always `init` or `systemd`).
* **Important Runlevels to Know:**
    * `init 0` : Shutdown/Poweroff system.
    * `init 1` : Single-user rescue mode.
    * `init 3` : Multi-user text-only console mode.
    * `init 5` : Full graphical user interface (GUI) mode.
    * `init 6` : Reboot the system.

---

### Category 7: Networking & Troubleshooting (83–94)

#### 83. `ping` (Packet InterNet Groper)
* **What it does:** Tests end-to-end network layer connectivity to a remote host using ICMP Echo Request packets.
* **Syntax:** `ping 8.8.8.8`

#### 84. `ifconfig` (Interface Configuration)
* **What it does:** Displays IP address configurations, MAC addresses, and network interface statuses.
* **Exam Point:** Deprecated in modern distributions but highly asked in exams. Replaced by the `ip addr` command.

#### 85. `ip`
* **What it does:** The modern powerful utility replacing `ifconfig` for managing interfaces, routing tables, and IP addresses.
* **Example:** View IP addresses:
    ```bash
    $ ip addr show
    ```

#### 86. `netstat` (Network Statistics)
* **What it does:** Shows active network connection sockets, routing tables, and open listening ports.
* **Crucial Flags:** `-tuln` (shows listening **t**cp, **u**dp ports with **l**iteral **n**umeric addresses without resolving domain names).

#### 87. `ss` (Socket Statistics)
* **What it does:** Modern alternative to `netstat`. It dumps socket statistics directly from kernel space, making it much faster.
* **Example:** `ss -tuln`

#### 88. `nslookup` (Name Server Lookup)
* **What it does:** Queries Internet Domain Name Servers (DNS) to resolve domain names to IP addresses or vice versa.
* **Example:** `nslookup google.com`

#### 89. `dig` (Domain Information Groper)
* **What it does:** An advanced DNS lookup utility that returns cleaner and comprehensive DNS record structures compared to `nslookup`.

#### 90. `traceroute`
* **What it does:** Tracks and records the exact network path route (hop-by-hop routers) a packet takes to reach a remote destination. Helpful for pinpointing network latency locations.

#### 91. `curl` (Client URL)
* **What it does:** Transfers data from or to a server using supported protocols (HTTP, HTTPS, FTP, etc.). Often used to download files or test API endpoints.
* **Example:** `curl http://example.com`

#### 92. `wget`
* **What it does:** A dedicated non-interactive command-line file downloader supporting HTTP, HTTPS, and FTP.
* **Example:** `wget https://download.linux.org/file.iso`

#### 93. `ssh` (Secure Shell)
* **What it does:** Establishes a highly secure, fully encrypted remote terminal connection to another Linux server across an untrusted network. Uses default port **22**.
* **Example:** `ssh username@192.168.1.50`

#### 94. `scp` (Secure Copy)
* **What it does:** Copies files securely between different network hosts over an encrypted SSH connection channel.
* **Example:** `scp document.pdf remote_user@10.0.0.5:/home/backup/`

---

### Category 8: Advanced Utilities & Shell Built-ins (95–100)

#### 95. `find`
* **What it does:** Searches real-time directory trees for specific files matching given criteria (name, size, type, modified date).
* **Syntax:** `find [path] -name "filename"`
* **Example:** Find all `.mp4` files inside `/var` larger than 100MB:
    ```bash
    $ find /var -type f -name "*.mp4" -size +100M
    ```

#### 96. `locate`
* **What it does:** Rapidly searches for files by scanning a pre-compiled database (`mlocate.db`) instead of crawling live disks.
* **Exam Comparison:** `locate` is much faster than `find`, but it won't show newly created files unless the database is manually refreshed using the `updatedb` command.

#### 97. `alias`
* **What it does:** Creates short-cut nicknames for long or complex commands to speed up CLI operations.
* **Example:** Make `c` clear the screen:
    ```bash
    $ alias c='clear'
    ```

#### 98. `history`
* **What it does:** Lists the entire history table of commands typed in the current user shell session.
* **Shortcut:** Typing `!45` reruns the 45th command from the history list.

#### 99. `echo`
* **What it does:** Prints/echoes a specified line of text or values of environmental variables onto the standard output screen.
* **Example:** Print current PATH variable:
    ```bash
    $ echo $PATH
    ```

#### 100. `clear`
* **What it does:** Wipes the terminal display screen clean, resetting your prompt to the top line. Shortcut: `Ctrl + L`.

---

## Part 3: High-Yield Mock Questions for IBPS SO IT 2026

Test your understanding against typical patterns seen in real IBPS SO IT professional knowledge sections:

**Q1. Which option of the `ls` command displays hidden files?** A) `-h`  
B) `-l`  
C) `-a`  
D) `-r`  
*Answer:* **C** (The `-a` option stands for 'all', capturing hidden files starting with `.`).

**Q2. What will be the final file permission set if `umask` is configured as 027 for a file?** A) 750  
B) 640  
C) 666  
D) 777  
*Answer:* **B** (Baseline file permission is 666. Subtraction: $666 - 027 = 640$. For owner: 6, group: 4, others: 0).

**Q3. To monitor real-time appended lines of a changing log file, which command configuration is used?** A) `head -f`  
B) `tail -f`  
C) `cat -n`  
D) `more -s`  
*Answer:* **B** (`tail -f` actively monitors and follows files dynamically).

**Q4. If you run `chmod 754 script.sh`, what permissions do "Others" have?** A) Read and Execute  
B) Read, Write, and Execute  
C) Read Only  
D) No Permissions  
*Answer:* **C** (The numbers represent Owner(7), Group(5), Others(4). Value 4 corresponds directly to Read-only (`r--`)).

**Q5. Which of the following is true for Hard Links?** A) They can cross different file systems.  
B) They can be created for directories.  
C) They share the exact same Inode number with the original file.  
D) Breaking the link deletes the target file instantly.  
*Answer:* **C** (Hard links are identical structural reference names point to the same Inode allocation block).

---
*Tip for Exam Success:* Focus heavily on the functional differences of text processing tools (`grep`, `sed`, `awk`), calculation of `umask`, and standard networking port maps. Best of luck for your **IBPS SO IT 2026** exam!
