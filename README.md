# 静华 · Jinghua

**高级感 × 华丽动效的 Agent Skill。**

市面上的 AI 生成界面，一听到"要华丽"就开始堆——发光、渐变、弹跳、走马灯。结果不是奢华，是廉价。

静华反向设计：**先定档，再动手；先挑毛病，再改。**

![静华预览](assets/preview-hero.png)

---

## 它解决什么

让 AI agent 做出来的界面具备"贵"的感觉，而不是"AI 味"。

| 机制 | 做什么 |
|---|---|
| **定档** | 静奢 / 动奢 / 静默三档，动效预算不同。默认静奢 |
| **审查优先** | 动手前按 6 个维度打分，输出 P0–P3 分级清单 |
| **9 条禁飞区** | 一犯就廉价的规则：弹跳缓动、彩色发光、径向光晕、紫蓝渐变、渐变文字、走马灯、脉冲点、卡片套卡片、边缘色条 |
| **修复有词** | bolder / quieter / typeset / layout / delight / overdrive / polish，一次只改一处 |

## 9 条禁飞区

![禁飞区](assets/preview-rules.png)

这 9 条是静华的核心资产。每一条都对应一个"看起来像 AI 做的"的具体特征。

## 工作流

```
需求
 └─ ① 定档（静奢 / 动奢 / 静默）
     └─ ② 建（按档位给动效预算）
         └─ ③ 审（6 维度打分 + 检测器扫描）
             └─ ④ 改（P0→P3，一次一处，改完复检）
                 └─ ⑤ 交付（过一遍自检清单）
```

## 安装

把 `skills/premium-motion-design/` 拷进你的 agent 技能目录：

```bash
cp -r skills/premium-motion-design ~/.your-agent/skills/
```

## 配套检测器（可选但强烈推荐）

静华的工作流依赖 [impeccable](https://github.com/pbakaus/impeccable) 的本地检测器提供客观数据。

```bash
npm install -g impeccable
impeccable detect src/                    # 扫源码
impeccable detect http://localhost:5173   # 扫渲染后的页面
```

62 条规则，纯本地运行，不需要 API key，不需要联网。

## 谁适合用

- 给产品做落地页，但不想做成"又一个 AI 创业页"
- 做作品集，需要精致但不浮夸
- 已有页面想升级质感，但不知道从哪下手

## 三条最容易翻车的反模式

| 反模式 | 为什么错 |
|---|---|
| 动效太多 = 没有动效 | 整页都在动，眼睛无处停。每屏留一处"静" |
| 时长太长 = 卡顿 | 入场超过 800ms 就让人等。单元素 400–700ms |
| 什么都要发光 = 什么都不亮 | 发光只在暗背景、只在 1 个元素上有意义 |

![收尾](assets/preview-end.png)

## 与同类项目的关系

- **[taste-skill](https://github.com/Leonxlnx/taste-skill)** — 强在"从零建页"的模具和五尺寸验收。静华复用了它的验收思路。
- **[impeccable](https://github.com/pbakaus/impeccable)** — 强在"设计的词汇"。静华用它的检测器做客观审查，用它的命令名做修复动作。
- **静华** — 回答它们都没回答的问题：**高级感和华丽如何共存**。

## 自证

`demo/index.html` 是用静华自己做的页面，通过 `impeccable detect` 全量检测，**零问题**。

```bash
impeccable detect demo/index.html
# 0 issues found
```

## License

MIT — 随便用、随便改。
