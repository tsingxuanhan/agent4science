# 跨框架横向对比摘要

> 数据来源：[NexusFlow/examples/horizontal_comparison](https://github.com/tsingxuanhan/NexusFlow/tree/main/examples/horizontal_comparison)
> 更新日期：2026-07-14

## 实验一：WHO 全球健康指标分析

**统一任务**：查询 WHO GHO 数据库，获取 BRICS 五国 3 项指标，计算综合健康指数并排名。

| 框架 | 得分 | 耗时 | Token 消耗 | 自我修正 | 拓扑切换 |
|------|:----:|:----:|:----------:|:--------:|:--------:|
| **NexusFlow (CDoL)** | **92/100** | 69.5s | ~20.5K | ✅ 多轮迭代 | ✅ 动态 |
| AutoGen v0.7.5 | 88/100 | 36.5s | 6.3K | ✅ 验证轮 | ❌ 固定对话 |
| CrewAI | 85/100 | 42.0s | 5.2K | ❌ 单向 | ❌ 固定顺序 |

**关键发现**：
- NexusFlow 质量最高（+4 vs AutoGen, +7 vs CrewAI），得益于 CDoL 多视角辩论 + Observer 纠错
- Token 消耗较高，但质量增益远超成本增幅
- NexusFlow 在「交叉验证」和「不确定性标注」维度显著领先

## 实验二：全球能源转型综合评估（复杂任务）

**任务**：5 国 × 6 维度能源转型综合评估（可再生能源占比、碳排放强度、能源安全等）

| 指标 | NexusFlow v3 |
|------|:------------:|
| 得分 | **94.4/100** |
| API 调用 | 8 次 |
| Token | 67,069 |
| 耗时 | 476 秒 |
| 数据准确性 | 100% |
| 排名正确性 | 100% |
| 分析深度 | 98% |

**结论**：NexusFlow 在复杂多维度任务中表现优异，CDoL 三轮协议有效避免了"虚假一致"问题。

---

## 评估方法论

采用 10 维度加权评分体系（满分 100），各维度权重根据科研任务特性设计：

```
数据准确性(15%) + 排名正确性(15%) + 分析深度(15%) 
+ 方法论(10%) + 完整性(10%) + 交叉验证(10%) 
+ 逻辑一致性(10%) + 不确定性(5%) + 可操作性(5%) + 可复现性(5%)
```

> *完整评估细节见 [NexusFlow/examples/horizontal_comparison](https://github.com/tsingxuanhan/NexusFlow/tree/main/examples/horizontal_comparison)*
