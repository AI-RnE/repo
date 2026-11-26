# 참고 자료

## 입문·배경

- 김성열 (2026.10), *영재고 실습 기초 개념 정리*, 한양대학교 전기공학과 (PPT)
- 한국전력거래소, 계통 수용여유량 전망 / 산업통상자원부 (2021.6.30), 분산에너지 활성화 추진전략 (PPT 인용 출처)

## PEM 수전해 모델링

- Beainy, A., Karami, N., Moubayed, N. (2014). *Simulink Model for a PEM Electrolyzer Based on an Equivalent Electrical Circuit*. 2nd Renewable Energy for Developing Countries (REDEC 2014), Beirut. — `PEMEL_modeling1`
- Albarghot, M., Sasi, M., Rolland, L. (2016). *MATLAB/Simulink Modeling and Experimental Results of a PEM Electrolyzer Powered by a Solar Panel*. Journal of Energy and Power Engineering, 10, 779–785. — `PEMEL_modeling2`
- Espinosa-López, M. et al. (2018). *Modelling and experimental validation of a 46 kW PEM high pressure water electrolyzer*. Renewable Energy, 119, 160–173. — `PEMEL_modelling3`

## P2G 연계 계통 운영·계획

- 손영건·김성열 (2023). 재생에너지 수용률 향상 및 계통 안정화를 위한 P2G 연계형 경제급전 계획법. 전기학회논문지, 72(11), 1358–1365.
- 손영건·김성열 (2024). 분산 에너지 특별법 도입에 따른 통합 에너지 시스템의 최적 계획법. 전기학회논문지, 73(1), 16–25.

## 전기화학 심화 모델

- Bard, A. J., Faulkner, L. R. (2001). *Electrochemical Methods: Fundamentals and Applications*, 2nd ed. Wiley.
- Newman, J., Thomas-Alyea, K. E. (2004). *Electrochemical Systems*, 3rd ed. Wiley.
- Lasia, A. (2014). *Electrochemical Impedance Spectroscopy and its Applications*. Springer.
- de Levie, R. (1963). On porous electrodes in electrolyte solutions. Electrochimica Acta, 8, 751–780.
- Shinagawa, T., Garcia-Esparza, A. T., Takanabe, K. (2015). Insight on Tafel slopes from a microkinetic analysis of aqueous electrocatalysis for energy conversion. Scientific Reports, 5, 13801.
- Man, I. C. et al. (2011). Universality in oxygen evolution electrocatalysis on oxide surfaces. ChemCatChem, 3, 1159–1165.
- Cherevko, S. et al. (2016). Oxygen and hydrogen evolution reactions on Ru, RuO₂, Ir, and IrO₂ thin film electrodes in acidic and alkaline electrolytes: A comparative study on activity and stability. Catalysis Today, 262, 170–180.
- Schalenbach, M. et al. (2015). Gas permeation through Nafion. Part 1: Measurements. The Journal of Physical Chemistry C, 119, 25145–25155.
- Trinke, P. et al. (2017). Current density effect on hydrogen permeation in PEM water electrolyzers. International Journal of Hydrogen Energy, 42, 14355–14366.
- Wan, T. H., Saccoccio, M., Chen, C., Ciucci, F. (2015). Influence of the discretization methods on the distribution of relaxation times deconvolution: implementing radial basis functions with DRTtools. Electrochimica Acta, 184, 483–499.

> 전기화학 심화 모델 문서의 서지는 기억과 검색 기록을 바탕으로 적었으므로 제출 전 원문과 대조한다.

## 도구

scipy (`brentq`, `least_squares`, `solve_ivp`, `solve_bvp`, `stats.qmc`), emcee, SALib, impedance.py, pyDRTtools
