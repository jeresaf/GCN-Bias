# GCN-bias

## Mitigating gender bias in occupation classification of job biographies with graph convolutional network

We use adapt the textGCN by Yao et al. (2018) https://github.com/yao8839836/text_gcn to classify job biographies from the https://github.com/Microsoft/biosbias dataset. We investigate the mitigation of gender bias by comparing the predictions of our trained model for the original test dataset and for a transformation of our test dataset where explicit gender indicators are removed or "scrubbed" in line with De-Arteaga et al. (2019).

Download data at https://drive.google.com/drive/folders/1h2oILArbrTsdN5VrdhWAKpzppwOXtyZO?usp=sharing .

Note that this is only a demo and does not include the training of our textGCN or the predictions for the "scrubbed" test dataset.

1. Imports
    - import packages <br>
2. Data
    - define directory path<br>
    - read raw data csv files into pandas for both original and reduced datasets from directory<br>
    - create summary statistic table with length of training and test sets and number of occupation labels<br>
    - create occupation frequency chart for original data set<br>
3. Utility Functions
    - define some utility functions<br>
4. Graphs
    - clean original test dataset by removing words that are not included in the training vocabulary<br>
    - build feature vectors and one hot labels for original test data<br>
    - load feature vectors, one hot labels and adjacency matrix for original training data from directory<br>
5. Model
    - define initialisation functions<br>
    - define layers<br>
    - define training metrics<br>
    - define model<br>
6. Prediction
    - load GCN trained with original dataset with gender indicators<br>
    - predict occupation labels for original dataset<br>
7. Analyses
    - calculate TPR, TPR gender gap and <img src="https://render.githubusercontent.com/render/math?math=\pi_{g,y}"> for the gender "female"<br>
    - plot for <img src="https://render.githubusercontent.com/render/math?math=\text{Gap}_{female,y}"> and <img src="https://render.githubusercontent.com/render/math?math=\pi_{female,y}"> and compute correlation <br>
    - compute gender imbalance and compounding factor<br>
    - load predictions on scrubbed test dataset<br>
    - TPR, TPR gender gap and correlation between TPR gender gap and <img src="https://render.githubusercontent.com/render/math?math=\pi_{female,y}"> on scrubbed dataset<br>
    - plot of <img src="https://render.githubusercontent.com/render/math?math=\text{Gap}_{female,y}"> and <img src="https://render.githubusercontent.com/render/math?math=\pi_{female,y}"> for original compared to scrubbed test dataset<br>
    - proportion of compounding factors pulled towards 1 after scrubbing
