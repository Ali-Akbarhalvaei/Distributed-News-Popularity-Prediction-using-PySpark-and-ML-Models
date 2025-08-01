# Distributed-News-Popularity-Prediction-using-PySpark-and-ML-Models
Predict news article popularity using distributed PySpark and 6 ML models. Includes ROC/AUC analysis, feature importance, EDA, and a virtualized Ubuntu+Spark+Hadoop setup. Based on UCI dataset and WIMS 2015 research.


## 🔎 Overview

This project replicates and extends the work from the research paper:

> Fernandes, K., Vinagre, J., & Cortez, P. (2015). "A proactive intelligent decision support system for predicting the popularity of online news." *Proceedings of the International Conference on Web Intelligence, Mining and Semantics (WIMS)*. [Link to paper](https://repositorium.sdum.uminho.pt/bitstream/1822/39169/1/main.pdf)

It uses the **UCI Online News Popularity Dataset**:

> [UCI Machine Learning Repository – Online News Popularity](https://archive.ics.uci.edu/dataset/332/online+news+popularity)

The objective is to build a distributed system using **PySpark** to predict whether an online article will be popular, applying six classification models, and analyzing their performance and feature importance.

---

## 🚀 Project Highlights

- Fully distributed data processing using **Apache Spark** and **PySpark**
- Six machine learning models:
  - Logistic Regression
  - Decision Tree
  - Random Forest
  - Gradient Boosted Trees
  - Linear SVC
  - Gaussian Naive Bayes
- Feature importance comparison
- ROC/AUC evaluation
- Exploratory Data Analysis and visualizations
- Developed and tested on a **virtualized distributed Ubuntu environment**

---

## 🪨 System Requirements

### 💻 Host Machine (Tested On):

- **Apple Silicon MacBook Pro M1**
- **16 GB RAM**
- Minimum 13 GB free disk space

### 🚀 Guest Virtual Machine (VM)

Installed using **VirtualBox** + **Ubuntu Server 24.04 ARM64**:

- 4 CPUs
- 4–8 GB RAM
- NAT Networking with port forwarding (SSH: 2022, VNC: 5910)

### Tools Installed:

- **Python 3.12**
- **Java JDK 21**
- **Apache Hadoop 3.4.0**
- **Apache Spark 3.5.x**
- **TigerVNC + IceWM desktop**
- **Emacs, Kitty terminal, Midnight Commander**

---

## 💡 VM Setup Guide (Based on Professor’s Instructions)

1. **Download and install VirtualBox**
2. **Download Ubuntu Server 24.04 ARM64 ISO**
3. Create a VM:
   - 4 CPU cores
   - 4GB RAM
   - Use the Ubuntu ISO to install system with user: `vboxuser`
4. Set up **SSH tunneling**: Port forward 2022 (host) to 22 (guest)
5. Install necessary packages:

```bash
sudo apt update && sudo apt upgrade
sudo apt install -y python3 default-jre openssh-server
```

6. Install Hadoop and Spark (see project notebook or professor's script)
7. Set environment variables in `.bashrc` for HADOOP\_HOME, JAVA\_HOME
8. Configure **TigerVNC** with IceWM and set up GUI access over port 5910
9. Use **Kitty terminal** + **VNC Viewer** to interact with the VM

---

## 🚜 How to Run This Project

### ✅ 1. Clone the Repository

```bash
git clone https://github.com/yourusername/news-popularity-pyspark.git
cd news-popularity-pyspark
```

### ✅ 2. Activate Virtual Environment

Make sure your virtual environment in the VM is activated:

```bash
source venv/bin/activate
```

### ✅ 3. Install Python Requirements

```bash
pip install -r requirements.txt
```

### ✅ 4. Start Spark

Ensure `SPARK_HOME` is set and run Spark:

```bash
pyspark
```

### ✅ 5. Open Jupyter or Execute `.ipynb` via terminal

You can also run the notebook in VS Code connected over SSH or use the GUI with Jupyter installed.

---

## 🔹 Dataset Info

- **Rows**: \~39,000 news articles
- **Features**: 58
  - NLP: subjectivity, polarity
  - Meta: shares, links, category flags
  - Semantic: LDA topic distributions
  - Text: keyword statistics

---

## 🔜 Citation & Credits

- UCI Dataset: [https://archive.ics.uci.edu/dataset/332/online+news+popularity](https://archive.ics.uci.edu/dataset/332/online+news+popularity)
- Research Paper: [https://repositorium.sdum.uminho.pt/bitstream/1822/39169/1/main.pdf](https://repositorium.sdum.uminho.pt/bitstream/1822/39169/1/main.pdf)
- Spark MLlib API: [https://spark.apache.org/docs/latest/ml-classification-regression.html](https://spark.apache.org/docs/latest/ml-classification-regression.html)
- TigerVNC: [https://tigervnc.org/](https://tigervnc.org/)

---

## 🚩 Disclaimer

This project is built for academic purposes for the **Big Data course at the University of Bologna**. All credits go to the dataset creators and the original researchers.

---

## ✨ Authors

- **Ali Akbar Halvaei**
- Contact: [ali.akbarhalvaei@example.com](mailto\:ali.akbarhalvaei@example.com)

