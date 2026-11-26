# 구간별 선형 근사

최적화에는 선형 함수가 다루기 쉬우므로 $f$를 구간 $P_0<P_1<\dots<P_n$에서 직선으로 근사한다.

$$H(P)\approx a_iP+b_i,\qquad a_i=\frac{H(P_{i+1})-H(P_i)}{P_{i+1}-P_i},\quad b_i=H(P_i)-a_iP_i$$

- 근사 오차: $E_{\max}=\max_P|f(P)-\hat f(P)|$, $E_{\mathrm{mean}}=\frac1n\sum|f(P_i)-\hat f(P_i)|$
- 구간 수에 따른 정확도와 계산량의 관계를 분석해 **필요한 최소 구간 수**를 정한다.
- 구간이 $f$의 볼록·오목 성질을 어떻게 보존하는지 확인한다. 최소 가동 전력, 가동/정지 조건이 있으면 이진변수가 필요한 MILP가 된다.
