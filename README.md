# Oni Programming Language

**Oni** is a modular, **statically typed** high-performance, multi-paradigm programming language designed for modern systems and application development. Inspired by the safety of **Rust**, the clarity of **Nim**, the concurrency power of **Go** and **Pony**, and the scientific programming ergonomics of **Julia**, Oni is built for **productivity, safety, versatility, and scalability** across platforms.

> **Write fast. Build safe. Run anywhere.**

---

## Key Features

* **Modern Memory Management**

  * **Manual mode**: Rust-style ownership and borrowing (Rust backend only)

  * **ARC/ORC GC**: For Kotlin, Swift, and Nim backends

* **Multi-Backend Compilation**

  * **Rust** – Core backend with system-level performance and ability to reverse-compile Rust code to Oni
  * **Kotlin Native** – Android & cross-platform
  * **Swift** – iOS/macOS support
  * **Nim** – Web-ready, scripting and embedded portable systems backend
  * **WASM**, **Machine Code**

* **Powerful Concurrency Models**

  * **Async/Await**
  * **Goroutines & Channels**
  * **Actor Model**
  * **Threading Primitives**:

    * Thread creation and management
    * Thread-safe data structures
    * Mutexes and condition variables
  * Optional **Kami VM/Runtime** for scalable concurrency, GC tasks, and hot code reloading (toggleable)

* **Parallelism Models**

  * **Data Parallelism**: Efficient parallel operations over collections and data streams
  * **Task Parallelism**: Concurrent execution of independent tasks
  * **Pipeline Parallelism**: Staged processing with asynchronous pipelines
  * **Actor-Based Parallelism**: Isolated concurrent actors communicating via message passing
  * **Fork-Join Parallelism**: Recursive task splitting and joining for divide-and-conquer algorithms
  * **SIMD Parallelism**: Single Instruction, Multiple Data for vectorized computation and low-level performance

* **Clean, Nim-like Syntax**

  * Minimal boilerplate
  * Easy to read and write
  * Powerful meta-programming (Rust, Nim, Lisp, Racket-style)

* **Julia-like Math Syntax**

  * Infix operators for matrix math (`*`, `.+`, `.-`, etc.)
  * Broadcasting with `.` notation (`sin.(x)`)
  * Unicode operator support (e.g., `∀`, `∑`)
  * Native support for arrays, tensors, and linear algebra

* **OASM DSL for Assembly**
  Oni uses **OASM**, a minimalistic DSL that feels like Oni syntax but compiles to inline assembly in the Rust backend.

  * Write simple Oni-like code:

    ```oni
    oasm:
      mov rax, rbx      # high-level Oni syntax
      add rax, rcx
    end
    ```
  * On compilation, emits `asm!` blocks in generated Rust source, with safe scoping and sandboxing.

* **Integrated Toolchain**

  * **Kami**: Interpiler (interpreter + compiler),package manager(the package manager will have Delta and parallel downloads and packages are made in appshred format that is made of tiny appshards and akuma will download the shards and combines them together and then installs them as appshred and all appshards will have security signatures and special IDs for recognition), build system, test runner, Toggleable VM/Runtime, Hot Code Reloading, Dependency Management
  * **Onikage**: IDE bridge with LSP, REPL, linting, type checking, static analysis, documentation generation, security scanning

---

## Use Cases

* Systems programming
* Cross-platform software development
* Game engines and embedded systems
* Cloud-native services
* High-performance libraries
* Reactive and actor-based concurrent applications
* Math and numerical computation

---

## Why Oni?

* **Rust-level safety** with a **friendlier syntax**
* **Ability to port Rust code to Oni**
* **Rapid prototyping** + **production-ready compilation**
* **Interoperable** with existing backend ecosystems
* **Cross-platform**, concurrent, and scalable out-of-the-box
* **Fully modular** toolchain with extensible architecture
* **Math-ready syntax** inspired by Julia

---

## My Reasons for Starting Oni Project

i started this project in order to first Learn and master the languages i like alongside turning myself into a better Developer. i want to create something that can be a true universal programming language so instead of having a need for learning tons of languages to cover more areas you can cover 95% of them with one language. i know it's a big deal and i may fail, but i'm going to try to make a language that will make programming more accessible, safer and more productive without tradeoffs.

## Current Status and Contribution

Right now Oni is in its early stages and until it reaches an acceptable point i will work on it alone—both for learning the topics i need to learn and to avoid wasting anyone else's time.
