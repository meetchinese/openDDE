openDDE

Open Drug Design Engine

An open-source, reproducible, and extensible Drug Design Engine (DDE) for protein–ligand and biomolecular complex modeling.

一个开源、可复现、可扩展的药物设计引擎（Drug Design Engine），用于蛋白-配体及多分子复合物建模与评估。

🚀 Why openDDE?

Closed drug design engines limit reproducibility, transparency, and local deployment.

openDDE provides:

🔓 Fully open-source orchestration framework

🔬 Reproducible structure prediction & scoring pipelines

🧩 Pluggable backend architecture (Boltz, OpenFold, optional adapters)

🖥 Local deployment support (no mandatory cloud dependency)

📊 Standardized evaluation & reporting

闭源药物设计引擎在可复现性、透明度和本地部署方面存在限制。

openDDE 提供：

🔓 完全开源的引擎编排框架

🔬 可复现的结构预测与评分流程

🧩 可插拔模型后端架构（Boltz、OpenFold、可选适配器）

🖥 支持本地部署（无需强制云服务）

📊 标准化评测与报告输出

🎯 Project Scope

openDDE focuses on building a standardized Drug Design Engine layer, not replicating proprietary models.

openDDE 的目标是构建标准化的“药物设计引擎层”，而不是复刻任何闭源模型。

Supported task types:

支持的任务类型包括：

Complex Structure Prediction
Protein–ligand / protein–protein / protein–nucleic acid complexes
蛋白-配体 / 蛋白-蛋白 / 蛋白-核酸复合物结构预测

Binding Affinity Estimation
Ranking and regression-based scoring
结合亲和力排序与回归预测

Constraint-Guided Modeling
Template constraints / distance constraints / site constraints
模板约束 / 距离约束 / 位点约束建模

Evaluation & Reporting
RMSD / lDDT / DockQ / confidence aggregation
结构评测与置信度汇总

🏗 Architecture
openDDE
 ├── pipeline      # Task orchestration
 ├── backends      # Model adapters
 ├── tasks         # Structure / affinity / pocket
 ├── scoring       # Metrics & confidence
 ├── data          # Featurization
 ├── viz           # Reporting

Design principles:

设计原则：

Backend-agnostic engine

No redistribution of restricted weights

Reproducible pipelines

Modular evaluation framework

⚡ Quickstart
1️⃣ Installation
git clone https://github.com/yourname/openDDE.git
cd openDDE
pip install -e .

Optional (backend setup):

可选（安装模型后端）：

pip install boltz
2️⃣ Run Structure Prediction
opendde predict \
  --protein protein.fasta \
  --ligand ligand.sdf \
  --backend boltz2 \
  --output results/

Output:

输出内容：

Complex structure (CIF/PDB)

Confidence summary (JSON)

Evaluation metrics (optional)

3️⃣ Run Binding Scoring
opendde score \
  --complex complex.cif \
  --backend boltz2
🔌 Backends

openDDE does not bundle proprietary weights.

openDDE 不包含任何受限模型权重。

Supported backends (extensible):

当前支持的后端（可扩展）：

Backend	Type	Status
Boltz-2	Structure + Affinity	✅
Boltz-1	Structure	✅
OpenFold	Protein Folding	✅
AF3 Adapter	Optional adapter	⚠ User-provided weights only

Adapters standardize:

统一接口规范：

predict()
score()
supports_constraints()
📊 Evaluation

Supported metrics:

支持的评测指标：

RMSD

lDDT

DockQ

Interface confidence

Affinity correlation (Pearson/Spearman)

Run benchmark:

运行基准评测：

opendde eval --benchmark pdbbind
🧪 Reproducibility

openDDE emphasizes deterministic workflows:

openDDE 强调可复现流程：

Fixed config templates

Logged inference settings

Version-locked dependencies

Standardized reporting

🛡 Compliance & Legal Notice

openDDE:

Is not affiliated with Google DeepMind or Isomorphic Labs

Does not distribute restricted model weights

Does not bypass any access controls

openDDE：

与 Google DeepMind 或 Isomorphic Labs 无隶属关系

不分发受限模型权重

不提供任何绕过访问控制的内容

🛣 Roadmap
v0.1

Basic CLI

Boltz backend

CIF output

v0.2

Benchmark suite

Docker support

Affinity scoring baseline

v1.0

Multi-backend support

Constraint modeling

Full evaluation dashboard

🤝 Contributing

We welcome contributions in:

欢迎以下方向的贡献：

New backend adapters

Improved scoring modules

Dataset integration

Performance optimization

Documentation improvements

Please read CONTRIBUTING.md before submitting a PR.

📜 License

Apache 2.0 License

📖 Citation

If you use openDDE in research, please cite:

如果在科研中使用 openDDE，请引用：

@software{opendde2026,
  title = {openDDE: Open Drug Design Engine},
  year = {2026},
  url = {https://github.com/yourname/openDDE}
}
🌍 Vision

Open infrastructure accelerates science.

开放基础设施，加速科学创新。

openDDE aims to make high-level drug design infrastructure transparent, extensible, and accessible to researchers worldwide.

openDDE 致力于构建透明、可扩展、可全球部署的药物设计基础设施。
