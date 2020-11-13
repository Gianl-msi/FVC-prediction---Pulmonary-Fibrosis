# FVC-prediction---Pulmonary-Fibrosis

### Table of Contents
- [Abstract](#Abstract)
- [Datasets](#Datasets)
- [Docs](#Docs)
- [Notebooks](#Notebooks)
- [Conclusions and Future Directions](#Conclusions-and-Future-Directions)

## Abstract

Respiratory failure is the 4th leading cause of death world-wide. After 30 years of age respiratory function declines, seemingly inexorably and exposure to cigarette smoke, infectious agents, atmospheric pollution and genetic predisposition are thought to play important roles in accelerating this process by impinging on the ability of stem and progenitor cells to repair the respiratory epithelium.

Pulmonary fibrosis is a chronic progressive lung disease characterized by scarring of the lung parenchyma. As the disease progresses, lung’s ability to oxygenate the blood decreases eventually leading to the death of the patient. Currently, there are no valid tools to predict the prognosis of patients with pulmonary fibrosis. 

The goal of this study was to develop a deep learning-based algorithm that, based on patient general information and chest CT images predicts how lung capacity will change over time. An ensemble approach was utilized in which chest images were processed through a convolutional network, while medical features of the patient were analyzed with a fully connected neural network. Numerous approaches were tested, and the best performing models employed transfer learning from the pretrained Vgg16 model. 

## Datasets
Dataset is available on Kaggle(https://www.kaggle.com/c/osic-pulmonary-fibrosis-progression)

## Docs
- [Final Report](https://github.com/Gianl-msi/FVC-prediction---Pulmonary-Fibrosis/blob/master/Lung%20capacity%20prediction%20in%20patients%20with%20pulmonary%20fibrosis%20-%20REPORT.pdf)
- [Slide Deck](https://github.com/Gianl-msi/FVC-prediction---Pulmonary-Fibrosis/blob/master/Lung%20capacity%20prediction%20in%20patients%20with%20pulmonary%20fibrosis%20-%20SLIDES.pdf)

## Notebooks
- [Data Wrangling, EDA, Modeling](https://github.com/Gianl-msi/FVC-prediction---Pulmonary-Fibrosis/blob/master/Data%20wrangling%20-%20EDA%20-%20Modeling%20-%20Lung%20Fibrosis.ipynb)

## Conclusions and Future Directions
Both patient medical information and chest CT images hold key insights for the prediction of future patient’s lung capacity. Out of all the approaches tested, transfer learning from the pretrained Vgg16 model is the winning approach. However, the model performs well when lung capacity decays linearly, but underperforms otherwise. In the clinical setting, one way to correct for this issue, is to utilize the last FVC measurement (or the average of last n measurements) as baseline value for the following predictions. This approach will allow the model to better adapt to unexpected drastic drops of the patient lung capacity. 

The model could be improved by including more information about the patient. For instance, there is no information on the pharmacological treatment (and when it was initiated), presence of comorbidities (such as diabetes, cardiovascular disease, other chronic diseases) and other general information (blood pressure, weight, body mass index). Furthermore, more images could help improving model performance. If the number of images is high enough, the whole 3D volume of the lung could be analyzed producing the most comprehensive strategy for this clinical problem. 

In conclusion, with a mean absolute percentage error ranging from 7.06% to 7.11% the transfer learning-based deep learning model produces a satisfying result. However, since the worst predictions are obtained for those patients with drastically drops in lung function, the implementation of this model should be carefully well-thought-out and should not substitute the assessment of the patient’s physician.  
