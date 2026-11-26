# 수학적 모델링 개요

태양광 발전량의 불확실성이 수소 생산량으로 어떻게 전달되는지 수학적으로 다루는 부분이다. 핵심은 발전량을 **하나의 값이 아니라 확률분포**로 보고, 전기분해 장치의 **비선형 응답**을 통과시킨다는 점이다.

```
기상 W ─▶ 발전량 분포 P ─▶ 전류 I (비선형 방정식) ─▶ 수소 H = f(P) ─▶ 분포·구간 ─▶ 구간별 선형 근사 ─▶ MILP
```

## 문서 구성

| 문서 | 내용 |
|---|---|
| [`01`](01-probabilistic-forecast.md) | 발전량의 확률분포와 예측 오차 |
| [`02`](02-power-to-hydrogen-map.md) | $H=f(P)$ 도출: 비선형 방정식, 뉴턴–랩슨, 패러데이 |
| [`03`](03-sensitivity-error-propagation.md) | 민감도, 탄력성, 2차 오차 전파 |
| [`04`](04-distribution-transform.md) | 분포의 비선형 변환, 젠센 효과, 몬테카를로 |
| [`05`](05-prediction-intervals.md) | 예측 구간, Conformal Prediction |
| [`06`](06-piecewise-linear-approximation.md) | 구간별 선형 근사와 오차 |
| [`07`](07-optimization.md) | 운영 최적화 |
| [`08`](08-summary.md) | 핵심 4가지와 단계별 정리 |
