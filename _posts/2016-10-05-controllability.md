---
layout: post
title: "Controllability"
categories: 수학
tags: Linear-algebra
date: 2016-10-05 10:00:00
excerpt: "Controllable, Reachable."
---

controllability 혹은 reachability란 어떤 system에 입력을 가해서 초기 state x0로 부터 터미널 state xf 로 보낼 수 있는지에 대한 것이다.  

System의 dynamic equation으로부터 state transition matrix를 얻을 수 있는데, 보통 controllability (reachability)의 증명은 이 state transition의 관계식으로부터 시작된다.

예를들어 Linear system의 경우 dynamic equation은 아래와 같이 나타낸다.
 
$$
\\dot{x}=Ax+Bu
$$
(x: state, u: input, A,B: system matrices)

이를 적분하면, 터미널시간 tf의 state는 아래와 같이 얻어질 수 있다.

$$
x(t\_f)=e^{At}x(t\_0)+\\int\_{t\_0}^{t\_f}{e^{At}B(\\alpha)u(\\alpha)}d\\alpha
$$

위 수식 우변항에 있는 x(t0) term을 좌변항으로 넘기면,
$$
x(t\_f)-e^{At}x(t\_0)=\\int\_{t\_0}^{t\_f}{e^{At}B(\\alpha)u(\\alpha)}d\\alpha
$$

따라서 위 조건을 만족시키는 u가 존재하는지에 대한 해석이 controllability(or reachability) 이다.

Linear time invariant(LTI) system에서는 쉽게 해석이 되지만, LTV system에서는 해석이 복잡하며, 새로운 유형의 system이 제안될 때마다 controllability issue는 필연적으로 일어나게 된다.

Continuous-time system에서 Controllability와 Reachability는 동일하다.

이 둘 개념에 대한 정의는  연구자마다 조금씩 다르다.  
주로 미국의 서부에서는 둘을 비슷하게 정의하는 것으로 보이고, 미국의 동부에서는 둘을 철저히 다르게 구분하는 것으로 보인다.

다르게 정의하는 부분에 대해 살펴보면,

* Reachability: 특정 state xf가 어떤 입력에 의해 원점으로부터 도달 가능하다면 Reachable.
* Controllability: 아무 초기 state x0가 어떤 입력에 의해 원점으로 갈 수 있다면 Controllable.

매우 비슷해 보이지만 약간의 차이가 있다.  
Controllability 개념이 더 상위 개념으로서 reachability를 포함하고 있다고 할 수 있다.

Reachbility 개념은 특정 state 혹은 그를 포함하는 set을 기준으로 reachable 여부를 판단하지만, Controllability의 경우 초기치가 어떤 값이든지 0으로 보낼 수 있다면, 이는 어떤 state에든 reachable하다는 이야기가 된다.   
즉, 어떤 state xf가 reachable 하다고 해도 controllable 하다 라고 이야기 할 수 없다. 하지만 controllable하다면 xf는 reachable하다.

[참고문헌1](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-241j-dynamic-systems-and-control-spring-2011/lecture-notes/MIT6_241JS11_lec20.pdf), [참고문헌2](http://www.cds.caltech.edu/~murray/courses/cds101/fa04/caltech/am04_ch5-24oct04.pdf). , [참고문헌3](https://see.stanford.edu/materials/lsoeldsee263/18-contr.pdf), [참고문헌4](http://sigpromu.org/steve/research/Systems_Theory.pdf)
