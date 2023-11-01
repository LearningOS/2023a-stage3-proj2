# About

本项目是开源操作系统训练营第三阶段项目二（Arceos宏内核）的第一个实验的测例。

## How to use

请按指导书的要求把 `testcases` 放到你第二阶段实验项目的根目录下。假设你的第二阶段项目在 `../2023a-rcore-yourname`，那么可以通过如下命令完成复制

```bash
cp -ar ./testcases ../2023a-rcore-yourname
```

在 `testcases` 下，`make build` 会将所有测例编译到 `testcases/build` 文件夹，`make clean` 会清除所有中间文件。

## Questions

- Q：出现报错 `make: riscv64-linux-musl-gcc: No such file or directory`

- - A：可能是由于没有安装交叉编译工具链 `https://musl.cc/riscv64-linux-musl-cross.tgz`

