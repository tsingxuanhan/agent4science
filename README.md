# agent4science

> 学术科研工具集 & 知识库入口

面向科研场景的 AI 辅助工具集，整合学术资源检索、知识库、实验评估等能力。

---

## 定位

本仓库是**轻量级学术工具集**，聚焦于：

- **学术文献检索**：PubMed、Semantic Scholar、arXiv 等多源搜索
- **知识库**：524 篇论文 / 30 分类 / AGI 认知地图（详见 [xuanshu-knowledge-base](https://github.com/tsingxuanhan/xuanshu-knowledge-base)）
- **实验评估工具**：任务评分、质量度量、场景模拟

> 💡 如果你需要**多智能体协作框架**，请查看 [NexusFlow](https://github.com/tsingxuanhan/NexusFlow)

---

## 工具清单

### 学术文献检索

```python
# 示例：文献综述生成
from examples.demo_lit_review import LiteratureReview

review = LiteratureReview(
    topic="AI for Materials Science",
    max_papers=50
)
review.run()
```

### 实验评估

```
evaluation/
├── metrics.py          # 评估指标定义
├── quality_scorer.py   # 质量评分器
├── task_scenarios.py   # 任务场景模拟
├── decay_analyzer.py   # 衰减分析
└── mock_llm.py         # LLM 模拟（用于测试）
```

---

## 知识库

**xuanshu-knowledge-base** (v2)
- 524 篇论文
- 30 个分类方向
- AGI 认知地图
- 地址：https://github.com/tsingxuanhan/xuanshu-knowledge-base

---

## 相关仓库

| 仓库 | 定位 |
|------|------|
| [NexusFlow](https://github.com/tsingxuanhan/NexusFlow) | 多智能体协作框架（CDoL 认知分工） |
| [xuanshu-knowledge-base](https://github.com/tsingxuanhan/xuanshu-knowledge-base) | 知识库 v2（524 篇 / 30 分类） |
| [materials-ai-kit](https://github.com/tsingxuanhan/materials-ai-kit) | AI 材料科学工具包 |
| [xuanshu-ui-gallery](https://github.com/tsingxuanhan/xuanshu-ui-gallery) | UI 风格库（6 种 CSS 主题） |

---

## License

MIT
