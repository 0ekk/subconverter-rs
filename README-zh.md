# subconverter-rs
一个功能强大的代理订阅格式转换工具，从 C++ 版本的 subconverter 转换而来！

> 转换. 优化. 简化. 一个用 Rust 重写的高性能代理订阅转换器。

**⚠️ 测试版已发布 ⚠️** - 该项目现已进入测试阶段。核心功能已实现，但可能仍有一些粗糙之处。

[![Rust](https://img.shields.io/badge/language-Rust-orange.svg)](https://www.rust-lang.org/)
[![Status](https://img.shields.io/badge/status-beta-blue.svg)](https://github.com/lonelam/subconverter-rs)
[![GPL-3.0+ License](https://img.shields.io/badge/license-GPL--3.0%2B-blue.svg)](LICENSE)
[![Crates.io](https://img.shields.io/crates/v/subconverter-rs.svg)](https://crates.io/crates/subconverter-rs)

subconverter-rs 借鉴了原始 [subconverter](https://github.com/tindy2013/subconverter) 项目的强大功能，并用 Rust 重新实现，带来内存安全、无数据竞争的并发处理以及显著提升的性能。

## 为什么选择 Rust？
原始的 subconverter 不易使用且难以贡献代码，超过一半的 PR 都被放弃。

然而，subconverter 几乎是唯一一个能够提供各种代理工具兼容性的工具。

## 路线图

| 功能 | 状态 | 优先级 | 描述 |
|---------|:------:|:--------:|-------------|
| 核心转换引擎 | ✅ | 高 | 基本的代理解析和格式之间的转换 |
| 节点操作 | ✅ | 高 | 过滤、重命名和预处理节点 |
| VMess 协议支持 | ✅ | 高 | 完整支持 VMess 协议 |
| Crates.io 发布 | ✅ | 中 | 作为 Rust crate 发布以便于安装 |
| HTTP 服务器 | 🔄 | 高 | 用于订阅转换的服务器 |
| 额外 API 端点 | 🔄 | 中 | 实现 /surge2clash, /getprofile 等 |
| 模板系统 | 🔄 | 中 | 支持可自定义模板 |
| Web 界面 | 🔄 | 中 | 在线转换界面 |
| RESTful API | 🔄 | 中 | 用于集成的全面 API |
| 自动上传到 Gist | 🔄 | 低 | 自动上传生成的配置 |
| 插件系统 | 🔄 | 低 | 轻松扩展功能 |
| 功能对等 | 🔄 | 持续 | 与原始 subconverter 完全功能对等 |
| 性能基准测试 | 🔄 | 低 | 与原始实现的比较 |
| Docker 容器 | 🔄 | 中 | 容器化以便于部署 |
| CI/CD 流水线 | 🔄 | 中 | 自动测试和部署 |

图例:
- ✅ 已完成
- 🔄 进行中/计划中

## 实现状态

subconverter-rs 已实现了原始 C++ 版本的核心功能，包括：

### 支持的功能
- 在各种代理订阅格式之间进行转换
- 基于备注和规则过滤节点
- 向节点备注添加 Emoji
- 基于自定义规则重命名节点
- 预处理节点
- 解析本地配置文件
- 命令行界面

### 支持的代理类型
- VMess
- Shadowsocks
- ShadowsocksR
- Trojan
- HTTP/HTTPS
- SOCKS
- Hysteria/Hysteria2
- WireGuard
- Snell

### 支持的输出格式
- Clash
- Surge
- Quantumult
- Quantumult X
- Loon
- ShadowsocksD (SSD)
- Mellow
- SingBox

## 安装

### 从 Crates.io 安装
```bash
cargo install subconverter
```

### 从源码安装
```bash
git clone https://github.com/lonelam/subconverter-rs.git
cd subconverter-rs
cargo build --release
```

编译后的二进制文件将位于 `target/release/subconverter-rs`。

## 使用方法

### 命令行
```bash
subconverter [选项]
```

## 配置
subconverter-rs 使用与原始 subconverter 类似的配置。

## 开发
欢迎贡献！请随时提交 Pull Request。

### 如何贡献

1. **选择一个问题**: 查看我们的 [issue tracker](https://github.com/lonelam/subconverter-rs/issues) 寻找标记为 `good first issue` 或 `help wanted` 的任务
2. **实现新的代理类型**: 帮助扩展对其他代理协议的支持
3. **改进解析**: 增强各种格式解析器的健壮性
4. **添加测试**: 增加测试覆盖率以确保稳定性
5. **文档**: 改进文档或添加示例以帮助他人使用该项目
6. **性能优化**: 帮助使转换器更快

如有问题或讨论，您可以：
- 在 GitHub 上开一个 issue
  
## 许可证
该项目采用 GPL-3.0+ 许可证 - 详见 LICENSE 文件。 