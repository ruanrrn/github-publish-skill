# GitHub Publish Skill

[English](README.md) | 简体中文

![GitHub Publish Skill banner](assets/social-preview.svg)

![OpenClaw Skill](https://img.shields.io/badge/OpenClaw-Skill-111827?style=flat-square)
![Focus-Skill Repo Publishing](https://img.shields.io/badge/Focus-Skill%20Repo%20Publishing-F59E0B?style=flat-square&labelColor=111827)
![Works-Standalone](https://img.shields.io/badge/Works-Standalone-F9FAFB?style=flat-square&labelColor=1F2937)
![Artifact-.skill Included](https://img.shields.io/badge/Artifact-.skill%20Included-FDE68A?style=flat-square&labelColor=1F2937)
![README-Bilingual](https://img.shields.io/badge/README-Bilingual-F9FAFB?style=flat-square&labelColor=92400E)
![License-MIT](https://img.shields.io/badge/License-MIT-F9FAFB?style=flat-square&labelColor=111827)

把 OpenClaw skill 发布或再发布为完整、专业、适合公开分发的 GitHub skill 仓库，并遵循一套只面向 skill 仓的仓库标准。

> [!IMPORTANT]
> 这套标准只适用于“主要产物是 OpenClaw skill”的仓库。它不是给应用、库、或混合用途代码仓库准备的通用 README / 品牌 / GitHub 门面规范。

## 概览

`github-publish-skill` 定义的是公开 OpenClaw skill 仓的发布标准，而不只是“把文件推到 GitHub”。

它同时覆盖两部分工作：

- skill 本体的发布或再发布
- 仓库公开门面的整理，让它看起来像完成品，而不是内部目录导出

落到实际操作上，就是把 `.skill` 产物打包好、把仓库叙事写清楚、把 metadata 对齐，并确保一个第一次在 GitHub 上看到这个仓的人也能独立理解它。

## 为什么需要它

让一个 skill 能跑起来并不难。真正经常缺失标准的，是如何把它发布成一个可理解、可复用、值得信任的公开仓库。

如果没有明确标准，公开 skill 仓通常会在同几个地方翻车：

- 仓库看起来像内部文件夹直出，而不像正式发布物
- 打包产物缺失，或者虽然存在但被埋得很深
- README 默认读者已经知道太多上下文
- 贡献方式和维护边界不清楚
- 同一 skill 家族里的仓库越长越不像一家人

`github-publish-skill` 的意义，就是把这类问题收敛成一套可重复执行的标准流程。

## 适用边界

当目标仓库本质上是一个可分发的 OpenClaw skill 仓，并且你要把它的公开门面整理完整时，就该用这个 skill。

适合这些场景：

- 为一个可复用 OpenClaw skill 新建公开 GitHub 仓库
- skill 发生实质更新后重新发布
- 把旧 skill 仓升级到当前的公开标准
- 统一 skill 家族中 README、badge、metadata、贡献文档和 social-preview 资源的表达方式

不适合这些场景：

- 普通软件项目
- 应用或库
- skill 只是附属产物的混合仓库

## 这套标准覆盖什么

这个 skill 会要求代理把真正决定“仓库像不像一个公开成品”的部分标准化：

- 发布前先校验 skill
- 正确生成 `.skill` 打包产物
- 组织完整的公开仓 payload，包括 `README.md`、`README.zh-CN.md`、`LICENSE`、`CONTRIBUTING.md`、skill 源码和 `dist/`
- 把仓库文案写到脱离私有上下文也能成立
- 让仓库 description 和 topics 与 skill 的真实职责对齐
- 使用以可读性优先的 banner / social-preview 方案，保证仓库列表尺度下也清晰
- README 文案按正式公开工具文档来写，而不是内部备忘录口吻
- 明确保留适用边界，避免仓库慢慢变成“GitHub 门面万能装修包”

## 工作流概览

一次标准的发布整理通常应该这样走：

1. 校验 skill，确认 frontmatter、references 和打包输入都能正确解析。
2. 生成或刷新 `.skill` 产物。
3. 组装公开发布所需的仓库内容。
4. 重写 README 和贡献说明，使其适合独立公开阅读。
5. 对齐仓库 metadata、badge 和 social-preview 资源，使其反映 skill 的真实定位。
6. 在 material update 之后干净地重新发布。

## 何时使用

当问题的核心是“怎么把仓库本身发布好”，而不是“skill 逻辑怎么写”时，就应该用 `github-publish-skill`。

典型触发语句包括：

- “把这个内部 skill 整理成公开 GitHub 仓。”
- “把这个 repo 收口到像正式发布物。”
- “让这个 skill 仓和同一家族的公开仓风格一致。”
- “把打包产物和公开门面一起整理好。”

## 代表性结果

### 新建公开 skill 仓

一个内部可复用的 skill 已经准备好对外发布。

靠谱的代理应该先校验 skill，再打包产物、组织公开仓内容，最后把仓库发布成一个不需要额外解释也能安装和理解的公开成品。

### 旧仓翻新

一个现有 skill 仓功能没坏，但公开门面已经落后于同一家族的新仓。

靠谱的代理应该保留 working skill，本着最小必要改动原则升级 README、贡献文档和公开资源，同时确保仓库本身仍然独立可用。

### 边界控制

有人想把这套标准拿去包装普通 app 仓或库仓。

靠谱的代理应该拒绝这种 scope 扩张，并明确指出这套标准只服务于 OpenClaw skill 仓。

## 相关 skill 仓

这些仓库是相关示例，不是依赖项：

- `multi-task-continuity`：总包型 skill 仓示例 —— <https://github.com/ruanrrn/multi-task-continuity>
- `task-orchestrator`：聚焦 orchestration lane 的示例 —— <https://github.com/ruanrrn/task-orchestrator>
- `task-state-sync`：聚焦 continuity / state lane 的示例 —— <https://github.com/ruanrrn/task-state-sync>

如果你要解决的是“这个仓该怎么发、怎么整理、怎么公开成立”，就从这里开始。

## 安装

两种方式都可以：

1. 直接把 `dist/github-publish-skill.skill` 导入到 OpenClaw 环境。
2. 如果你需要可编辑源码，就把 `github-publish-skill/` 复制到你的 skills 目录。

## 仓库内容

- `github-publish-skill/` - skill 源码
- `github-publish-skill/references/public-skill-style.md` - 公开 skill 仓风格蓝图
- `dist/github-publish-skill.skill` - 可直接导入的打包产物
- `assets/social-preview.svg` - 仓库 banner 和建议使用的 social-preview 资源

## Social preview

建议使用的 social preview 资源：`assets/social-preview.svg`

建议一句话文案：

> Publish OpenClaw skills as complete public GitHub skill repositories.

> [!NOTE]
> 公开的 `gh` CLI 和 GraphQL `UpdateRepositoryInput` 目前都没有可写的 custom social preview 字段。
> 如果要把这张图真正设成仓库 social preview，仍然需要到 GitHub 仓库设置页手动上传 `assets/social-preview.svg`。

## 仓库结构

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

## 贡献

见 `CONTRIBUTING.md`。里面写明了贡献范围、PR 预期，以及如何保持这个仓继续聚焦“公开 skill 仓发布标准”，而不是滑坡成通用 GitHub 装修工具。

## 发布卫生

- 每次 skill 有实质改动后，都要重新生成 `dist/github-publish-skill.skill`
- 保持 `README.md`、`README.zh-CN.md`、`SKILL.md` 与仓库 metadata 一致
- 始终明确适用边界：这套标准只服务于 skill 仓
- 优先选择更窄、更稳、更可维护的发布标准，而不是功能膨胀

## 仓库信息

- GitHub: `https://github.com/ruanrrn/github-publish-skill`
- License: MIT
