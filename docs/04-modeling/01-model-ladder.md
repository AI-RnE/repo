# 모델 사다리 M0~M3

모델은 네 단계로 쌓고, 각 단계는 이전 단계와 같은 시나리오에서 비교할 수 있게 한다. M0·M1은 비교 기준, M2가 본 모델, M3는 시간 결합 효과를 더한다.

| 단계 | 내용 | 근거 자료 |
|---|---|---|
| M0 정효율 | 수소 = $\eta P / \mathrm{HHV}$ (HHV 39.4 kWh/kg) | 2023·2024 국문 논문의 계획 모델 |
| M1 등가회로 | $V = e_{rev} + I R_i$ (선형) | Beainy 외(2014) §III |
| M2 반경험 전기화학 | 가역전압 + 활성화(asinh) + 옴 + 농도 손실, 패러데이 효율 | Espinosa-López 외(2018) §3 |
| M3 동적 | M2 + 열수지, 산소 쪽 분리기 물질수지, 막 박화, 탱크 | [막 열화](advanced-electrochem/01-membrane-degradation.md)·[기체 동역학](advanced-electrochem/02-gas-dynamics-safety.md), [통합 모델](advanced-electrochem/08-integrated-model.md) |
