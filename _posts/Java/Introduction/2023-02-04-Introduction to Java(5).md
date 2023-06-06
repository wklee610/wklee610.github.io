---
title: Introduction to Java (5) - 클래스와 객채 1
author: Hajun
date: 2023-02-04 01:00:00 +0900
categories: [Java, Introduction to Java]
tags: [java]
---

## 1. 객체 지향 프로그래밍과 클래스 (절차지향 vs 객체지향)
- - - 
절차지향 프로그래밍이란 물이 위에서 아래로 흐르는 것처럼 순차적인 처리가 중요시 되며 프로그램 전체가 유기적으로 연결되도록 만드는 프로그래밍 기법입니다. 대표적인 절차지향 언어에는 C언어가 있습니다. 이는 컴퓨터의 작업 처리 방식과 유사하기 때문에 객체지향 언어를 사용하는 것에 비해 더 빨리 처리되어 시간적으로 유리합니다. 옛날에는 하드웨어와 소프트웨어의 개발 속도차이가 크지 않았습니다. 하지만 하드웨어의 빠른 발전을 통해 컴퓨팅 환경은 급속도로 증가했지만 소프트웨어 개발 시간이 따라가지 못하게 되고 이런 상황에 소프트웨어의 개발시간을 단축하되 하드웨어에 기본적인 사양을 잡아먹어도 더 이상 큰 단점이 아니기에 모듈화, 캡슐화해서 개념적으로 접근하는 형태를 갖는 객체지향 프로그래밍이 탄생했습니다. 객체지향 프로그래밍은 개발하려는 것을 기능별로 묶어 모듈화를 함으로써 같은 기능을 중복으로 연산하지 않거나 모듈을 재활용하기 때문에 유지보수에 유리합니다.


  * 클래스란?
    + 객체 지향 프로그램은 클래스를 기반으로 프로그래밍합니다.  
    + 클래스는 객체의 속성과 기능을 코드로 구현한 것입니다.


## 2. 클래스 살펴보기
- - - 
클래스에 선언하는 '멤버 변수'는 다른 말로 속성(property), 특성(attribute) 등으로 표현하기도 합니다.

### 패키지란?
패키지는 클래스 파일의 묶음입니다. 패키지를 만들면 프로젝트 하위에 물리적으로 directory가 생성됩니다. 또한 패키지는 계층 구조를 가질 수 있는데, 프로젝트를 수행할 때 패키지의 계층 구조를 구성하는 것은 전체 프로젝트의 소스 코드를 어떻게 관리할지와 관련 있습니다.

### 패키지 선언하기
```
package domain.student.view;

public class StudentView {

}

클래스 이름은 StudentView이지만, 클래스 전체 이름은 domain.student.view.StudentView입니다.
```


## 3. 메서드
- - - 
매서드는 함수(function)의 한 종류입니다.

### 함수란?
함수는 '하나의 기능을 수행하는 일련의 코드' 혹은 어떤 기능을 수행하도록 미리 구현해 놓고 필요할 때마다 호출하여 사용할 수 있습니다.

### 함수 정의하기
```
int add (int num1, int num2) {
    int result;
    result = num1 + num2;   //num1 + num2를 더한 최종 값
    return result;          // 최종 값 반환
}

add = 함수 이름
(int num1, int num2) = 매개 변수
return = 반환
int = 함수 반환형
```

### 함수 호출과 스택 메모리 (stack memory)
함수를 호출하면 그 함수만을 위한 메모리 공간이 할당 되는데, 이 메모리 공간을 스택(stack)이라고 부릅니다.  
스택은 자료가 상자처럼 쌓이는 자료 구조를 말하는데, 마지막에 추가된 자료부터 순서대로 꺼내서 사용할 수 있으며 LIFO(Last In First Out) 구조라고 합니다.  


### 함수의 장점
  * 기능을 나누어 코드를 효율적으로 구현 가능 (main에만 때려넣지 않아도 됨)
  * 기능별로 함수를 구현해 놓으면 같은 기능을 매번 코드로 만들지 않고 그 기능의 함수를 호출

