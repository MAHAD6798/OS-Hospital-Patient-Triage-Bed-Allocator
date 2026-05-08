# OS-Hospital-Patient-Triage-Bed-Allocator
An Operating Systems simulation project built in C and Bash that models a multi-threaded hospital administration system. This project demonstrates advanced OS concepts including process synchronization, inter-process communication (IPC), and memory allocation algorithms.


# Hospital Patient Triage & Bed Allocator 🏥

## Project Description
The Hospital Patient Triage & Bed Allocator is an Operating Systems simulation project built in C and Bash. It models a multi-threaded hospital administration system designed to process incoming patients, assign them appropriate care units based on the severity of their condition, and manage bed availability in real-time. The system acts as a practical implementation of core OS mechanisms, effectively handling concurrent tasks and inter-process communication without race conditions or memory leaks.

## OS Concepts Demonstrated
This project serves as a hands-on application of several fundamental Operating Systems concepts:
* **Concurrency & Multi-threading:** Utilizes POSIX threads (`pthreads`) to run concurrent `receptionist`, `scheduler`, and `nurse` operations within a single server daemon.
* **Process Management:** Dynamically creates simulated patient processes using `fork()` and executes their unique lifecycles via `execv()`.
* **Process Synchronization:** Implements Mutex locks (`pthread_mutex_t`) and Condition Variables (`pthread_cond_t`) to ensure thread-safe queue operations and prevent race conditions when assigning beds.
* **Inter-Process Communication (IPC):**
    * **System V Shared Memory (`shmget`, `shmat`):** Maintains a globally accessible, synchronized state of the 20 hospital beds across distinct, independent processes.
    * **Named Pipes (FIFOs):** Facilitates asynchronous, one-way signaling from independent patient processes back to the central nursing thread upon patient discharge.
* **Memory Management Algorithms:** Includes a standalone module demonstrating contiguous memory allocation strategies (First-Fit, Best-Fit, Worst-Fit).

## Build Instructions

This project is designed to run in a Linux environment (or Windows Subsystem for Linux - WSL). 

1. **Clone the repository:**
   ```bash
   git clone <your-repository-url>
   cd <repository-directory>
