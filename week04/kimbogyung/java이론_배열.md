# java이론_배열

## 배열 : 같은 타입의 변수를 사용하기 편하게 하나로 묶은 것

배열이 필요한 이유 ? 

```java
int student1 = 90;
int student2 = 90;
int student3 = 70;
int student4 = 60;
int student5 = 50;

System.out.println("학생1 점수 : " + student1);
System.out.println("학생2 점수 : " + student2);
System.out.println("학생3 점수 : " + student3);
System.out.println("학생4 점수 : " + student4);
System.out.println("학생5 점수 : " + student5);
```

학생을 더 추가해야 할 때, 학생이 수백 명 이상이라면, 학생 수에 비례하여 코드 양이 증가함. 비슷한 변수를 반복해서 선언하는 문제가 발생

—> 같은 타입 변수를 반복 선언하고 반복 사용하는 문제를 해결한 것 : 배열

## 1. 배열 변수 선언

- int[] students; 
배열 변수를 선언해야 배열을 사용할 수 있음 // 일반 변수와의 차이점 : 변수 타입 다음 [] 대괄호가 들어감
- 변수 선언했다고 해서 사용할 수 있는 배열이 만들어진 것은 아님
- 배열 변수에는 10,20 같은 값이 아닌 배열을 담을 수 있음

## 2. 배열 생성

- students = new int [5]; (5개의 int공간이 생성되고 0으로 자동 초기화됨)
배열 사용하려면 배열을 생성해야 함
- new : 새로 생성한다는 뜻, int[5] : int형 변수가 5개라는 뜻

## 3. 배열 초기화

- new int [5] 는 총 5개의 int형 변수가 만들어진 것
- 자바는 배열 생성할 때, 내부값을 자동으로 초기화 함
- 숫자 : 0 | boolean : false | String : null로 초기화 됨

## 4. 배열 참조값 보관

- new int [5]로 배열 생성하면 그 크기만큼 메모리 확보함
int형 5개 사용 → 5byte * 5 = 20byte 확보
- 배열 생성하면, 자바는 해당 배열에 접근할 수 있는 참조값(=주소) 반환함
- 앞서 선언한 배열 변수 int [] students에 생성된 배열 참조값 보관함 —> int [] students 변수는 new int [5]로 생성한 배열의 참조값을 가짐
참조값을 통해 메모리의 실제 배열에 접근하고 사용할 수 있음
배열 생성하는 new int [5]에는 아무런 이름이 없기 때문에 생성한 배열에 접근하는 방법이 필요함 —> 배열 생성 시 반환되는 참조값을 보관해야 함 (int[] students 변수에 참조값이 보관되었으므로 이 변수를 통해 배열에 접근할 수 있게 됨)

## 배열 사용

배열 사용 방법 : students [0] 처럼 대괄호 [] 사이에 배열 위치를 나타내는 인덱스 번호를 넣어줌 (인덱스 번호는 0부터 생성되므로 int[5]의 인덱스는 0,1,2,3,4,5가 존재하게 됨)

## 배열에 값 대입

```java
students[0] = 90; //배열에 값 대입하는 방법
x001[0] = 90; // 변수의 참조값을 통해 실제 배열에 접근하여 값 대입
```

## 배열 값 읽기

```java
System.out.println("학생1 점수 : " + students[0]; //변수 참조값을 통해 실제 배열에 접근
```

## 기본형과 참조형

자바의 변수 데이터 타입은 크게 기본형과 참조형으로 분류

기본형 : 사용하는 값 직접 넣을 수 있음  (int, long, double, boolean)

- 선언과 동시에 크기가 정적으로 정해짐

참조형 : 배열 변수처럼 메모리 참조값 넣을 수 있음 (int [] students, 객체나 클래스 담을 수 있는 변수)

- 크기를 동적으로 할당할 수 있음

## 배열 리펙토링

리펙토링 : 기존 코드 기능은 유지하면서 코드를 개선하는 것 (중복 제거, 복잡성 줄이기 —> 이해하기 쉬운 코드 만들기)

- 생성과 동시에 초기화 하는 기능
int [] students = {90, 80, 70, 60,50};  —> 자바가 내부에서 배열 크기 보고 new int [5] 사용해서 배열 생성함

## 2차원 배열 (행과 열로 구성됨)

1. 2차원 배열 선언 
    - int [] [] arr = new int [2] [3]  —> 행 다음 열 번호

1. 2차원 배열 리펙토링

```java
System.out.println(arr[0][0] + " ");
System.out.println(arr[0][1] + " ");
System.out.println(arr[0][2] + " ");
System.out.println();
System.out.println(arr[1][0] + " ");
System.out.println(arr[1][1] + " ");
System.out.println(arr[1][2] + " ");
System.out.println();
```

행 출력 부분 출력이 거의 같고, [0]에서 시작할지, [1]에서 시작할지의 차이만 있음

```java
System.out.println(arr[row][0] + " ");
System.out.println(arr[row][1] + " ");
System.out.println(arr[row][2] + " ");
System.out.println();
```

## 향상된 for문 (각각의 요소 탐색한다는 의미로 =for-each문)

```java
for (변수 : 배열 또는 컬렉션 ) {
	반복할 작업
}
```

인덱스 사용X 종료 조건X

(왼쪽)반복할 때마다 찾은 값 저장할 변수 선언 : (오른쪽)에 탐색할 배열 선택

—> for문 끝나면 다음 값 꺼내서 number에 담고, 더 값이 없으면 for문 종료

- 향상된 for문 사용하지 못하는 경우

- int i 처럼 증가하는 인덱스값 직접 사용해야 하는 경우