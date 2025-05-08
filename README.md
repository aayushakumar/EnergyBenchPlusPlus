# EnergyBench++

**A Comprehensive Framework for Dynamic Energy–Accuracy Trade-Offs in Edge Deep Learning**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![PyPI version](https://img.shields.io/pypi/v/energybenchpp.svg)](https://pypi.org/project/energybenchpp)

---

## 🚀 Overview

EnergyBench++ is an open-source benchmark suite designed to systematically profile the **energy**, **latency**, and **accuracy** trade-offs of deep neural networks under varied deployment configurations. It supports:

* **Batch×Power Sweeps**: Explore performance under different batch sizes and GPU power caps.
* **Layer Profiling**: Decompose per-layer energy consumption.
* **Early-Exit Architectures**: Integrate BranchyNet, MSDNet, and configurable confidence thresholds.
* **Multi-Device Evaluation**: Run on high-end GPUs (e.g., RTX 3090) and edge platforms (e.g., NVIDIA Jetson Nano).
* **Multi-Workload Support**: From CIFAR-10 and TinyImageNet to audio classification (Google Speech Commands v2).

## ✨ Key Features

1. **Dynamic Energy-Accuracy Efficiency Ratio (D-EAER)**

   * Computes accuracy per Joule with statistical rigor (mean ± 95% CI).
2. **Modular Architecture**

   * Easily extend to new models, datasets, or hardware.
3. **Reproducible Experiments**

   * Configuration via YAML/JSON, multiple random seeds, built-in logging.
4. **Rich Visualizations**

   * Heatmaps, trade-off plots, tables formatted for LaTeX and markdown.


## 📦 Installation

```bash
# Clone the repository
git clone https://github.com/YourOrg/EnergyBenchPlusPlus.git
cd EnergyBenchPlusPlus

# (Optional) Create a virtual environment
python3 -m venv venv
source venv/bin/activate  # Linux/macOS
venv\Scripts\activate   # Windows

# Install dependencies
pip install -r requirements.txt
```

## 🚩 Quick Start

```bash
# 1. Edit configs/config_default.yaml to specify:
#    - models: [MobileNetV2, ResNet18, ...]
#    - datasets: [CIFAR10, TinyImageNet, SpeechCommands]
#    - devices: [RTX3090, JetsonNano]
#    - batch_sizes: [1,8,16,32]
#    - power_caps: [0,30,60,90]

# 2. Run benchmark engine
python benchmark.py --config configs/config_default.yaml

# 3. Generate reports
python report.py --input logs/ --output results/
```

## 🔍 Examples

* **Batch×Power Sweep**: `python benchmark.py --mode sweep`
* **Layer Profiling**: `python benchmark.py --mode layer_profile --model MobileNetV2`
* **Early-Exit Analysis**: `python benchmark.py --mode early_exit --tau 0.9`
* **Cross-Device Comparison**: `python evaluate.py --devices RTX3090 JetsonNano`

Charts and tables will be saved under `results/` with LaTeX-friendly naming.

## 🤝 Contributing

Contributions are welcome! Please open issues or submit pull requests. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## 📄 License

This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.

---

*Built with ❤️ for Green AI and Edge ML research.*
