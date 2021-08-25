# Operation System
* [운영체제란](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Operating_System.md#%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C%EB%9E%80)
* [프로세스와 스레드의 차이](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Operating_System.md#%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4%EC%99%80-%EC%8A%A4%EB%A0%88%EB%93%9C%EC%9D%98-%EC%B0%A8%EC%9D%B4)
* [스레드 세이프](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Operating_System.md#%EC%8A%A4%EB%A0%88%EB%93%9C-%EC%84%B8%EC%9D%B4%ED%94%84thread-safe)

[메뉴로](https://github.com/JH-TT/CS_Practice)
- - -
## 운영체제란?
### Operation System
일반적으로 **하드웨어를 관리하고, 응용 프로그램과 하드웨어 사이에서 인터페이스 역할을 하며 시스템의 동작을 제어하는 시스템 소프트웨어**로 정의한다.

운영체제는 사용자와 하드웨어간의 전반적인 상호작용을 하면서 컴퓨터가 실행되는 동안 항상 수행되는 프로그램이다.

#### 운영체제의 목적
- 사용자가 컴퓨터를 편리하게 사용하는 것
- 컴퓨터 하드웨어가 효율적으로 사용되는 것

#### 운영체제의 구조와 구성 요소
운영체제는 하드웨어 위에 커널이 올라가고, 커널 위에서 셸과 애플리케이션이 실행된다. 사용자는 기본적으로 셀을 통해 애플리케이션을 실행한다.
- 유닉스 운영체제의 구조   
![image](https://user-images.githubusercontent.com/79801565/130762262-45c9e6f2-b1ba-47fa-bfe8-b69c6abbdad2.png)
- 현대의 운영체제는 여러 개의 프로그램으로 구성되어 있다.
  - 커널 : 운영체제에서 가장 핵심이 되는 프로그램. 드라이버를 이용해서 CPU나 그래픽카드와 같은 하드웨어를 제어하고 여러 응용프로그램들이 갖가지 다른 하드웨어 위에서 돌아가도록 호환성을 보장하기 위해 API를 제공한다. 프로그램이 요청한 처리를 하드웨어에 나누어 처리를 요구하며, 시스템 호출 수행, 메모리 제어 등을 한다.
  - 부트 로더 : 컴퓨터가 켜졌을 때 운영체제에 필요한 조치를 취하고 하드 디스크 드라이브에 기록되어 있는 운영체제를 실행하는 프로그램이다.
  - 셸 : 화면에 사용자가 볼 수 있는 요소. 사용자의 지시를 해석하여 커널에게 전달하여 주는 역할을 맡는다.

- 구성요소(4개의 서브시스템)
  - **프로세스 관리자** : 프로세스 관리자는 프로세서, 즉 중앙처리장치(CPU)를 프로세스에게 어떻게 할당할 것인가를 결정한다. 프로세스는 현재 실행 중인 프로그램으로 메모리를 할당받은 프로그램을 의미하는데, 컴퓨터는 여러개의 프로세스를 동시에 처리해야 하는 상황에서 프로세스 관리자는 프로세스 스케쥴링 및 동기화를 담당하고 프로세스 생성 및 소멸, 시작과 정지, 일시중지 및 재실행을 제어한다. 또한 프로세스들 간의 통신을 위한 메시지 전달 등의 기능도 담당한다.
  - **기억장치 관리자** : 기억장치 관리자는 프로세스에 메모리를 할당하거나 회수하는 등 주기억장치의 관리를 담당한다. 주기억장치 영역에 대한 요청이 들어오면 요구사항이 유효한지를 체크하고, 적법한 요구의 경우 주기억장치 관리자가 미사용 부분을 할당하고 작업을 마친 프로세스의 메모리 공간에 대해서는 회수하는 역할을 수행한다. 뿐만 아니라 보조기억장치인 HDD와 가상메모리에 대한 관리를 수행하는 데 디스크 탐색 알고리즘과 가상메모리 할당기법을 이용하여 기능을 수행한다.
  - **파일 관리자** : 파일 관리자는 파일의 생성, 삭제, 변경, 유지 등의 관리를 담당한다. 즉 컴파일러, 인터프러터, 어셈블러, 유틸리티 프로그램, 데이터 파일과 응용 프로그램을 포함한 시스템의 모든 파일을 모니터링하여 파일의 접근을 제어한다.
  - **장치 관리자** : 장치관리자는 입출력장치 스케쥴링 및 전반적인 관리를 담당한다. 채널과 제어장치를 모니터링하여 시스템의 모든 장치를 가장 효율적으로 할당하는 역할을 한다.
 - 구성을 그림으로 나타낸 모습.


> [이미지출처1](https://johnloomis.org/ece314/notes/OperatingSystems/UNIX.html)   
> [참고1](https://www.youtube.com/watch?v=EAoJb00Iwso)   
> [참고2](https://blog.naver.com/phisldlfma/221278766833)
> [참고3](https://github.com/gyoogle/tech-interview-for-developer/blob/master/Computer%20Science/Operating%20System/Operation%20System.md#%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4-%EA%B4%80%EB%A6%AC)
> 
>[Top](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Operating_System.md#operation-system)
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
#### Stack을 독립적으로 할당하는 이유
  - 스택은 함수 호출 시 전달되는 인자, 되돌아갈 주소값 및 함수 내에서 선언하는 변수 등을 저장하기 위해 사용되는 메모리 공간이므로 스택 메모리 공간이 독립적이라는 것은 **독립적인 함수 호출이 가능하다**는 것이고 이는 **독립적인 실행 흐름**이 추가되는 것이다. 따라서 스레드의 정의에 따라 독립적인 실행 흐름을 추가하기 위한 최소 조건으로 독립된 스택을 할당한다.
#### 장점
  - 성능과 프로그램 처리율 향상
  - 응답시간 단축
  - 기억장소 낭비 줄어듬
  - 효율적 통신

> [참고1](https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/master/OS#%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4%EC%99%80-%EC%8A%A4%EB%A0%88%EB%93%9C%EC%9D%98-%EC%B0%A8%EC%9D%B4)   
> [참고2](https://blog.naver.com/wltjdrmsdl/222343752066)   
> [참고3](https://gmlwjd9405.github.io/2018/09/14/process-vs-thread.html)   
> [참고4](https://shoark7.github.io/programming/knowledge/difference-between-process-and-thread)
>    
> [Top](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Operating_System.md#operation-system)
- - -

## 스레드 세이프(Thread Safe)
- 다수의 스레드에 의한 동시 호출에서 안정성이 보장되는 코드를 스레드 세이프하다고 한다. 스레드 세이프한 코드에는 경합 조건이 없다.

예시를 보자.
(Not Thread Safe)
```
int num;
boolean is_even;

int inc(int n)
{
  num += n;
  if((num % 2) == 0)
    is_even = true;
  else
    is_even = false;
  return num;
}
```
위 코드를 보면, 싱글 스레드 환경에서는 문제가 없는 코드다.
다만, 멀티 스레드 환경에서는 문제를 발생시킬 소지가 있다. 두 개의 스레드가 위 코드를 같이 수행한다고 가정해보자. 두 개의 스레드는 전역변수인 num, is_even을 공유한다.
1번과 2번 스레드가 다음 함수를 수행했다고 하자
```
a = inc(1)
```
먼제 1번 스레드가 다음 라인까지 수행했다고 하자.
```
  num += n; // num = 1, n = 1
  if ((num % 2) == 0)
```
num이 1인 상황에서 1을 더했으니 num % 2는 0이 되는 것이 맞다. 그리고 is_even에 true를 설정하기 바로 직전 다른 스레드가 다음 코드를 수행했다고 하자.
```
  num += n; // 2 + 1 = 3
  ...
  else
    is_even = false;
    
  return num;
}
```
1번 스레드가 num을 2로 세팅해 놓았기 때문에 num += n을 계산하면 3이 된다.
3은 홀수이므로 is_even = false가 된다.
이때, 다시 1번 스레드가 수행되어 is_even = true;를 수행한다.
이런 수행 순서를 지나면, num값은 3이 되고, is_even은 true로 세팅된다. 프로그래머의 의도와 맞지 않는 결과가 멀티 스레드 환경에서 발생했기 때문에 Thread safe하지 않다고 할 수 있다.
(Thread Safe)
```
int num;
boolean is_even;
pthread_mutex_t mutex_lock = PTHREAD_MUTEX_INITIALIZER;

int inc(int n)
{
  pthread_mutex_lock (&mutex_lock);
  /* Critical Section Start */
  
  num += n;
  if ((num % 2) == 0)
    is_even = true;
  else
    is_even = false;
    
  /* Critical Section End */
  pthread_mutex_unlock(&mutex_lock);
  
  return num;
}
```
이렇게 Critical Section을 정의해서 Critical Section은 한 번에 한 스레드만 수행되도록 만들어줘야 한다.
그래서 하나의 스레드가 Critical Section에서 나오면, 기다리고 있었던 다른 스레드가 Critical Section으로 들어가게 된다. 들어가는 순서는 Critical Section을 만드는 구현체에 따라 다르다. Wait Queue를 두어 FIFO로 구현할 수도 있고, spinlock처럼 random하게 구현할 수도 있다.

### 객체 멤버변수
객체 멤버변수(필드)는 그 객체(클래스의 인스턴스)를 따라 힙에 저장된다. 때문에, 만약 두 스레드가 같은 객체 인스턴스의 메소드를 호출하고 이 메소드가 객체 멤버변수를 update한다면 이 메소드는 스레드 세이프하지 않다.

예제를 보자.
```
public class NotThreadSafe{
  StringBuilder builder = new StringBuilder();
  
  public add(String text){
    this.builder.append(text);
  }
}

NotThreadSafe sharedInstance = new NotThreadSafe(); // !!

new Thread(new MyRunnable(sharedInstance)).start(); // !!
new Thread(new MyRunnable(sharedInstance)).start(); // !!

public class MyRunnable implements Runnable{
  NotThreadSafe instance = null;

  public MyRunnable(NotThreadSafe instance){
    this.instance = instance;
  }

  public void run(){
    this.instance.add("some text");
  }
}
```
이렇게 두 스레드가 동시에 같은 NotThreadSafe의 인스턴스의 add()메소드를 호출한다면, 이는 경합 조건을 일으킨다.(느낌표 2개 있는곳 주목)

약간 수정해서 경합 조건이 발생하지 않도록 해보자.
```
new Thread(new MyRunnable(new NotThreadSafe())).start();
new Thread(new MyRunnable(new NotThreadSafe())).start();
```
이렇게 하면 두 스레드는 각자의 NotThreadSafe 인스턴스를 가지며, 이 스레드들의 add() 메소드 호출은 더이상 서로 간섭하지 않는다.
어떤 객체가 경합 조건을 일으키는 코드를 포함하고 있다고 해도 이 객체를 사용하는 방식에 따라 경합 조건은 발생하지 않을 수 있다.
> [출처1](https://blog.naver.com/complusblog/220985528418)   
> [출처2](https://parkcheolu.tistory.com/12)   
> 
> [Top](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Operating_System.md#operation-system)   

- - -
