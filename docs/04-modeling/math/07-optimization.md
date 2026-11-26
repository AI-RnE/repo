# 운영 최적화

$$\max\sum_{t=1}^T H_t\quad\text{s.t.}\quad 0\le P_{\mathrm{ELZ},t}\le P_{\max},\;\; P_{\mathrm{ELZ},t}\le P_{\mathrm{PV},t},\;\; H_t\approx\hat f(P_{\mathrm{ELZ},t})$$

저장탱크를 포함하면 질량 보존식을 추가한다.

$$S_t=S_{t-1}+H_{\mathrm{prod},t}-H_{\mathrm{demand},t},\qquad 0\le S_t\le S_{\max}$$

최소 작동 전력, 가동 여부, 시동·정지 조건은 추가 제약으로 넣는다.
