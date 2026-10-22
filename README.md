# 腾讯FDE考试助手

腾讯云 FDE 认证备考 Skill。按 FDE_Learning 模拟题库工程的方法论生成原创模拟题：M1-M7 模块体系、13 字段题目规范、来源可审计命题合同、组卷与间隔复习工作流。

## 在线体验

[▶ 在线体验（ima Skill）](https://ima.qq.com/skill?shareId=待上传ima后替换&from=share) · [源码](https://github.com/lklbar666/fde-exam-assistant)

> 注：ima 链接为占位，上传 ima 后替换 shareId 即生效。

## 目录

```
fde-exam-assistant/
├── SKILL.md                    # 技能定位、适用场景、调用方式、核心能力
├── usage-examples.md           # 5 条可直接复制的调用示例
├── references/
│   ├── authoring-contract.md   # 命题合同：事实边界、题干规则、质量门禁
│   ├── question-schema.md      # 13 字段规范与校验规则（含样例题）
│   ├── module-map.md           # M1-M7 模块职责与考点切分
│   └── study-flow.md           # 组卷/错题/间隔复习/备份工作流
└── assets/
    └── question-template.json  # 出题模板
```

## 使用

把 skill 目录放入 Agent 的技能目录（如 `workspace/.user_skills/`）即可加载。调用方式见 [usage-examples.md](usage-examples.md)。

## 溯源

方法论提炼自 [FDE_Learning](https://github.com/lusouldepth-ai/FDE_Learning)（腾讯云 FDE 原创模拟题库，题库版本 2026.10.13.3）。本仓库为原创重写，不复制原文，不包含原仓库题库数据。

## 许可

MIT。
