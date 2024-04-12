---
title: Session 대신에 JWT를 써야하는 이유
date: 2024-04-06 11:00:30 +09:00
categories: [JWT vs Session]
tags: [jwt,session,cookie]     # TAG names should always be lowercase
---

# <u>Session의 문제점</u>
 로드밸런싱 하는 경우
![session2](https://github.com/taek95/beforeMatch/assets/50096950/4a8400b0-5103-4288-8f59-0c0d73316896)
동시 접속자 수가 증가하여 로드 밸런싱을 통해 서버의 부하를 나눈다. 아이디 aa를 가진 유저가 계속 serverB와 연결되면 상관없지만 로드밸런싱을 통해 serverC와 연결된다면?
<br><span style="color:red"> serverC 입장에서는 최초연결이라 세션ID가 또 생성된다. </span><br>
    - <span style="color:red"> 해결방법 1 </span> : Sticky Session이라는 개념을 도입하여 로드밸런싱 신경안쓰고 최초 연결 서버와 계속 통신하게 만든다.<br>
    - <span style="color:red"> 해결방법 2 </span> : 최초 연결 서버에서 세션ID를 만들면 로드밸런싱 서버 전체에 세션ID를 복제.<br>
    - <span style="color:red"> 해결방법 3 </span> : 서버들이 하나의 DB를 이용해 세션ID를 관리한다.<br>
![session3](https://github.com/taek95/beforeMatch/assets/50096950/b8e3198b-299b-45ab-a7fc-9563282bf574)
원래 Session은 서버의 메모리에 저장된다. 그래서 빠르다. 근데 DB를 이용한다면 하드디스크를 이용하게 된다. 그러면 엄청나게 느려진다.
DB에서는 IO가 일어나기 때문에 속도가 약 100만배 가량 느려진다. 그래서 DB대신 메모리서버를 사용한다. 대표적으로 redis가 있다.
        <br><br><span style="color:red"> -> 이런 해결방법들은 좋은 해결방법이 아니다.</span>


그래서 세션이 가지는 문제점 해결가능
각각의 서버가 키값만 알고있으면 되니까

+ 보안