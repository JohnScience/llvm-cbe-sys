# Rust bindings for [`LLVM-CBE`]

[`LLVM-CBE`] is a C-backend for [`LLVM`]. At the time of writing, [`rustc`] - the standard compiler for the Rust programming language - relies on [LLVM compiler infrastructure][`LLVM`] for machine code generation and optimization. For that, [`rustc`] internally, after transforming the Rust source code through a series of other Intermediate Representations (IRs), eventually produces so-called [**LLVM IR**] that then gets handled by [LLVM infrastructure][`LLVM`]. You can learn more about [**LLVM IR**] and LLVM Bitcode File Format [here](https://llvm.org/docs/BitCodeFormat.html).

The goal that the authors have in mind is combining [`LLVM-CBE`] with [`SWIG`], a software development tool that connects programs written in C and C++ with a variety of high-level programming languages: (1) C# (Mono and MS .NET), (2) D, (3) Go, (4) Guile, (5) Java, (6) JavaScript (Node.js, V8, and WebKit), (7) Lua, (8) MzScheme/Racket, (9) OCaml, (10) Octave, (11) Perl, (12) PHP, (13) Python, (14) R, (15) Ruby, (16) Scilab, and (17) Tcl/Tk. This combination would be not just on par with [`cbindgen`](https://github.com/eqrion/cbindgen) but would be considerably better.

# License

<sup>
Licensed under either of <a href="LICENSE-APACHE">Apache License, Version
2.0</a> or <a href="LICENSE-MIT">MIT license</a> at your option.
</sup>

<br>

<sub>
Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in this crate by you, as defined in the Apache-2.0 license, shall
be dual licensed as above, without any additional terms or conditions.
</sub>

[`LLVM`]: https://en.wikipedia.org/wiki/LLVM
[`LLVM-CBE`]: https://github.com/JuliaComputingOSS/llvm-cbe
[`rustc`]: https://doc.rust-lang.org/rustc/what-is-rustc.html
[**LLVM IR**]: https://rustc-dev-guide.rust-lang.org/overview.html#:~:text=LLVM%20IR:%20This%20is
[`SWIG`]: http://www.swig.org/