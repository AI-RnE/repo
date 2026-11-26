# 발전량과 수소 생산량의 관계 H = f(P)

기존 모델은 효율을 상수로 둔다.

$$H=\frac{\eta P}{\mathrm{HHV}_{H_2}}$$

이 연구는 효율을 전류·전압·온도의 함수로 두고 전압–전류 관계에서 출발한다.

$$V(I)=E_{\mathrm{rev}}+\eta_{\mathrm{act}}(I)+\eta_{\mathrm{ohm}}(I)+\eta_{\mathrm{other}}(I),\qquad P=N_{\mathrm{cell}}\,V(I)\,I$$

1. **전류 구하기**: 주어진 $P$에 대해 $g(I)=N_{\mathrm{cell}}V(I)I-P=0$을 푼다. 비선형이라 뉴턴–랩슨법을 쓴다.

$$I_{n+1}=I_n-\frac{N_{\mathrm{cell}}V(I_n)I_n-P}{N_{\mathrm{cell}}\left[V(I_n)+I_nV'(I_n)\right]}$$

2. **수소 생산량**: 패러데이 법칙으로 전류를 몰 생산 속도로 바꾼다.

$$\dot n_{H_2}=\frac{N_{\mathrm{cell}}\,\eta_F\,I}{2F}$$

3. 결과적으로 $H=f(P)$는 단순 비례가 아닌 **비선형 함수**다. $V(I)$의 구체적인 항은 선택한 전해조 모델에 따라 달라진다([심화 모델](../advanced-electrochem/00-selection-criteria.md) 참고).