## 4. 클래스와 인스턴스
- - - 
클래스를 사용하여 프로그램을 실행하려면 먼저 main() 함수를 알아야합니다. main() 함수는 자바 가상 머신(Java Virtual Machine; JVM)이 프로그램을 시작하기 위해 호출하는 함수입니다. 클래스 내부에 만들지만, 클래스의 메서드는 아닙니다.
main() 함수에서 클래스를 사용하는 방법은 두가지 있습니다.
  * 우리가 만든 클래스 내부에 main() 함수를 만든다.
  * 외부에 테스트용 클래스를 만들어 사용한다.

  
  
### new 예약어로 클래스 생성하기
자바에서 클래스를 생성할 때는 new 예약어를 사용하고 이어서 생성자를 써줍니다.
클래스 자료형 변수를 선언하고 new 예약어로 생성자를 호출하여 대입하면 새로운 클래스가 생성됩니다. 클래스가 생성된다는 것은 클래스를 실제 사용할 수 있도록 메모리 공간(힙 메모리; heap memory)을 할당 받는다는 뜻입니다. 이렇게 실제로 사용할 수 있도록 생덩된 클래스를 '인스턴스'라고 합니다.

```
클래스형 변수 이름 = new 생성자;
Student studentLee = new Student();
```

### 인스턴스와 참조 변수
  * 객체
    + 객체란 '의사나 행위가 미치는 대상' 입니다.
  
  * 클래스
    + 객체를 코드로 구현한 것이 클래스 입니다.
  
  * 인스턴스
    + 클래스가 메모리 공간에 생성된 상태를 인스턴스라고 합니다.
  
  * 참조 변수
    + ```
    studentLee.studentName = "Lee";   //이때 .이라는 도트 연산자 사용
    ```

### 인스턴스와 힙메모리
new student()를 선언하면 student 하나가 생성되는데 각 student는 studentID, studentName 등의 멤버 변수를 가지고 있습니다. 이때, 이들 변수를 저장할 공간이 필요합니다. 이때 사용하는 메모리가 힙 메모리(heap memory) 입니다.

### 힙 메모리란?
힙(heap)은 프로그램에서 사용하는 동적 메모리(dynamic memory) 공간을 말합니다. 일반적으로 프로그램은 스택, 힙, 데이터 이렇게 세 영역을 사용하는데, 객체가 생성될 때 사용하는 공간이 힙입니다. 힙은 동적으로 할당되며 사용이 끝나면 메모리를 해제해 주어야 합니다. C나 C++과 같은 언어에서는 개발자가 직접 메모리를 해제해야 하지만, 자바에서는 가비지 컬렉터(garbage collector)가 자동으로 메모리를 해제해 줍니다.

## 5. 생성자 (Constructor)
- - - 

```
package constructor;

public class PersonTest {
    public static void main(String[] args) {
        Person personLee = new Person();    // 이때 new 'Person()' = 생성자
    }
}
```

### 디폴트 생성자 (default constructor)
생성자가 없는 클래스는 클래스 파일을 컴파일할 때 자바 컴파일러에서 자동으로 생성자를 만들어 줍니다.



### 생성자 만들기
생성자는 주료 멤버 변수에 대한 값들을 매개변수로 받아서 인스턴스가 새로 생성될 때 멤버 변수 값들을 초기화 하는 역할을 합니다. 즉, 인스턴스가 생성됨과 동시에 멤버 변수의 값을 지정하고 인스턴스를 초기화하기 위해 생성자를 직접 구현하여 사용합니다.


### 생성자 오버로드 (constructor overload)
클래스에 생성자가 두 개 이상 제공되는 경우를 생성자 오버로드(constructor overload)라고 합니다. 필요에 따라 매개변수가 다른 생성자를 여러 개 만들 수 있습니다. 


## 6. 참조 자료형
- - - 
크기가 정해진 기본 자료형(int, char, float, double 등)으로 선언하는 변수가 있고, 클래스 자료형으로 선언하는 참조 자료형 변수가 있습니다.

```
package reference;

public class Subject {
    String SubjectName;
    int scorePoint;
}

public class Student{
    int studentID;
    String studentName;
    Subject korean;
    Subject math;
}
```



## 7. 정보 은닉 (public vs private)
- - - 
```
package hiding;

public class Student{
    int studentID;
    private String studentName;         //private한 값
    int grade;
    String address;

    public String getStudentName() {
        return studentName;        
    }

    public void setStudentName() {
        this.studentName = studentName;
    }
}

getStudentName() or setStudentName()으로 우회해서 사용 가능
```


