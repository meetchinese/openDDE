#  <center>🚀 openDDE: Open Drug Design Engine </center>

<p align="center">
  <img src="https://img.shields.io/badge/License-Apache%202.0-blue.svg" alt="License">
  <img src="https://img.shields.io/badge/Python-3.9%2B-green.svg" alt="Python">
  <img src="https://img.shields.io/badge/Framework-Modular-orange.svg" alt="Framework">
  <img src="https://img.shields.io/badge/PRs-Welcome-brightgreen.svg" alt="PRs Welcome">
</p>

**openDDE** 是一个开源、可复现、可扩展的药物设计引擎（Drug Design Engine），专为蛋白-配体及多分子复合物的建模与评估而设计。
An open-source, reproducible, and extensible orchestration framework for protein–ligand and biomolecular complex modeling.

---

## 🌟 核心优势 | Why openDDE?

目前许多先进的药物设计引擎由于闭源特性，在**可复现性**、**透明度**和**本地化部署**方面存在诸多限制。openDDE 提供：

- 🔓 **完全开源 (Fully Open-Source)**: 透明的编排框架，无黑盒操作。
- 🔬 **可复现流水线 (Reproducible Pipelines)**: 标准化的结构预测与评分流程。
- 🧩 **可插拔后端 (Pluggable Backends)**: 轻松集成 Boltz, OpenFold 等多种模型。
- 🖥 **本地优先 (Local-First)**: 支持完全本地部署，保障数据隐私。
- 📊 **标准化报告 (Standardized Reporting)**: 内置多维度生物物理指标评测。

---

## 🎯 任务支持 | Project Scope

openDDE 专注于构建**引擎中间层**，支持以下核心任务：

| 任务类型 (Task) | 描述 (Description) |
| :--- | :--- |
| **复合物预测** | 蛋白-配体 / 蛋白-蛋白 / 蛋白-核酸复合物结构预测 |
| **亲和力评估** | 基于回归与排序的结合亲和力预测 (Affinity Scoring) |
| **约束建模** | 支持模板、距离及位点等空间约束引导建模 |
| **评估报告** | 自动计算 RMSD, lDDT, DockQ 及置信度汇总 |

---

## 🏗 架构设计 | Architecture

```text
openDDE
 ├── 🛰 pipeline     # 任务编排 (Task orchestration)
 ├── 🔌 backends     # 模型适配器 (Model adapters: Boltz, OpenFold, etc.)
 ├── 🧬 tasks        # 核心任务 (Structure / Affinity / Pocket)
 ├── 📏 scoring      # 指标与置信度 (Metrics & confidence)
 ├── 💾 data         # 特征工程 (Featurization)
 └── 📊 viz          # 视觉化报告 (Reporting & Visualization)
```
---
## ⚡ 快速上手 | Quickstart
####  1. 安装 (Installation)
```bash
# 克隆仓库
git clone https://github.com/yourname/openDDE.git
cd openDDE

# 开发模式安装
pip install -e .

# 可选：安装后端支持 (例如 Boltz)
pip install boltz
```
#### 2. 运行结构预测 (Structure Prediction)
```bash
opendde predict \
  --protein protein.fasta \
  --ligand ligand.sdf \
  --backend boltz2 \
  --output ./results/
```
#### 3. 亲和力评分 (Binding Scoring)
```bash
opendde score --complex ./results/complex.cif --backend boltz2
```
---
## 🔌 后端适配器 | Supported Backends
openDDE 通过适配器模式支持多种后端，且**不包含任何受限模型权重**。

| Backend | Task Type | Status | Note |
| :--- | :--- | :--- | :--- |
| **Boltz-2** | Structure + Affinity | ✅ | Recommended |
| **Boltz-1** | Structure | ✅ | Stable |
| **OpenFold** | Protein Folding | ✅ | - |
| **AF3 Adapter** | All-atom | ⚠ | 需要用户自备权重 (User-provided weights only) |
---
## 🧪 评测与可复现性 | Evaluation
我们强调 "Deterministic Workflows"（确定性工作流）：
固定配置：所有推理参数均通过配置文件锁定。
环境一致性：依赖库版本锁定，确保结果在不同设备间可比。
基准测试：```bash opendde eval --benchmark pdbbind      ```

---
## 🛣 路线图 | Roadmap
**[x] v0.1**: 基础 CLI 工具、Boltz 后端集成、CIF 格式输出。

**[ ] v0.2**: Benchmark 基准测试套件、Docker 镜像支持、亲和力评分基线。

**[ ] v1.0**: 多后端并行支持、约束建模、可视化 Dashboard。

---
## 🛡 合规性声明 | Compliance
**Notice**: openDDE 是一个独立的研究框架。
1. 与 Google DeepMind 或 Isomorphic Labs 无任何隶属关系。
2. 不分发、不托管任何受版权保护或受限的模型权重。
3. 用户需遵守所使用后端模型的原始许可协议（如 Boltz, OpenFold 等）。

## 🤝 贡献与引用 | Contributing & Citation
我们欢迎任何形式的贡献！
```
@software{opendde2026,
  author = {openDDE Contributors},
  title = {openDDE: An Open-source Drug Design Engine},
  year = {2026},
  url = {https://github.com/yourname/openDDE}
}
```
<p align="center"><b>Open infrastructure accelerates science.</br>
开放基础设施，加速科学创新。</p>
