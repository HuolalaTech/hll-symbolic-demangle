[![License](https://img.shields.io/badge/License-Apache%202.0-orange.svg)](https://github.com/HuolalaTech/hll-symbolic-demangle/blob/main/LICENSE.txt) 

> [English](https://github.com/huolalatech/hll-symbolic-demangle/blob/master/README.md) | 

## hll-symbolic-demangle是什么

hll-symbolic-demangle是货拉拉基于开源项目[symbolic-demangle](https://github.com/getsentry/symbolic/blob/master/symbolic-demangle/README.md)自行迭代的符号demangle工具。最大的差异在于支持了5.10版本的swift符号demangle。通过直接安装whl的方式可以快速实现调用。
支持多种语言：

* C++ (GCC-style compilers and MSVC)
* Rust (both `legacy` and `v0`)
* Swift (up to Swift 5.10)
* ObjC (only symbol detection)

## 使用

```
use symbolic::common::{Language, Name};
use symbolic::demangle::{Demangle, DemangleOptions};

let name = Name::new("__ZN3std2io4Read11read_to_end17hb85a0f6802e14499E");
assert_eq!(name.detect_language(), Language::Rust);
assert_eq!(name.try_demangle(DemangleOptions::default()), "std::io::Read::read_to_end");
```


## 注意

因为环境问题，可能在部分Linux服务器上运行失败，遇到这种情况，可参考掘金文章《货拉拉是如何实现symbolic demangle？》自行编译匹配当前环境的python包。
