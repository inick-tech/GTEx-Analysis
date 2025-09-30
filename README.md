# Deconstructing Tissue-Specific Gene Regulatory Architecture: A PCA-Based Framework for GTEx Data

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/release/python-390/)

**Author:** Mohammad Nikbakhtbideh  
**Affiliation:** Universiti Sains Malaysia (USM)  
**GitHub:** [inick-tech](https://github.com/inick-tech)

---

## 📝 Abstract
This repository contains the official code and analysis pipeline for the paper, "A Generalizable Computational Framework for Deconstructing Tissue-Specific Gene Regulatory Architecture into Orthogonal Components of Module Amplitude and Logic." This research introduces a modular, statistically validated computational framework to analyze co-regulated gene sets (modules) across GTEx tissue transcriptomes. Using Principal Component Analysis (PCA) with rigorous validation (Horn's Parallel Analysis, leave-one-gene-out cross-validation), the framework decomposes variance into two orthogonal axes: **Module Amplitude (PC1)** quantifying overall pathway investment, and **Regulatory Logic (PC2)** capturing functional trade-offs. Demonstrated on circadian clock, interferon-alpha response, and hypoxia pathways, the pipeline uncovers conserved "amplitude-logic" principles, generating hypotheses for tissue-specific regulation.

## 📂 Repository Structure
The repository is organized to ensure clarity and reproducibility of the research findings.

```markdown
# Deconstructing Tissue-Specific Gene Regulatory Architecture: A PCA-Based Framework for GTEx Data

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/release/python-390/)

**Author:** Mohammad Nikbakhtbideh  
**Affiliation:** Universiti Sains Malaysia (USM)  
**GitHub:** [inick-tech](https://github.com/inick-tech)

---

## 📝 Abstract
This repository contains the official code and analysis pipeline for the paper, "A Generalizable Computational Framework for Deconstructing Tissue-Specific Gene Regulatory Architecture into Orthogonal Components of Module Amplitude and Logic." This research introduces a modular, statistically validated computational framework to analyze co-regulated gene sets (modules) across GTEx tissue transcriptomes. Using Principal Component Analysis (PCA) with rigorous validation (Horn's Parallel Analysis, leave-one-gene-out cross-validation), the framework decomposes variance into two orthogonal axes: **Module Amplitude (PC1)** quantifying overall pathway investment, and **Regulatory Logic (PC2)** capturing functional trade-offs. Demonstrated on circadian clock, interferon-alpha response, and hypoxia pathways, the pipeline uncovers conserved "amplitude-logic" principles, generating hypotheses for tissue-specific regulation.

## 📂 Repository Structure
The repository is organized to ensure clarity and reproducibility of the research findings.

```
GTEx-Gene-Regulatory-Framework/
│
├── 📂 data/
│   └── placeholder.txt         # Placeholder for the GTEx dataset (see Data section)
│
├── 📂 notebooks/
│   └── Code.ipynb              # Jupyter notebook for data preprocessing, PCA, sensitivity analysis, correlation networks, and visualizations.
│
├── 📂 publication_outputs_comprehensive/
│   └── .gitkeep                # This directory will store generated high-resolution figures and outputs.
│
├── .gitignore                  # Specifies files to be ignored by Git.
├── LICENSE                     # MIT License for the project.
└── README.md                   # You are here.
```

## 🚀 Getting Started
To replicate the analysis, please follow the steps below.

### Prerequisites

* Python 3.9 or higher
* Jupyter Notebook or Google Colab
* Git for cloning the repository

### Installation & Setup

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/inick-tech/GTEx-Gene-Regulatory-Framework.git
    cd GTEx-Gene-Regulatory-Framework
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    # For macOS/Linux
    python3 -m venv venv
    source venv/bin/activate

    # For Windows
    python -m venv venv
    .\venv\Scripts\activate
    ```

3.  **Install the required libraries:**
    The necessary Python packages (e.g., pandas, numpy, scikit-learn, matplotlib, seaborn, adjustText, statsmodels, pingouin, gseapy) are installed via pip in the notebook itself. Run the first cell to install them if needed.

### Data

Due to the size and licensing of the GTEx dataset, the raw data file (`GTEx_Analysis_2022-06-06_v10_RNASeQCv2.4.2_gene_median_tpm.gct`) is not included in this repository.

To run the notebooks, you will need to download the dataset from the [GTEx Portal](https://gtexportal.org/home/downloads) and place it in the `/data` directory. The expected file is the median gene-level TPM across tissues (v10 release). Rename or symlink it to match the path in the code: `data/GTEx_Analysis_2022-06-06_v10_RNASeQCv2.4.2_gene_median_tpm.gct`.

## ⚙️ Usage: Running the Analysis

The analysis is contained in a single Jupyter notebook, which can be run end-to-end.

1.  **`notebooks/Code.ipynb`**:
    * This notebook handles the entire pipeline:
        1.  Loads and preprocesses GTEx data for predefined gene sets (Circadian Clock, Interferon Alpha Response, Hypoxia).
        2.  Performs Horn's Parallel Analysis for significant PC determination.
        3.  Executes PCA with biplots and loadings visualizations.
        4.  Runs leave-one-gene-out sensitivity analysis for robustness.
        5.  Computes Pearson and partial correlation networks.
        6.  Generates summary visualizations (tissue rankings, PC2 vs. PC1 scatters).
    * Outputs are saved to `/publication_outputs_comprehensive/` as high-resolution PNG figures.

To run: Open the notebook in Jupyter or Colab, ensure the data file is in place, and execute all cells.

## 📊 Key Findings

The framework reveals a conserved "amplitude-logic" structure across pathways, validated statistically.

#### Horn's Parallel Analysis
Only the first two PCs are significant, justifying retention for all gene sets.

![Horn's Parallel Analysis for Circadian Clock](./publication_outputs_comprehensive/horns_parallel_analysis_circadian_clock.png)
*Figure: Horn's Parallel Analysis (example for Circadian Clock).*

#### PCA Biplots and Loadings
PC1 (Amplitude) shows uniform positive loadings; PC2 (Logic) reveals bipolar trade-offs.

![PCA Biplot for Hypoxia](./publication_outputs_comprehensive/pca_biplot_hypoxia.png)
*Figure: PCA Biplot (example for Hypoxia).*

#### Sensitivity and Correlation Networks
Leave-one-gene-out confirms PC2 stability; partial correlations refine direct gene links.

![PC2 Stability for Interferon](./publication_outputs_comprehensive/pca_sensitivity_logo_interferon_alpha_response.png)
*Figure: PC2 Loading Stability (example for Interferon Alpha Response).*

#### Tissue Rankings
Ranks tissues by module activity, aligning with biology (e.g., immune tissues high in Interferon).

![Tissue Ranking for Circadian](./publication_outputs_comprehensive/tissue_activity_ranking_circadian_clock.png)
*Figure: Tissue Ranking by Module Activity (example for Circadian Clock).*

## 📄 Citation
If you use the code or findings from this research in your work, please cite our paper:

```bibtex
@article{Nikbakhtbideh2025,
  title   = {A Generalizable Computational Framework for Deconstructing Tissue-Specific Gene Regulatory Architecture into Orthogonal Components of Module Amplitude and Logic},
  author  = {Nikbakhtbideh, Mohammad},
  journal = {arXiv preprint},
  year    = {2025},
  url     = {https://github.com/inick-tech/GTEx-Gene-Regulatory-Framework}
}
```

## 📜 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```
