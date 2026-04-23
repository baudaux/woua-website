+++
title = "Standard library"
weight = 3
+++

## `core` — language foundation

Included automatically via `(include core)`. Defines all numeric operators,
comparison operators, and literal types.

## `wasi_p1` — WASI preview 1 imports

```woua
(include wasi_p1)
```

Declares the full WASI preview 1 surface: `fd_write`, `fd_read`, `proc_exit`, etc.

## `string` — string utilities

```woua
(include string)
```

| Function | Description |
|----------|-------------|
| `(string-len s)` | byte length of `s` |
| `(string-ptr s)` | raw data pointer |
| `(string= a b)` | 1 if equal, 0 otherwise |
| `(string-eq s "lit")` | compare runtime string with a literal |
| `(string-copy s)` | allocate a fresh copy |
| `(string-slice s offset len)` | sub-string (no copy) |
| `(string-concat a b)` | concatenate into a new string |
| `(string-index-of-byte s b)` | first index of byte `b`, or -1 |

## `io` — input/output

```woua
(include io)
```

| Macro / function | Description |
|-----------------|-------------|
| `(print sym)` | write a static string to stdout |
| `(print-string s)` | write a runtime `String` to stdout |
| `(print-int n)` | write an i32 as decimal |
| `(print-int64 n)` | write an i64 as decimal |
| `(print-char c)` | write a single byte as a character |
| `(printf "fmt" args...)` | formatted output (compile-time) |
| `(write fd ptr len)` | raw write to file descriptor |
| `(write-string fd s)` | write a `String` to a file descriptor |
| `(read-line fd buf maxlen)` | read a line from a file descriptor |
