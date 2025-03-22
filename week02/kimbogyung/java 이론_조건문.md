# java 이론_조건문

## 조건문 : 특정 조건에 맞는 코드를 실행 (if / switch)

## if 문

- if : 조건이 참인지 확인 > 참이면 특정 코드 실행
- else : if문에서 만족하는 조건이 없을 때 코드 실행 (생략 가능)
- else if : if문의 조건이 거짓일 때 코드 실행 // 순서대로 맞는 조건을 찾고, 맞는 조건 딱 하나만 실행됨

— if 문 + else if 문 >> 서로 연관된 조건일 때 사용  // 

서로 관련 없는 독립 조건이면 else if 사용 X, if문 각각 따로 사용

- {} 중괄호 생략 : if문(else if, else) 다음 실행할 명령이 하나 뿐이면 {} 중괄호 생략 가능
    - 하지만 보통 if 문 명령이 하나만 있어도 {} 사용하는 것 권장 (가독성, 유지보수성)

```java
if (true)
	System.out.println("if문에서 실행됨");
	System.out.println("if문에서 실행 안됨")
	
	
if (true) {
	System.out.println("if문에서 실행됨");
	System.out.println("if문에서 실행 안됨")
}
```

## switch 문

- if 문을 더 편리하게 사용할 수 있는 기능

```java
switch (조건식) {
	case value 1 : 
		break;
	case value 2:
		break;
	default:
	}
```

조건식 값 == 특정 case 값 → 해당 case 코드 실행함

break : 현재 실행 중인 코드 종료, switch 문 빠져나가기

— break 문 없으면 일치하는 case 이후의 모든 case 코드가 순서대로 실행됨

default : 조건식 ≠ 모든 case 값 → 실행 (else와 같은 역할)

- if 문 switch 문 비교

— if 문 : 비교 연산자 (>, ≥, =, ≤, <) 사용 가능

— switch 문 : 조건식이 특정 case와 같은지만 확인 가능

## 삼항 연산자 (=조건 연산자) >> ?:

- 단순히 참, 거짓에 따라 값 구하는 경우 ?: 연산자 사용해서 코드 단순화할 수 있음
- 삼항 연산자 : 항이 3개라는 뜻 (조건, 참 표현식, 거짓 표현식) 으로 자바에서 유일한 3개 항 연산자
- 조건 연산자 : 특정 조건에 따라서 결과가 나와서 조건 연산자

(조건) ? 참 표현식 : 거짓 표현식