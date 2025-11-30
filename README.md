# Rust 项目模板

## 环境设置

### 安装 Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

### 安装 VSCode 插件

- `Dependi`: Rust 包管理
- `Even Better TOML`: TOML 文件支持
- `Better Comments`: 优化注释显示
- `Error Lens`: 错误提示优化
- `GitLens — Git supercharged`: Git 增强
- `Github Copilot`: 代码提示
- `indent-rainbow`: 缩进显示优化
- `Prettier - Code formatter`: 代码格式化
- `REST Client`: REST API 调试
- `rust-analyzer`: Rust 语言支持
- `Rust Test lens`: Rust 测试支持
- `Rust Test Explorer`: Rust 测试概览
- `TODO Highlight`: TODO 高亮
- `vscode-icons`: 图标优化
- `YAML`: YAML 文件支持

### 安装 cargo generate

[cargo generate](https://github.com/cargo-generate/cargo-generate) 是一个用于生成项目模板的工具。它可以使用已有的 github repo 作为模版生成新的项目

```bash
cargo install cargo-generate
```

使用 `mantic-bootcamp/template.git` 模版生成基本的代码

```bash
cargo generate mantic-bootcamp/template.git
```

### 安装 pre-commit

[pre-commit](https://pre-commit.com/) 是一个代码检查工具，可以在提交代码前进行代码检查。

```bash
pipx install pre-commit  #ubuntu不建议使用pip安装，防止与系统包产生依赖冲突

# 建议使用uv安装
curl -LsSf https://astral.sh/uv/install.sh | sh
uv pip install pre-commit

# 安装 git hook scripts
pre-commit install

# 配置需手动创建： .pre-commit-config.yaml
```

### 安装 Cargo deny

[Cargo deny](https://github.com/EmbarkStudios/cargo-deny) 是一个 Cargo 插件，可以用于检查依赖的安全性。

```bash
cargo install --locked cargo-deny # 安装
cargo deny init #生成默认配置
```

### 安装 typos

[typos](https://github.com/crate-ci/typos) 是一个拼写检查工具。

```bash
cargo install typos-cli # 安装
# 配置需手动创建： _typos.toml
```

### 安装 git cliff

[git cliff](https://git-cliff.org/docs/) 是一个生成 `changelog` 的工具。

```bash
cargo install git-cliff # 安装
git-cliff --init  # 生成默认配置
```

更改仓库地址为自己的仓库地址

```toml
postprocessors = [
    # Replace the placeholder <REPO> with a URL.
    { pattern = '<REPO>', replace = "https://github.com/mantic-bootcamp/template" },
]
```

### 安装 cargo nextest

[cargo nextest](https://nexte.st/) 是一个 Rust 增强测试工具。

```bash
cargo install cargo-nextest --locked
```

## 新项目

初始化步骤
```bash
cargo generate mantic-bootcamp/template
pre-commit install
```

提交代码

```bash
git add .
git commit -a     # 这里会自动执行pre-commit
```