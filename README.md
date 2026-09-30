# 东方风格选题

角色与场景提示词设计之前的 Codex Skill：根据风格参考图推荐 2–3 个东方题材选题并说明原因，用户选定后输出具体角色与场景方向。

## 使用流程

1. 提供风格图片，获得 2–3 个选题及适配原因。
2. 选择一个方向，或提出调整意见。
3. 确定后只输出标题、角色方向和场景方向；默认各十个，两个独立代码块，每行一个方向，不加序号。

本项目只负责选题与确认，不生成提示词。角色提示词交给 [角色 Skill](https://github.com/2053197099/midjourney-oriental-game-characters)，场景提示词交给 `midjourney-wuxia-environments`；用户自行复制方向到对应聊天。

## 文件

- [SKILL.md](SKILL.md)：工作流程和交付格式。
- [东方题材库](references/oriental-genres.md)：用户指定的 26 类题材。
- [agents/openai.yaml](agents/openai.yaml)：Skill 的展示信息与调用入口。

## 本地使用

将 `SKILL.md`、`agents/` 和 `references/` 放入 `~/.codex/skills/oriental-style-topic-selection/`，随后在新聊天中使用 `$oriental-style-topic-selection` 并提供参考图。仓库维护源与本地安装副本应保持一致。

## 验证

使用 `skill-creator` 的 `scripts/quick_validate.py` 检查 Skill 元数据，并检查相对引用、题材目录及安装副本一致性。按实际使用验证两个阶段：提供图片时推荐 2–3 个候选；确认选题后只输出标题和分开的无序号方向代码块，默认各十个。结构校验不代表选题审美判断已经验收。
