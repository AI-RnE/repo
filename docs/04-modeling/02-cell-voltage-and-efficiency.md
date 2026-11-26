# 셀 전압, 부하의존 효율, 출력→전류 역산

## M2 셀 전압식

$$V_{cell}(j,T,p)=E_{rev}(T,p)+\frac{RT}{\alpha_{an}F}\,\mathrm{asinh}\!\left(\frac{j}{2i_{0,an}(T)}\right)+\frac{RT}{\alpha_{ca}F}\,\mathrm{asinh}\!\left(\frac{j}{2i_{0,ca}(T)}\right)+j\,R_{ohm}(T,\lambda)+\eta_{conc}(j)$$

온도 의존성은 아레니우스 형태로 둔다. 이 형태 덕분에 [단계별 식별 절차](../06-parameter-estimation/02-identification-steps.md) S3에서 선형 회귀로 활성화 에너지를 구할 수 있다.

$$i_{0,an}(T)=i_{0,an}^{ref}\exp\!\left[-\frac{E_{exc}}{R}\left(\frac1T-\frac1{T_{ref}}\right)\right],\qquad R_{ohm}(T)=\frac{\delta_{mem}}{\sigma_{ref}}\exp\!\left[\frac{E_{pro}}{R}\left(\frac1T-\frac1{T_{ref}}\right)\right]$$

## 패러데이 효율과 부하의존 효율

저부하에서는 수소 크로스오버 비중이 커져 효율이 떨어지고, 고부하에서는 과전압이 커져 효율이 떨어진다. 이 두 효과가 정효율 가정이 놓치는 부분이다.

$$\eta_F(j)=1-\frac{2F\,N_{H_2}^{cross}}{j},\qquad \dot n_{H_2}=\eta_F\,\frac{jA}{2F},\qquad \eta_{sys}(P)=\eta_F(j)\,\frac{1.48\,\mathrm{V}}{V_{cell}(j)}$$

## 출력 → 전류 역산

재생에너지 출력 $P$가 주어지면 $P=N_{cell}\,A\,j\,V_{cell}(j)$를 $j$에 대해 푼다. $V_{cell}\cdot j$는 $j$에 대해 단조증가이므로 구간 $[0,j_{\max}]$에서 해가 하나뿐이고, Brent 법으로 안정적으로 풀린다. $P$가 정격을 넘으면 정격으로 자르고(출력제한), 최소부하 아래에서는 [상태 방정식](03-state-equations.md) 규칙을 따른다.
