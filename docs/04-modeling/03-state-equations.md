# 상태 방정식 (M3)

$$C_{th}\frac{dT}{dt}=(V_{cell}-V_{tn})\,I-\frac{T-T_{amb}}{R_{th}}-\dot Q_{cool},\qquad V_{tn}=1.48\,\mathrm{V}$$

$$n_{gas}\frac{dx}{dt}=(1-\eta_{rec})N_{H_2}A-x\left(\frac{jA}{4F}+(1-\eta_{rec})N_{H_2}A\right),\qquad \frac{d\delta}{dt}=-c\,\frac{\varepsilon\,p_{H_2}}{\delta}$$

- **열**: 항온수조 실험에서는 $\dot Q_{cool}$로 $T$를 고정하고, E3에서만 자유 온도로 둔다.
- **분리기 수소 몰분율 $x$**: 최소부하 아래 운전 시 2 % 도달 시각을 이벤트로 잡는다. 즉시 차단 가정보다 생산 0 확률을 덜 과대평가한다.
- **막 두께 $\delta$** (실측 기상 백테스트에서는 하루 단위로 갱신한다. [`../07-numerics/05-measured-weather-backtest.md`](../07-numerics/05-measured-weather-backtest.md)): 하루 계산 안에서는 상수, 수명 시나리오(신품 178 µm / 수명 말기 125 µm)로 바꾼다.
- **탱크**: 저장량 = 초기량 + Σ(생산 − 수요), 용량 상한과 초기·종료 저장량 조건을 명시한다(Albarghot §2.4).
