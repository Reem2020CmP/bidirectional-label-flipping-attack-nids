# Methodology

As illustrated in Fig.1, the proposed methodology consists of dataset preparation, baseline model training, simulation of label-flipping attacks, defense implementation, and performance evaluation.

## Proposed Approach

First, we will prepare our dataset, the UNSW-NB15 dataset, which consists of benign traffic and nine types of network intrusion attacks (e.g., DoS, Exploits, Reconnaissance). The classification task will use the existing binary label provided in the dataset, where 0 represents (Benign) traffic, and 1 represents (Attack) traffic. We will also clean the dataset by removing missing or null values. We will then divide the dataset into training, validation, and test sets, following a 70%, 15%, and 15% split.
Next, we will train the ML models, specifically Random Forest and Decision Tree, on the clean training set and showcase the baseline NIDS performance before the attacks by testing them on the test set. Their performance will then be evaluated using key metrics such as accuracy, precision, recall, F1-score, and the confusion matrix.
After that, we will poison the training set using a bidirectional label-flipping attack by changing the selected labels from attack (1) to benign (0), and vice versa, at poisoning rates of 10%, 20%, and 30% of the overall training set. The models will then be retrained on the poisoned set and evaluated on the clean test set. This will provide us with the opportunity to compare the performance of the system before and after the attacks and assess its vulnerability.
Next, we will apply a defense mechanism to help the system identify which instances may have flipped labels. For this, we will propose a hybrid approach combining KNN neighborhood label disagreement and out-of-fold model-label disagreement. If both defense mechanisms agree that the sample belongs to the opposite class, then it will be relabeled accordingly. For example, a suspicious benign sample might be relabeled as an attack, and a suspicious attack sample might be relabeled as benign. Otherwise, if the two mechanisms disagree or generate a low confidence score, the sample will instead be removed from the training set. The models will then be trained again on the cleaned set.
A final evaluation will then be conducted by measuring the accuracy, precision, recall, F1-score, false-positive rate, false-negative rate, and clean-data retention, as well as how accurately poisoned samples were detected. Finally, we will extensively analyze where the defense works and where it fails, its computational cost, and its limitations. A further comparison will be made with recent papers to compare the performance of the different approaches.

## Tools/Dataset/Technologies

Several tools and libraries will be used in our project to support preprocessing, coding, implementation, experimentation, and evaluation. One of the main tools is Google Colab, where we will primarily code in Python. Other tools include NumPy and Pandas, which are Python libraries that help perform mathematical operations and handle and clean the dataset. Scikit-learn, a machine-learning library, will also be used to train ML classifiers and calculates evaluation metrics. Additionally, Matplotlib will be used to create visualizations, such as graphs and charts, when needed. To support effective collaboration, GitHub will be used to store the project online, enabling us to edit the code and documentation and track members’ contributions.
UNSW-NB15, a benchmark dataset containing network traffic classified as “Benign” and nine categories of malicious traffic, “Fuzzers”, “Analysis”, “Backdoors”, “DoS” (Denial of Service), “Exploits”, “Generic”, “Reconnaissance”, “Shellcode”, and “Worms”, will be the core dataset for system training and testing. The dataset is particularly useful for NIDS and contains a large number of network traffic samples, including their features and labels classifying them as either benign traffic or different types of attacks. 
As for the technologies our project will use, we will focus on machine learning and adversarial machine learning techniques for NIDS. This includes Random Forest and Decision Tree classifiers, as well as the simulation of bidirectional label-flipping data poisoning attacks. 

## System Design

## Evaluation Plan

## Ethical/Legal Considerations
