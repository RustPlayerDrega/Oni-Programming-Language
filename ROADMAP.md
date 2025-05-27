# Oni Programming Language – Development Roadmap & Feature Checklist

Use this document to track every planned milestone.

---

## 0. Basic Language Features (Rust/Kotlin Native/Swift/Nim Parity)

### Language Core
- [ ] `let`, `const`, `mut`, `var` declarations  
- [ ] Functions, closures, first-class functions  
- [ ] Control flow: `if`, `else`, `match`, `case`, `while`, `for`  
- [ ] Pattern matching and destructuring  
- [ ] Modules and imports  
- [ ] Tuples, records, enums, union types  
- [ ] Generics and type parameters  
- [ ] Traits/interfaces  
- [ ] **Error Handling**  
  - [ ] `result T,E` for recoverable errors  
  - [ ] `option T` for explicit optional values  
  - [ ] `panic!` for unrecoverable errors  
- [ ] Type inference  
- [ ] **Non-nullable by default**  
  - [ ] All types `T` guarantee valid values  
  - [ ] `option T` required for optional/missing values  
- [ ] Compile-time evaluated constants  

---

## 1. String & Numeric Type System

### String Types
- [ ] `str` → Owned string (non-null)  
- [ ] `stref` → String slice (non-null)  
- [ ] `ostr` → `OsString` equivalent  
- [ ] `cstr` → C-compatible (`option cstr`)  
- [ ] `vbstr` → `Vec<u8>` equivalent  
- [ ] `bstr` → `&[u8]` equivalent  
- [ ] Conversions/encoding helpers (UTF-8, Base64, Hex)  
- [ ] C-FFI-safe string handling  

### Numeric Types
- [ ] Signed: `i8`, `i16`, `i32`, `i64`, `i128`  
- [ ] Unsigned: `u8`, `u16`, `u32`, `u64`, `u128`  
- [ ] Literal suffix support & type inference  
- [ ] Overflow/underflow checking (debug)  
- [ ] Safe casting utilities
- [ ] Auto Minimum Types of int, uint, float, ufloat 

---

## 2. Memory Management

- [ ] Manual memory (ownership & borrowing) – Rust backend  
- [ ] ARC GC – Kotlin Native/Swift/Nim backends  
- [ ] ORC GC – Nim backend  
- [ ] Interop between GC and manual modes  
- [ ] Lifetime analysis & leak detection tools  

---

## 3. Metaprogramming System

- [ ] Rust-style procedural macros  
- [ ] Nim-style `macro`/`template` blocks  
- [ ] Lisp-style symbolic macros (code-as-data)  
- [ ] Racket-style hygienic macros & scope control  
- [ ] CTFE (compile-time function execution)  
- [ ] Compile-time reflection/codegen  
- [ ] DSL authoring helpers  

---

## 4. Concurrency & Parallelism

- [ ] Async/await  
- [ ] Goroutines  
- [ ] Channels  
- [ ] **Actor Model (BEAM/OTP-inspired)**  
  - [ ] Supervisor trees (hierarchical supervision)  
  - [ ] Self-healing mechanisms (auto-restarts)  
  - [ ] Lightweight processes (millions of actors)  
  - [ ] Distributed process registry  
  - [ ] Hot code reloading  
  - [ ] "Let it crash" philosophy  
- [ ] Threading primitives (Nim-style threads, mutex, condvar)  
- [ ] Fork-join parallelism  
- [ ] Task parallelism  
- [ ] Data parallelism  
- [ ] Pipeline parallelism  
- [ ] SIMD parallelism/vector ops  
- [ ] Thread-local storage & atomics  

---

## 5. Logic Programming

- [ ] `fact` & `rule` declarations  
- [ ] Query syntax (`?- predicate(args)`)  
- [ ] Unification & backtracking with continuations  
- [ ] Clause indexing for fast lookup  

---

## 6. Dataflow/Flow-Based Programming

- [ ] Wire connectors/pipe syntax (`|>`)  
- [ ] Static DAG analysis & scheduling  
- [ ] Monitoring/diagnostics of nodes  
- [ ] Back-pressure/flow control  

---

## 7. Event-Driven Programming

- [ ] Signals/`event` definitions & `emit`  
- [ ] Event loop/dispatcher  
- [ ] Event queue with priorities  
- [ ] Asynchronous handler dispatch  
- [ ] Subscription registry & cancellation tokens  

---

## 8. Functional Reactive Programming (FRP)

- [ ] Change-propagation engine for signals/behaviors  
- [ ] Time primitives (`.at`, `.every`, `.delay`)  
- [ ] Batching/coalescing updates  

---

## 9. Security Standard Library

- [ ] `obfuscate key="..."` (compile-time obfuscation)  
- [ ] `encrypt` (compile-time encryption)  
- [ ] `seal` (anti-reflection protection)  
- [ ] `audit` (integrity checks)  
- [ ] `public` keyword (private by default, explicit exposure)  

