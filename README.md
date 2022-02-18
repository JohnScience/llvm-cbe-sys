# Rust bindings for [`LLVM-CBE`]

[`LLVM-CBE`] is a C-backend for [`LLVM`]. At the time of writing, [`rustc`] - the standard compiler for the Rust programming language - relies on [LLVM compiler infrastructure][`LLVM`] for machine code generation (and optimization). For that, [`rustc`] (internally) after going through a series of other Intermediate Representations (IRs) eventually produces so-called [**LLVM IR**] that then gets handled by [LLVM infrastrcture][`LLVM`]. You can learn more about [**LLVM IR**] and LLVM Bitcode File Format [here](https://llvm.org/docs/BitCodeFormat.html).

[`LLVM`]: https://en.wikipedia.org/wiki/LLVM
[`LLVM-CBE`]: https://github.com/JuliaComputingOSS/llvm-cbe
[`rustc`]: https://doc.rust-lang.org/rustc/what-is-rustc.html
[**LLVM IR**]: https://rustc-dev-guide.rust-lang.org/overview.html#:~:text=LLVM%20IR:%20This%20is