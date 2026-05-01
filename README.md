# Digital-Twin
Phenotypic Digital Twin for Temporal Gene Expression | Python, PyTorch, Scikit-learn, Pandas

Architected an LSTM neural network in PyTorch to simulate phenotypic progression, acting as a digital twin to forecast temporal gene expression trajectories from cell-free RNA microarray data.

Engineered a data pipeline to parse, clean, and align unstructured patient metadata, transforming 2D microarray matrices into 3D tensors for sequence-to-sequence learning.

Implemented vectorized one-way ANOVA to perform statistical feature selection, reducing dimensionality by isolating the top 500 significantly varying genes (p < 0.1) to optimize memory and model performance.

Developed comprehensive visualization dashboards using Seaborn and Matplotlib to benchmark the digital twin's predicted trajectories against actual biological baselines across individual subjects.

