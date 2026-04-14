{\rtf1\ansi\ansicpg1252\cocoartf2761
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fnil\fcharset0 HelveticaNeue;}
{\colortbl;\red255\green255\blue255;}
{\*\expandedcolortbl;;}
\margl1440\margr1440\vieww11520\viewh8400\viewkind0
\deftab560
\pard\pardeftab560\slleading20\pardirnatural\partightenfactor0

\f0\fs26 \cf0 # Single-cell RNA-seq Analysis of PBMC 3k Dataset\
\
This project performs an end-to-end single-cell RNA-seq (scRNA-seq) analysis of the publicly available Peripheral Blood Mononuclear Cells (PBMC) 3k dataset using Python and Scanpy.\
\
The workflow includes data preprocessing, dimensionality reduction, clustering, cell-type annotation, and a simple machine learning extension to evaluate cluster separability.\
\
---\
\
## Workflow\
\
- Quality control (cell and gene filtering)\
- Normalization and log-transformation\
- Highly variable gene selection\
- Dimensionality reduction (PCA)\
- Neighborhood graph construction\
- Clustering (Leiden algorithm)\
- UMAP visualization\
- Differential expression analysis for marker gene identification\
- Cell-type annotation using canonical immune markers\
\
---\
\
## Machine Learning Extension\
\
As a downstream analysis, a supervised machine learning model was applied to evaluate whether cell cluster identity could be predicted from transcriptomic features.\
\
- **Features**: PCA-reduced gene expression  \
- **Labels**: Leiden cluster assignments  \
- **Model**: Random Forest classifier  \
\
Model performance was evaluated using a confusion matrix, which showed that most clusters were correctly classified. Misclassifications occurred primarily between biologically similar cell populations (e.g., related T cell subsets), indicating that the learned errors reflect biological similarity rather than model failure.\
\
---\
\
## Results\
\
- Identified major immune cell populations, including T cells, B cells, NK cells, and monocytes  \
- Cluster identities were validated using differential expression and canonical marker genes  \
- UMAP visualization revealed clear separation of cell populations  \
- Machine learning analysis confirmed that clusters are well-separated in feature space  \
\
---\
\
## Tools and Libraries\
\
- Python  \
- Scanpy  \
- AnnData  \
- NumPy  \
- pandas  \
- matplotlib  \
- scikit-learn  \
\
---\
\
## Environment\
\
This analysis was performed in a Google Colab environment.\
\
---\
\
\pard\pardeftab560\slleading20\partightenfactor0
\cf0 ## Repository Structure\
\
```\
pbmc-scrnaseq-analysis/\
\uc0\u9500 \u9472 \u9472  pbmc_analysis.ipynb\
\uc0\u9500 \u9472 \u9472  README.md\
\uc0\u9492 \u9472 \u9472  figures/\
    \uc0\u9500 \u9472 \u9472  umap_cell_types.png\
    \uc0\u9492 \u9472 \u9472  confusion_matrix.png\
```}