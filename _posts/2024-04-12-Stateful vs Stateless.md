---
title: Stateful vs Stateless
date: 2024-04-12 09:10:30 +09:00
categories: [Web]
tags: [stateful, stateless]     # TAG names should always be lowercase
---

# <u>Stateful</u>
- 상태를 유지하는가를 의미한다.
- 클라이언트에 대한 <span style="color:red">특정 정보</span>가 서버에 저장된다.<br>
세션방식은 로그인을 하게 되면 서버의 세션ID에 유저의 정보가 연결되어 저장된다. 

# <u>Stateless</u>
- 상태를 유지하지 않는것을 의미한다. 
- 클라이언트에 대한 <span style="color:red">특정 정보</span>가 서버가 아닌 클라이언트 측에 저장되어 있는것을 의미한다.
<br>토큰의 payload에는 인증정보들이 담겨있는데 토큰은 클라이언트 측에 있으므로 stateless하다고 할 수 있습니다.
- REST API는 stateless를 지향하기 때문에 토큰을 사용해야 합니다.

# <u>QnA</u>
1. 그럼 http는 stateless한대 session을 사용하면 안되는거 아니냐?
- 아닙니다. 그저 http가 stateless하다는 특성인 것이지 session은 stateful해서 못쓴다 그런 개념이 아닙니다.