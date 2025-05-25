# Oni Programming Language

**Oni** is a modular, high-performance, multi-paradigm programming language designed for modern systems and application development. Inspired by the safety of **Rust**, the clarity of **Nim**, and the concurrency power of **Go** and **Pony**, Oni is built for **productivity, safety, and scalability** across platforms.

> **Write fast. Build safe. Run anywhere.**

---

## Key Features

- **Modern Memory Management**
  - **Manual mode**: Rust-style ownership and borrowing (Rust backend only)
  - **AOB (Automatic Ownership & Borrowing)**: Rust-style semantics with automatic management (Rust backend only)
  - **ARC/ORC GC**: For Kotlin, Swift, Zig, and TypeScript backends

- **Multi-Backend Compilation**
  - **Rust** – Core backend with system-level performance and ability to Reverse Compile Rust code to Oni
  - **Kotlin Native** – Android & cross-platform
  - **Swift** – iOS/macOS support
  - **TypeScript** – Web-ready
  - **Zig** – Portable systems backend
  - **Lua** – Scripting and embedded

- **Powerful Concurrency Models**
  - **Async/Await**
  - **Goroutines & Channels**
  - **Actor Model**
  - **Threading Primitives**:
    - Thread creation and management
    - Thread-safe data structures
    - Mutexes and condition variables
  - Optional **Akuma VM/Runtime** for scalable concurrency, GC tasks, and hot code reloading that can easily be turned off or on

- **Parallelism Models**
  - **Data Parallelism**: Efficient parallel operations over collections and data streams.
  - **Task Parallelism**: Concurrent execution of independent tasks.
  - **Pipeline Parallelism**: Staged processing with asynchronous pipelines.
  - **Actor-Based Parallelism**: Isolated concurrent actors communicating via message passing.
  - **Fork-Join Parallelism**: Recursive task splitting and joining for divide-and-conquer algorithms.
  - **SIMD Parallelism**: Single Instruction, Multiple Data for vectorized computation and low-level performance.

- **Clean, Nim-like Syntax**
  - Minimal boilerplate
  - Easy to read and write
  - Powerful meta-programming

- **Integrated Toolchain**
  - **Akuma**: Interpiler (interpreter + compiler),package manager(the package manager will have Delta and parallel downloads and packages are made in appshred format that is made of tiny appshards and akuma will download the shards and combines them together and then installs them as appshred and all appshards will have security signatures and special IDs for recognition), build system, test runner, Toggleable VM/Runtime, Hot Code Reloading, Dependency Management
  - **Onikage**: IDE bridge with LSP, REPL, linting, type checking, static analysis, docs, security scanning

---

## Use Cases

- Systems programming  
- Web & mobile app development  
- Game engines and embedded systems  
- Cloud-native services  
- High-performance libraries  
- Reactive and actor-based concurrent applications  

---

## Why Oni?

- **Rust-level safety** with a **friendlier syntax**
- **Ability to Port Rust Code to Oni**
- **Rapid prototyping** + **production-ready compilation**
- **Interoperable** with existing Backend ecosystems
- **Cross-platform**, concurrent, and scalable out-of-the-box
- **Fully modular** toolchain with extensible architecture

---

## Getting Started

Coming soon:  
- Installation guide  
- Hello world  
- Code examples  
- Documentation  
- Contribution guide  

---

## License

[MIT License](LICENSE)

---

## My Reasons for Starting Oni Project

i started this project in order to first Learn and master the languages i like alongside turning myself into a better Developer.i want to create something that can be a true universal programming language so instead of having a need for learning tons of languages to cover more areas you can cover all of them with one language,i know its a big deal and i may fail, but im going to try to make a language that will make programming more accessable, safer and more productive without tradeoffs.

---

## Current Status and Contribution
Right now Oni is on early stages and untill it reaches a acceptable point i will work on it alone,both for learning the topics i need to learn and for not waisting anyones time.
