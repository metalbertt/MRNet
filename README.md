# ACL Tear Detection on Knee MRI: SVM, KNN and Decision Tree

Group project for the Research Methodology course, Bina Nusantara University (2024).

The project compares three classical classifiers (SVM, KNN and Decision Tree) for detecting ACL tears in knee MRI scans. Each classifier runs on two feature sets: deep features from a pretrained VGG16 network and hand-crafted SIFT descriptors.

## Data

The project uses the MRNet dataset from the Stanford ML Group (1,370 knee MRI exams). The dataset is not included in this repository. Download it from the Stanford AIMI website and place it in a folder named `MRNet-v1.0/` next to the notebooks.

## How to run

1. `pip install -r requirements.txt`
2. Run `Feature_Extraction_VGG16.ipynb` and `Feature_Extraction_SIFT.ipynb`. Each notebook extracts features, trains the three classifiers and prints the evaluation.

## Results (test set, 750 samples)

|     Classifier   | VGG16 features | SIFT features |
|------------------|----------------|---------------|
|        SVM       |      71.1%     |     74.5%     |
|        KNN       |      78.8%     |     74.3%     |
|   Decision Tree  |      68.3%     |     67.7%     |
|      Ensemble    |      77.7%     |     77.6%     |

KNN on VGG16 features gave the best single result. The ensemble reached 96% to 98% training accuracy but under 78% on the test set, so it overfits.