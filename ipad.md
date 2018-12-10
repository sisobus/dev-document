ipad
====

### iPad로 간단한 코딩하는 환경 만들기

- 목표: 테스트 코드 작성, 간단한 자료구조 구현, 문제풀이 코드 작성
  - 모바일 네트워크에서 끊기지 않는 코딩을 할 수 있도록 환경설정하기

* 결론 한줄 요약
  - python coding만 할거면 pythonista쓰고, 더 많은걸 하고 싶으면 서버하나 파서 mosh 세팅해서 blink를 쓰면 된다.

아래는 과정을 나열해봤습니다.
1. 먼저 Native terminal이 있는지 찾아보자 >> 없다.
2. Terminal 앱중에 iCloud기반의 Native 쉘을 구현해놓은 앱을 찾아보자 >> Blink
    - scp, cp, mv, sed, ... 등의 실행파일은 있지만 c++ compiler, python interpreter 등이 없다.
3. python interpreter 앱이 있는지 찾아보자 >> 있다!! (Pythonista - 12,000원)
    - Pythonista는 2.7과 3.6을 지원한다. console도 분할해서 띄울 수 있고 빠르고 쓸만한 듯 싶다.
4. 혹시 iPad앱중에 docker... >> 없다ㅎㅎ;
5. 그렇다면 ssh를 지원하는 앱들을 살펴보자.
    - Terminus (free/ssh/mosh(beta)), blink(25,000원/mosh/ssh), prompt2(19,000원/ssh)
    - terminus, blink모두 ssh로 사용했을 땐 끊김현상이 있거나 장기간 이벤트가 없을시 꺼짐
6. mosh라는게 뭐지? >> mobile shell
7. ssh는 TCP, mosh는 UDP
8. 아래 이미지에서 mosh와 ssh의 차이점을 볼 수 있음
<img width="300" alt="ssh" src="https://user-images.githubusercontent.com/3329885/49706381-e2ff9880-fc68-11e8-81e6-c5f6f2c210fc.png">
<img width="300" alt="mosh" src="https://user-images.githubusercontent.com/3329885/49706382-e4c95c00-fc68-11e8-8c34-0ead475c8ecd.png">

9. mosh를 추천합니다.
      - 대신 서버에서 mosh를 설치해줘야함. 방화벽도 열어줘야함.
      - ec2의 경우 보안그룹에서 포트도 UDP 60000-61000열어줘야함
      - client에서 osx server로 접속할 경우, mosh-server를 /usr/local/bin/mosh-server로 변경해줘야함


```
  $ sudo apt-get install mosh (ubuntu)
  $ brew install mosh (osx)
```