---

## 10. OASM DSL for Inline Assembly

- [ ] `oasm … end` inline blocks  
- [ ] Architecture support (x86_64, ARM, RISC-V)  
- [ ] Register binding & memory access  
- [ ] Clobber lists & constraints  
- [ ] VM fallback mechanism  

---

## 11. Julia-like Math Syntax

- [ ] Infix/vector operators (`*`, `.+`, `.-`)  
- [ ] Broadcasting (`fn.(args)`)  
- [ ] Unicode operators (`∀`, `∑`)  
- [ ] Native arrays/tensors  
- [ ] Linear algebra primitives  
- [ ] GPU offloading support  
- [ ] BLAS/LAPACK integration  

---

## 12. Backends

- [ ] Rust (manual memory)  
- [ ] Kotlin Native (ARC)  
- [ ] Swift (ARC)  
- [ ] Nim (ORC)  
- [ ] WASM  
- [ ] Machine Code  
- [ ] Cross-platform builds  
- [ ] Backend-specific optimizations  
- [ ] FFI layers per backend  
- [ ] Reverse compilation from Rust  

---

## 13. Kami Toolchain

- [ ] Interpreter  
- [ ] Optimizing compiler  
- [ ] Multi-backend build system  
- [ ] **Package Manager**  
  - [ ] Appshred format (appshard units)  
  - [ ] Delta updates  
  - [ ] Parallel downloads  
  - [ ] Cryptographic signatures  
  - [ ] Shard ID verification  
- [ ] Test runner/coverage  
- [ ] Hot code reloading  
- [ ] **Kami VM**  
  - [ ] BEAM-style scheduler  
  - [ ] Runtime GC modes  
  - [ ] Process isolation  
  - [ ] Distributed messaging  
  - [ ] Toggleable execution  

---

## 14. Onikage Developer Tools

- [ ] LSP server  
- [ ] Syntax highlighting  
- [ ] Auto-completion  
- [ ] Security scanner  
- [ ] REPL/debugger  
- [ ] IDE plugins (VS Code, Neovim, JetBrains)  
- [ ] Documentation generator  
- [ ] Code formatter  
- [ ] Static analyzer  

---

## 15. Interoperability

- [ ] Rust crate linking  
- [ ] C FFI (`option Ptr<T>`)  
- [ ] WASM exports  
- [ ] Multi-language `.uof` files  
- [ ] Reverse compilation from Rust  

---

## 16. Documentation & Learning

- [ ] Formal language reference  
- [ ] "The Oni Book" introductory guide  
- [ ] Example repository  
- [ ] Web playground/REPL  
- [ ] Migration guides  
- [ ] Tutorial series  

---

## 17. Ecosystem Infrastructure

- [ ] Standard library  
- [ ] Utility crates (collections, math, I/O)  
- [ ] Public package registry  
- [ ] Plugin system  
- [ ] Contribution guidelines  
- [ ] Cross-compilation pipelines  
- [ ] Ecosystem marketplace  

---

## 18. Advanced Features

- [ ] Modular architecture  
- [ ] Runtime reflection  
- [ ] Embedded sandboxing  
- [ ] Cross-compilation  
- [ ] Binary optimization  
- [ ] Security-hardened memory model  
- [ ] Lightweight process isolation  

---

## 19. Object-Oriented Programming (OOP) Models

- [ ] Structs with methods  
- [ ] Traits/interface polymorphism  
- [ ] Kotlin-like inheritance  
- [ ] Lua-style prototypes  
- [ ] Mixins/decorators  
- [ ] Method overloading/overriding  
- [ ] Abstract classes/members  

---

## 20. Source File Formats

### `.oni` Files
- [ ] Pure Oni code  
- [ ] Multi-backend compilation  
- [ ] Source maps  
- [ ] Backend-specific directives  

### `.uof` Files
- [ ] Multi-language support  
- [ ] `[language=backend=filename]` syntax  
- [ ] Section-based processing  
- [ ] `[EndOfFile]` terminators  
- [ ] Cross-language diagnostics  

---

## Milestones

### Milestone 1 – MVP
- [ ] Core language implementation  
- [ ] Rust backend  
- [ ] Basic toolchain  
- [ ] Package manager (appshred prototype)  

### Milestone 2 – Extended Capabilities
- [ ] BEAM-style concurrency  
- [ ] Security features  
- [ ] Multi-backend support  
- [ ] Scientific computing stack  
- [ ] IDE tooling  

### Milestone 3 – Production Ready
- [ ] Certified toolchain  
- [ ] Enterprise features  
- [ ] Ecosystem maturity  
- [ ] Appstore integration  
- [ ] Safety certifications  

---
