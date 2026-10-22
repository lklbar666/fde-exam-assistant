# 题目字段规范

每题 13 字段，JSON 对象。缺一不可。

## 字段表

| 字段 | 类型 | 说明 |
|---|---|---|
| id | string | 形式 FDE-M1-001（模块+序号） |
| module | string | M1-M7，见模块考点图 |
| topic | string | 细粒度考点，如"大模型/部署与精调" |
| type | string | single（单选）/ multiple（多选） |
| stem | string | 题干，情境化、唯一、可验证 |
| options | object | A/B/C/D 四选项对象 |
| answer | array | 正确项字母数组，如 ["D"] |
| explanation | string | 详细解析，含判断要点 |
| distractors | object | 逐错误选项解释原因 |
| difficulty | string | 基础/进阶/综合 |
| sources | array | 六件套：url/title/section/fact/verifiedAt/version |
| review | object | 审校链：status/author/reviewer/notes/recheck |

## 示例（真实题库同构）

```json
{
  "id": "FDE-M1-001",
  "module": "M1",
  "topic": "大模型/部署与精调",
  "type": "single",
  "stem": "某团队已获得模型服务地址，但合同字段抽取仍不稳定，准备使用标注样本继续训练。如何区分这两项工作？",
  "options": {
    "A": "部署以任务样本更新权重，精调只开放访问地址",
    "B": "部署改变输出格式，精调只增加上下文",
    "C": "部署与精调都只建立知识索引",
    "D": "部署使模型可被调用，精调针对任务继续优化模型"
  },
  "answer": ["D"],
  "explanation": "在线部署与精调训练是不同动作：前者提供服务，后者改善特定任务表现。判断要点：区分服务可调用与任务适配效果；部署成功不能证明完成精调。",
  "distractors": {
    "A": "训练与部署职责颠倒",
    "B": "精调不只是增加上下文",
    "C": "二者均不等于索引构建"
  },
  "difficulty": "基础",
  "sources": [
    {
      "url": "https://cloud.tencent.com/document/product/851/109354",
      "title": "大模型广场",
      "section": "概述",
      "fact": "在线部署与精调训练是不同动作：前者提供服务，后者改善特定任务表现。",
      "verifiedAt": "2026-10-09",
      "version": "2026-06-04"
    }
  ],
  "review": {
    "status": "approved",
    "author": "foundations_modes",
    "reviewer": "逐题内容复核",
    "notes": ["区分服务可调用与任务适配效果"]
  }
}
```

## 校验规则

- answer 必须在 options 的键集合内
- multiple 的正确项 2-3 个
- 每题至少 1 个 source，且含 url 与 fact
- explanation 必须能独立判定对错，不含未核规则
