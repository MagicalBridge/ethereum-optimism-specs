<div align="center">
  <br />
  <br />
  <a href="https://optimism.io"><img alt="Optimism" src="https://raw.githubusercontent.com/ethereum-optimism/brand-kit/main/assets/svg/OPTIMISM-R.svg" width=600></a>
  <br />
  <h3><a href="https://optimism.io">Optimism</a> is Ethereum, scaled.</h3>
  <h3><a href="https://optimism.io">Optimism</a> 是以太坊的扩容解决方案。</h3>
  <br />
</div>

## OP Stack Specification
## OP Stack 规范

This repository contains the [Specs Book](https://static.optimism.io/specs).
本仓库包含 [规范手册](https://static.optimism.io/specs)。

Please chat with us on the [discussion board](https://github.com/ethereum-optimism/specs/discussions).
欢迎在[讨论区](https://github.com/ethereum-optimism/specs/discussions)与我们交流。

## Contributing
## 贡献指南

We welcome your contributions. Read through [CONTRIBUTING.md](./CONTRIBUTING.md) for a general overview of the contributing process for this repository.
我们欢迎您的贡献。请阅读 [CONTRIBUTING.md](./CONTRIBUTING.md) 了解本仓库贡献流程的总体概述。

### Dependencies
### 依赖项

#### Using `mise`
#### 使用 `mise`

We use [`mise`](https://mise.jdx.dev/) as a dependency manager for these tools.
Once properly installed, `mise` will provide the correct versions for each tool. `mise` does not
replace any other installations of these binaries and will only serve these binaries when you are
working inside of the `optimism` directory.
我们使用 [`mise`](https://mise.jdx.dev/) 作为这些工具的依赖管理器。
正确安装后，`mise` 将为每个工具提供正确的版本。`mise` 不会替换这些二进制文件的其他安装，只会在您在 `optimism` 目录中工作时提供这些二进制文件。

##### Install `mise`
##### 安装 `mise`

Install `mise` by following the instructions provided on the
[Getting Started page](https://mise.jdx.dev/getting-started.html#_1-install-mise-cli).
请按照[入门指南](https://mise.jdx.dev/getting-started.html#_1-install-mise-cli)中的说明安装 `mise`。

##### Install dependencies
##### 安装依赖项

```sh
mise install
```

#### Manual installation
#### 手动安装

**Rust Toolchain**
**Rust 工具链**

```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

**`mdbook` + plugins** mdbook及插件

```sh
cargo install mdbook mdbook-katex mdbook-linkcheck mdbook-mermaid
```

**`just` [installation](https://github.com/casey/just?tab=readme-ov-file#installation)**

```sh
brew install just
```

### Serving the book locally
### 在本地运行文档

```sh
just serve
```

### Linting
### 代码检查

`doctoc` is used to automatically add a table of contents.
`doctoc` 用于自动添加目录。

```sh
just lint-specs-toc-check
```

To fix markdown linting errors:
markdown检查错误：


```sh
just lint-specs-md-fix
```

See the [markdownlint rule reference](https://github.com/DavidAnson/markdownlint/blob/main/doc/Rules.md)
and an example [config file](https://github.com/DavidAnson/markdownlint/blob/main/schema/.markdownlint.jsonc).

Justification for linting rules in
[.markdownlint.json](https://github.com/ethereum-optimism/specs/blob/main/.markdownlint.json):

- _line_length_ (`!strict && stern`): don't trip up on url lines
- _no-blanks-blockquote_: enable multiple consecutive blockquotes separated by white lines
- _single-title_: enable reusing `<h1>` for content
- _no-emphasis-as-heading_: enable emphasized paragraphs

To lint links:

```sh
just lint-links
```

[lychee](https://github.com/lycheeverse/lychee) is used for linting links.
