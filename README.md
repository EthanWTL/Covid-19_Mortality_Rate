# ICU Needs Classification with COVID-19 Dataset by Decentralized Machine Learning Approach.
![Contributors](https://img.shields.io/github/contributors/EthanWTL/HeartDiseasePakula?style=plastic)
![Forks](https://img.shields.io/github/forks/EthanWTL/HeartDiseasePakula)
![Stars](https://img.shields.io/github/stars/EthanWTL/HeartDiseasePakula)
![Licence](https://img.shields.io/github/license/EthanWTL/HeartDiseasePakula)
![Issues](https://img.shields.io/github/issues/EthanWTL/HeartDiseasePakula)

## Description

Welcome! 😀

We are dedicated data scientists working with [Pakula BioMedical Fellowship Program](https://www.beloit.edu/academics/biology/resources-opportunities/summer-research/) for summer research! 

It has a focus on implementing Federated Learning on [UCI Heart Disease dataset](https://archive.ics.uci.edu/dataset/45/heart+disease) to help early stage detection of cardiovasular diseases.

---





## Stage I: Baseline Modeling

To create a baseline understanding of the project as well as testing our data cleaning accuracy, we delpoyed a set of traditional machine learning technique, the results for Cleveland datasets are shown as following.

| ML Technique  | Cleveland Accuracy  | Other Research's Accuracy  |
| ------------- | ------------- | ------------------------ |
| Decision Tree  | 79.00%  | 83.57%  [Shrinivas D Desai et al.](https://link.springer.com/chapter/10.1007/978-981-13-0680-8_13)  |
| Random Forest  | 84.37%  |  86.90% [Pal and Parija](https://link.springer.com/chapter/10.1007/978-981-99-0412-9_11)  |
| SVM | 86.89%  |   77.70%    [Anitha S., Sridevi N.](https://hal.science/hal-02196156/)  |
| Bayesian Classifier  | 82.26%  |   86.60%      [Anitha S., Sridevi N.](https://hal.science/hal-02196156/)  |


The table below presents the comprehensive results for our baseline models.
|  | Combined  | Cleveland | Long Beach | Hungary | Switzerland |
| --- | --- | --- | --- | --- | --- | 
| Decision Tree | 80% | 79%  | 68% |85%| 89%|
| Random Forest | 85% | 84%  | 83% |91%| 92%|
| SVM | 86% | 86% | 82% |84%| 95%|
| Bayesian Classifier | 83% | 82%  | 80% |43%| 57%|
| ANN | 85% | 84%  | 82% |85%| 95%|
| CNN | 85% | 79%  | 82% |87%| 95%|
| RNN | 80% | 79%  | 77% |85%| 92%|



## Stage II: Federated Learning
### Getting started with FL
* Download the [MNIST data set from Kaggle](https://www.kaggle.com/datasets/scolianni/mnistasjpg)
* Run the Python files
  ```sh
   python FL_demo/run_federated_learning.py
   ```
* Global Model Accuracy: ```80.20%```
* Check out [Flower](https://github.com/adap/flower) with more detailed explanation about FL.

### Our FL pipeline:
```mermaid
graph TB
    A{Global Model} <-- weights_transfer --> B[Cleveland_model]
    A{Global Model} <-- weights_transfer --> C[Virginia_model]
    A{Global Model} <-- weights_transfer --> D[Hungarian_model]
    A{Global Model} <-- weights_transfer --> E[Switzerland_model]

    B -- training --> F((Cleveland_data))
    C -- training --> G((Virginia_data))
    D -- training --> H((Hungarian_data))
    E -- training --> I((Switerland_data))

    F -- update_model --> J(Cleveland_model_updated)
    G -- update_model --> K(Virginia_model_updated)
    H -- update_model --> L(Hungarian_model_updated)
    I -- update_model --> M(Switzerland_model_updated)

```
### Results:
* ```Learning rate```: 0.01
* ```Optimizer```: SGD
* ```Loss function```: Sparse Cross Entropy
* Result after 100 ```global epochs```:

  |Model| Combined  | Cleveland | Long Beach | Hungary | Switzerland |
  |--------|--------|--------|--------|--------|--------|
  |ANN-FL|84%|82%|80%|85%|92%|
  |CNN-FL|85%|87%|78%|87%|89%|
  |RNN-FL|83%|79%|80%|85%|95%|


---



## Analysis & Comparison

![image](https://github.com/EthanWTL/HeartDiseasePakula/assets/97998419/177720dd-3293-4bbd-91c7-f37804695174)


![image](https://github.com/EthanWTL/HeartDiseasePakula/assets/97998419/078ee836-76f1-4ff5-b4b3-d21e1c072209)


![ROC curves FL](https://github.com/EthanWTL/HeartDiseasePakula/assets/97998419/98d2ceb8-bbfe-4770-953b-f77964fa77e6)


## Roadmap
- [x] Implement Baseline experiment
- [x] Federated Learning
  - [x] MLP
  - [x] CNN
  - [x] RNN
- [ ] Tranfer Learning





## Contact
Ethan Wang - [e13wang@gmail.com](e13wang@gmail.com) - [Linkedin Profile](https://www.linkedin.com/in/ethan-wang-938588175/)

Takeshi Matsuda - [takeshimatsuda27@gmail.com](takeshimatsuda27@gmail.com) - [Linkedin Profile](https://www.linkedin.com/in/takeshi-matsuda-41777b1ab/)

Project Link: [https://github.com/matsudatakeshi27/HeartDiseasePakula](https://github.com/matsudatakeshi27/HeartDiseasePakula)




## Acknowledgments:
* [Back-Propagation Neural Network Versus Logistic Regression in Heart Disease Classification](https://link.springer.com/chapter/10.1007/978-981-13-0680-8_13)
* [Heart Disease Risk Prediction Using Supervised Machine Learning Algorithms](https://link.springer.com/chapter/10.1007/978-981-99-0412-9_11)
* [HEART DISEASE PREDICTION USING DATA MINING TECHNIQUES](https://hal.science/hal-02196156/)
* [A Submodularity-based Agglomerative Clustering Algorithm for the Privacy Funnel](https://www.semanticscholar.org/paper/A-Submodularity-based-Agglomerative-Clustering-for-Ding-Sadeghi/4e7b3b31659c945ed0c953da9fe7af297b3f3675)
* [Early detection of silent ischaemic heart disease by 24-hour electrocardiographic monitoring of active subjects.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC458846/)
* [Development of a federated learning approach to predict acute kidney injury in adult hospitalized patients with COVID-19 in New York City](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8328073/)
* [Federated learning for multi-center imaging diagnostics: a simulation study in cardiovascular disease](https://www.nature.com/articles/s41598-022-07186-4)
