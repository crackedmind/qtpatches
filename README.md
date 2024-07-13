# Windows XP Support patches for Qt 5.9

Patches moslty based on Qt 5.6 source code

## Prerequisites
1. Perl
2. Jom

## Build with Visul C++ 2017 Toolchain
- Install Visual Studio 2022, also select 14.16 toolchain and winxp support
- Add Perl and jom to %PATH%
- `C:\Program Files (x86)\Microsoft Visual Studio\2022\Community\VC\Auxiliary\Build\vcvarsall.bat" x86 -vcvars_ver=14.16`
- `set PATH=C:\Program Files (x86)\Microsoft SDKs\Windows\v7.1A\Bin;%PATH%`
- `set INCLUDE=C:\Program Files (x86)\Microsoft SDKs\Windows\v7.1A\Include;%INCLUDE%`
- `set LIB=C:\Program Files (x86)\Microsoft SDKs\Windows\v7.1A\Lib;%LIB%`
- `git apply *.patch`
- `configure -prefix e:\Qt\5.9.9_xp -opensource -confirm-license -debug-and-release -nomake examples -no-compile-examples -nomake tests -no-sse2 -no-sse3 -no-ssse3 -no-sse4.1 -no-sse4.2 -no-avx -no-avx2 -platform win32-msvc-xp -no-angle -no-opengl`
- `jom`
- `jom install`

