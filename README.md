# Signature Verifier

## About the Project
The **Signature Verifier** aims to address the problem of identifying forged signatures in real-world scenarios. This solution has critical applications in sectors like banking, judiciary, and other domains where signature verification is essential.

We have developed a state-of-the-art approach using **Siamese Network Architecture** to detect forged signatures. Our unique integration of **Convolutional Neural Networks (CNNs)**, **Transfer Learning**, and **Siamese Networks** provides an effective and scalable solution to the problem.

## Problem Statement
Signature forgery is a common issue in many sectors. Current methods often rely on human experts or outdated systems, which are not scalable or entirely reliable. This project introduces an AI-driven approach to automate signature verification with high accuracy.

## Dataset
We utilized the **CEDAR Signature Dataset**, which consists of:
- 24 genuine and 24 forged signatures for each of the 55 unique individuals.
- The forgeries were performed by skilled professionals, making this dataset suitable for real-world applications.

After pairing genuine and forged signatures, we created a dataset of **46,860 total pairs** with a nearly equal distribution between genuine and forged pairs. This dataset was split into:
- 80% training
- 10% validation
- 10% testing

## Technical Approach
### 1. **Siamese Network with Xception Backbone**
   - We employed a **Siamese Network** to compare signature pairs.
   - For feature extraction, we fine-tuned the **Xception model**, which was pre-trained on the **ImageNet** dataset, known for excelling in feature extraction tasks.
   - The final network is designed to compare pairs of images and classify them as either genuine or forged.

### 2. **Contrastive Loss Function**
   - We used **Contrastive Loss** to optimize the model. This loss function:
     - Increases the Euclidean distance between forged signature pairs.
     - Decreases the distance between genuine signature pairs.
   - This formulation is ideal for training Siamese networks where the goal is to differentiate between two inputs.

### 3. **Training and Performance**
   - The model was trained on Kaggle GPUs using the **Contrastive Loss** to adjust the network's weights based on signature pair distances.
   - After training, the model achieved **99.23% accuracy** on the test set, proving its robustness.

## Features
### 1. **Fine-tuning on New Signatures**
   - The model supports fine-tuning when introduced to new signature samples. By applying specific augmentations, the model adapts to the new data, enhancing real-world usability.
   
### 2. **Flask API Integration**
   - A **Flask-based web app** was developed to serve the model in real-time. The backend APIs are fully functional, allowing users to upload signatures and get predictions instantly.

## Deployment
### 1. **Frontend Development**
   - We have designed a complete **Figma design** for the frontend to enhance the user experience and interface. The frontend implementation is extremely user friendly.
   
### 2. **Exhibition Testing**
   - A mechanism was implemented where visitors performed live signature tests. Users signed on provided paper boxes, and our system verified the authenticity of the signatures in real-time.

### 3. **Research Paper**
   - We are in the process of preparing a **research paper** based on this work, detailing our unique contributions to solving this problem using deep learning architectures.


## Usage
- Upload two signature images: one genuine and one test signature.
- The system will return a prediction indicating whether the signature is forged or genuine.

## Acknowledgments
- Special thanks to the creators of the **CEDAR Dataset** for providing an invaluable resource for this project.
- We also thank the authors of the **Xception model** for their contributions to the deep learning community.
