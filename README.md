# 📁 In-Memory Virtual File System (VFS)

A high-performance, in-memory simulated virtual file system written in Modern C++ (C++17). This project emulates core Unix-like shell utilities for directory navigation, file creation, and memory allocation tracking.

---

## 🚀 Features

- **Hierarchical Structure:** Full implementation of standard Tree-based directory management.
- **Smart Memory Management:** Built entirely utilizing Modern C++ smart pointers (`std::shared_ptr`, `std::weak_ptr`) ensuring absolute zero memory leaks.
- **Efficient Lookup:** $O(1)$ to $O(\log n)$ file index tracking using structured maps.
- **Memory Profiling:** Dynamic scale metrics (`df` command) to check exactly how many bytes your custom files occupy in-RAM.

## 🛠️ Supported Commands

| Command | Arguments | Description |
| :--- | :--- | :--- |
| `mkdir` | `<dir_name>` | Creates a new virtual subdirectory. |
| `touch` | `<file_name> [content]` | Generates a data file with optional inline content. |
| `cd` | `<dir_name> / ..` | Changes current working directory context. |
| `ls` | *None* | Lists all resources inside the current directory. |
| `df` | *None* | Displays virtual disk usage calculation in bytes. |
| `exit` | *None* | Safely terminates the shell session. |

---

## 💻 Tech Stack & Architecture

- **Language:** C++17 or higher.
- **Design Patterns:** Object-Oriented Composite Structure (File/Directory polymorphism inheritances).
- **Safe-Pointers:** Solves Cyclic Dependencies by pairing parent directories as `std::weak_ptr` against explicit child shared objects.

---

## 🔧 Building and Running

### Prerequisites
Make sure you have a standard modern compiler environment installed (GCC, Clang, or MSVC supporting C++17).

### Compilation via Terminal
```bash
# Compile the source code
g++ -std=c++17 main.cpp -o vfs_shell

# Run the binary execution executable
./vfs_shell
