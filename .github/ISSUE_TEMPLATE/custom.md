---
name: Request access for building gollvm
about: Build automation of https://go.googlesource.com/gollvm/ (llvm-goc and libgo) and end-user Go projects
title: 'Aarch64 port of gollvm'
labels: ''
assignees: 'vielmetti, pgmwoa'

---


Ivan Serdyuk, local.tourist.kiev@gmail.com, Self-employed, Web developer/DevOps
Than Macintosh, thanm@google.com, Google, Compiler developer
Ian Lance Taylor, ian@airs.com, Google, Programmer
Eric Fang, eric.fang@arm.com, ARM, Software Engineer



Gollvm is an LLVM-based Go compiler. It incorporates “gofrontend” (a Go language front end written in C++ and shared with GCCGO), a bridge component (which translates from gofrontend IR to LLVM IR), and a driver that sends the resulting IR through the LLVM back end.

Probably ARM centric Go developers

https://github.com/llvm/llvm-project.git
https://go.googlesource.com/gollvm/
https://go.googlesource.com/gofrontend
https://github.com/libffi/libffi.git
https://github.com/ianlancetaylor/libbacktrace.git
https://gmplib.org/download/gmp/gmp-6.2.0.tar.bz2
https://www.mpfr.org/mpfr-current/mpfr-4.1.0.tar.bz2
https://ftp.gnu.org/gnu/mpc/mpc-1.2.0.tar.gz

What would be required:
- complete list of CPU features, for available ARM cores/CPU models (LLVM related)
- VMs, containers on ARM servers for
- integration with CI pipelining ("debug", "release" builds)
- pre-defined configurations of specific OSs (mainly Linux distros/falvors - but ARM ports of other OSs are welcome, as well), for testing installation
- a list of end-user software, in Golang, to build with gollvm (result would be shared with external people, to open bug reports/patching)
- SIMD and auto-vect. benchmarking tools (like for gonum and other stuff)

There are no specific issues, regarding general CI, for building gollvm (open for propositions).
As for building Kubernetes, containerd and other CNCF projects - available testing pipelines, to test virtualization middleware, would be of help (hence that despite the same front-end calling conventions and the linker differs, compared to the main-go)

>Are you testing every check-in on arm64? (Would you like to?) If so, share a public URL of a CI dashboard.
Not sure what this means, really.

There where some tryouts to use Github Actions (for x86_64, on Azure):
https://github.com/advancedwebdeveloper/clang_test_cpu_features/blob/main/.github/workflows/llvm.yml
If you are providing https://docs.github.com/en/free-pro-team@latest/actions/hosting-your-own-runners/about-self-hosted-runners , on ARM servers - we could give in a try.

I am heading to contribute into i686 support (unrelated to this request).
My interest is in contributing into both Golang's language front-end and specific back-ends.
I am interested to promote gollvm among the owners of small and entermidiate sized businesses (variuous domains).


