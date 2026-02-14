# Lab 5: K-Means Clustering on Facial Images

## Aim
The aim of this lab is to explore basic feature extraction and unsupervised machine learning using KMeans clustering. More specifically, the goal is to extract colour-based features (hue and saturation) from a dataset of facial images (of the Plaksha faculty), group them into clusters, and finally classify a new, unseen image (of Dr. Sashi Tharoor) by projecting it in the established feature space. 

## Methadology

1. **Face Detection** -- This is done using the Haar-cascades dataset (built into the OpenCV toolkit).
2. **Fearture Extraction** -- Extracted images were converted from BGR to the HSV (Hue Saturation Value) colourspace. The features extracted were the **mean hue** and the **mean saturation** of each face.
3. **Clustering** -- was done with the KMeans clustering algorithm with a value of $K = 2$. The results of this clustering, along with the two cluster centroids have been visualized ina diagram in the following section.
4. ** Template Matching ** -- A template image was processed using the same pipeline and assigned to the cluster to the centroid of which it was clostest to.

## Results

![KMeans Scatttering](Results/clustering.png)

* **Cluster Representation:** The K-Means algorithm successfully split the dataset into two clusters. However, because the feature space relies purely on average color, the clusters do not represent distinct human identities or any facial characteristics. Instead, they represent lighting conditions and skin/background color tones.

* **Template Classification:** The Dr. Shashi Tharoor image was plotted as a purple dot on the scatter plot for easier visualization. The model calculated its Euclidean distance to both centroids and successfully assigned it to **Cluster 1** (the blue cluster).

![KMeans Template Point](Results/new_point.png)

## Conclusions

This lab sucessfully demonstrates the mechanics of the KMeans algorithm and its use in unsupervised learning, and the concept of feature  extraction and feature space projection. It is also evident that Mean Hue and Mean Saturation are insufficient features for facial recognition (not to mention that these features are subject to external conditions such as lighting).

While the algorithm executed mathematically perfectly, it failed to produce a meaningful or practical machine learning model.