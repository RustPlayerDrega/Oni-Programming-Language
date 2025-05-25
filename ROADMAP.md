# Oni Programming Language – Development Roadmap & Feature Checklist

Use this document to track every planned milestone.

---

## 0. Basic Language Features (Rust / Kotlin Native / Swift / TypeScript / Zig / Lua parity)

### Language Core
- [ ] `let`, `const`, `mut`, `var` declarations  
- [ ] Functions, closures, first-class functions  
- [ ] Control flow: `if`, `else`, `match`, `case`, `while`, `for`  
- [ ] Pattern matching and destructuring  
- [ ] Modules and imports  
- [ ] Tuples, records, enums, union types  
- [ ] Generics and type parameters  
- [ ] Traits / interfaces  
- [ ] Error handling (`try`/`catch`/`throw`, `Result`, `Option`)  
- [ ] Type inference  
- [ ] Nullable / non-nullable types  
- [ ] Compile-time evaluated constants  

---

## 1. String & Numeric Type System

### String Types
- [ ] `str`   → Rust `String`  
- [ ] `stref`    → `&str`  
- [ ] `ostr`     → `OsString`  
- [ ] `cstr`     → `CString`  
- [ ] `vbstr`    → `Vec<u8>`  
- [ ] `bstr`     → `&[u8]`  
- [ ] Conversions / encoding helpers (UTF-8, Base64, Hex)  
- [ ] C-FFI-safe string handling  

### Integer Types
- [ ] Signed: `i8`, `i16`, `i32`, `i64`, `i128`  
- [ ] Unsigned: `u8`, `u16`, `u32`, `u64`, `u128`  
- [ ] Literal suffix support & type inference  
- [ ] Overflow/underflow checking (debug)  
- [ ] Safe casting utilities  

---

## 2. Memory Management

- [ ] Manual memory (ownership & borrowing) – Rust backend  
- [ ] AOB GC – Automatic Ownership & Borrowing (Rust backend)  
- [ ] ARC GC – Kotlin Native / Swift backends  
- [ ] ORC GC – TypeScript / Lua backends  
- [ ] Interop between GC and manual modes  
- [ ] Lifetime analysis & leak detection tools  

---

## 3. Metaprogramming System

- [ ] Rust-style procedural macros  
- [ ] Nim-style `macro` / `template` blocks  
- [ ] Lisp-style symbolic macros (code-as-data)  
- [ ] Racket-style hygienic macros & scope control  
- [ ] CTFE (compile-time function execution)  
- [ ] Compile-time reflection / codegen  
- [ ] DSL authoring helpers  

---

## 4. Concurrency & Parallelism

- [ ] Async / await  
- [ ] Goroutines  
- [ ] Channels  
- [ ] Actor model (elixir/Pony-like)  
- [ ] Threading primitives (Nim-style threads, mutex, condvar)  
- [ ] Fork-join parallelism  
- [ ] Task parallelism  
- [ ] Data parallelism  
- [ ] Pipeline parallelism  
- [ ] SIMD parallelism / vector ops  
- [ ] Thread-local storage & atomics  

---

## 5. Backends

- [ ] Rust (manual + AOB)  
- [ ] Kotlin Native  
- [ ] Swift  
- [ ] TypeScript  
- [ ] Lua  
- [ ] Zig  
- [ ] Cross-platform build orchestration  
- [ ] Backend-specific optimizations  
- [ ] FFI layer for each backend  

---

## 6. Akuma Toolchain

- [ ] Interpreter for rapid prototyping  
- [ ] Optimizing compiler  
- [ ] Build system (multi-backend)  
- [ ] Package manager & dependency resolver  
- [ ] Test runner / coverage  
- [ ] Hot code reloading  
- [ ] Optional Akuma VM / runtime  
  - [ ] Concurrency scheduler  
  - [ ] Runtime GC for actors/goroutines  
  - [ ] Lightweight process isolation  

---

## 7. Onikage Developer Tools

- [ ] Language Server Protocol (LSP) server  
- [ ] Syntax highlighting & code formatting  
- [ ] Autocompletion and navigation  
- [ ] Type checking & diagnostics  
- [ ] Static analysis & linting  
- [ ] Documentation generator  
- [ ] REPL / interactive debugger  
- [ ] Security scanner  
- [ ] IDE plugins (VS Code, Neovim, JetBrains, etc.)  

