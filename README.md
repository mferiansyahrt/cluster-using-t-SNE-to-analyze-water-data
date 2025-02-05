# t-SNE-Clustering

NOTES : <b>for a detailed explanation please refer to [tsne_clustering.ipynb](./tsne_clustering.ipynb)</b>. I have explained the details of the dataset, model, preprocessing, and results there. This section provides only a brief overview.

The dataset used on this project comes from [water_data](./CleanedUp_DataSet_Orbi.csv)

Clustering anomalies from water data based on t-SNE algorithm using t-SNE to group spesific cluster and performs dimensionality reduction, then use Gaussian Mixture to label each cluster.

Written in Python and uses the Scikit-Learn machine learning library.

This is unsupervised machine learning problem which purposed to see smaller clusters are identified as anomalies (Polluted water data).

The data is included on repo ("CleanedUp_DataSet_Orbi.csv"), with:
- Important Features start on first date column until the end of the column. Which "2021-11-29" column till "2022-09-02".
- "Ufid_1" and "Ufid_2" columns can be treated as index.

As written on the code, we use many class to label each cluster using Gaussian Mixture algorithm as shown below. 

<div align="center">
    <a href="./">
        <img src="./figure/clustered_data.png" width="79%"/>
    </a>
</div>

Also, in this project we test reproducibility on each run and check it by similiarity measure if t-SNE + Gaussian Mixture will produce same result if we run more than one time. Figure shown below is the second run.

<div align="center">
    <a href="./">
        <img src="./figure/clustered_data_2.png" width="79%"/>
    </a>
</div>

Then, calculate many datapoint on each cluster/label from each run, for the smaller one are identified as anomalies.

<div align="center">
    <a href="./">
        <img src="./figure/anom.png" width="79%"/>
    </a>
</div>

As we can see, the similarity results only identify cluster-20 and cluster-12, which approximately have the same value. This is a valid result because they come from different runs.

<div align="center">
    <a href="./">
        <img src="./figure/sim.png" width="60%"/>
    </a>
</div>
