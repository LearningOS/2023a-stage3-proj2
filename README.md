# About

本项目用于开源操作系统训练营第三阶段项目二（Arceos宏内核）的实验，包含了实验中需要用到的代码和测试用例。

## How to use

### hellostd

第二章实验使用的测例 `hellostd` 的可执行文件。指导书中会用它做一个小测试。

### ctl.rs

请把 `ctl.rs` 放到 `Starry` 的 `ulib/axstarry/syscall_fs/src/imp` 下，替换掉同名文件。

### fatfs.rs

请把 `fatfs.rs` 放到 `Starry` 的 `modules/axfs/src/fs/` 下，替换掉同名文件。

这个文件的修改其实只有一行，你也可以在原本文件的 235 行加上一句 `let dst_path = dst_path.trim_matches('/');`，将 `rename` 函数变成

```rust
    fn rename(&self, src_path: &str, dst_path: &str) -> VfsResult {
        // `src_path` and `dst_path` should in the same mounted fs
        debug!(
            "rename at fatfs, src_path: {}, dst_path: {}",
            src_path, dst_path
        );
        let dst_path = dst_path.trim_matches('/');
        self.0
            .rename(src_path, &self.0, dst_path)
            .map_err(as_vfs_err)
    }
```

这样做等同于替换了该文件。