> 출처 : Kotlin 공식문서, 만들면서 배우는 코틀린&안드로이드 프로그래밍, 깡쌤의 안드로이드

<br>

# 코틀린 기본 문법


## 패키지 선언
패키지 정의는 소스파일의 최상단에 위치해야한다.
```kotlin
    package project.demo

    import kotlin.test.*
```

## 프로그램의 시작
Kotlin은 java와 동일하게 main함수가 먼저 실행된다.
```kotlin
    fun main(){
        println("Hellow world")
    }
    // kotlin은 다양한 인수를 허용한다.
    fun main(args : Array<String>) {
        println(args.contentToString())
    }

```

<br><br>

## 출력문
kotlin은 기본적으로 print()를 사용한다.
```kotlin
    print("Hello ") 
    print("World!")
    // Hello World!
```
줄바꿈을 원한다면 println()을 사용한다.
```kotlin
    println("Hello world!")
    println(42)
    // Hello world!
    // 42
```



<br><br>

## 함수
두개의 Int형 인수를 받고, Int타입을 return하는 함수의 형태는 다음과 같다.
```kotlin
    fun sum(a : Int, b : Int) : Int {
        return a+b
    }
```
함수의 본문을 표현식으로 나타낼 수 도 있으며,  
이 경우에는 반환값이 유추될 수 있다.
```kotlin
    fun sum(a: Int, b: Int) = a + b
```
반환값이 없을 경우에는 Unit으로 표현할 수 있다.
```kotlin
    fun printSum(a: Int, b: Int): Unit {
        println("sum of $a and $b is ${a + b}")
    }
```
또한 Unit은 생략가능하다.
```kotlin
    fun printSum(a: Int, b: Int) {
        println("sum of $a and $b is ${a + b}")
    }
``` 

<br><br>

## 변수
(지역) 상수변수는 키워드 val을 통해 정의한다.  
 상수이기 때문에 값변경은 금지되며, 즉시할당과 지연할당이 가능하다.
```kotlin
    val a : Int = 1     //즉시할당
    val b = 2           //'Int' type이 유추됨
    val c : Int         //즉시할당이 아닌 경우 type지정 필수
    c = 3               //지연할당
``` 

상수가 아닌 일반 변수를 선언할 경우 키워드 var을 사용한다.
```kotlin
    var x : Int = 5
    var y = 6           //'Int' type이 유추됨
``` 


## 형변환
변환하고자 하는 자료형의 앞에 to를 붙이면 끝이다.



<br><br>

## 클래스 생성
클래스 정의는 키워드 class를 사용한다.
```kotlin
    class Shape
``` 
클래스의 속성은 클래스의 본문이나 선언문에 나열될 수 있다.
```kotlin
    class Rectangle(var height: Double, var width: Double){
        var parameter = (height+width)*2
    }
``` 
클래스 선언에 나열된 매개변수가 있는 기본 생성자는 자동으로 생성된다.
```kotlin
    var rect = Rectangle(5.0,10.0)
    println("둘레는 ${rect.parameter}입니다.")
``` 

클래스간의 상속은 콜론(:)을 통해 선언한다. 클래스는 기본적으로 final이다.
```kotlin
    open class Shape
    class Rectangle(var height: Double, var width: Double) : Shape() {
        var parameter = (height+width)*2
    }

``` 

<br><br>

## 주석
Java나 C 등 다른 대부분의 언어처럼 다음과 같이 주석을 작성한다.
```kotlin
    //  one-line-comment

    /*  multi-line-comment
        multi-line-comment  */
``` 

<br><br>

## 문자열 형식
```kotlin
    var a = 1
    val s1 = "a is $a" 

    a = 2
    val s2 = "${s1.replace("is", "was")}, but now is $a"

    //a was 1, but now is 2

```

## 조건문
if문
```kotlin
    fun maxOf(a: Int, b: Int): Int {
        if (a > b) {
            return a
        } else {
            return b
        }
    }
``` 
Kotlin에서는 단일 표현으로 if문을 사용할 수 있다.
```kotlin
    fun maxOf(a: Int, b: Int) = if (a > b) a else b
``` 


## 반복문
list의 내용을 출력하는 for (1)
```kotlin
    val items = listOf("apple", "banana", "kiwifruit")
    for (it in items) {
        println(it)
    }
    //  apple
    //  banana
    //  kiwifruit 
```
list의 내용을 출력하는 for (2)
```kotlin
    val items = listOf("apple", "banana", "kiwifruit")
    for (index in items.indices) {
        println("item at $index is ${items[index]}")
    }
```
0~9의 값을 출력하는 for
```kotlin
    for (i in 0..9) {
        println(i)
    }
```
9~0의 값을 출력하는 for
```kotlin
    for (i in 9 downTo 0) {
        println(i)
    }
```
1,3,5,7,9의 값을 출력하는 for
```kotlin
    for (i in 0..9 step 2) {
        println(i)
    }
```
'a'~'e'를 출력하는 for
```kotlin
    for (i in 'a'..'e') {
        println(i)
    }
```


<br><br>

## while문
```kotlin
    val items = listOf("apple", "banana", "kiwifruit")
    var index = 0
    while (index < items.size) {
        println("item at $index is ${items[index]}")
        index++
    }
```



## 흐름제어문
break와 continue는 다른 언어와 동일, Kotlin에서는 loop(레이블)을 지원함
```kotlin
    loop@for(i in 0..100){
        for(j in 1..10){
            if(i==1&&j==10) break@loop
        }
    }
```


<br><br>





## when문
Java의 switch와 비슷한 기능을 하지만, switch와는 다르게 int형이 아닌 다른 자료형(객체 포함)도 사용할 수 있음
```kotlin
    fun describe(obj: Any): String =
    when (obj) {
        1          -> "One"
        "Hello"    -> "Greeting"
        is Long    -> "Long"
        !is String -> "Not a string"
        else       -> "Unknown"
    }
```


## 범위 표현
in 연산자를 사용하여 
```kotlin
    val x = 10
    val y = 9
    if (x in 1..y+1) {
        println("fits in range")
    }
```
```kotlin
    val list = listOf("a", "b", "c")

    if (-1 !in 0..list.lastIndex) {
        println("-1 is out of range")
    }
    if (list.size !in list.indices) {
        println("list size is out of valid list indices range, too")
    }
```
```kotlin
    for (x in 1..5) {
        print(x)
    }
```
```kotlin
    for (x in 1..10 step 2) {
        print(x)
    }
    println()
    for (x in 9 downTo 0 step 3) {
        print(x)
    }
```
