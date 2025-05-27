# Oni Programming Language

Oni is a statically-typed, high-performance, multi-paradigm systems programming language designed to meet the needs of modern software development. Drawing inspiration from Rust, Nim, Go, Pony, and Julia, Oni combines productivity, safety, versatility, and scalability to support applications ranging from embedded systems to cloud infrastructure.

**Write fast. Build safe. Run anywhere.**

---

## Table of Contents

- [Core Philosophy](#core-philosophy)
- [Safety by Design](#safety-by-design)
- [Universal Programming](#universal-programming)
- [Safety First](#safety-first)
- [Key Features](#key-features)
  - [Basic Language Features](#basic-language-features)
  - [String & Numeric Type System](#string--numeric-type-system)
  - [Memory Management](#memory-management)
  - [Metaprogramming System](#metaprogramming-system)
  - [Concurrency](#concurrency)
  - [Parallelism](#parallelism)
  - [Logic Programming](#logic-programming)
  - [Dataflow/Flow-Based Programming](#dataflowflow-based-programming)
  - [Event-Driven Programming](#event-driven-programming)
  - [Functional Reactive Programming (FRP)](#functional-reactive-programming-frp)
  - [Security Standard Library](#security-standard-library)
  - [OASM DSL for Inline Assembly](#oasm-dsl-for-inline-assembly)
  - [Julia-like Math Syntax](#julia-like-math-syntax)
- [Development Ecosystem](#development-ecosystem)
  - [Multi-Backend Compilation](#multi-backend-compilation)
  - [Kami Toolchain](#kami-toolchain)
  - [Onikage IDE Suite](#onikage-ide-suite)
- [Use Cases](#use-cases)
- [Project Vision](#project-vision)
  - [Creator’s Mission](#creators-mission)
  - [Design Goals](#design-goals)
  - [Development Status](#development-status)
- [Why Choose Oni?](#why-choose-oni)
- [Contribution Status](#contribution-status)

---

## Core Philosophy

Oni is driven by four guiding principles:

- **Safety**
- **Versatility**
- **Speed**
- **Readability**

---

## Safety by Design

- Null-safe type system with explicit `option T` handling
- Hybrid memory management (ownership/GC) with leak detection
- Compile-time security validation and cryptographic verification
- Security-focused specialized standard library
- Zero-trust protocol implementation
- Modularity and isolation mechanisms

---

## Universal Programming

- **One Language for All**: Covers 95% of programming use cases, minimizing the need for multiple languages.
- **Seamless Workflow**: Smooth transitions from prototyping to production within a single environment.
- **Accessible Learning**: Balances simplicity for beginners with depth for advanced users across diverse domains.

---

## Safety First

- **Null Safety**: Employs option types to eliminate null pointer errors.
- **Memory Safety**: Uses ownership models and garbage collection to prevent memory bugs at compile time.
- **Security by Design**: Enforces compile-time checks to catch vulnerabilities early.
- Compile-time code obfuscation
- Anti-reflection protection
- Tamper-evident audit trails
- Encrypted constant storage
- Cryptographic package verification

---

## Key Features

Oni provides a rich set of features tailored for a broad range of programming tasks:

### Basic Language Features

- **Declarations**: `let`, `const`, `mut`, `var`
- **Functions**: Supports closures and first-class functions
- **Control Flow**: `if`, `else`, `match`, `case`, `while`, `for`
- **Pattern Matching**: Includes destructuring and exhaustive checks
- **Modules**: Facilitates imports and code organization
- **Types**: Offers tuples, records, enums, and unions
- **Generics**: Provides type parameters and traits/interfaces
- **Error Handling**: Uses `result T,E`, `option T`, and `panic!`
- **Type Inference**: Reduces boilerplate code
- **Non-Nullable by Default**: Requires `option T` for optional values
- **Compile-Time Constants**: Evaluates constants at compile time

### String & Numeric Type System

**String Types:**

- `str`: Owned, non-null string
- `stref`: Non-null string slice
- `ostr`: OS-specific string
- `cstr`: C-compatible string (`option cstr`)
- `vbstr`: Vector of bytes
- `bstr`: Byte slice
- **Conversions**: UTF-8, Base64, and Hex encoding

**Numeric Types:**

- **Signed**: `i8`, `i16`, `i32`, `i64`, `i128`
- **Unsigned**: `u8`, `u16`, `u32`, `u64`, `u128`
- **Features**: Literal suffixes, type inference, overflow checks (debug mode), safe casting
- **Auto Minimum Types**: Dynamic numeric wrappers which automatically choose the appropriate numeric type based on required memory, starting from 8 bits and scaling up to 128 bits as needed with uint int ufloat float

### Memory Management

- **Manual Mode**: Rust-style ownership and borrowing
  - Ownership/borrowing semantics
  - Lifetime annotations
  - Zero-cost abstractions
- **Automatic Modes:**
  - **ARC** (Automatic Reference Counting): Used in Kotlin/Swift backends
  - **ORC** (Optimized Reference Counting): Used in Nim backend
- **Hybrid Support**: Mixing manual and automatic memory management
- **Lifetime Tools**: Leak detection and analysis

### Metaprogramming System

- **Procedural Macros**: Rust-inspired
- **Template Macros**: Nim-style
- **Symbolic Macros**: Lisp-style code-as-data
- **Hygienic Macros**: Racket-style scope control
- **CTFE**: Compile-time function execution
- **Reflection**: Compile-time code generation
- **DSL Support**: Tools for domain-specific languages

### Concurrency

- **Async/Await**: For asynchronous programming
- **Goroutines & Channels**: Go-inspired concurrency
- **Actor Model**: BEAM/OTP-inspired with supervision trees and hot reloading
- **Thread Primitives**: Threads, mutexes, condition variables, atomic operations
- **Parallelism Models**: Fork-join, task, data, pipeline, SIMD
- **Thread Safety**: Atomics and thread-local storage
- **Toggleable Kami VM/Runtime**: For scalable concurrency, GC tasks, and hot code reloading

### Parallelism

- **Data Parallelism**: Parallel operations over collections and data streams
- **Task Parallelism**: Concurrent execution of independent tasks
- **Pipeline Parallelism**: Staged processing with asynchronous pipelines
- **Actor-Based Parallelism**: Isolated actors communicating via message passing
- **Fork-Join Parallelism**: Recursive task splitting and joining
- **SIMD Parallelism**: Vectorized computation

### Logic Programming

- **Facts & Rules**: Declarative logic definitions
- **Queries**: `?- predicate(args)` syntax
- **Unification**: Backtracking with continuations
- **Clause Indexing**: Optimized lookups

### Dataflow/Flow-Based Programming

- **Pipe Syntax**: `|>` for operation chaining
- **DAG Analysis**: Static scheduling of data flows
- **Monitoring**: Diagnostics for flow nodes
- **Back-Pressure**: Flow control mechanisms

### Event-Driven Programming

- **Signals**: `emit` definitions
- **Event Loop**: Prioritized dispatcher
- **Handlers**: Asynchronous subscription registry

### Functional Reactive Programming (FRP)

- **Signals & Behaviors**: Propagates changes
- **Time Primitives**: `.at`, `.every`, `.delay`
- **Batching**: Coalesces updates

### Security Standard Library

- **Obfuscation**: `obfuscate key="…"`
- **Encryption**: `encrypt`
- **Anti-Reflection**: `seal`
- **Integrity**: `audit`
- **Exposure**: `public` keyword (private by default)

### OASM DSL for Inline Assembly

- **Inline Blocks**: `oasm … end`
- **Architectures**: x86_64, ARM, RISC-V
- **Registers**: Binding and memory constraints
- **Fallback**: VM support on unsupported platforms
- **Assembly Output**: Emits `asm!` blocks in generated Rust source

### Julia-like Math Syntax

- **Operators**: `.*`, `.+`, `.-` for element-wise operations
- **Broadcasting**: `fn.(args)`
- **Unicode**: ∀, ∑, etc.
- **Arrays/Tensors**: Native linear algebra support
- **GPU Offloading**: BLAS/LAPACK integration

## Development Ecosystem

### Multi-Backend Compilation

| Backend       | Use Case               | Key Strength              |
|---------------|------------------------|---------------------------|
| Rust          | Systems programming    | Native performance        |
| Kotlin        | Android/cross-platform | JVM interoperability      |
| Swift         | iOS/macOS development  | Apple ecosystem           |
| Nim           | Web/embedded/scripting | Metaprogramming           |
| WASM          | Browser-based apps     | Portable execution        |
| Machine Code  | Bare-metal systems     | Direct hardware control   |

### Kami Toolchain

- **Package Manager**:
  - Delta updates, parallel shard downloads
  - Cryptographic signatures, shard verification
- **Runtime Features**:
  - Hot-reloading, toggleable BEAM-style VM
  - Distributed process registry
- **Build System**:
  - Multi-backend compilation
  - Cross-target dependency resolution

### Onikage IDE Suite

- **Security Scanner**: Detects vulnerabilities
- **Ownership Visualizer**: Memory insights
- **Multi-backend Debugger**: Supports all backends
- **AI Completion**: Context-aware suggestions
- **Docs Generator**: Auto-generates documentation
- **Extras**: LSP, REPL, linting, static analysis

## Use Cases

| Domain                | Oni Features Utilized                |
|-----------------------|--------------------------------------|
| Systems Programming   | Manual memory, OASM, hardware access |
| Mobile Development    | Kotlin/Swift backends                |
| Scientific Computing  | GPU math, tensors, Julia syntax      |
| Web Services          | WASM, async pipelines                |
| Embedded Systems      | Nim backend, low footprint           |
| Cloud Native Apps     | Actor model, Kubernetes compatibility|
| Game Engines          | Concurrency, SIMD                    |
| Reactive Apps         | Actor parallelism, hot reloading     |
| Cross-platform Dev    | Web, desktop, mobile, embedded       |

## Project Vision

### Creator’s Mission

> "Oni is my vision for a universal language that eliminates the need to switch between specialized tools. It’s about making programming safer, more productive, and accessible—without compromises. This project is my journey to master the languages I admire and grow as a developer."

### Design Goals

- **Cross-Platform**: Write once, deploy anywhere.
- **Safe Systems**: Accessible safety for all levels.
- **Domain Bridge**: Unites numerical and systems programming.
- **Enterprise Ready**: Built-in security for professional use.

### Development Status

- **Phase**: Core language specification
- **Team**: Solo until MVP
- **Open Source**: Planned post-MVP
- **Vision**:
  - Safety-critical certification (e.g., aerospace, healthcare)
  - App store integration
  - AI-powered development assistant

## Why Choose Oni?

- **Productivity**:
  - Unified syntax across domains
  - Rapid prototyping with metaprogramming
  - AI-assisted coding
- **Performance**:
  - LLVM-optimized binaries
  - Auto-vectorized SIMD
  - Bare-metal efficiency
  - Inline assembly via OASM
- **Safety**:
  - Compile-time bug prevention
  - Memory validation
  - Cryptographic supply chain
  - Anti-tamper protections
- **Versatility**:
  - Scales from embedded to cloud
  - Hardware and ML workflows
  - Multi-platform deployment

## Contribution Status

Right now Oni is in its early stages and is developed solo for learning and efficiency.

> **"Write once, deploy anywhere—without compromises."**

**Last Updated**: May 27, 2025  
**Status**: Active Development
