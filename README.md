# Nocturne OS

**Nocturne** is a memory-safe, microkernel-style operating system written in **Rust**, designed from scratch with a strong emphasis on **cybersecurity**, **process isolation**, and **modern OS architecture**. It is a personal project aimed at building a minimal but secure kernel suitable for high-integrity computing environments.

---

## 🚀 Features (WIP)

- Bare-metal boot using custom kernel in Rust
- Memory-safe kernel using `#![no_std]`
- QEMU emulation for fast testing
- Paging and virtual memory isolation
- Capability-based security model (like Capsicum / Fuchsia)
- Sandboxed process design (secure syscall interface)
- Logging and audit system (write-once logs)
- Secure boot with kernel verification (SHA-based)

---

## 🎯 Project Goal

> To create a secure-by-design OS kernel using Rust, focusing on reducing attack surfaces, preventing common memory vulnerabilities, and implementing modern isolation & security primitives.

This project is part of my journey to understand OS internals, secure kernel development, and systems programming in Rust.

---

## 🛠️ Tech Stack

| Layer           | Stack / Crate                |
|----------------|------------------------------|
| Language        | Rust (`#![no_std]`)          |
| Architecture    | `x86_64`                     |
| Bootloader      | [`bootloader`](https://github.com/rust-osdev/bootloader) |
| Emulator        | QEMU                         |
| Filesystem      | Custom / FAT (planned)       |
| Cryptography    | [`ring`](https://crates.io/crates/ring) |
| Security Model  | MAC + Capabilities           |

---

## 🧰 Getting Started

### Requirements:
- Linux/macOS or WSL2
- Rust + `cargo` + `bootimage`
- `qemu-system-x86_64`
- `nasm`, `lld`, and `llvm-tools-preview`

### Build and Run:
```bash
cargo bootimage
qemu-system-x86_64 -drive format=raw,file=target/x86_64-blog_os/debug/bootimage-nocturne.bin
