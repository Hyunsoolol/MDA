#### Factor Analysis
##### 추정: 3가지 방법
1) Principal Component method
	- m개의 인자만 사용했을 때 오차의 상한은 사용하지 않은 eigenvalue's의 제곱합이다.
	  (m이p에 가까워지면 오차는 점점 커짐)
2) Principal factor method
	- Heywood cases, $\hat{\lambda}_{m}^{(t)}=0$
	- Ultra Heywood cases, $\hat{\lambda}_{m}^{(t)}<0$
		- 초기값 설정 오류
		- 인자 수(m)이 너무 클 때
		- 표본 크기 (n)이 너무 작을 때
3) Maximum likelihood method
	- 분포 가정 필요, $F_{i}\sim N_{m}(0,I_m)$ & $\epsilon_{i}\sim N(0,\Phi)$
	- $X-\mu=LF+\epsilon$
	- $X=LF+\epsilon+\mu$
	- uniqueness condition
