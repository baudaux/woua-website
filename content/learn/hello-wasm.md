+++
title = "Hello, WebAssembly"
description = ""
weight = 1
+++

This tutorial walks through writing and running your first woua program step by step.

## What you'll build

A program that prints a greeting to the terminal using the `io` library.

## The program

```woua
(include io)

(defn main ()
  (printf "hello %s!\n" (string "world")))
```

## What's happening

- `(include io)` pulls in the I/O library, which itself includes `wasi_p1` and `string`.
- `(defn main () ...)` declares the entry point — woua exports `_start` pointing to `main`.
- `(string "world")` allocates a `String` struct on the heap pointing to the static bytes for `"world"`.
- `(printf "hello %s!\n" ...)` is a compile-time macro that scans the format string and emits
  the appropriate print calls.

## Compile and run

```bash
wasmtime --dir . wouac/dist/wouac.wasm hello.woua -o hello.wat
wat2wasm hello.wat -o hello.wasm
wasmtime hello.wasm
# hello world!
```

## Next steps

Continue with [Variables and types](/learn/variables-and-types/) to learn how to declare
locals, work with integers, and define your own struct types.
