[![License](https://img.shields.io/badge/License-Apache%202.0-orange.svg)](https://raw.githubusercontent.com/HuolalaTech/hll-symbolic-demangle/master/LICENSE) 

> [中文文档](https://github.com/huolalatech/hll-symbolic-demangle/blob/master/README-zh.md) | 

## What is hll-symbolic-demangle

hll-symbolic-demangle is a symbol demangle tool iterated by Lalamove based on the open source project [symbolic-demangle] ( https://github.com/getsentry/symbolic/blob/master/symbolic-demangle/README.md ). The biggest difference is that it supports the 5.10 version of swift symbol demangle. It can be quickly called by directly installing whl.
Supports multiple languages:

* C++ (GCC-style compilers and MSVC)
* Rust (both `legacy` and `v0`)
* Swift (up to Swift 5.10)
* ObjC (only symbol detection)

## Usage

```
use symbolic::common::{Language, Name};
use symbolic::demangle::{Demangle, DemangleOptions};

let name = Name::new("__ZN3std2io4Read11read_to_end17hb85a0f6802e14499E");
assert_eq!(name.detect_language(), Language::Rust);
assert_eq!(name.try_demangle(DemangleOptions::default()), "std::io::Read::read_to_end");
```


## Attention

Because of environmental issues, it may fail to run on some Linux servers. In this case, you can refer to the article "How does Lalamove implement symbolic demangle?" by compiling the Python package that matches the current environment.
