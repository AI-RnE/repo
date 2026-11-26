# 태양광 발전량의 확률적 예측

- 발전량을 확률변수로 두고 기상 조건에 따른 분포를 분석한다: $P \sim f_P(p \mid W)$
- 맑은 날, 구름 변동이 있는 날, 흐린 날의 분포를 비교한다. 평균이 비슷해도 구름 변동이 크면 분산이 더 크다. 평균 $E[P]$와 분산 $\mathrm{Var}(P)$로 불확실성을 정량화한다.
- 예측 오차는 MAE, RMSE로 보고, 기상 조건에 따라 오차 특성이 어떻게 달라지는지 분석한다.

$$\mathrm{MAE}=\frac1n\sum_{i=1}^n|P_i-\hat P_i|,\qquad \mathrm{RMSE}=\sqrt{\frac1n\sum_{i=1}^n(P_i-\hat P_i)^2}$$
