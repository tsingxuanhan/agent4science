<div align="center">

# agent4science

**学术科研工具集 & 知识库入口**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Python 3.9+](https://img.shields.io/badge/Python-3.9+-blue.svg)]()
[![Version](https://img.shields.io/badge/Version-3.3-blue.svg)]()

*AI-augmented tools for scientific research workflows.*

</div>

---

## 🎯 定位

面向科研场景的 AI 辅助工具集，提供**学术文献检索**、**实验评估**、**知识库管理**三大核心能力。与 [NexusFlow](https://github.com/tsingxuanhan/NexusFlow) 多智能体框架深度集成，可实现从文献调研到实验分析的端到端自动化。

> 💡 如果你需要**多智能体协作框架**，请查看 [NexusFlow](https://github.com/tsingxuanhan/NexusFlow) —— 已验证在 WHO 健康分析任务中得分 **92/100**（vs AutoGen 88 / CrewAI 85）。

---

## 🔧 工具清单

### 1. 学术文献检索

多源学术搜索，覆盖 PubMed / Semantic Scholar / arXiv / Crossref 等主流数据库。

```python
from examples.demo_lit_review import LiteratureReview

review = LiteratureReview(
    topic="AI for Low-Carbon Cement",
    max_papers=50,
    sources=["pubmed", "semantic_scholar", "arxiv"]
)
results = review.run()
print(f"检索到 {len(results)} 篇相关文献")
```

### 2. 实验评估引擎

10 维度科研任务质量评估体系，支持任务场景模拟、质量评分、衰减分析。

```
evaluation/
├── metrics.py          # 10 维度评估指标（准确性/深度/完整性/可复现性...）
├── quality_scorer.py   # 加权评分器（支持自定义权重）
├── task_scenarios.py   # 100 步科研任务场景（低碳水泥配方研发）
├── decay_analyzer.py   # 性能衰减分析（Agent 疲劳检测）
└── mock_llm.py         # LLM 模拟（用于离线测试）
```

**评估维度：**

| 维度 | 权重 | 说明 |
|------|------|------|
| 数据准确性 | 15% | 数值与源数据一致性 |
| 排名正确性 | 15% | 排序结果与基准事实匹配 |
| 分析深度 | 15% | 因果分析 vs 表层罗列 |
| 方法论 | 10% | 指数/权重设计合理性 |
| 完整性 | 10% | 指标覆盖度 |
| 交叉验证 | 10% | 多源数据比对 |
| 不确定性标注 | 5% | 数据局限声明 |
| 可操作性 | 5% | 建议可落地程度 |
| 逻辑一致性 | 10% | 结论自洽性 |
| 可复现性 | 5% | 过程透明度 |

### 3. 知识库

**[xuanshu-knowledge-base](https://github.com/tsingxuanhan/xuanshu-knowledge-base)** (v2)
- 524 篇论文 | 30 个分类方向
- 覆盖 AGI / 认知科学 / 世界模型 / 因果推理等前沿方向
- AGI 认知地图（143 篇深度文献 / 12 个研究方向）

---

## 📊 评估实验亮点

### CDoL 认知分工对比实验

在低碳水泥配方研发场景中，验证了认知分工机制的有效性：

| 模式 | 总分均值 | 方案完整性 | 创新性 |
|------|:--------:|:----------:|:------:|
| **CDoL ON** (信息不对称) | **40.0** | **9.0** | **7.3** |
| CDoL OFF (全信息基线) | 31.7 | 5.0 | 5.0 |
| **提升幅度** | **+26%** | **+80%** | **+46%** |

> 核心发现：信息不对称迫使 Agent 发展出更深层的推理能力，方案完整性和创新性显著提升。

### 跨框架对比（NexusFlow 集成）

统一任务：WHO 全球健康指标分析（BRICS 五国 × 3 指标）

| 框架 | 得分 | 耗时 | Token | 拓扑切换 | 自我修正 |
|------|:----:|:----:|:-----:|:--------:|:--------:|
| **NexusFlow (CDoL)** | **92** | 69.5s | ~20.5K | ✅ | ✅ |
| AutoGen | 88 | 36.5s | 6.3K | ❌ | ✅ |
| CrewAI | 85 | 42.0s | 5.2K | ❌ | ❌ |

**复杂任务（全球能源转型 5 国 × 6 维度）：** NexusFlow 得分 **94.4**，数据准确性与排名正确性均 100%。

---

## 🚀 Quick Start

```bash
# 克隆仓库
git clone https://github.com/tsingxuanhan/agent4science.git
cd agent4science

# 安装依赖
pip install -r requirements.txt

# 运行文献综述示例
python examples/demo_lit_review.py

# 运行评估测试
python evaluation/quality_scorer.py
```

---

## 📁 项目结构

```
agent4science/
├── evaluation/           ← 评估引擎
│   ├── metrics.py        # 10 维度指标定义
│   ├── quality_scorer.py # 评分器
│   ├── task_scenarios.py # 100 步任务场景
│   └── ...
├── examples/             ← 示例脚本
│   └── demo_lit_review.py
├── reports/              ← 实验报告
│   ├── cdol_real_experiment_report.md
│   └── horizontal_comparison_summary.md
├── config/               ← 配置文件
└── requirements.txt
```

---

## 🌐 生态导航

```
🏛️ XuanHub 开源生态
├── 🔬 NexusFlow                 ← 核心 AGI 框架 (v2.8, 10-Agent, CDoL)
├── 📚 xuanshu-knowledge-base    ← 知识库 (524篇 / 30分类)
├── 🧪 materials-ai-kit          ← 材料AI工具包 (v4.2)
├── 🧰 agent4science             ← 学术工具集（本仓库）
├── 🎨 xuanshu-ui-gallery        ← UI风格库 (6种CSS主题)
└── 📖 qiu                       ← 项目指南
```

| 仓库 | 定位 | 最近更新 |
|------|------|---------|
| [NexusFlow](https://github.com/tsingxuanhan/NexusFlow) | 群体智能引擎 · CDoL 认知分工 | 2026-07-14 |
| [xuanshu-knowledge-base](https://github.com/tsingxuanhan/xuanshu-knowledge-base) | 知识库 v2 · 524 篇论文 | 2026-06-15 |
| [materials-ai-kit](https://github.com/tsingxuanhan/materials-ai-kit) | 材料科学 AI 工具包 | 2026-07-15 |
| [xuanshu-ui-gallery](https://github.com/tsingxuanhan/xuanshu-ui-gallery) | UI 风格库 · 6 种主题 | 2026-06-14 |
| [qiu](https://github.com/tsingxuanhan/qiu) | 秋 · 项目指南 | 2026-06-13 |

---

## 📄 License

MIT
