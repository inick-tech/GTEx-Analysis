A Generalizable Computational Framework for Deconstructing Tissue-Specific Gene Regulatory Architecture
Author: Mohammad Nikbakhtbideh
GitHub: inick-tech

📝 Abstract
The proliferation of high-throughput sequencing has generated vast transcriptomic datasets, such as those from the Genotype-Tissue Expression (GTEx) project, presenting a significant computational challenge in extracting tissue-specific regulatory principles. This report introduces a modular, statistically validated computational framework designed to deconstruct the complexity of any co-regulated gene set (module) across a pan-tissue atlas. The framework consistently reveals that tissue-specific regulatory architecture is structured along two primary, orthogonal axes. The first principal component (PC1) invariably represents the overall expression amplitude of the entire module, quantifying a tissue's total investment in the pathway. The second principal component (PC2), validated for statistical significance using Horn's Parallel Analysis and for structural robustness via leave-one-gene-out cross-validation, captures the internal regulatory logic (a functional trade-off between distinct sub-modules). The utility of this framework and the conservation of the two-axis structure are demonstrated across three diverse and fundamental biological systems: the human circadian clock, the interferon-alpha response, and the hypoxia pathway. This work establishes a powerful, hypothesis-generating tool for dissecting context-dependent gene regulation and suggests that the uncovered "amplitude-logic" principle is a fundamental and recurring feature of biological system design.

📂 Repository Structure
This repository is organized to ensure the clarity and complete reproducibility of the research findings.

Gene-Regulatory-Architecture-Analysis/
│
├── 📂 data/
│   └── GTEx_Analysis_2022-06-06_v10_RNASeQCv2.4.2_gene_median_tpm.gct
│
├── 📂 notebooks/
│   └── Code.ipynb              # Main Jupyter Notebook with the complete analysis pipeline.
│
├── 📂 results/
│   └── .gitkeep                # This directory will store generated charts and tables.
│
├── .gitignore                  # Specifies files to be ignored by Git.
├── LICENSE                     # MIT License for the project.
├── requirements.txt            # List of required Python packages.
└── README.md                   # You are here.


🚀 Getting Started
To replicate the analysis presented in the paper, please follow the steps below.

Prerequisites
Python 3.9 or higher

Jupyter Notebook or Google Colab

Git for cloning the repository

Installation & Setup
Clone the repository:

git clone [https://github.com/inick-tech/Gene-Regulatory-Architecture-Analysis.git](https://github.com/inick-tech/Gene-Regulatory-Architecture-Analysis.git)
cd Gene-Regulatory-Architecture-Analysis

Create a virtual environment (recommended):

# For macOS/Linux
python3 -m venv venv
source venv/bin/activate

# For Windows
python -m venv venv
.\venv\Scripts\activate

Install the required libraries:
The necessary Python packages are listed in requirements.txt.

pip install -r requirements.txt

⚙️ Running the Analysis
The entire analytical pipeline is contained within a single Jupyter Notebook for ease of use and reproducibility.

notebooks/Code.ipynb

This notebook executes the complete, end-to-end workflow presented in the manuscript:

Data Loading & Preprocessing: Loads the GTEx TPM data and prepares it for analysis.

Principal Component Analysis (PCA):

Performs Horn's Parallel Analysis to statistically justify retaining the first two principal components.

Generates PCA biplots to visualize the relationship between tissues and gene loadings.

Robustness & Stability Validation:

Conducts a Leave-One-Gene-Out cross-validation to confirm the stability and robustness of the PC2 (Regulatory Logic) axis.

Network Inference:

Constructs and compares Pearson (overall) and Partial (direct) correlation networks to dissect the co-expression topology.

Results Generation:

Produces all figures and quantitative metrics discussed in the paper, saving them to the results/ directory.

Simply open and run the notebook cells sequentially to reproduce all findings.

📄 Citation
If you use the code or findings from this research in your work, please cite our paper:

@article{Nikbakhtbideh2025,
  title   = {A Generalizable Computational Framework for Deconstructing Tissue-Specific Gene Regulatory Architecture into Orthogonal Components of Module Amplitude and Logic},
  author  = {Nikbakhtbideh, Mohammad},
  journal = {Journal of Computational Biology},
  year    = {2025},
  url     = {[https://github.com/inick-tech/Gene-Regulatory-Architecture-Analysis](https://github.com/inick-tech/Gene-Regulatory-Architecture-Analysis)}
}

📜 License
This project is licensed under the MIT License - see the LICENSE file for details.
