# 오픈소스sw개론
## 20243082 컴퓨터공학과 김세정

**1. top [실시간 프로세스 출력]** 
<!--뛰어쓰기 2번-->
**$ top**은 시스템 활동을 *실시간*으로 확인할 수 있다.

| 옵션 | 의미                                       |
|------|--------------------------------------------|
| -n   | 지정한 숫자만큼 화면 출력을 갱신한후 명령    |
| -u   | 지정한 사용자의 프로세스를 모니터링        |
| -b   | 출력결과를 파일이나 다른 프로그램으로 전달 |
| -d   | 화면갱신주기를 초 단위로 설정              |
| -p   | 지정한 PID 프로세스를 모니터링             |

![image](https://github.com/sejung-k/project-1/assets/171359826/4fbf5246-9f2d-4a19-ba59-da8605a82b6c)

---
**2. ps [프로세스 출력]**
<!--뛰어쓰기 2번-->
**$ ps 명령어**는 명령어가 실행된 순간의 프로세스 상태들에 대해서 *정적인 정보*만을 제공한다.

**기본** 프로세스 출력
| 옵션 | 의미 |
|------|-----------------------------------------------------------------------------|
|  a | 터미널과 연관된 프로세스만 출력                                             |
|  x | 터미널과 연관되지 않는 프로세스만 출력                                      |
| -A | 모든 프로세스 출력 (-e와 동일)                                              |
| -e | 모든 프로세스 출력                                                          |
| -a | 세션 리더와 커미널과 연관되지 않은 프로세스를 제외하고 모든 프로세스를 출력 | 

**지정한** 프로세스 출력
| 옵션 | 의미                                           |
|------|------------------------------------------------|
| p    | 지정한 PID 목록의 정보만 출력                  |
| -C   | 지정한 프로세스의 실행 파일 이름의 정보만 출력 |
| -u   | 특정 사용자의 프로세스 정보를 출력             |

프로세스 **표시 형식**
| 옵션 | 의미                                                 |
|------|------------------------------------------------------|
| u    | 프로세스의 소유자 정보를 함께 출력                   |
| l    | BSD 형식의 긴 형식으로 출력                          |
| e    | 프로세스 정보와 함께 프로세스의 환경변수 정보도 출력 |
| -l   | 긴 포맷으로 출력                                     |
| -o   | 사용자 정의 형식 지정 가능                           |

프로세스 **장식**
| 옵션 | 의미                                            |
|------|-------------------------------------------------|
| f    | 프로세스 계층을 텍스트 형식의 트리구조를 보여줌 |
| -f   | 전체 포맷으로 출력                              |

![image](https://github.com/sejung-k/project-1/assets/171359826/a884ed50-95b7-4bbb-ba39-dca7691f1511)

---
**3. jobs [백그라운드 프로세스 출력]**
<!--뛰어쓰기 2번-->
**jobs 명령어**는 현재 돌아가고 있는 백그라운드 프로세스 리스트를 *모두 출력*해준다.
백그라운드 프로세스는 스택처럼 쌓이는데, 

+는 **스택의 가장 위**에 있다는 뜻이고,

-는 **바로 그다음 밑**에 있다는 뜻이다.

![image](https://github.com/sejung-k/project-1/assets/171359826/0e90882f-9c0f-470e-9f4d-b299a3acab73)
![image](https://github.com/sejung-k/project-1/assets/171359826/cfb13eb1-7009-41d4-b2b4-a7f55c0e0182)

---
**4. 시그널 - kill [프로세스 종료]**
<!--뛰어쓰기 2번-->
**시그널**은 프로세스 사이의 통신 수단인데 어떤 *프로세스에 메시지를 보내 프로세스를 제어*한다.

![image](https://github.com/sejung-k/project-1/assets/171359826/c09e3936-9653-45c1-848e-1e4d04b1f5a0)

| 번호 | 시그널  | 의 미                                                                                          |
|------|---------|------------------------------------------------------------------------------------------------|
| 1    | SIGHUP  | 터미널에서 접속이 끊겼을때 보내지는 시그널, 변화된 내용을 적용하기 위해 재시작 할 때 사용된다. |
| 2    | SIGINT  | 인터럽트 시그널로 실행을 중지시킴, Ctrl + c 입력시 보내지는 시그널                             |
| 3    | SIGQUIT | 실행 중지 시그널로서 Ctrl + \ 입력시 보내지는 시그널                                           |
| 9    | SIGKILL | 프로세스를 강제로 종료 시키는 시그널                                                           |
| 15   | SIGTERM | kill의 기본 시그널로 정상 종료 시키는 시그널                                                   |
| 18   | SIGCONT | 시그널에 의해 정지된 프로세스를 다시 실행시키는 시그널                                         |
| 19   | SIGSTOP | 정지 시그널                                                                                    |
| 20   | SIGTSTP | 일시정지 시키는 시그널로서 Ctrl + z 입력시 보내지는 시그널                                     |

위의 경우처럼 *몇 가지 시그널*이 존재하는데 **불필요한 프로세스, 잘못 실행된 프로세스를 죽이는**데 사용할 것은 **KILL**이 있다.



