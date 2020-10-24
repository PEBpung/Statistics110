---
layout: post
title: "[Statistics 110] 10강 - 기댓값 (Expectation Continued)"
subtitle : 기대값
tags: [Statistics]
author: Kimin Park
use_math: true
comments : True
---

# 10강- 기댓값 (Expectation Continued)

- **키워드**
    - `선형성`
    - `음이항분포(negative binomial)`
    - `First Success 분포`

## 기대값의 선형성 증명 (Linearity)

T = X + Y라고 할 때, 아래와 같은 식이 성립해야 선형성이 증명된다.

![/assets/img/2020-10-13-statistics/Untitled.png](/assets/img/2020-10-13-statistics/Untitled.png)

![2020-10-13-statistics%208e50fe9c6da8465ab9ddd301f1088930/Untitled%201.png](/assets/img/2020-10-13-statistics/Untitled%201.png)

평균을 구하는 방법은 i) 그룹으로 묶어서 가중평균을 구하는 방법과, ii) 전부 더해서 나누는 방법이 있다.

![2020-10-13-statistics%208e50fe9c6da8465ab9ddd301f1088930/Untitled%202.png](/assets/img/2020-10-13-statistics/Untitled%202.png)

이와 같은 방법으로 E(X+Y)를 구하면 E(X)+E(Y)가 나온다.

![2020-10-13-statistics%208e50fe9c6da8465ab9ddd301f1088930/Untitled%203.png](/assets/img/2020-10-13-statistics/Untitled%203.png)

E(cX)에서 c는 상수이므로 시그마 밖으로 빼면 cE(X)가 된다.

![2020-10-13-statistics%208e50fe9c6da8465ab9ddd301f1088930/Untitled%204.png](/assets/img/2020-10-13-statistics/Untitled%204.png)

위의 증명은 왜 X와 Y가 종속적이어도 사실인지 설명하는 데 도움이 된다.

**가장 극단적인 상황**: X = YX=Y 이라는 극단적인 종속 상황에서도 성립하기 때문이다.

![2020-10-13-statistics%208e50fe9c6da8465ab9ddd301f1088930/Untitled%205.png](/assets/img/2020-10-13-statistics/Untitled%205.png)

## 음이항분포 (Negative Binomial): X~NegBin(r, p)

- **음이항 분포**

    이름에 속지 말자 음수도 아니고 이항도 아니다. 기하분포의 일반화이다.

    **정의:** 여러 번의 베르누이 독립 시행에서 r번째 성공까지의 실패 횟수

    (기하분포는 음이항분포에서 r=1인 경우를 말한다)

    r=5 일 때의 예시를 들어보자.

    ![2020-10-13-statistics%208e50fe9c6da8465ab9ddd301f1088930/Untitled%206.png](/assets/img/2020-10-13-statistics/Untitled%206.png)

    5번째 성공 이전 4번의 성공은 $_{n+r-1}\mathrm{C}_{r-1}$가지로 존재할 수 있다.

    즉, **PMF**를 구해보면

    ![2020-10-13-statistics%208e50fe9c6da8465ab9ddd301f1088930/Untitled%207.png](/assets/img/2020-10-13-statistics/Untitled%207.png)

- **음이항분포의 기대값**

    지시확률변수 $X_j$를 j-1번째 성공과 j번째 성공 사이의 실패 횟수라고 하면, X~Geom(p)

    전체 실패 횟수를 X=X1+...+Xr로 나타낼 수 있다.

    ![2020-10-13-statistics%208e50fe9c6da8465ab9ddd301f1088930/Untitled%208.png](/assets/img/2020-10-13-statistics/Untitled%208.png)

## 상트페테르부르크의 역설(St. Petersburg Paradox)

- **문제:** 처음으로 동전 앞면이 나올 때까지 동전을 던진 횟수(성공 포함)를 X라고 하였을 때, $2^X$달러를 받는 게임이 있다고 하자. 이 게임을 하기 위해 얼마를 내야 합당한 가격이라고 볼 수 있는가?

    ![2020-10-13-statistics%208e50fe9c6da8465ab9ddd301f1088930/Untitled%209.png](/assets/img/2020-10-13-statistics/Untitled%209.png)

- 컴퓨터 모의실험

    ![2020-10-13-statistics%208e50fe9c6da8465ab9ddd301f1088930/Untitled%2010.png](/assets/img/2020-10-13-statistics/Untitled%2010.png)

    - 여기서 연속 평균은 게임 마다 $2^k$의 평균값
