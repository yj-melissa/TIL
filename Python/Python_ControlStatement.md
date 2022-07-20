<제어문>

- 조건문
- 반복문

## 1. 제어문(Control Statement)

- 파이썬은 기본적으로 위에서 아래로 차례대로 명령을 수행
- 특정 상황에 따라 코드를 선택적으로 실행(분기/조건)하거나 계속하여 실행(반복)하는 제어가 필요함
- 제어문은 순서도(flowchart)로 표현이 가능

## 2. 조건문

1. 조건문(Conditional Statement)
- 조건문은 참/거짓을 판단할 수 있는 조건식과 함께 사용

![2022-07-20-09-05-16-image.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9b53937e-3903-4176-94bc-9152745ff0a4/2022-07-20-09-05-16-image.png)

1. 기본 형식
- 조건에는 참/거짓에 대한 조건식
  
  - 조건이 참인 경우 이후 들여쓰기 되어있는 코드 블록을 실행
  
  - 이외의 경우 else 이후 들여쓰기 되어있는 코드 블록을 실행
    
    - else는 선택적으로 활용 가능
    
    ```python
    if 조건 == True :
        # code block
    else:
        # code block
    ```

- 조건문 예시
  
  ```python
  a = 5
  if a > 5 :
      print('5 초과')
  else :
      print('5 이하')
  print(a)
  ```

- 조건문 실습 문제
  
  - 조건문을 통해 변수 num값의 홀수/짝수 여부를 출력하시오.
    - 이때 num은 input을 통해 사용자로부터 입력을 받으시오.
  
  ```python
  num = int(input('숫자 입력'))
  if num % 2 :  # num % 2 == 1
      print('홀수')
  else :
      print('짝수')
  ```
1. 복수 조건문
- 복수의 조건식을 활용할 경우 **elif**를 활용하여 표현함
  
  ```
  if 조건 :
      # code block
  elif 조건 :
      # code block
  elif 조건 :
      # code block
  else :
      # code block
  ```

- 실습 문제(미세먼지)
  
  ```python
  dust = int(input('미세먼지 농도'))
  
  if dust > 150 :
      print('매우 나쁨')
  elif dust > 80 :
      print('나쁨')
  elif dust > 30 :
      print('보통')
  else :
      print('좋음')
  print('미세먼지 확인 완료')
  ```
  
  ! 조건식을 동시에 검사하는 것이 아니라 순차적으로 비교한다.
1. 중첩 조건문
   
   - 조건문은 다른 조건문에 중첩되어 사용될 수 있음
     
     - **들여쓰기**에 유의하여 작성
     
     ```python
     if 조건:
       # code block
       if 조건 :
           # code block
     else :
       # code block
     ```
   
   - 미세먼지 농도가 300이 넘는 경우, 음수인 경우 각각 경고 문구 출력
     
     ```python
     dust = int(input())
     
     if dust > 150 :
        print('매우 나쁨')
        if dust > 300 :
            print('실외 활동을 자제하세요')
     elif dust > 80 :
        print('나쁨')
     elif dust > 30 :
        print('보통')
     elif dust >= 0 :
        print('좋음')
     else:
        print('값이 잘못 되었습니다.')
     ```

2. 조건 표현식

(1) 조건표현식(Conditional Expression) 정의

- 일반적으로 조건에 따라 값을 정할 때 활용

- 삼항 연산자(Ternary Operator)로 부르기도 함
  
  ```python
  'true인 경우 값' if 조건 else 'false인 경우 값'
  ```

- 예시 1)
  
  ```python
  value = num if num >= 0 else -num
  ```

num이 정수일 때, 절댓값을 저장하기 위한 코드

- 예시 2)
  
  ```python
  num = 2
  result = '홀수' if num % 2 else '짝수'
  print(result)   # 짝수
  ```

## 3. 반복문

1. 반복문
   
   - 특정 조건을 만족할 때까지 같은 동작을 계속 반복하고 싶을 때 사용
   
   ![2022-07-20-19-55-43-image.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/13717c9d-e32a-4dfd-a8c6-92bc6d64d7e1/2022-07-20-19-55-43-image.png)

2. 반복문의 종류
   
   - while문
     - **종료 조건**에 해당하는 코드를 통해 반복문을 종료시켜야 함
   - for문
     - 반복가능한 객체를 모두 순회하면 종료(**별도의 종료 조건 필요 x**)
   - 반복 제어
     - break, continue, for-else

3. While문
- while문은 조건식이 참인 경우 반복적으로 코드를 실행
  
  - 조건이 참인 경우 들여쓰기 되어 있는 코드 블록이 실행됨
  
  - 코드 블록이 모두 실행되고, 다시 조건식을 검사하며 반복적으로 실행됨
  
  - while문은 무한 루프를 하지 않도록 종료 조건이 반드시 필요
    
    ```python
    while 조건:
        # code block
    ```
  
  - 예시
    
    ```python
    a = 0
    while a < 5 :
        print(a)
        a = a + 1
    print('끝')
    ```

- 복합 연산자(In-Place Operator)
  
  - 복합 연산자는 연산과 할당을 합쳐 놓은 것
  
  - 예시) 반복문을 통해 개수를 카운트하는 경우
    
    ```python
    a = 0
    while a < 5 : # 종료조건
        print(a)
        a = a + 1 # 반복시 a가 계속 증가
    print('끝')
    ```
    
    `a = a + 1` : a에 1을 더하면서 a에 그 값을 저장함.
1. for문
   - for문은 시퀀스(string, tuple, list, range)를 포함한 순회 가능한 객체(iterable)의 요소를 모두 순회
     - 처음부터 끝까지 모두 순회하므로 별도의 종료 조건 필요x
   - iterable
     - 순회할 수 있는 자료형(string, list, dict, tuple, range, set 등)
     - 순회형 함수(range, enumerate)

