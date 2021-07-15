# 자료구조(Date Structure)
* ### [Stack](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Date_Structure.md#stack-1)
* ### [Queue](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Date_Structure.md#queue-1)
## Stack
* 개념
  * 가장 마지막에 입력된 자료를 가장 먼저 처리하는 선형 자료구조이다.
![image](https://user-images.githubusercontent.com/79801565/125725794-5d1d01ad-7817-4611-bbad-79ceaf816818.png)
* 스택의 기능
  * 스택은 개념부분에서 말했듯이, **후입선출(LIFO, Last In First Out)** 방식을 따른다. 그래서 이를 구현하기 위한 기능이 있다.
    * **pop** : 스택에서 top부분을 제거한다.
    * **push** : item을 스택의 가장 윗 부분에 추가한다. (파이썬은 append이다.)
  * 파이썬의 경우 리스트에서 뒤의 원소를 빼거나 넣을때 상수시간이 걸린다.

* 스택의 간단한 코드(파이썬)

```
    class Stack:
        #리스트를 이용하여 스택 생성
        def __init__ (self):
            self.top = []

        #스택 초기화
        def clear(self):
            self.top=[]

        #PUSH
        def push (self, item):
            self.top.append(item)

        #POP
        def pop(self):
            #if Stack is not empty
            if not self.isEmpty():
                #pop and return 
                return self.top.pop(-1)
            else:
                print("Stack underflow")
                exit()

        #스택에서 top의 값을 읽어온다
        def peek(self):
            if not self.isEmpty():
                return self.top[-1]
            else:
                print("underflow")
                exit()

        #스택이 비어있는지 확인
        def isEmpty(self):
            return len(self.top)==0


    if __name__ == "__main__":
        s = Stack()
        s.push(1)
        s.push(2)
        s.push(3)
        print(s.peek())
        print(s.pop())
        print(s.pop())
        print(s.pop())
        print(s.pop())
        
    결과값
    3
    3
    2
    1
    Stack underflow
    None
```
* 스택의 활용 예시
  * 재귀 알고리즘
    * 재귀 함수 : 자기 자신을 다시 호출하는 함수.(ex. DFS : 깊이 우선 탐색)
      * 재귀함수는 **언제 끝날지**, **종료 조건**을 반드시 적어줘야 한다.(그렇지 않으면 무한 호출될 수 있음.)
    * 재귀함수를 이용한 팩토리얼 계산함수.
    ```
        def factorial_recursive(n):
            if n <= 1:
                return 1
            return n * factorial_recursive(n - 1)
        print(factorial_recursive(5))
        
        결과값 : 120
    ```
  * 웹 브라우저 방문기록의 뒤로가기
  * 역순 문자열
  * 실행취소
  * 후위 표기법 계산
  * 수식 괄호 검사(연산자 우선순위 표현을 위한 검사 ex. VPS(괄호 짝이 맞는지 검사))
* 관련 문제
  * 백준[스택] : https://www.acmicpc.net/problem/10828
  * 백준[괄호] : https://www.acmicpc.net/problem/9012
    
### Reference
> [이것이 코딩을 위한 코딩 테스트다 with 파이썬](https://book.naver.com/bookdb/book_detail.nhn?bid=16439154)
>
> https://github.com/WeareSoft/tech-interview#1-data-structure

> [top](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Date_Structure.md#%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0date-structure)/[Home](https://github.com/JH-TT/CS_Practice#pushpin-cs_practice)
***
## Queue
* 개념
  * 먼저 넣은 데이터가 먼저 나오는 자료구조.
![image](https://user-images.githubusercontent.com/79801565/125732224-ec1522a7-c88c-43ad-a2ca-38f8b97282bb.png)
###### <출처> 컴퓨터인터넷IT용어대사전
* 큐의 기능
  * 큐는 **선입선출(FIFO, First In First Out)** 방식을 따른다.
  * 파이썬의 경우 **collections** 모듈에서 제공하는 **deque** 자료구조를 활용한다.
    * 리스트에서 앞에 원소를 넣거나 뺄 때 O(N)의 시간복잡도가 나오지만, deque를 이용하면 상수시간에 넣거나 뺄 수 있어서 좀 더 효율적이다.
* 큐의 간단한 코드(Python)
```
    from collections import deque
    q = deque()
    q.append(1)
    q.append(2)
    q.append(3)
    print(q)
    print(q.popleft())
    print(q.popleft())
    print(q.popleft())
    print(q.popleft())
    
    결과값
    deque([1, 2, 3])
    1
    2
    3
    IndexError: pop from an empty deque (원소가 없는데 popleft를 하면 인덱스 에러가 뜬다.)
```
* 큐의 활용 예시
  * 큐는 주로 데이터가 입력된 시간 순서대로 처리해야 할 필요가 있는 상황에 이용한다.
    * 우선순위가 같은 작업 예약(프린터의 인쇄 대기열)
    * 콜센터 고객 대기시간
    * 너비 우선 탐색(BFS)
    * 캐시 구현
    * 프린터의 출력 처리
    * 프로세스 관리
    * 선입선출이 필요한 대기열(티켓 카운터)
* 관련 문제
  * 백준[큐] : https://www.acmicpc.net/problem/10845
  * 백준[프린터 큐] : https://www.acmicpc.net/problem/1966
### Reference
> [이것이 코딩을 위한 코딩 테스트다 with 파이썬](https://book.naver.com/bookdb/book_detail.nhn?bid=16439154)
> 
> https://github.com/WeareSoft/tech-interview#1-data-structure

> [top](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Date_Structure.md#%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0date-structure)/[Home](https://github.com/JH-TT/CS_Practice#pushpin-cs_practice)
***
