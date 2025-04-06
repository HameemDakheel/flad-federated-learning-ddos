
# FLAD: Adaptive Federated Learning for DDoS Attack Detection

This project is based on **FLAD**, an adaptive Federated Learning (FL) approach designed for DDoS attack detection using feed-forward neural networks. It was originally proposed by [Roberto Doriguzzi-Corin](https://github.com/doriguzzi) and [Domenico Siracusa], and I’ve built upon this foundation as part of my **graduation project**.

This version includes several modifications and enhancements, including a packaged dataset provided in the `Clients.zip` file to help others get started quickly with evaluation and testing.

---

## 📚 Project Background

FLAD implements an adaptive Federated Learning technique that dynamically monitors and adjusts computation among clients based on their local classification accuracy — without exchanging raw data. This makes it highly effective in environments with varying attack profiles.

🔗 Original Research:  
Roberto Doriguzzi-Corin, Domenico Siracusa,  
*"FLAD: Adaptive Federated Learning for DDoS Attack Detection"*,  
**Computers & Security**, Volume 137, 2024.  
DOI: [10.1016/j.cose.2023.103597](https://doi.org/10.1016/j.cose.2023.103597)

---

## 🔧 Installation & Setup

This project uses **Python 3.9**, **TensorFlow 2.7.1**, and dependencies from the LUCID project (https://github.com/doriguzzi/lucid-ddos).

### 1. Install Miniconda (Recommended)

Install Miniconda from:  
👉 https://docs.conda.io/en/latest/miniconda.html

Then, run the following:

```bash
conda create -n python39 python=3.9
conda activate python39
```

### 2. Install Requirements

For Linux:
```bash
pip install tensorflow==2.7.1
pip install scikit-learn h5py pyshark protobuf==3.19.6
```

For macOS (M1):
```bash
conda install -c conda-forge tensorflow=2.7.1
conda install -c conda-forge scikit-learn h5py pyshark
```

> ⚠️ Ensure `tshark` is installed (`sudo apt install tshark`) and version is either ≤ 3.2.3 or ≥ 3.6 for compatibility with `pyshark`.

---

## 📁 Dataset

The project includes a preprocessed dataset (`Clients.zip`) for testing and evaluation purposes. Extract the contents to the working directory, and reference the paths during training.

---

## 📊 Training and Evaluation

To run the federated learning pipeline, use:

```bash
python3 flad_main.py --clients /path_to/Clients/
```

You can modify training behavior using flags like:
- `--training_mode`: flad | fedavg_1e | fedavg_5e | flddos
- `--rounds`, `--local_epochs`, `--steps_per_epoch`
- `--output_folder`, `--model`, `--optimizer`, `--rn_seed`

More information can be found in the full usage documentation below.

---

## 📂 Preprocessing & Dataset Info

FLAD uses the LUCID dataset parser to handle `.pcap` files and extract traffic features into `.hdf5` format. Refer to the [original README](https://github.com/doriguzzi/lucid-ddos) for detailed steps, or follow the summarized instructions in this repo.

---

## 🧠 Citation & Credits

All credit for the original FLAD implementation goes to:
- [Roberto Doriguzzi-Corin](https://github.com/doriguzzi)
- Domenico Siracusa

If using FLAD in your research, please cite their paper:

```bibtex
@article{flad2024,
  title={FLAD: Adaptive Federated Learning for DDoS attack detection},
  author={Doriguzzi-Corin, Roberto and Siracusa, Domenico},
  journal={Computers \& Security},
  volume={137},
  year={2024},
  doi={10.1016/j.cose.2023.103597}
}
```

---

## 📜 License

This project is released under the [Apache 2.0 License](https://www.apache.org/licenses/LICENSE-2.0).

