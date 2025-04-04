# Minigrep
一个 Rust 实现的简易文本搜索工具（仿 grep 基础功能），参考了[入门实践：文件搜索工具](https://course.rs/basic-practice/intro.html)，在这篇教程的基础上完善并优化了代码。

## 项目结构
```
src/
├── main.rs    # 命令行入口
├── lib.rs     # 核心逻辑模块
Cargo.toml     # 依赖管理
```

## 功能特性
- 指定文件内容搜索
- 环境变量控制大小写敏感
- 错误处理提示

## 使用
```bash
# 克隆项目
git clone https://github.com/yourname/minigrep.git
# 编译运行
cargo run -- <查询字符串> <文件路径>
```

## 示例
```bash
# 大小写敏感搜索
cargo run -- I sample.txt

# 大小写不敏感搜索（需设置环境变量）
IGNORE_CASE=1 cargo run -- I sample.txt
```

## To-do List

**1. 增强搜索能力**

- 正则表达式支持
  - 替换 contains 为 regex 库实现模式匹配（需引入 regex = \"1.5\" 依赖）
- 多文件搜索
  - 扩展 file_path 参数支持通配符（如 *.txt）1
- 上下文显示
  - 添加 -A 3 / -B 2 参数显示匹配行的前后内容

 
**2. 优化性能**

- 计划使用 rayon 并行迭代器改造搜索逻辑


**3. 优化交互界面**
- 彩色高亮输出
  - 集成 colored = \"2.0\" 库标注匹配字符串
- 进度指示器
  - 大文件搜索时显示进度条
