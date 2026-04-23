+++
title = "Getting started"
weight = 1
+++

## Prerequisites


You can use woua in two ways:

- [**In exaequOS**](#in-exaequos): Use the prebuilt environment with everything ready to go—no setup needed.
- [**On your local machine**](#on-your-local-machine): Install the required tools and build the compiler yourself.


### In exaequOS

All prerequisites are preinstalled. Just open a terminal and start using woua!

[exaequOS](https://exaequos.com) is a Web computer that fully runs in your browser, with all the tools you need preinstalled. No setup required—just open a terminal and start using woua!
 
exaequOS also includes a WASM WASI runtime (called **wex**), so you can run apps developed in woua directly in your browser environment.

### On your local machine

You need two tools:

- **wasmtime** — WASI-compatible WebAssembly runtime
- **wat2wasm** — assembles `.wat` text modules to binary `.wasm` (part of the [WABT toolkit](https://github.com/WebAssembly/wabt))

Install them using your system package manager, or download official releases:

- **Debian/Ubuntu:**
  ```bash
  sudo apt install wasmtime wabt
  ```
- **macOS (Homebrew):**
  ```bash
  brew install wasmtime wabt
  ```
- **Windows:**
  - **wasmtime:** Download the latest Windows release from the [official site](https://github.com/bytecodealliance/wasmtime/releases) and extract the archive. Add the folder to your PATH.
  - **wat2wasm:** Download the latest WABT Windows release from the [Releases page](https://github.com/WebAssembly/wabt/releases) (look for `wabt-...-windows.zip`), extract, and add the folder to your PATH.

---



## Getting the source

Clone the woua repository from GitHub:

```bash
git clone https://github.com/baudaux/woua-lang
```

## Building the compiler

From the `woua-lang/wouac` directory:


```bash
cd woua-lang/wouac
npm install
npm run build
```

This produces `wouac/dist/wouac.wasm`.


## Building the demos

You can build all the example programs in the `demos` directory with:

```bash
./build_demos.sh
```



## Compiling a program

In exaequOS, you can use the built-in WASI runtime wex. In your project directory:

```bash
wex --dir . --dir /usr/lib/woua::lib /usr/bin/wasm/wouac.wasm hello_world.woua -o hello_world.wat
wat2wasm hello_world.wat -o hello_world.wasm
wex hello_world.wasm
```

On your own machine, you can use wasmtime. In your project directory:

```bash
wasmtime --dir . --dir <path/to/woua-lib>::lib <path/to/wouac>/dist/wouac.wasm hello_world.woua -o hello_world.wat
wat2wasm hello_world.wat -o hello_world.wasm
wasmtime hello_world.wasm
```

## Your first program

```woua
(include io)

(defn main ()
  (printf "Hello, World!"))
```

Save as `hello.woua`, compile and run — you should see:

```
Hello, World!
```
