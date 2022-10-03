# Dimentionality-Reduction-on-MNIST-Dataset
The goal of this project was to test different Dimentionality Reduction techniques on MNIST dataset and evaluate their performances.
Four dimentionality Reduction Techniques were tested:
<ul>
<li>PCA</li>
<li>t-SNE</li>
<li>LLE</li>
<li>MDS</li>
</ul>
PCA was performed along with the Random Forest Classification Model.
The model performance actually dropped in accuracy as well as the computational time for random forest classification. Generally dimentionality reduction techniques are expected to decrease the computational time but in this it didnt happen that way. Perhaps with lesser features, Random forest tries to find the decision splits which become more convoluted and hence the algorithm is faced with higher comlexity and hence more computational times. Also we saw how image clarity was affected with PCA reduction so perhaps this could also be the reason in slight lower model accuracy.<br>

MDS Multi dimentional scaling is a locally dimentionality reduction technique, which preserves the distances between the data points. So in MNIST dataset, we can see that it seems to have worked pretty well for digit 1 and somewhat for digit 9 as well, however as by definition, its unable to really distinguish the individual difference in different digits. MDS model works best to find the similarities by calculating distances between the data pairs and hence we see that almost all data points are cluttered in the same spatial space. Probably not the best way to classify MNIST dataset. Or perhaps, a 3D visualization may help us to visualise the separate clusters for each digit. Also the processing time for MDS technique was the highest on the sample dataset i.e. 69.34s

LLE Locally Linear Embedding (LLE) is an unsupervised method for non-linear dimensionality reduction technique. It works best to discover non-linear structures in the data set, and also preserve the distances within local neighborhoods.In our 2D visualisation, it doesnt seem to be the best representation of the MNIST data classification. The data points are arranged in an upside V looking shape specially in the case of digits 1s and 2s. Perhaps the layout is suggesting how the handwritten imaging has some similarities matching a certain direction and the same digit perhaps tilted in other directions. Although its the shortest processing time in the dimentionality reduction technique but it has its limitations in being the best technique for MNIST dataset. One more reason is that LLE is an unsupervised method which assumes that data points are on or near a similar manifold and perhaps thats also a reason, we are unable to distinguish the individual classification of digits.

t-SNE T-distributed stochastic neighbor embedding (tSNE) seems to be the best dimentionality reduction technique for MNIST dataset.t-SNE is also a non-linear dimentionality reduction technique. One of the best attributes of t-SNE is that it preserves the local structure of the data and can choose to preserve the global structure as well, which is probably why we see a clear visualisation of each digit in clear/distinct clusters. When a given point is embedded to a point in low-dimensions (in our case in 2 dimensions), the actual distances between the given point and the points in its neighbourhood are somewhat similar to the distances that were in 784-dimensions. Also the processing time is reasonable enough. In visualisation of t-SNE, we can see that almost all digit clusters are also split in 2 groups which is probably how different images are tilted in a certain direction. For instance we can see a clear cluster for digit 1. Similarly digits with lower curve at bottom or top have certain similarities and seem to have multiple clusters spread around. Overall t-SNE showed the best classification for MNIST dataset.
