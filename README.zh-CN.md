# GitHub Publish Skill

[English](README.md) | 简体中文

![GitHub Publish Skill banner](assets/social-preview.svg)

![OpenClaw Skill](https://img.shields.io/badge/OpenClaw-Skill-111827?style=flat-square)
![Focus-Skill Repo Publishing](https://img.shields.io/badge/Focus-Skill%20Repo%20Publishing-F59E0B?style=flat-square&labelColor=111827)
![Works-Standalone](https://img.shields.io/badge/Works-Standalone-F9FAFB?style=flat-square&labelColor=1F2937)
![Artifact-.skill Included](https://img.shields.io/badge/Artifact-.skill%20Included-FDE68A?style=flat-square&labelColor=1F2937)
![README-Bilingual](https://img.shields.io/badge/README-Bilingual-F9FAFB?style=flat-square&labelColor=92400E)
![License-MIT](https://img.shields.io/badge/License-MIT-F9FAFB?style=flat-square&labelColor=111827)

把 OpenClaw skill 发布成一个像样的公开 GitHub skill 仓，而不是把文件夹直接倒上去。

## Quick pitch

把 OpenClaw skill 发布成完整、可读、可复用的公开 GitHub skill 仓。
重点：这套仓库风格规范只适用于 skill 仓，不适用于普通代码仓。

## Why this exists

把 skill 发到 GitHub，最容易犯的错不是“发不上去”，而是“虽然发上去了，但看起来像半成品”。

一个单纯能下载的仓库，并不等于一个做得好的公开 skill 仓。没有清楚的 README、没有打包产物、没有贡献说明、没有统一风格，后面的人就得靠猜：这仓到底怎么装、怎么用、怎么维护、和别的 skill 仓是什么关系。

`github-publish-skill` 就是拿来解决这件事的。

它把两类事情合成一条标准工作流：

- 把一个 OpenClaw skill 发布或再发布到 GitHub
- 把这个仓整理成一个完整、独立、可复用的公开 skill 仓

## Works independently

`github-publish-skill` 可以独立使用。

只要你要发布的是 OpenClaw skill 仓，它就够用了，不依赖别的 skill 才成立。

但边界也必须讲死：这里的公开仓风格规范只对 skill 仓有效，不要拿它去美化普通应用仓、库仓或乱七八糟的混合仓。

## What the skill teaches

这个 skill 会要求代理：

- 发布前先校验 skill
- 正确打包 `.skill` 产物
- 组织一个完整的公开 skill 仓 payload，包括 README、中文 README、LICENSE、CONTRIBUTING、skill 源码和 `dist/`
- 把 README 写成独立可理解，而不是一页跳转说明
- 对公开 skill 仓使用统一的 badge、banner、social preview 结构
- 保证 banner 的图形元素别压进文字区，标题和说明在仓库列表里也得一眼能读
- 优先做干净的文字主视觉，别为了显得有设计感硬塞右侧装饰垃圾
- 让 repo description 和 topics 与 skill 的真实职责对齐
- 让同一家族 skill 仓风格统一，但不制造隐藏依赖
- 始终保留一条硬边界：这套风格只给 skill 仓用

## When to use it

适合这些场景：

- 要为一个可复用 OpenClaw skill 新建公开仓
- skill 更新后要重新发布
- 要把一个旧的公开 skill 仓整理成更完整的公开作品
- 要统一 skill 仓的 README、badge、CONTRIBUTING、metadata、social preview 等门面

不适合：普通软件项目、应用、库、或混合用途仓库。

## Example behavior

### Example 1: 第一次公开发布 skill

一个工作区里的 skill 已经准备好对外分享。

靠谱的代理应该：

1. 先校验 skill 并打包 `.skill`
2. 准备 repo payload，包括 README、中文 README、LICENSE、CONTRIBUTING、skill 源码和 `dist/`
3. 把 README 写到第一次看到的人也能看懂
4. 发布仓库，并把 GitHub 元数据和 skill 职责对齐

### Example 2: 升级老的公开 skill 仓

一个旧 skill 仓功能没坏，但卖相和新仓不统一。

靠谱的代理应该：

1. 保留 skill 逻辑和打包产物
2. 升级 README 结构、badge 和 social preview 区块
3. 缺什么补什么，比如 `CONTRIBUTING.md`
4. 让仓库自己成立，而不是变成一个“去别处看”的占位页

### Example 3: scope 用错了

有人想把这套规则拿去套普通 app 仓。

靠谱的代理应该明确拒绝 scope creep，并指出这套标准只对 skill 仓有效。

## Related skills

这些是相关项，不是依赖项：

- `multi-task-continuity`：一个总包型公开 skill 仓示例 —— <https://github.com/ruanrrn/multi-task-continuity>
- `task-orchestrator`：一个 focused lane skill 仓示例 —— <https://github.com/ruanrrn/task-orchestrator>
- `task-state-sync`：一个 focused continuity skill 仓示例 —— <https://github.com/ruanrrn/task-state-sync>

当问题本身是“怎么把 skill 仓发布好”时，用这个仓。

## Social preview

建议 social preview 资源：`assets/social-preview.svg`

建议一句话文案：

> Publish OpenClaw skills as polished public GitHub skill repositories.

GitHub 备注：

- 当前公开的 `gh` CLI 和 GraphQL `UpdateRepositoryInput` 都没有可写的 custom social preview 字段。
- 如果你要把这张图真正设成仓库 social preview，只能去 GitHub 仓库设置页手动上传 `assets/social-preview.svg`。

## What you get

- `github-publish-skill/` - skill 源码
- `github-publish-skill/references/public-skill-style.md` - 公开 skill 仓风格蓝图
- `dist/github-publish-skill.skill` - 可直接导入的打包产物

## Install

两种方式都可以：

1. 直接导入 `dist/github-publish-skill.skill`
2. 把 `github-publish-skill/` 复制到你的 skills 目录，按源码方式使用

## Repository layout

```text
github-publish-skill/
├── LICENSE
├── README.md
├── README.zh-CN.md
├── CONTRIBUTING.md
├── assets/
│   └── social-preview.svg
├── github-publish-skill/
│   ├── SKILL.md
│   └── references/
│       └── public-skill-style.md
└── dist/
    └── github-publish-skill.skill
```

## Contributing

见 `CONTRIBUTING.md`，里面写了贡献范围、PR 预期，以及怎么确保这个仓继续只服务于 skill 仓发布，而不是变成 GitHub 万物包装机。

## Release hygiene

- 每次 skill 有实质改动后，都要重新生成 `dist/github-publish-skill.skill`
- 仓库描述要和 skill 的触发语义保持一致
- 硬边界必须一直存在：这套风格规范只适用于 skill 仓
- 保持仓库克制，别把它扩展成无关项目的 GitHub 装修包

## Repository

- GitHub: `https://github.com/ruanrrn/github-publish-skill`
- License: MIT