```python
for 변수명 in iterable:
    # code block
```

- for문을 이용한 문자열(String) 순회(range 활용)
  
  ```python
  chars = 'happy'
  
  for idx in range(len(chars)) :
      print(chars[idx])
  ```

- 딕셔너리(Dictionary) 순회
  
  - 딕셔너리는 기본적으로 key를 순회하며, key를 통해 값을 활용
    
    ```python
    grades = {'john': 80, 'eric' : 90}
    for student in grades:
        print(student)
    
    # 결과
    '''
    john
    eric
    '''
    
    grades = {'john': 80, 'eric' : 90}
    for student in grades:
        print(student, grades[student])
    
    '''
    john 80
    eric 90
    '''
    ```

- 추가 메서드를 활용한 딕셔너리 순회
  
  - 추가 메서드를 활용하여 순회할 수 있음
    - keys() : key로 구성된 결과
    - values() : value로 구성된 결과
    - items() : (key, value)의 튜플로 구성된 결과

```python
grades = {'john': 80, 'eric' : 90}
print('grades.keys() : ', grades.keys())
print('grades.values() : ', grades.values())
print('grades.items()  :', grades.items())

# grades.keys() :  dict_keys(['john', 'eric'])
# grades.values() :  dict_values([80, 90])
# grades.items()  : dict_items([('john', 80), ('eric', 90)])

grades = {'john': 80, 'eric' : 90}
for student, grade in grades.items():
    print(student, grade)

# john 80
# eric 90
```

- enumerate 순회
  
  - enumerate()
    - 인덱스와 객체를 쌍으로 담은 열거형(enumearte) 객체 반환
      - (index, value) 형태의 tuple로 구성된 열거 객체를 반환
  
  ```python
  members = ['민수', '영희', '철수']
  
  for idx, member in enumerate(members):
      print(idx, member)
  
  '''
  0 민수
  1 영희
  2 철수
  '''
  
  print(list(enumerate(members))) 
  # [(0, '민수'), (1, '영희'), (2, '철수')]
  # 숫자와 값의 tuple
  
  print(list(enumerate(members, start=1)))
  # [(1, '민수'), (2, '영희'), (3, '철수')]
  # enumerate 사용시 start 기본값 = 0, start 지정하면 해당 값부터 순차적으로 증가
  ```

- List Comprehension
  
  - 표현식과 제어문을 통해 특정한 값을 가진 리스트를 간결하게 생성하는 방법
  
  ```python
  [code for 변수 in iterable]
  [code for 변수 in iterable if 조건식]
  ```
  
  - 1~3의 세제곱 리스트 만들기
  
  ```python
  # for문 사용
  cubic_list = []
  for number in range(1, 4):
      cubic_list.append(number ** 3)
  print(cubic_list) # [1, 8, 27]
  
  # list comprehension
  cubic_list = [number ** 3 for number in range(1, 4)]
  print(cubic_list) # [1, 8, 27]
  ```

- Dictionary Comprehension
  
  - 표현식과 제어문을 통해 특정한 값을 가진 딕셔너리를 간결하게 생성하는 방법
  
  ```python
  {key: value for 변수 in iterable}
  
  {key: value for 변수 in iterable if 조건식}
  ```
  
  - 예시
  
  ```python
  cubic_dict = {}
  
  for number in range(1, 4) :
      cubic_dict[number] = number ** 3
  print(cubic_dict)
  
  # {1: 1, 2: 8, 3: 27}
  ```
1. 반복문 제어

2. 종류
- break
  - 반복문을 종료
- continue
  - continue 이후의 코드 블록은 수행하지 않고, 다음 반복을 수행
- for-else
  - 끝까지 반복문을 실행한 이후에 else문 실행
    - break를 통해 중간에 종료되는 경우 else문은 실행되지 않음
- pass
  - 아무것도 하지 않음(문법적으로 필요하지만, 할 일이 없을 때 사용)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/65723720-e274-4c5f-b181-1e40239d35fb/Untitled.png)

2. break
- break 문을 만나면 반복문은 종료됨
- 예시

```python
n = 0
while True:
    if n == 3:
        break
    print(n)
    n+=1
'''
0
1
2
'''

for i in range(10) :
    if i > 1:
        print('0과 1만 필요해!')
        break
    print(i)
'''
0
1
0과 1만 필요해!
'''
```

! 특정 조건에 반복문을 종료시키기 위해서 break 사용

3. continue
- continue 이후의 코드 블록은 수행하지 않고, 다음 반복을 수행(→ skip!)
- 예시

```python
for i in range(6):
    if i % 2 == 0 :
        continue
    print(i)
'''
1
3
5
'''
```

! continue를 만나면 이후 코드인 print(i)가 실행되지 않고 바로 다음 반복을 수행

4. pass
- 아무것도 하지 않음
  
  - 특별히 할 일이 없을 때 자리를 채우는 용도로 사용(ex. 테스트 등 임시 용도.)
  - 반복문 아니어도 사용 가능
  - pass vs. continue
  
  ```python
  for i in range(4):
      if i == 2:
          **pass**
      print(i)
  '''
  0
  1
  **2**
  3
  '''
  
  for i in range(4):
      if i == 2:
          **continue**
      print(i)
  '''
  0
  1
  3
  '''
  ```
5. else
- 끝까지 반복문을 실행한 이후에 else문 실행
- 예시

```python
for char in 'apple' :
    if char == 'b' :
        print('b!')
        break
else:
    print('b가 없습니다.') # b가 없습니다.

for char in 'banana' :
    if char == 'b' :
        print('b!')
        break
else:
    print('b가 없습니다.') # b!
```
