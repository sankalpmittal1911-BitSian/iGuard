# iGuard
iGuard: Efficient Isolation Forest Design for Malicious Traffic Detection in Programmable Switches
## Abstract
Deploying machine learning (ML) models in programmable switch
data planes facilitates low latency and high throughput traffic inference
at line speed. However, data planes pose significant constraints
due to the limited memory and minimal support for mathematical
operations and data types. As a result, the only unsupervised ML
models implemented in data planes to date are Isolation Forests
(iForests). However, conventional iForest models yield suboptimal
malicious traffic detection performance in various traffic use cases.
To address this limitation, this paper proposes iGuard , the first
iForest implementation that can accurately detect malicious traffic
by incorporating the "knowledge" of more powerful autoencoders.
We deploy iGuard in the form of a small set of whitelist rules that
could be easily installed in the switch data planes. We implement
iGuard using the P4 language, and assess its performance in an
experimental platform based on Intel Tofino switches. Upon evaluating
iGuard on various attack traffic use cases, our model can
improve accuracy up to 48.3% while maintaining a similar or lower
switch memory footprint over previous approaches to implement
iForest models in real-world equipment.
## Overview
![image](https://github.com/user-attachments/assets/e0d45852-d68b-4041-b562-e54119a02116)
![image](https://github.com/user-attachments/assets/d5ba0c17-253e-4aba-9f94-759ae80b3435)
![image](https://github.com/user-attachments/assets/724b2213-61e0-47e4-8da4-9519a373c931)

We recently got accepted at ACM CoNext 2024!

## Reproducing Artifacts
First, clone this repository.
### Control plane (software) experiments

1. Populate ``DataSets/`` folder by downloading datasets from [here](https://drive.usercontent.google.com/download?id=1k-oTsxVD3fkZnjwj-4XclVhQdAC36nLd&export=download&authuser=0) as shown in https://github.com/vicTorKd/HorusEye/. For data plane simulations, populate the ``DataSets/Dataplane`` folder using this [link](https://drive.google.com/drive/folders/1d9pf-e9vSW3jf4_R3vFbqvHXD4VcrG_S). Alternatively, simply download the ``DataSets`` folder from this [link](https://drive.google.com/drive/folders/1d9pf-e9vSW3jf4_R3vFbqvHXD4VcrG_S).
2. Run ``iGuard Artifact Evaluation.ipynb`` to completion and verify the plots for software experiments. Please make sure to update the datasets path wherever possible!
