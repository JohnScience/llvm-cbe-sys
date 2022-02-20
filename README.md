# Rust bindings for [`LLVM-CBE`] (HALTED)

[`LLVM-CBE`] is a C-backend for [`LLVM`], i.e. a tool that turns [LLVM bitcode] [^1] into C. It requires to be built near LLVM, which was found to be so heavy dependency that shipping it as Cargo crate would be absurd.

# Motivation

The goal that the authors have in mind is combining [`LLVM-CBE`] with [`SWIG`] for the purpose of facilitation **cross-language code reuse**. [`SWIG`] is a software development tool that connects programs written in C and C++ with a variety of high-level programming languages: (1) C# (Mono and MS .NET), (2) D, (3) Go, (4) Guile, (5) Java, (6) JavaScript (Node.js, V8, and WebKit), (7) Lua, (8) MzScheme/Racket, (9) OCaml, (10) Octave, (11) Perl, (12) PHP, (13) Python, (14) R, (15) Ruby, (16) Scilab, and (17) Tcl/Tk. For every of the earlier mentioned target languages, [`SWIG`] can generate wrappers around C libraries produced by [`LLVM-CBE`].

Generation of these libraries-wrappers from [LLVM bitcode] would be possible for all programming languages whose build tools offer [**LLVM IR**] generation: (1) Rust, (2) ActionScript, (3) Ada, (4) C#, (5) Common Lisp, (6) PicoListp, (7) Crystal, (8) CUDA, (9) D, (10) Delphi, (11) Dylan, (12) Forth, (13) Fortran, (14) Free Basic, (15) Free Pascal, (16) Graphical G, (17) Halide, (18) Haskell, (19) Java bytecode, (20) Julia, (21) Kotlin, (22) Lua, (23) Objective-C, (24) OpenCL, (25) PostreSQL and PLpgSQL, (26) Ruby, (27) Scala, (28) Swift, (29) XC, (30) Xojo, and (31) Zig.[^2]

# Current goal: Rust

 At the time of writing, [`rustc`] - the standard compiler for the Rust programming language - relies on [LLVM compiler infrastructure][`LLVM`] for machine code generation and optimization. For that, [`rustc`] internally, after transforming the Rust source code through a series of other Intermediate Representations (IRs), eventually produces so-called [**LLVM IR**] that then gets handled by [LLVM infrastructure][`LLVM`]. You can learn more about [**LLVM IR**] and LLVM Bitcode File Format [here][LLVM bitcode].

Thus, this combination when applied for Rust would be not just on par with [`cbindgen`](https://github.com/eqrion/cbindgen) but would also be considerably better.

# F.A.Q.
* 
  **Q**: What does `*-sys` mean?
  **A**: `*-sys` is a naming convention for crates that help Rust programs use `C` ("system") libraries, e.g. `libz-sys`, `kernel32-sys`, `lcms2-sys`.[^3]

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

[^1]: There is no typo. Bitcode, [as the maintainers admit](https://llvm.org/docs/BitCodeFormat.html#:~:text=anachronistically%20known%20as%20bytecode), sometimes indeed is anachronistically called bytecode.
[^2]: https://en.wikipedia.org/wiki/LLVM
[^3]: https://kornel.ski/rust-sys-crate

[`LLVM`]: https://en.wikipedia.org/wiki/LLVM
[`LLVM-CBE`]: https://github.com/JuliaComputingOSS/llvm-cbe
[`rustc`]: https://doc.rust-lang.org/rustc/what-is-rustc.html
[**LLVM IR**]: https://rustc-dev-guide.rust-lang.org/overview.html#:~:text=LLVM%20IR:%20This%20is
[`SWIG`]: http://www.swig.org/
[LLVM bitcode]: https://llvm.org/docs/BitCodeFormat.html