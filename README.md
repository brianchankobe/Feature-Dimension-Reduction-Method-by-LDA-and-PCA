# Feature-Dimension-Reduction-Method-by-LDA-and-PCA
Implementation of dimensionality reduction by LDA and PCA.

# Idea of LDA  
A supervised approach as it takes class label (类标签) to do the classification.  LDA can help dataset to find the boundary between clusters of classes by projecting data points in dataset (不同样本) 
onto a line so that it can be separated as possible.

How to determine the clusters？
  1. Find the centroid of each class datapoints
  
 Criteria: 
	1. Maximize the distance between centroid of each class
  2. Minimize the variance within the data point of each class (Covariance)

Example:
**N_components: LDA其中一个参数，定义降维后的维度。通常<= min(number of classes-1, number of features)**
from sklearn.discriminant_analysis import LinearDiscriminantAnalysis as LDA
lda = LDA(n_components=1)

# Idea of PCA
PCA is unsupervised linear dimensionality reduction approach by extracting information from high-dimensional space via projecting it into low-dimensional subspace.
It is a statistical approach to use orthogonal transformation to convert a set of observations of possibly correlated variables (一些有不同数值的特征) into a set of linearly uncorrelated variables (Principle components)

How to use PCA:
	1. 创建class时，参数可以定义主成分数量
	2. Fit()： 拟合数据集
  3. Transform(): 将原数据集或其他数据集投射到一个子空间（一个特定维度）
  
Example:
from sklearn.decomposition import PCA
pca = PCA(n_components=2, random_state=42)
pca.fit(X_train_uncorr)

# Input File
CSV file Format:
row-instance(observation vector) column-attribute(feature vector)

# LDA VS PCA
	1. 主成分数量（降维后的维度）
		a. LDA: 根据数据集的类标签数和特征数判定
    b. PCA：根据数据集的特征数和样本数来判定

# Common
	1. 降维后，训练速度快
  2. 准确率 < 完整数据集训练后 和 移除相关特征后
