# TIL(20.06.02)

- 빨강/초록 공을 분류하는 문제(Binary classification problem)
  - "이 공이 초록색일 확률은 얼마나 되나?"
    - 예측 확률값이 높을경우(이 공은 초록색이다)
    - 예측 확률값이 낮을경우(이 공은 초록색이 아니다==이 공은 빨간색이다)

### Loss Function : Binary Cross-Entropy/Log Loss

![binary_cross_entropy](/TIL/img/200602/binary_cross_entropy.PNG)

- **y**: 초록/빨강을 나타내는 label(초록=1,빨강=0)
- **p(y)**: 초록색일 확률을 나타내는 확률값
- **N**: 전체 샘플의 수
- $log(p(y))$: 초록공에 대한 로그확률 값
- $log(1-p(y))$: 빨간공에 대한 로그확률 값
  - log probability 사용이유? : [위키피디아][https://en.wikipedia.org/wiki/Log_probability]
  - ![minus_logpx](/TIL/img/200602/minus_logpx.PNG)
  - $$P(x)$$가 1에 가까울수록 $$-log(p(x))$$값은 0에 가까워진다

### Entropy

- 정보량 $$H=nlog(s)=log(s^n)$$
  - $$n$$은 보내는 문자열의 문자 개수, $$s$$는 각 선택에서 가능한 결과의 가지수
  - 예) 알파벳 6글자를 보낼때, 한 글자를 0 또는 1로 표현해 보내야한다. 이럴경우 최선의 질문 전략은 보내려는 글자 하나를 알파벳 앞쪽 절반(1)에 속하는지 뒷쪽 절반(0)에 속하는지 묻는것. 이 방법을 반복하면 4~5번만에 한 글자를 표현할수있다.
  - $$2^{질문개수}=26$$  따라서 $$질문개수=log_226$$
- Shannon entropy
  - 이산확률 분포일때 '가능한 결과의 수'는 그 사건 발생확률의 역수
  - $$H=\sum(사건발생확률)\cdot log_2(\frac{1}{사건발생확률})\\\;\;\;=\sum_ip_ilog_2(\frac{1}{p_i})\\\;\;\;=-\sum_ip_ilog_2(p_i)$$

