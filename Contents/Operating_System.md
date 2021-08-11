# Operation System
* 프로세스와 스레드의 차이
* 스레드 세이프

[메뉴로](https://github.com/JH-TT/CS_Practice)

- - -
## 프로세스와 스레드의 차이
### 프로세스
- 컴퓨터에서 연속적으로 실행되고 있는 컴퓨터 프로그램
- 운영체제가 관리하는 최소단위 작업
- 메모리 위에서 서로 독립적으로 실행되고 있음
- PCB(프로세스 제어 블록)를 가진 프로그램
  - PCB란?
    - 운영체제가 프로세스에 대한 중요한 정보를 저장해 놓는 곳. Task Control Block, Job Control Block 이라고 함.
    - 운영체제는 프로세스를 관리하기 위해 프로세스의 생성과 동시에 고유한 PCB를 생성한다. 프로세스는 CPU를 할당받아 작업을 처리하다가도 프로세스 전환이 발생하면 진행하던 작업을 저장하고 CPU를 반환해야 하는데, 이때 작업의 진행 상황을 모두 PCB에 저장하게 된다. 그리고 다시 CPU를 할당받게 되면 PCB에 저장돼있던 내용을 불러와 이전에 종료됐던 시점부터 다시 작업을 수행한다.
  - PCB에 저장되는 정보
    - 프로세스 고유 식별자 : 프로세스를 구분할 수 있는 고유의 번호
    - 프로세스 상태 : new, ready, running, waiting, terminated 등의 상태를 저장
    - 프로그램 카운터 : 프로세스가 다음에 실행할 명령어의 주소
    - CPU 레지스터 정보 : Accumulator, Index Register, 범용 레지스터, PC 등에 대한 정보
    - 입출력 상태 정보 : 입출력장치, 개방된 파일 목록
    - 주기억장치 관리 정보 : Base Register, Page Table 에 대한 정보
    - 계정 정보 : CPU 사용 시간, 실제 사용 시간, 한정된 시간
    - 스케줄링 및 프로세스의 우선순위 : 스케줄링 정보 및 프로세스가 실행될 우선순위
#### 특징
![image](https://user-images.githubusercontent.com/79801565/129071207-b77481df-ed02-4ee8-9385-0aea49701484.png)
- 위의 이미지와 같이 프로세스는 각각 독립된 메모리 영역(Code, Date, Stack, Heap)을 할당받는다.
- 기본적으로 프로세스당 최소 1개의 스레드를 가지고 있다.
- 다만 프로세스간 통신은 스레드간 통신보다 어렵다.

### 스레드(시스템 자원을 효율적으로 처리하기 위한 수단)
- 프로세스 내에서 실행되는 여러 흐름의 단위
- 프로세스의 특정한 수행 경로
- 프로세스와 다르게 스레드 간 메모리를 공유하며 작동한다.
- 한 프로세스 내에서 많은 자원을 공유하면서 병렬적으로 실행됨
- Stack만 독립적으로 할당받고 나머지(Code, Data, Heap)은 공유한다. (이미지 참고)
![image](https://user-images.githubusercontent.com/79801565/129076178-23547c9a-7442-4bf0-830e-15e264ec8712.png)
- 스레드는 code, data, heap을 공유하고 있기 때문에, 어떤 스레드 하나에서 오류가 발생한다면 같은 프로세스 내의 다른 스레드 모두가 강제로 종료된다.
- Stack을 독립적으로 할당하는 이유
  - 스택은 함수 호출 시 전달되는 인자, 되돌아갈 주소값 및 함수 내에서 선언하는 변수 등을 저장하기 위해 사용되는 메모리 공간이므로 스택 메모리 공간이 독립적이라는 것은 **독립적인 함수 호출이 가능하다**는 것이고 이는 **독립적인 실행 흐름**이 추가되는 것이다. 따라서 스레드의 정의에 따라 독립적인 실행 흐름을 추가하기 위한 최소 조건으로 독립된 스택을 할당한다.


> [참고1](https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/master/OS#%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4%EC%99%80-%EC%8A%A4%EB%A0%88%EB%93%9C%EC%9D%98-%EC%B0%A8%EC%9D%B4)   
> [참고2](https://blog.naver.com/wltjdrmsdl/222343752066)   
> [참고3](https://gmlwjd9405.github.io/2018/09/14/process-vs-thread.html)   
> [참고4](https://shoark7.github.io/programming/knowledge/difference-between-process-and-thread)
> [Top](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Operating_System.md#operation-system)
- - -
