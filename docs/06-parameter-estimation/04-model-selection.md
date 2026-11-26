# 모델 선택

M1, M2(단일 $\alpha$), M2 + 2단계 OER 기작([OER 미시동역학](../04-modeling/advanced-electrochem/03-oer-microkinetics.md))을 같은 데이터에 맞추고 AIC·BIC와 온도 홀드아웃 오차로 비교한다. 차이가 유의하지 않으면 기작을 하나로 정하지 않고, **이산 불확실성 요인**(두 기작에 각각 가중치)으로 넣는다.
