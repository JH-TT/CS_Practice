# 자료구조(Date Structure)
* ### Stack
* ### Queue
## Stack
* 개념
  * 가장 마지막에 입력된 자료를 가장 먼저 처리하는 선형 자료구조이다.
![image](https://user-images.githubusercontent.com/79801565/125725794-5d1d01ad-7817-4611-bbad-79ceaf816818.png)
* 스택의 기능
  * 스택은 개념부분에서 말했듯이, **후입선출(LIFO, Last In First Out)** 방식을 따른다. 그래서 이를 구현하기 위한 기능이 있다.
    * **pop** : 스택에서 top부분을 제거한다.
    * **push** : item을 스택의 가장 윗 부분에 추가한다. (파이썬은 append이다.)
    * **peek** : 가장 위에 있는 항목을 반환한다.
    * **empty** : 비어있는지 확인. 비어있으면 true를 반환한다. (파이썬은 보통 len함수를 이용.)
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
* 스택의 사용 사례
  * 재귀 알고리즘
    * 재귀 함수 : 자기 자신을 다시 호출하는 함수.(DFS : 깊이 우선 탐색)
      * 재귀함수는 언제 끝날지, 종료 조건을 반드시 적어줘야 한다.(그렇지 않으면 무한 호출될 수 있음.)
  * 웹 브라우저 방문기록의 뒤로가기
  * 역순 문자열
  * 실행취소
  * 후위 표기법 계산
  * 수식 괄호 검사(연산자 우선순위 표현을 위한 검사 ex. VPS(괄호 짝이 맞는지 검사))
    
> [top](https://github.com/JH-TT/CS_Practice/blob/main/Contents/Date_Structure.md#%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0date-structure)
