# Visual Studio / CI Notes

## Current project

Open: cs2/velocity-cs2/velocity-cs2.slnx

Project: cs2/velocity-cs2/velocity-cs2.vcxproj

Configurations present:
- Development|x64
- Ship|x64

Toolchain:
- ClangCL
- LLVM 19
- C++ latest

## Recommended audit configuration

For ordinary code review and static analysis, use a separate configuration with:
- x64
- C++20 or latest
- warnings at level 4
- security checks enabled
- SDL checks enabled
- optimization matching the test objective

Do not use audit settings to bypass runtime protections or anti-cheat checks.

## Build verification

A real Visual Studio build must be performed on a Windows host with the required LLVM/Visual Studio components and third-party libraries available.

The following cannot be truthfully claimed from repository inspection alone:
- successful DLL compilation;
- successful link;
- successful runtime load;
- successful CS2 integration.

## Resource verification

The resource pack should be generated from the exact source revision being tested. Because the resource IDs are counter/order dependent, mixing packs from different revisions is unsafe.