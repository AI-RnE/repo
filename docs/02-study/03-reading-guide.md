# 논문 읽기 가이드

| 자료 | 읽을 곳 | 얻는 것 |
|---|---|---|
| 기초개념정리 PPT (김성열) | 전체 | 전력수급 균형, 잉여전력, P2G 필요성, LSTM 개념. 입문 배경 |
| **PEMEL_modeling1** — Beainy 외 (2014), *Simulink Model for a PEM Electrolyzer Based on an Equivalent Electrical Circuit* | §III, Fig. 4 | 단일 PEM 셀의 등가회로. 정상상태 I–V 특성. 수소 생산률은 전류에 선형, 전력에 비선형(로그형) |
| **PEMEL_modeling2** — Albarghot 외 (2016), *MATLAB/Simulink Modeling and Experimental Results of a PEM Electrolyzer Powered by a Solar Panel* | §2.4, Fig. 5~7 | PEM과 대기압 수소탱크 연결. 저장량·압력 계산. 모델과 실험 모두 약 7.345 mL/(min·A) |
| **PEMEL_modelling3** — Espinosa-López 외 (2018), Renewable Energy 119 | §3(모델), §4(단계별 식별), Table 3 | 46 kW 고압 PEM의 반경험적 전기화학 모델 + 집중 열용량 동특성. 파라미터는 PSO로 식별. 셀 전압방정식과 소재 파라미터 참고 |
| 손영건·김성열 (2023), 전기학회논문지 72(11) | 전체 | 알칼라인 수전해 기반 P2G 연계 경제급전, 용량 시나리오 비교. MILP + C&CG. P2G 시스템 구성·최적화 참고 |
| 손영건·김성열 (2024), 전기학회논문지 73(1) | §2.4, §2.6, §3.4, Table 1 | 분산에너지 특별법과 IES 최적 계획. PEM·수소저장·비용·설비용량 계획 |

## 두 국문 논문의 요지

- **2023**: 재생에너지가 늘면 기존 경제급전(ED)에서 발전사업자(IPP)와 재생에너지 사업자(REP)가 손해를 볼 수 있다. ISO, IPP, REP 각자의 목표 이익을 정하고 P2G를 ED에 넣어 모두의 이익을 개선했다. CBP 시장 기준이며, 복잡해진 MILP는 C&CG로 풀었다. RES 용량이 클수록 성능이 좋아졌다. CBP 시장만 다룬 것이 한계다.
- **2024**: 지역 전력계통(LPS)에서 분산 재생에너지를 가상에너지관리시스템(VEMS)과 연계해, 가상 에너지 상쇄 거래로 지역 안 자원을 최적 배분한다. 이해관계자는 ISO, REP, EXA(에너지 교환 어그리게이터), 최종 사용자이고 각자의 목표 이익이 개선됐다.

## 읽을 때의 주의

- modeling3의 PSO는 모델 파라미터 식별에 쓰인다. 용량 최적화와 혼동하지 않는다.
- 2024년 논문 식 (8) 오타(상한/하한)에 유의한다.
