# 获取与安装说明

## 当前可用状态

2026-11-11：工具包draft-0.3已包含[工作流](knowledge-gate-network/workflow.md)、[工具卡](knowledge-gate-network/templates/index.md)及[Skill](knowledge-gate-network/SKILL.md)，可按下列路径阅读和使用。仓库托管于[ATLALALA/KnowledgeGateNet](https://github.com/ATLALALA/KnowledgeGateNet)，当前为私有仓库；尚无正式Release或发布压缩包。

Skill格式和完整目录相对引用已检查，实案绘图与返修仍在进行。宿主自动发现及安装后的实际调用尚未实测；下文Codex安装位置依据官方文档，不表示本包已完成安装验证。

## 不使用 AI

打开[工具包索引](knowledge-gate-network/index.md)，先读工作流理解概念并选择入口，再从工具卡索引阅读对应说明、示例和填写区，在自己的现成画板中绘制。无需安装Skill、注册专用工具账号或维护机器数据文件。

Markdown是工具卡维护源；目前没有PDF。有打印或分享需要时从同版Markdown制作，避免分别维护两套内容。

## 让 AI 直接读取文件

若所用AI环境能读取本地文件或完整附件，可以先显式提供整个 `knowledge-gate-network/` 目录及用户项目材料，要求读取 `SKILL.md` 并按其中的相对链接使用工作流、工具卡和三个过程Skill。主入口通过文件读取接续，不依赖宿主自动发现嵌套子技能；不能单独复制专项目录。这条路径不依赖自动发现；它也不等于已安装或已验证宿主兼容。

可使用如下开场语，并将路径和任务换为自己的内容：

> 请读取工具包目录中的SKILL.md，按其指引处理我提供的谜题材料。先读取现有任务和最新设计；允许你提出补缺提案，但实际绘制前请列出具体内容并等我决定。绘图方式和目标软件尚未确定时先问我。绘制后先列已加入的新内容并逐锁说明，再整理排版。

若AI只能读取粘贴文本，须一并提供指引要求的工作流与相关工具卡；只发送SKILL.md，无法取得配套材料时，应补齐材料再继续依赖它们的工作。

## Codex 本地安装与调用

核对日期：2026-11-11。Codex支持从项目的 `.agents/skills/` 或用户目录的 `.agents/skills/` 发现Skill；更新通常自动识别，未显示时重启。这里采用完整目录复制方式，保留本包相对引用。[官方说明](https://learn.chatgpt.com/docs/build-skills)

1. **选择一个安装范围。**项目使用：复制到 `<项目目录>/.agents/skills/knowledge-gate-network/`。个人使用：复制到 `~/.agents/skills/knowledge-gate-network/`；Windows通常对应 `%USERPROFILE%\.agents\skills\knowledge-gate-network\`。两者选一，避免同名副本混淆。
2. **复制完整工具包。**安装目录必须直接包含下方文件，不要只复制SKILL.md，也不要额外嵌套一层同名目录。
3. **确认识别。**在目标项目开启会话，确认技能列表中出现 `knowledge-gate-network`。Codex CLI/IDE可通过 `/skills` 或输入 `$` 选择；其他界面以其技能选择入口为准。未出现时检查目录及SKILL.md，再重启。[官方调用说明](https://learn.chatgpt.com/docs/build-skills)
4. **做一次最小调用并记录实际结果。**选择该Skill后，使用下方请求。确认AI能读取工作流与网络卡，并针对缺失的绘图选择询问；这一步需由实际会话执行，不是文件检查的替代说法。

```text
knowledge-gate-network/
├─ SKILL.md
├─ index.md
├─ workflow.md
├─ templates/
│  ├─ index.md
│  ├─ local-lock.md
│  ├─ network.md
│  ├─ handoff.md
│  ├─ board-style.md
│  └─ local-layout.png
└─ skills/
   ├─ knowledge-gate-propose/
   │  └─ SKILL.md
   ├─ knowledge-gate-explain/
   │  └─ SKILL.md
   └─ knowledge-gate-layout/
      └─ SKILL.md
```

最小调用请求：

> 使用knowledge-gate-network，读取网络组织卡中的“山地观测站”教学例。先说明它的知识与实际条件，再准备一份便于我审阅的图稿。绘图方式和目标软件尚未选择，请先询问。这次只使用教学例，不改写工具包或连接外部画板。

通过调用入口选中Skill后附上这段请求；CLI/IDE也可在请求前使用 `$knowledge-gate-network`。教学例是虚构材料，检查本次是否正确读取、询问和解释，不据此宣称谜题体验已验证。只整理教学例时不强行补设计；另需验证提案路径时可追加“允许你提出一项反馈补充，先给我具体提案，等待我的决定后再绘制”，检查AI是否在确认前停止绘图。图稿完成后检查说明先列实际已加入的新内容，再逐锁讲解，最后整理排版。三个过程Skill由主入口按路径读取，不需要分别安装或另开会话。

**更新：**在同一安装位置整体更新工具包，并核对 `index.md` 中的配套版本；有本地工具修改时先保留并比较。用户图、任务记录和游戏材料存放在用户项目，不放入安装目录，因此不随工具更新覆盖。更新后再检查识别及最小调用；不要把不同版本的Skill、工作流和卡片混装。

安装本包不会自动提供某个画板的读写能力。具体绘图由用户选择；需要连接服务时按所选环境的实际能力配置，未验证的平台不列为已支持。

## ZIP 与 GitHub

- 仓库入口是根 `README.md`；工具内容入口是包内 `index.md`。
- 发布ZIP至少包含README、本说明及完整 `knowledge-gate-network/`，首次公开前补齐已确认的许可。
- `.local/`、本地开发文档`.docs/`（或`docs/`）及`AGENTS.md`只保留在本机，不进入Git或发布包；工具使用不依赖这些文件。
- 本机任务快照用于版本留存，不是正式发布件。首次发布前分别实测下载压缩包及拉取仓库后的阅读、安装与调用入口，并记录验证环境。
- 有仓库访问权限的用户可通过[GitHub仓库](https://github.com/ATLALALA/KnowledgeGateNet)的Code菜单下载ZIP或克隆，使用GitHub Desktop时选择该仓库进行克隆。下载源文件不等于正式版本发布；其他AI环境须分别确认读取或安装能力。
