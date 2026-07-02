# IBPS SO IT Officer Linux Handbook
## Part 01 – Introduction to Linux & UNIX

> This is Part 1 of the handbook.

# What is Linux?

Linux is an **Operating System (OS)**. It helps you communicate with the computer.

**Real-life analogy:**  
Hardware = Body  
Operating System = Brain  
Applications = Skills

```
User
 |
Apps
 |
Operating System (Linux)
 |
Hardware
```

## What is UNIX?

UNIX is an older operating system. Linux was inspired by UNIX.

| Linux | UNIX |
|-------|------|
| Open source | Mostly proprietary |
| Free | Usually paid |
| Used in servers | Used in enterprises |

## Kernel

The **Kernel** is the heart of Linux.

```
User
 |
Shell
 |
Kernel
 |
Hardware
```

- Talks to hardware
- Manages memory
- Runs processes

## Shell

The shell accepts commands from the user and sends them to the kernel.

Example:

```bash
ls
pwd
```

## Terminal

The terminal is the window where we type commands.

## CLI vs GUI

| CLI | GUI |
|-----|-----|
| Type commands | Click icons |
| Faster | Easier for beginners |

## Distribution (Distro)

A Linux distribution is Linux + useful software.

Examples:
- Ubuntu
- Debian
- Fedora
- Red Hat

## File System

Everything in Linux starts from `/`

```
/
├── home
├── root
├── etc
├── bin
├── usr
└── var
```

## Root

`/` = Root directory (top of filesystem)

`root` = Administrator user

These are different.

## Home Directory

Every user has a home directory.

Example:

```
/home/yash
```

## Directory

A directory is a folder.

## Current Working Directory

The directory you are currently inside.

Command:

```bash
pwd
```

## Absolute Path

Starts from `/`

Example:

```
/home/yash/Documents
```

## Relative Path

Starts from current location.

Example:

```
Documents/file.txt
```

## Case Sensitivity

Linux treats:

```
File
file
FILE
```

as different names.

## Hidden Files

Files beginning with `.` are hidden.

Example:

```
.bashrc
```

## File Permissions

```
r = Read
w = Write
x = Execute
```

## Users and Groups

- User = Individual account
- Group = Collection of users

## Processes

A process is a running program.

Example:
- Browser
- Editor
- Terminal

---

# Summary

| Topic | One-line revision |
|--------|-------------------|
| Linux | Open-source operating system |
| UNIX | Parent inspiration of Linux |
| Kernel | Heart of Linux |
| Shell | Command interpreter |
| Terminal | Window to type commands |
| CLI | Command Line Interface |
| GUI | Graphical Interface |
| Root | Top directory / Admin user (context matters) |

# Frequently Asked MCQs

1. Which is the heart of Linux?
- A) Shell
- B) Kernel ✅
- C) Terminal
- D) GUI

2. Which command shows the current directory?
- A) ls
- B) pwd ✅
- C) cd
- D) who

# Exam Tips

- Learn the difference between **Kernel**, **Shell**, and **Terminal**.
- Remember `/` (root directory) is different from `root` (administrator user).
