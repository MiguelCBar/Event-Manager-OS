# Part 1 Project

## Overview
Part 1 focuses on developing the foundational functionality of the Event Manager System. The goal is to manage events by allowing users to create, reserve, and display event data. This part also introduces parallelization techniques using processes and threads.

## Key Features
1. **File-based Input and Output**: The system processes batch jobs described in `.jobs` files and generates corresponding `.out` files.
2. **POSIX File Descriptors**: File handling is implemented using low-level POSIX APIs for enhanced system-level interaction.

## Usage
1. Build the project using `make`.
2. Execute the program with the following syntax:
   ```
   ./ems <path-jobs-directory> <MAX-number-processes> <MAX-number-threads> [delay] 
   // delay is in milliseconds
   ```