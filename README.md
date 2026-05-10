<div align="center">

# learning-journal

**让每一次 AI 对话，都变成一节好课**

[![Skill Type](https://img.shields.io/badge/Type-Claude%20Code%20Skill-blue)]()
[![License](https://img.shields.io/badge/License-MIT-green)]()
[![Status](https://img.shields.io/badge/Status-Active-brightgreen)]()

从与 Claude 的交互中，自动提取知识点、原理、实操细节和 AI 推理过程，
以老师的口吻编写结构化学习文档——不仅记录"做了什么"，更讲透"怎么想到的"。

</div>

---

## 它解决什么问题

和 AI 聊了一个小时，解决了好几个技术问题，学到了不少东西。
但对话一关，这些知识就散落在聊天记录里，再也找不回来。

**learning-journal** 就是来解决这个问题的：

- 对话即将结束或上下文即将压缩时，**自动扫描整个对话**
- 提取所有涉及的知识点、工具用法、推理过程
- 以老师手把手教学的口吻，生成结构化的 Markdown 学习笔记
- 支持 Obsidian 风格的双向链接，构建个人知识图谱

## 核心特点

| 特性 | 说明 |
|------|------|
| **老师口吻** | 不是冰冷的 AI 摘要，而是像老师讲课一样——有直觉、有类比、有态度 |
| **AI 思考过程还原** | 不仅记录结论，更还原 AI 是怎么推理到结论的——看到了什么线索、排除了什么方向 |
| **实操细节完整保留** | 工具怎么调用、脚本怎么写、地址和字节序列——一个不落 |
| **知识领域归类** | 按领域组织，不按问题组织——方便日后检索和关联 |
| **Obsidian 双向链接** | 自动扫描已有笔记，建立 `[[文件名]]` 风格的关联 |
| **上下文压缩保护** | 在上下文被压缩之前执行，确保知识不丢失 |

## 快速开始

### 安装

将本项目作为 Claude Code skill 安装：

```bash
# 克隆到你的 skills 目录
git clone https://github.com/v2ish1yan/learn-journey.git
```

在 Claude Code 的配置中引用 SKILL.md，或直接在项目中使用。

### 使用方式

**自动触发：** 当对话上下文即将被压缩时，自动执行知识提取和文档生成。

**手动触发：** 在对话中输入：

```
/learning-journal
```

### 输出示例

生成的学习文档遵循以下结构：

```markdown
---
title: 逆向工程入门 — PE 文件与 AES 解密
date: 2026-05-10
tags:
  - 逆向工程
  - PE文件
  - AES加密
  - IDA-Pro
links:
  - "[[2026-05-08_cryptography-basics]]"
---

# 学习笔记：逆向工程入门 — PE 文件与 AES 解密

---

## 知识地图

| 领域 | 知识点 |
|------|--------|
| 逆向工程 | PE 文件结构、IDA Pro 分析流程 |
| 密码学 | AES 加解密、密钥扩展算法 |

---

## 逆向工程

### PE 文件结构

PE 文件是 Windows 可执行文件的标准格式。它的结构是这样的...

> 💭 **思考过程：** 当时我看到了 AES 解密输出全是乱码...

## 工具实操手册

### IDA Pro
- **用途：** 二进制逆向分析
- **调用方式：** `ida64 -A -S"script.py" target.exe`
- **注意事项：** ...
```

## 工作流程

```
对话进行中
    │
    ▼
扫描完整对话历史 ─── 识别所有知识点、工具用法、推理过程
    │
    ▼
按知识领域归类 ─── 不按问题分，按领域分
    │
    ▼
老师口吻讲解 ─── 原理 → 实操 → 可复用代码 → 思考过程
    │
    ▼
生成结构化文档 ─── Markdown + Obsidian 链接
    │
    ▼
保存到学习笔记目录
```

## 配置

### 输出目录

学习文档默认保存到 `E:\AI\SKILL\learn\`，可在 SKILL.md 中修改。

### 文件命名规则

```
{YYYY-MM-DD}_{主题缩写}.md
```

例如：`2026-05-10_reverse-engineering.md`

### 标签系统

每篇笔记自动生成 1-10 个 tags，用于知识分类和跨笔记关联。

## 文档质量标准

learning-journal 生成的文档遵循严格的质量标准：

- **不说空话** — 不写"XX很重要因为XX"，而是直接讲原理
- **不给半截代码** — 提到工具就给完整调用，提到脚本就贴完整代码
- **保留锚点** — 地址、字节序列、函数名等细节完整保留
- **还原思考** — 关键推理节点用 `> 💭 思考过程` 标注
- **预测困惑** — 主动指出新手容易踩的坑

## 作为 Claude Code Skill

本项目是一个 [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skill，可以：

- 通过 `/learning-journal` 命令手动触发
- 配置为上下文压缩前自动触发
- 与其他 skill 配合使用

## 项目结构

```
learn-journey/
├── README.md          # 项目说明（你正在看的）
├── SKILL.md           # Skill 定义 — 完整的工作流程和模板
└── .claude/           # Claude Code 配置
    └── settings.local.json
```

## License

MIT

---

<div align="center">

**知识不等人，对话即课堂。**

</div>
