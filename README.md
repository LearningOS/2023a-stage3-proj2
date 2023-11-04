# About

本项目用于开源操作系统训练营第三阶段项目二（Arceos宏内核）的实验，包含了实验中需要用到的代码和测试用例。

## How to use

### testcases/

请按指导书的要求把 `testcases` 放到你第二阶段实验项目的根目录下。假设你的第二阶段项目在 `../2023a-rcore-yourname`，那么可以通过如下命令完成复制

```bash
cp -ar ./testcases ../2023a-rcore-yourname
```

在 `testcases` 下，`make build` 会将所有测例编译到 `testcases/build` 文件夹，`make clean` 会清除所有中间文件。

### loaders/

1. 把这个文件夹放到放到你第二阶段实验项目的 `os/src/` 下，也即让它成为一个和 `fs` `mm` `syscall` 等这些子模块同级的模块。
2. 在 `os/src/main.rs` 中加入声明 `pub mod loaders;`
3. 跟随指导书的指引，在 `os/src/task/process.rs:ProcessControlBlock::exec` 函数中，使用 `loader` 模块提供的功能，替换掉原本“手动”写入用户栈的代码。

> 这段代码来自往届比赛的一个一等奖作品。这是在内核中使用外部代码的一种方式，但很明显这样不太 “Rusty”。
> 
> 如果有兴趣，你可以把 `loaders/mod.rs` 开头提到的那个模块整理成一个 `Rust Crate`，这样我们就可以在 `os/Cargo.toml` 里直接引入这个模块，而不是使用“丑陋”的复制粘贴了。当然，这并不是实验的必做题。
> 
> 下一届课程就有可能用到你改造的模块！

## Questions

- Q：出现报错 `make: riscv64-linux-musl-gcc: No such file or directory`

- - A：可能是由于没有安装交叉编译工具链 `https://musl.cc/riscv64-linux-musl-cross.tgz`
