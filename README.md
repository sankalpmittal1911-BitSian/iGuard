# iGuard 
![image](https://github.com/user-attachments/assets/32861086-12b4-4c82-ab88-9113799e182f)

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
3. Verify the results from [here](https://docs.google.com/spreadsheets/d/1DVljB4ODjpUPCPUhgQmXLwM9dhUEfgg5Kwsav-rLBrQ/edit?usp=sharing). This is the document we have curated for all possible numbers!

### Data plane (hardware) experiments
Reproducing these can be very cumbersome as main overhead is in setting up the switch. We recommend use these only to verify data plane simulations and we deem these not necessary for artifact reproducability. 
1. Install hardware switch and P4 runtime by following this
[tutorial](https://docs.google.com/document/d/1gyYWL0HY2SanzAoA6GGRImf9ERR1KXrG0Ngg8Zh5VfA/edit#heading=h.r7zf0lr53zqp).
2. Download [PCAP traces](https://drive.usercontent.google.com/download?id=191CmJYWszlSmIitfid2J53UMYtiaqhhe&export=download&authuser=0) from https://github.com/vicTorKd/HorusEye/.
3. Using these traces, send the packets to the switch while compiling ``Data_plane/logic.p4``.
4. Verify the results with data plane simulations from accuracy metrics.
5. Use the P4i tool (we do not have the license as of now) with ``logic.p4`` as target to monitor resource and memory consumption gains compared to iForest models.

### Cite
```
@inproceedings{10.1145/3680121.3697807,
author = {Mittal, Sankalp and V., Harikrishnan and Heetkumar, Patel and Tammana, Praveen},
title = {iGuard: Efficient Isolation Forest Design for Malicious Traffic Detection in Programmable Switches},
year = {2024},
isbn = {9798400711084},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
url = {https://doi.org/10.1145/3680121.3697807},
doi = {10.1145/3680121.3697807},
abstract = {Deploying machine learning (ML) models in programmable switch data planes facilitates low latency and high throughput traffic inference at line speed. However, data planes pose significant constraints due to the limited memory and minimal support for mathematical operations and data types. As a result, the only unsupervised ML models implemented in data planes to date are Isolation Forests (iForests). However, conventional iForest models yield suboptimal malicious traffic detection performance in various traffic use cases. To address this limitation, this paper proposes iGuard, the first iForest implementation that can accurately detect malicious traffic by incorporating the "knowledge" of more powerful autoencoders. We deploy iGuard in the form of a small set of whitelist rules that could be easily installed in the switch data planes. We implement iGuard using the P4 language, and assess its performance in an experimental platform based on Intel Tofino switches. Upon evaluating iGuard on various attack traffic use cases, our model can improve accuracy up to 48.3\% while maintaining a similar or lower switch memory footprint over previous approaches to implement iForest models in real-world equipment.},
booktitle = {Proceedings of the 20th International Conference on Emerging Networking EXperiments and Technologies},
pages = {55–64},
numpages = {10},
keywords = {intrusion/anomaly detection, machine learning, network security, programmable switches, software defined networking},
location = {Los Angeles, CA, USA},
series = {CoNEXT '24}
}
```
