#### 08. PCA
##### Principal component analysis
- 정의
- 방법
- (증명) Spectral decopmposition 관계
- (증명) 공분산, 분산합
- (증명) 상관관계

#### Sample PCA
- 정의
- 방법 (sigular value decomposition)

#### Selection of the number of PCs
- 3가지 방법

##### Remark
- Correlation PCA
- PCA in high-dimension

##### Canonical correlation analysis
- 정의

#### 09. Factor analysis
##### Methods of estimation
1) Principal Component method
	- m개의 인자만 사용했을 때 오차의 상한은 사용하지 않은 eigenvalue's의 제곱합이다.
	  (m이p에 가까워지면 오차는 점점 커짐)
2) Principal factor method
	- Heywood cases, $\hat{\lambda}_{m}^{(t)}=0$
	- Ultra Heywood cases, $\hat{\lambda}_{m}^{(t)}<0$
		- 초기값 설정 오류
		- 인자 수(m)가 너무 클 때
		- 표본 크기(n)가 너무 작을 때
3) Maximum likelihood method
	- 분포 가정 필요, $F_{i}\sim N_{m}(0,I_m)$ & $\epsilon_{i}\sim N(0,\Phi)$
	- uniqueness condition, $L_1=L_2(L_1P)$ up to sign of their columns.
	- Standardized variable case
	- Large sample test

##### Factor ratation
- Effect of rotation
	- Mean and variance of factors
	- Communalities: unchanged
	- Variance explained by the $k$-th factor: changed
- Determine the **optimal** factor rotation
	- L의 각 열이 최대한 sparse 하도록, variation 확인
	  -> L의 각 열 성분에서 큰 것을 더 크게, 작은 것을 더 작게 만들도록 유도.
	- (normal) Varimax method: $\sum_{j=1}^{m}\hat{Var}(\tilde{\ell}_{\dot,j}^{*2})$를 최대화하는 원리

##### Factor scores
- $\hat{F_i}$가 관심이 대상이며, 1) 모형 진단(모형 가정 확인), 2) 다음 분석의 자료로서 활용
1) Weighted least square method
	- 분포 가정 없음
	* $\hat{F}=(L^T\Phi^{-1}L)^{-1}L^T\Phi^{-1}(X-\mu)$
		* ML method: $\hat{F_{j}}=\hat{\Delta}^{-1}L^T\Phi^{-1}(X_{j}-\bar{X})$, $L^T\Phi^{-1}L=\Delta$
		* PC method: $\hat{F_{j}}=(\hat{L}^{T}\hat{L})^{-1}\hat{L}(X_{j}-\bar{X})$, $\Phi=I_{p}$, $$\hat{F_{jk}}=\frac{\hat{u_k}^{T}(X_j-\bar{X})}{\sqrt{\hat{\lambda_{k}}}}$$
			* sample mean of factors scores is 0, covariance of factors scores is $I_m$
2) Regression method
	- 분포 가정 필요: $F$ and $\epsilon$ are jointly normal distribution.
	- the conditional distribution of F given X is  $$F|X \sim N_m(L^{T}(LL^T+\Phi)^{-1}(X-\mu),I_m-L^T(LL^T+\Phi)^{-1}L).$$
	- $E(F|X)=L^T(LL^T+\Phi)^{-1}(X-\mu)$
	- $\hat{F_j}=\hat{L}^T(\hat{L}\hat{L}^T+\hat{\Phi})^{-1}(X_j-\bar{X})$, $(\hat{L}\hat{L}^T+\hat{\Phi})^{-1}=\hat\Sigma^{-1}$, $$\hat{F_j}=\hat{L}^TS^{-1}(X_j-\bar{X}).$$
- Remark
	- $\hat{F_{j}^{R}}=(I_m+(L^T\Phi^{-1}L)^{-1})^{-1}\hat{F_{j}^{LS}}$, $L^T(LL^T+\Phi)^{-1}=(I_m+L^T\Phi^{-1}L)^{-1}L^T\Phi^{-1}$
	  -> $\Delta$가 큰 값이면 $\hat{F_{j}^{R}}$가 ${F_{j}^{LS}}$에 근사하게 됨


#### 11. Discrimination and Classification
##### 0-1 Loss and Bayes decision rule
- 정의
	- $I(Y \neq \phi(X))$: 분류기 (loss)
	- $E(Y \neq \phi(X))=P(Y \neq \phi(X))$: risk(loss의 기대값)
	- $\phi_{Bayes}(x)=\arg_{k=1,2,\ldots,K}\max P(Y=k|X=x)$
- Bayes Rule Classifier: Gaussian Example
$$\hat\delta_k(x)=b_{0k}+b^T_{k}x+x^TC_{k}x$$
- Linear Discriminant Analysis
- Quadratic Discriminant Analysis

##### Assessment of classifiers
- training and testing sets
- Validation
	- K-fold Cross Validation
	- Leave-One-Out Cross Validation
	- misclassification rate if biased
	- Larger K means less biased estimate.
	- Larger K means more variance. (cov is added)

#### 12. Clustering
##### Dissimilarity and within-cluster scatter

##### Combinatorial algorithm
- $W(c)$를 작게하는 cluster 함수를 찾고자 함
- 경우의 수는 약 $\frac{K^n}{K!}$으로 너무 크기 때문에 이상적인 알고리즘임

##### $K$-means algorithm
- motivation
	- $W(c)$를 변형 후 작게 만들어주는 함수를 찾는 것
- Process
- 자료 값이 필요

##### $K$-medoids algorithm
- 개별 자료 값이 필요 없고, 자료 간 거리(비유사성 측도)만 있으면 됌
- 다만, 군집의 중심은 n개의 자료 중 하나가 되어야 함
- Process

##### Hierarchical clustering
- one unique solution
- K를 선택할 필요가 없음
- 연속적인 클러스터 분화 과정을 볼 수 있음
- Linkage
	- Single linkage
	- Complete linkage
	- Average linkage
- Process
##### Cluster index
- K가 커지면 지수가 좋게 될 수 밖에 없음
##### Scatter decomposition
- K가 커지면 지수가 좋게 될 수 밖에 없음
##### CH(Calinski-Harabasz) Index
- K에 대한 패널티가 부여된 index

