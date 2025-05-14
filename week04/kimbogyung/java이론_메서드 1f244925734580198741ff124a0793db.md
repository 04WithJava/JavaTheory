# java이론_메서드

## 자바에서는 함수를 메서드(Method)라고 한다

## 메서드 (메서드 선언과 메서드 본문으로 나뉜다)

- 메서드 선언 (메서드 이름, 반환 타입, 매개변수(파라미터) 포함함)

```java
public static int add(int a, int b)

// public : 다른 클래스에서 호출할 수 있는 메서드
// static : 객체 생성하지 않고 호출할 수 있는 정적 메서드
// int : 반환 타입
// add : 메서드 이름 (이 이름으로 메서드 호출함)
// (int a, int b) : 메서드 호출할 때 전달하는 입력값, 메서드 안에서만 사용됨
// 메서드 선언에 사용되는 변수를 파라미터 (=매개변수)라고 함
```

- 메서드 본문 : 메서드가 수행해야 하는 코드 블록

```java
{
	System.out.println(a + " + " + b + " 연산 수행");
	int sum = a + b;
	return sum;
}
```

- 메서드 호출하면 메서드 본문이 순서대로 실행됨 

- 메서드는 블랙박스 같은 느낌 (메서드 호출 부분에서는 메서드 선언은 알아도 본문 내용은 모름

- 메서드 실행 결과 반환하려면 return 문 사용 // return sum → sum 변수 값 반환

## 메서드 호출

정의한 메서드를 호출해서 실행하려면 메서드 이름에 입력 값 전달하면 됨

```java
int sum1 = add (5, 10); // add 메서드를 숫자 5,10 전달하며 호출
int sum1 = 15; // add(5,10)이 실행되고, 반환 값은 15
```

메서드 호출이 끝나면 메서드 정의에 사용한 파라미터 변수와 그 안에서 정의한 변수들이 모두 제거됨

- 메서드 호출할 때는 넘기는 값과 순서, 갯수가 메서드 값과 파라미터 값이 맞아야 함

```java
호출 : call("hello", 20)
메서드 정의 : int call(String str, int age)
```

### < 용어정리 >

인수(=Argument, 인자) : “hello”, 20처럼 넘기는 값을 의미

매개변수(Parameter) : 메서드 정의할 때 선언한 변수 String str, int age를 매개변수, 파라미터라고 함 // 메서드 호출 시 인수 넘기면, 그 인수가 파라미터에 대입됨

## 메서드 정의

```java
public static int add(int a, int b) {
		메서드 본문, 실행 코드
}
제어자 반환타입 메서드이름 (매개변수 목록) {
		메서드 본론
}
```

제어자 : public, static같은 부분

반환 타입 : 메서드 실행 후, 반환하는 데이터 타입 (값 반환 안 하는 경우는 void사용)

메서드 이름 : 메서드 호출 시 사용하는 이름

매개변수 : 메서드 내부에서 사용하는 변수 // 입력값 필요없는 메서드는 매개변수 지정 안 해도 가능    ex.add()

메서드 본문 : 실제 메서드 코드

** 모든 메서드는 항상 return 호출해야 하는데, 반환 타입 void 경우에는 예외로 생략해도 됨. 자바가 반환 타입 없는 경우에는 return을 마지막줄에 넣어줌. return 만나면 해당 메서드는 종료됨 **

## 반환 타입 : 반환 타입이 있으면 반드시 값 반환해야 한다

반환 타입 있는 메서드는 ! 반드시 ! return 사용해서 값 반환해야 함

```java
boolean result = odd(2);
        System.out.println(result);
    }
    public static boolean odd(int i) {
        if (i % 2 == 1) {
            return true;
// if 조건 만족하지 않아서 return문 실행XX 컴파일 오류 남

boolean result = odd(2);
        System.out.println(result);
    }
    public static boolean odd(int i) {
        if (i % 2 == 1) {
            return true;
        } else {
            return false;
        } --> 이렇게 바꿔주기
```

## 메서드 형변환

1. 명시적 형변환

```java
public class MethodCasting1 {
    public static void main(String[] args) {
        double number = 1.5;
        printNumber((int) number);
    }
    public static void printNumber(int n) {
        System.out.println("숫자: " + n);
    }
}
```

printNumber(number); 하면 컴파일 오류 발생

—> 명시적 형변환으로 double을 int로 변환해주기

1. 자동 형변환 (int < long < double)

```java
public class MethodCasting1 {
    public static void main(String[] args) {
        double number = 1.5;
        printNumber((int) number);
    }
    public static void printNumber(int n) {
        System.out.println("숫자: " + n);
    }
}
```

메서드 호출 시, 전달하는 인수 타입과 매개변수 타입이 맞아야 하지만, 타입이 달라도 큰 타입에서 작은 타입의 형변환은 자동 형변환이 가능하여 호출이 가능

## 메서드 오버로딩 (과하게 물건을 담았다는 뜻)

이름이 같고 매개변수가 다른 메서드를 여러 개 정의하는 것

```java
add(int a, int b)
add(int a, int b, int c)
add(double a, double b)
```

오버로딩 규칙 : 메서드 이름이 같아도 매개변수 타입, 순서가 다르면 오버로딩이 가능

```java
int add(int a, int b)
double add(int a, int b)
```

—> 메서드 이름과 매개변수 타입이 같기 때문에 컴파일 발생

- 메서드 시그니처 = 메서드 이름 + 매개변수 타입 (순서)

자바에서 메서드 구분할 수 있는 고유한 식별자를 의미 (구분하는 기준)

어떤 메서드를 호출할 지 결정하기 위해 각각의 메서드를 고유하게 구분할 수 있어야 함 // 따라서 메서드 이름이 같아도, 메서드 시그니처가 다르면 다른 메서드로 간주