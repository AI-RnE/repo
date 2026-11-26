# 연구 설계

## 연구 질문

정효율 가정 대신 **부하에 따라 효율이 달라지는 전해조 모델**을 쓰면, 기상 기반 확률 예측에서 나오는 수소 생산량의 **평균, 표준편차, 생산 0 확률**이 얼마나 달라지는가.

세부 질문 (원문에서 첫째·셋째 질문만 확인되어, 둘째는 문서 구성에 맞춰 정리한 것이다):

1. 정효율 가정은 수소 생산량 분포를 얼마나 왜곡하는가? (수학: 민감도·곡률·$E[f(P)]\ne f(E[P])$)
2. 기상 불확실성이 수소 생산량 불확실성으로 어떻게 전달되는가? 전기화학 파라미터, 기작 선택, 수명 시점은 얼마나 기여하는가? (Sobol 분산 분해)
3. 비선형 전기화학 모델을 최적화(MILP)에 넣을 수 있게 구간별로 근사하면 정확도와 계산량은 어떻게 교환되는가?

## 접근 전략

- **소형 PEM 셀 실험은 절차 검증용**이다. 실험실 셀의 파라미터 값을 30 bar 스택에 그대로 쓰지 않는다. 스택 값은 문헌 사전분포로 두고, 실험은 "이 절차로 파라미터를 얼마나 정확히 알 수 있는가"를 정량화한다.
- 검증된 절차로 얻은 **파라미터 사후분포**를 기준 스택(80 °C, 30 bar, Nafion 117) 모델에 넣어 수소 생산 분포를 계산한다.
- 정효율 모델(M0)은 같은 시나리오에 병렬로 돌려 차이를 비교한다.
- 개념이 어렵다는 이유가 아니라 **연구 질문의 답을 바꾸는지**를 직접 계산해 심화 항목의 채택 여부를 정한다([`04-modeling/advanced-electrochem/00-selection-criteria.md`](04-modeling/advanced-electrochem/00-selection-criteria.md)).

## 파이프라인

```
(1) 기상 예보 ──▶ 재생에너지 출력의 시간대별 확률분포·시나리오
(2) 출력 P ──▶ 전류밀도 j 역산        P = N_cell · A · j · V_cell(j)
(3) j ──▶ 전압·패러데이 효율 ──▶ 수소 생산률
(4) 열·분리기·막 상태의 시간 적분
(5) 시나리오별 수소 생산량 ──▶ 확률 최적화 입력 (MILP)
```

| 단계 | 문서 |
|---|---|
| (1) | [`07-numerics/02-forecast-and-scenarios.md`](07-numerics/02-forecast-and-scenarios.md), [`04-modeling/math/01-probabilistic-forecast.md`](04-modeling/math/01-probabilistic-forecast.md) |
| (2)(3) | [`04-modeling/02-cell-voltage-and-efficiency.md`](04-modeling/02-cell-voltage-and-efficiency.md) |
| (4) | [`04-modeling/03-state-equations.md`](04-modeling/03-state-equations.md) |
| (5) | [`08-optimization/01-milp-interface.md`](08-optimization/01-milp-interface.md) |

## 실험의 제약

실험은 포텐시오스탯 없이 **정전류 DC 전원**으로 한다. 분극곡선만으로는 옴 저항과 활성화 손실이 섞이므로, 전류 차단법으로 옴 저항을 따로 재고 저전류 측정점을 늘려 보완한다. 그래도 구별되지 않는 기작 차이는 **이산 불확실성 요인**으로 남긴다. 포텐시오스탯을 쓸 수 있으면 EIS·DRT로 분리한다([`04-modeling/advanced-electrochem/05-eis-drt.md`](04-modeling/advanced-electrochem/05-eis-drt.md)).

## 비교 모델 사다리

M0(정효율) → M1(등가회로) → M2(반경험 전기화학, 본 모델) → M3(동적). 같은 시나리오에서 단계별로 비교한다. 자세한 내용은 [`04-modeling/01-model-ladder.md`](04-modeling/01-model-ladder.md).

## 불확실성 요인

| 요인 | 종류 |
|---|---|
| 기상 | 연속 |
| 전기화학 파라미터 | 연속 (사후분포 표본) |
| 기작 선택 | 이산 |
| 수명 시점 | 시나리오 (신품 / 수명 말기) |
| BOP 소비전력 비율 (확장) | 연속 ([`04-modeling/04-balance-of-plant.md`](04-modeling/04-balance-of-plant.md)) |

## 입력 기상의 두 경로

| 경로 | 역할 |
|---|---|
| 가상 기상 분포(분위수 예측 + 코퓰러 시나리오) | 불확실성 요인 분해(Sobol), 확률 최적화 입력 |
| 실측 기상 시계열(검토 중, 시간축 확장) | 현실 확인, 막 열화 진행·계절 변동·탱크 용량 반영 |

자세한 설계는 [`07-numerics/05-measured-weather-backtest.md`](07-numerics/05-measured-weather-backtest.md).
