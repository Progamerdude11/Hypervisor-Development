<div align="center">

```
██╗  ██╗██╗   ██╗██████╗ ███████╗██████╗ ██╗   ██╗██╗███████╗ ██████╗ ██████╗
██║  ██║╚██╗ ██╔╝██╔══██╗██╔════╝██╔══██╗██║   ██║██║██╔════╝██╔═══██╗██╔══██╗
███████║ ╚████╔╝ ██████╔╝█████╗  ██████╔╝██║   ██║██║███████╗██║   ██║██████╔╝
██╔══██║  ╚██╔╝  ██╔═══╝ ██╔══╝  ██╔══██╗╚██╗ ██╔╝██║╚════██║██║   ██║██╔══██╗
██║  ██║   ██║   ██║     ███████╗██║  ██║ ╚████╔╝ ██║███████║╚██████╔╝██║  ██║
╚═╝  ╚═╝   ╚═╝   ╚═╝     ╚══════╝╚═╝  ╚═╝  ╚═══╝  ╚═╝╚══════╝ ╚═════╝ ╚═╝  ╚═╝
```

### *Intel VT-x · VMX · EPT · Complete Reference*

**A HTML book on building hypervisor drivers in C++.**

---

![Beta](https://img.shields.io/badge/edition-BETA-c8956c?style=for-the-badge&labelColor=1a1208)
![Intel VT-x](https://img.shields.io/badge/Intel-VT--x%20%2F%20VMX-0071c5?style=for-the-badge&labelColor=1a1208)
![Language](https://img.shields.io/badge/language-C%2B%2B%20%26%20MASM%20x64-c8956c?style=for-the-badge&labelColor=1a1208)
![Ring](https://img.shields.io/badge/privilege-Ring%20%E2%88%921-8b0000?style=for-the-badge&labelColor=1a1208)
![Chapters](https://img.shields.io/badge/chapters-145-2a6e3f?style=for-the-badge&labelColor=1a1208)
![Platform](https://img.shields.io/badge/platform-Windows%20x64%20Kernel-555?style=for-the-badge&labelColor=1a1208)

</div>

---

> [!WARNING]
> **BETA EDITION** This is an active work in progress. Core chapters are complete and technically verified. Some chapters currently exist as structured outlines. Corrections, feedback, and pull requests are all welcome.

---

## What Is This?

A **single-file HTML reference book** for engineers who want to build real Intel VT-x hypervisors from scratch, not toy demos, but real production grade VMX root drivers that can intercept, inspect, and control a running Windows kernel from Ring −1.

Every technique is grounded in **Volume 3C of the Intel Software Developer's Manual**. The same VMX lifecycle, VMCS field encodings, and EPT structures that power Xen, KVM, Hyper-V, Bareflank, and DRAKVUF are documented here with bit-exact precision.

```
┌─────────────────────────────────────────────────────────┐
│                    Your Hypervisor                      │  ← Ring −1  VMX Root
│              VMXON / VMCS / EPT Engine                  │
├─────────────────────────────────────────────────────────┤
│                   Guest OS Kernel                       │  ← Ring 0   NT / Linux
│             Drivers · HAL · System Calls                │
├─────────────────────────────────────────────────────────┤
│                 Guest Applications                      │  ← Ring 3   User Space
│              Win32 / POSIX / Everything Else            │
└─────────────────────────────────────────────────────────┘
```

---

## The Book at a Glance

| | |
|---|---|
| **Format** | Single self-contained `.html` — open in any browser, no server needed |
| **Audience** | Windows kernel developers, security researchers, hypervisor engineers |
| **Scope** | Intel x86-64 VMX (AMD-V and ARM covered as reference overviews) |
| **Code** | C++ with MSVC intrinsics + MASM x64 assembly |
| **Reference** | Every encoding tied to Intel SDM Vol. 3C, Chapters 23–34 and Appendix B |
| **Chapters** | 145 total across foundations, EPT, advanced topics, and appendices |

---


## Prerequisites

You should be comfortable with all of the following:

- **C and C++** — pointers, structs, bitfields, bit manipulation
- **x64 assembly** — register operations, stack frames, Windows x64 calling convention
- **Windows kernel driver development** — `DriverEntry`, IRQL, pool allocation, WDK basics
- **Hex and binary** — you will read Intel SDM tables constantly
- **Basic OS memory management** — virtual vs physical addresses, page tables

### Required Tools

| Tool | Purpose |
|------|---------|
| Visual Studio 2022 | C++ and WDK workloads |
| VMware Workstation Pro | Nested VT-x enabled — safe development environment |
| WinDbg Preview | Kernel debugging over network or serial |
| Intel SDM Volume 3C | Your primary reference alongside this book |
| Dedicated Windows 10/11 x64 VM | **Never develop on your main machine** |

---

## Getting Started


# Download the book.
# Open the book and that's it


No build step. No dependencies. No server.

---

## Scope and Limitations

> [!NOTE]
> This reference targets **Intel x86-64 VMX exclusively**. AMD-V (SVM) shares many concepts but uses different MSRs, VMCB structures, and intercept mechanisms. AMD-V and ARM virtualization extensions are covered as overview chapters only, not as primary development references.

---

## Contributing

This is a beta — rough edges exist and expert eyes are appreciated.

**What's useful:**
- Technical corrections (wrong bit positions, incorrect encodings, stale SDM references)
- Clarity improvements on complex sections
- Missing exit reasons or VMCS fields in the appendix tables
- Typos and broken formatting

Open an issue or submit a PR. All corrections will be credited.

---



*Built against Intel SDM Volume 3C · Tested on Windows 10/11 x64 with nested VT-x*

**⚠️ BETA EDITION — expect incomplete chapters and evolving content ⚠️**


