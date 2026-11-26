# OER 미시동역학과 타펠 기울기 전이

## 문제

M2의 asinh 식은 전달계수 하나로 모든 전류 구간을 표현한다. 실제 OER은 여러 단계의 양성자–전자 결합 반응이며, 율속 단계 앞의 중간체 **피복률**이 전위에 따라 변하면서 타펠 기울기가 바뀐다.

## 2단계 기작

첫 단계가 빠른 평형이고 두 번째 단계가 율속인 기작:

$$\mathrm{S}+\mathrm{H_2O}\rightleftharpoons \mathrm{S\text{-}OH}+\mathrm{H^+}+e^-\ (\text{평형},\,K_1),\qquad \mathrm{S\text{-}OH}\to \mathrm{S\text{-}O}+\mathrm{H^+}+e^-\ (\text{율속},\,k_2)$$

$$j=2F\,k_2\,\theta_{OH}\,e^{\beta f\eta},\qquad \theta_{OH}=\frac{K_1e^{f\eta}}{1+K_1e^{f\eta}},\qquad f=\frac FRT$$

## 타펠 기울기 전이

| 영역 | 피복률 | 타펠 기울기 | 80 °C 값 |
|---|---|---|---|
| 저과전압 | 작음 | $2.303RT/((1+\beta)F)$ | 약 47 mV/dec |
| 고과전압 | 1에 가까움 | $2.303RT/(\beta F)$ | 약 140 mV/dec |

($\beta=0.5$일 때 $2.303RT/F\approx70$ mV로 위 값이 나온다.)

## 결과

이 기작을 0.2~1.0 A/cm² 구간의 기준 분극곡선에 맞추면, 전이 과전압 가정(0.2~0.4 V)에 따라 2 A/cm²의 과전압이 기준 모델보다 **최대 45 mV 높게 외삽**되었다.

| 지표 | 단일 전달계수 모델 | 2단계 기작 |
|---|---|---|
| 정격 효율 | 78.2 % | 76.4 % |
| 흐린 날 평균 왜곡 | −6.5 % | −9.2 % |

## 의미

- 기작 선택 자체가 **불확실성의 원천**이다. 중간 전류 자료만으로는 기작을 정할 수 없고, 고부하·저부하로 외삽할 때 차이가 커진다.
- 따라서 기작(단일 전달계수 모델, 2단계 기작)을 **이산 불확실성 요인**으로 두고 분산 분해에 포함한다([`../../07-numerics/03-uncertainty-propagation.md`](../../07-numerics/03-uncertainty-propagation.md)).
- 모델 선택은 AIC·BIC와 온도 홀드아웃으로 한다([`../../06-parameter-estimation/04-model-selection.md`](../../06-parameter-estimation/04-model-selection.md)).

## 보충 이론: 이론적 최소 과전압

계산 수소 전극 모형에서 \*OOH와 \*OH 흡착 자유에너지의 차이가 산화물 표면에 관계없이 약 3.2 eV로 거의 일정하다는 **척도 관계**(Man 등, 2011)가 있다. 이상적인 촉매라면 이 차이가 2.46 eV(= 2 × 1.23 V)여야 하는데 3.2 eV에 묶여 있으므로, OER에는 **이론적 최소 과전압**이 존재한다.

$$\eta_{\min}\approx\frac{3.2\ \mathrm{eV}}{2e}-1.23\ \mathrm V\approx0.37\ \mathrm V$$
