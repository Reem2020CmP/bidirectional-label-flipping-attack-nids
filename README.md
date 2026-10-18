# Bidirectional Label-Flipping-Hybrid and KNN-OOF Defense for ML-Based Network Intrusion Detection

Machine learning-based network intrusion detection systems play a significant role in detecting malicious network
traffic. They are primarily responsible for protecting computers from cyberattacks.

The method in this experiment hybrid K-Nearest Neighbors and Out-of-Fold (KNNOOF) defense mechanism is proposed, and the influence of label-flipping attacks on ML-based intrusion detection systems is studied in both directions. The research involved the training of
classifiers, namely Random Forest and Decision Tree, using the UNSW-NB15 dataset and testing using clean data and poisoned
data involving 10%, 20%, and 30% poisoning rates. 

The evaluation focuses on two complementary aspects using clean, poisoned, and defended training
datasets, as well as evaluating the effectiveness of the defense in detecting flipped labels. Overall, the study aims to investigate the potential of combining KNN and OOF predictions as a defense against label-flipping attacks in a centralized NIDS and to identify the strengths and limitations of the proposed approach.


## Project Structure

```text
bidirectional label-flipping-nids/
│
├── data/              # Dataset-related files and documents
├── src/               # Source code
├── experiments/       # Experimental scripts and configurations
├── results/           # Results from the experiments
├── figures/           # Graphs and visualzations
├── notebooks/         # Jupyter Notebooks
├── docs/              # Additional documentation
└── README.md          # Project documenation
