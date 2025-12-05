
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
