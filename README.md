# anemia-detection-using-fingernail-colour
This project develops a classifier (anemic vs. non-anemic) using fingernail images as a non-invasive screening approach. We explored a **hybrid pipeline** because our data came from two different sources:  
1) a **labeled pediatric fingernail dataset** (clinical labels based on hemoglobin tests), and  
2) an **unlabeled adult hand/fingernail dataset** (adult images without class labels). 

To make use of the unlabeled adult dataset, we first **learned features without labels** using a **convolutional autoencoder**, then applied **PCA + K-means++ clustering** to assign **pseudo-labels** (2 clusters) for adults. After that, we trained supervised classifiers on:
- the labeled children dataset
- the pseudo-labeled adult dataset
- and a combined dataset (children + adults)

## Models explored
- **Traditional ML:** SVM, Random Forest  
- **Deep Learning:** ResNet50, ResNet18, AlexNet

## Dataset
Two datasets were used:
- **Children (labeled):** fingernail images labeled as anemic/non-anemic based on lab-tested Hb levels.
- **Adult (unlabeled):** adult hand images with metadata (Hb level) and nail bounding boxes, but without direct anemia class labels.

Due to size limits, the datasets are not stored in this repository.
Download (Google Drive): [Dataset](https://drive.google.com/drive/folders/1J5pEaBOUA1FJaThe0BH7ewyolzavyzB-?usp=sharing)

## What’s inside this repo
- `notebooks/` – step-by-step pipeline (preprocessing → feature learning → pseudo-labeling → training → evaluation)

