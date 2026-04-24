+++
title = "Language reference"
description = "How to code in Woua"
weight = 2
+++


## Overview

Woua programming language aims at creating WebAssembly programs. Woua syntax is inspired from Lisp syntax.

## Syntax Basics

### Whitespace and Comments

### Identifiers and Naming

## Literals

### Numbers
| Syntax | Type | Example |
|--------|------|---------|
| `-?[0-9]+` | `:i32` | `42`, `-7` |
| `-?[0-9]+i64` | `:i64` | `1000i64` |
| `0x…` | `:i32` | `0xFF` |
| `-?[0-9]*\.[0-9]+` | `:f32` | `3.14` |
| `'c'` | `:i32` | `'A'` → 65, `\n'` → 10 |

### Strings
| Syntax | Type | Example |
|--------|------|---------|
| `"…"` | `:String` | `"hello"` |

### Booleans
<!-- Boolean literal examples go here -->

### Nil/Unit
<!-- Nil/unit literal examples go here -->

## Types

### Primitive Types
<!-- Primitive type docs go here -->

### Structs and Value Types
<!-- Struct/value type docs go here -->

### Reference Types
<!-- Reference type docs go here -->

### Type Annotations and Inference
<!-- Type annotation/inference docs go here -->

## Variables and Bindings

### let, set!
<!-- let/set! docs go here -->

### Scoping Rules
<!-- Scoping rules docs go here -->

## Functions

### defn
```woua
(defn add (a :i32 b :i32) :i32
  (+ a b))
```

### Parameters and Return Types
<!-- Parameter/return type docs go here -->

### Variadic Functions
<!-- Variadic function docs go here -->

### Anonymous Functions (lambdas)
<!-- Lambda docs go here -->

## Macros

### defmacro
```woua
(defmacro when (cond body)
  (if cond body 0))
```

### Macro Expansion
<!-- Macro expansion docs go here -->

### Variadic Macros
```woua
(defmacro my-macro (fixed ...rest)
  ...)
```

## Control Flow

### if, cond
<!-- if/cond docs go here -->

### when, unless
<!-- when/unless docs go here -->

### loop, recur, while
<!-- loop/recur/while docs go here -->

### match/case
<!-- match/case docs go here -->

## Data Structures

### Arrays/Vectors
<!-- Array/vector docs go here -->

### Maps/Dictionaries
<!-- Map/dictionary docs go here -->

### Sets
<!-- Set docs go here -->

## Pattern Matching
<!-- Pattern matching docs go here -->

## Modules and Imports

### include, import, require
<!-- include/import/require docs go here -->

## Interop

### WASI/host calls
<!-- WASI/host call docs go here -->

### Foreign Function Interface (FFI)
<!-- FFI docs go here -->

## Memory Management

### Value vs Reference Semantics
<!-- Value/reference semantics docs go here -->

### Garbage Collection
<!-- GC docs go here -->

## Error Handling

### try/catch, error values
<!-- Error handling docs go here -->

## Standard Library Overview

### IO, Math, String, etc.
<!-- Standard library docs go here -->

## Compilation and Execution

### Building
<!-- Build docs go here -->

### Running
<!-- Run docs go here -->

### WASM/WASI specifics
<!-- WASM/WASI docs go here -->

## Appendix

### Grammar
<!-- Grammar docs go here -->

### Reserved Words
<!-- Reserved words docs go here -->

### Style Guide
<!-- Style guide docs go here -->