---

## 8. Interoperability

- [ ] Rust crate linking  
- [ ] Zig / C interop  
- [ ] Lua embedding  
- [ ] Swift / Kotlin FFI  
- [ ] JS / TypeScript glue  
- [ ] WebAssembly output  
- [ ] Inline foreign code sections  

---

## 9. Documentation & Learning

- [ ] Formal language reference  
- [ ] “The Oni Book” introductory guide  
- [ ] Example & snippet repository  
- [ ] Online playground / web REPL  
- [ ] Migration guides

---

## 10. Ecosystem Infrastructure

- [ ] Standard library (pure Oni)  
- [ ] Utility crates (collections, math, I/O, async, net)  
- [ ] Public package registry & semver  
- [ ] Plugin system for Akuma / Onikage  
- [ ] Contribution & governance docs  

---

## 11. Advanced Features

- [ ] Modular architecture facilities  
- [ ] Optional runtime reflection  
- [ ] Sandboxing / embedded mode  
- [ ] Embedded-system support (via Zig/Rust)  
- [ ] Debugger & profiler  
- [ ] Cross-compilation pipeline  
- [ ] Binary size optimizations  
- [ ] Security-hardened memory / thread model  

---

## 12. Object-Oriented Programming (OOP) Models

- [ ] Structs with methods  
- [ ] Traits / interfaces for polymorphism  
- [ ] Trait objects (`dyn Trait`)  
- [ ] Extension methods & default impls  
- [ ] Implicit interface satisfaction (Go-style)  
- [ ] Optional class syntax  
- [ ] Inheritance & constructors (Kotlin-like)  
- [ ] Lua-style prototypes & metatables  
- [ ] Method overloading / overriding  
- [ ] Nullable vs non-nullable OOP types  
- [ ] Mixins & interface extension  
- [ ] Decorators / annotations  
- [ ] Abstract classes & members    

---

## 13. Source File Formats

### Standard `.oni` Files
- [ ] `.oni` files support Oni code only  
- [ ] Compiler parses and compiles `.oni` to all enabled backends:  
  - Rust  
  - TypeScript  
  - Swift  
  - Kotlin Native  
  - Lua  
  - Zig  
  - WASM  
  - Machine Code  
- [ ] Output generated files to same directory  
- [ ] Source maps for debugging and error tracking  
- [ ] Backend-specific code filtering using inline tags or compiler directives  
- [ ] Linting, formatting, REPL, and diagnostics via Onikage  

### Unified `.uof` Files
- [ ] Multi-language, multi-target hybrid format  
- [ ] Syntax: `[language=backend=filename]`  `[language=filename]`  
  - Example: `[oni=rust=engine]`, `[css=styles]`, `[html=index]`, `[sql=data]`  
- [ ] `[EndOfFile]` marks the end of each section  
- [ ] Compiler extracts and builds files per section  
- [ ] Oni section supports same backend targeting as `.oni` files  
- [ ] Compiler generates `.rs`, `.ts`, `.swift`, `.kt`, `.lua`, `.zig`, `.wasm`, `.html`, `.css`, `.sql` files  
- [ ] Output generated files into same directory as `.uof`  
- [ ] Compiler diagnostics mapped back to `.uof` lines  
- [ ] Onikage support:  
  - Linting `.uof` files  
  - Multi-language syntax highlighting  
  - Code folding per section  
  - Section-scoped REPL / tests  
  - Unified formatter  

---

## 14. Inline Assembly Support

- [ ] `asm` block for inline assembly (Rust/Zig-like)  
- [ ] Architecture-specific backends (x86_64, ARM, RISC-V, etc.)  
- [ ] Backend support for:
  - Rust (via `asm!`)
  - Zig (via native `asm`)  
- [ ] C-style inline assembly support where applicable  
- [ ] Register binding, memory access & clobber syntax  
- [ ] Safe escape hatches & memory sandboxing  
- [ ] Tooling support (Onikage: syntax highlighting, formatter)  
- [ ] Compilation diagnostics and VM fallback when unavailable  

