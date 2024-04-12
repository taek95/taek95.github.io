---
title: Cookie vs LocalStorage vs SessionStorage
date: 2024-04-11 18:10:30 +09:00
categories: [JWT vs Session]
tags: [jwt,session,cookie,browser storage]     # TAG names should always be lowercase
---

# <u>Cookie</u>
- 쿠키는 브라우저 Storage에 위치하고 key-value 형태의 값들이 들어있는 작은 데이터 파일이다.
- 쿠키는 사용자가 따로 요청하지 않아도 브라우저가 요청시에 header에 넣어서 자동으로 서버에 전송한다.
- 세션ID는 "JSESSIONID = 12A32" 형태로 저장된다.

# <u>localStorage</u>
- key-value의 형태의 값들이 존재한다.
- <span style="color:red">브라우저를 종료하고 다시 들어와도 local storage의 데이터는 남아있다.</span>
- 오직 문자열 데이터 타입만 지원한다.

# <u>sessionStorage</u>
- key-value의 형태의 값들이 존재한다.
- <span style="color:red">브라우저를 종료하면 데이터들이 없어진다.</span>

### 오로지 쿠키만이 요청시 자동으로 서버에 전송 <br>-> <span style="color:red">그래서 세션ID를 쿠키에 넣는 것</span>