# 🛡️ Securing and Enhancing the Repy Reference Monitor with Undo Support

This repository contains an enhanced and secured version of the [Repy Reference Monitor](https://github.com/SeattleTestbed/docs/blob/master/EducationalAssignments/UndoPartOne.md) from the SeattleTestbed project. The work is based on the three-part Undo assignment series:

- [Undo Part One](https://github.com/SeattleTestbed/docs/blob/master/EducationalAssignments/UndoPartOne.md)
- [Undo Part Two](https://github.com/SeattleTestbed/docs/blob/master/EducationalAssignments/UndoPartTwo.md)
- [Undo Part Three](https://github.com/SeattleTestbed/docs/blob/master/EducationalAssignments/UndoPartThree.md)

## 📌 Project Overview

The original Repy-based reference monitor offered basic file operation security and an undo mechanism. However, it had several critical vulnerabilities related to:

- Inadequate error and exception handling
- Lack of input validation
- Missing safety checks for undo operations
- Race conditions in concurrent access

This project implements security and functionality enhancements that improve the reliability and robustness of the system.

## 🔧 Enhancements Implemented

1. **Thread Safety with Locks**  
   Prevents race conditions by ensuring exclusive access to shared resources during read, write, and undo operations.

2. **Offset Error Handling**  
   Validates file offsets before read/write to prevent out-of-bound errors. Raises `RepyArgumentError` or `SeekPastEndOfFileError` if invalid.

3. **Exception Handling Alignment**  
   Revised exceptions thrown by the security layer to match the expected behavior of the Repy API.

4. **File Size Validation**  
   Adds checks for maximum file size to prevent memory overflows or resource exhaustion.

5. **FileClosedError Handling**  
   Custom error to gracefully handle operations attempted on closed file handles.

6. **Validation for Negative Byte Reads**  
   Ensures `readat()` raises `RepyArgumentError` if negative values are passed.

## ✅ Outcome

The enhanced reference monitor is:
- Aligned with Repy's API behavior
- More secure against potential misuse or attack
- Capable of reliably handling file operations and undo functionality under concurrent workloads

## 📂 Repo Structure

```bash
├── secure_reference_monitor/
│   ├── secure_reference_monitor.py   # Updated secure monitor implementation
│   ├── original_reference_monitor.py # Original version for comparison
│   ├── testcases.py                  # Sample test cases for validation
│   └── README.md                     # This README file
```

## 🧠 Lessons Learned

This project demonstrates how basic security assumptions in reference monitors can be tested and strengthened with defensive programming techniques, robust error handling, and secure concurrency controls.