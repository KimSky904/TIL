> 출처 : cos pro python (성안당), 파이썬 입문 프로그래머스

<br>

# Python 기본 문법

## 출력하기
파이썬의 print()문은 기본으로 줄바꿈을 지원한다.
```python
    print("Hello, ")
    print("World!")
    #Hello, 
    #World!
```
줄바꿈을 원하지 않을 시, end='' 속성을 추가한다.
```python
    print("Hello, ",end='')
    print("World!")
    #Hello, World!
```
변수의 값과 문자를 동시에 출력하기 위해선 다음과 같이 작성한다.
```python
    a = "안녕"
    print(a,"하세요")
    #안녕 하세요
```

<br><br>

## 주석
파이썬은 우물정(#)문자와 따옴표 3개(""")로 주석을 표시한다.
 ```python
    #one-line-comment

    """ multi-line-comment
        multi-line-comment """
```

<br><br>

## 변수
파이썬은 Java와는 다르게 변수의 자료형을 명시하지 않는다.  
하지만 실행 시 자료형을 자동으로 구분한다. (동적 타입;바인딩)
```python
    a = 10
    b = 2.2
    print(a,b)                  #10 2.2
    print(type(a),type(b))      #<class 'int'> <class 'float'>
```


<br><br>

## 연산자
1. 산술연산자  
    기본적인 산술연산자는 다음과 같다.
    ```python
        a + 3
        a - 3

        a * 3
        a ** 2  #a의 2제곱

        a / 3   #실수값
        a // 3  #정수값
        a % 3
    ```
    주의할 점은, Java와 달리 파이썬은 증감연산자를 지원하지 않는다.   

    ```python
        a = 1
        a++
        print(a)
        #Syntax Error
    ```
    때문에 1씩 증가 또는 감소하는 연산은 +,-와 대입연산자 '='을 사용하여 표현한다.
    ```python
        a = 1
        # a++
        a += 1  # a = a + 1
        print(a)
    ```

    또한 Java에서의 정수몫을 구하는 연산자'/'는 파이썬에서 실수몫을 구하며, 정수몫은 '//'을 통해 구한다.
    ```python
        num1 = 10
        num2 = 2
        a = num1 / num2     # 5.0
        b = num1 // num2    # 5
        # b == int(a)
    ```
    <br>
2. 관계연산자  
    기본적인 관계연산자(대소비교)는 모두 Java와 동일하다.  
    하지만 파이썬에서 Java의 기능 외에 추가적으로 지원하는 기능이 있는데, 
    '3항 동시비교'이다.
    ```python
        a = 7
        print(2 < a <= 10) #True
    ```
    또한 파이썬은 'is'연산을 지원한다.  
    'is'연산은 값이 아닌 참조를 비교한다는 점에서 비교연산자(==)와 동작의 차이가 있다.
    ```python
        a = 20
        b = 20
        c = 10
        print(a==b)     #True
        print(a is b)   #True
        print(a==c)     #False
        print(a is c)   #False
    ```
    <br>

3. 논리연산자  
    Java의 '&&','||','!'은 각각 파이썬에서 'and','or','not'으로 사용된다.
    ```python
        a = 5
        b = 7
        print((a<b) and (a<0))  #False
        print((a<b) or (a<0))   #True
        print(not(a<0))         #True
    ```



<br><br>

## 반복문
```python
    #방법 1
    for 변수 in range(시작,끝값,증감)
    for 변수 in range(종료값) ==> 시작~종료값-1까지

    #방법 2
    for 변수 in [리스트,,,,,]
    for 변수 in 리스트

    #range
    range(종료값) : 0~종료값-1 까지의 정수 나열
    range(시작값, 종료값) : 시작~(종료-1)까지의 정수 나열
    range(시작값, 종료값, 증감) : 시작~(종료-1)까지 증감만큼씩 정수 나열
    list(range(종료값)) : range함수의 반환한 것을 list로 변경
```