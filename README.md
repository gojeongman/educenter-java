# 목차
 1. [JAVA란?](#java란) 
 2. [JAVA의 특징](#java의-특징)  
	2-1. [GC(Garbage Collection)](#gcgarbage-collection)  
	2-2. [Java 컴파일](#java-컴파일)
 3. [JDK? JRE?](#jdk-jre)  
	3-1. [JVM(Java Virtual Machine)](#jvmjava-virtual-machine)
 4. [Java Application 유형](#java-application-유형)  
	4-1. [Java 언어 활용처](#java-언어-활용처)
 5. [Java 프로그램 작성 규칙 및 기타 특징](#java-프로그램-작성-규칙-및-기타-특징)
 6. [Java Package/Module](#java-packagemodule)
 7. [Java 소스 코드의 구조](#java-소스-코드의-구조)
 8. [Java 데이터 타입](#java-데이터-타입)  
	8-1. [Promotion과 Casting](#java-데이터-타입---promotion과-casting)  
	8-2. [String](#string)
 9. [변수](#변수)  
	9-1. [인스턴스 변수의 개념](#인스턴스-변수의-개념)  
	9-2. [상수 변수의 개념](#상수-변수의-개념)  
	9-3. [클래스(전역, static) 변수의 개념](#클래스전역-static-변수의-개념)  
	9-4. [Main 메서드의 특성 및 멤버변수 사용 관련](#기타---main-메서드의-특성-및-멤버변수-사용-관련)
 10. [Java의 메모리 종류](#java의-메모리-종류)
 11. [Java 출력 메서드](#java-출력-메서드)
 12. [Java 입력 메서드](#java-입력-메서드)
 13. [연산자 분류](#연산자-분류)  
	13-1. [비교 연산자](#비교-연산자)  
	13-2. [산술 연산자](#산술-연산자)  
	13-3. [비트 연산자](#비교-연산자)  
	13-4. [shift 연산자](#shift-연산자)  
	13-5. [논리 연산자](#논리-연산자)  
	13-6. [삼항 연산자](#삼항-연산자)  
	13-7. [기타 연산자 문제](#기타-연산자-문제)
 14. [제어문](#제어문)  
	14-1. [조건문(if)](#조건문if)  
	14-2. [조건문(switch)](#조건문switch)
 15. [반복문](#반복문)  
	15-1. [반복문(for)](#반복문for)  
	15-2. [반복문(while)](#반복문while)  
	15-3. [반복문(do ~ while)](#반복문do--while)
 16. [배열(Array)](#배열array)
 17. [열거(Enum) 타입](#열거enum-타입)
 18. [클래스(Class)](#클래스class)  
	18-1. [프로그램의 발전(왜 Java에서는 Class라는 것을 쓰는가?)](#기타---프로그램의-발전왜-java에서는-class라는-것을-쓰는가)  
	18-2. [은행 입출금 로직 구성](#은행-입출금-로직-구성)
 99. [기타 - main 메서드에 인수 주기](#기타---main-메서드에-인수-주기)

---
<br/><br/>

## JAVA란?
 - 파이썬과 비슷한 시기에 등장한 언어이다
 - 만들어 질 때부터 객체 지향을 위해 만들어졌다.
	- 여러 가전제품에 OS 및 기능을 탑재하기 위해 Oak 라는 프로젝트가 있었다.
		- 그 당시에 기존에 존재하던 C, C++과 같은 언어를 탑재하려고 했으나 오동작이 발생하였다.
			- 당시 대부분의 언어는 OS(플랫폼)나 HW(CPU 등)에 맞게 컴파일 되도록 설계하였는데, 각 OS 마다 해당 환경에 맞는 컴파일러가 필요했는데 이는 비용적인 측면에서 낭비가 심했다.
        - 하여, OS나 HW에 상관 없이 다양한 환경에서 실행되는 이식성이 뛰어난 Cross Platform 언어의 개발에 착수했다.
        	- 이러한 배경을 바탕으로 **Write Once, Run AnyWhere(WORA)** 의 철학을 가진 JAVA가 탄생했다.
    - 하지만 당시 가전제품들은 메모리가 JAVA 프로그램을 구동시킬 수 있는 성능이 안되어 제대로 활용되진 못했다.
    - 그 이후, 인터넷의 도입이 되었는데 초기에는 단순히 사용자에게 UI만 제공하는 즉, View만을 위한 환경이였다.
    	- 추가로 CS 환경이라는 단점도 있었다.
    	- CSS나 JS 없이 HTML만 사용됬다고 생각하면 될 듯하다.
    - 위 단점으로 인해, 각 PC별로 소형 JVM을 탑재하여 JAVA를 활용한 여러 프로그램을 구동시켜 WEB 기술 발달의 도움을 주었다.
    	- 이 때, JAVA 1.0이 등장하였다.


## JAVA의 특징
 - OS(Platform)에 독립적이다.
 - 데이터 타입이 심플하다.
 - 클래스 기반의 객체지향 언어이다.
 - JRE와 JVM을 통해 OS에 독립적을 실행할 수 있다.
 - 컴파일 언어이면서 인터프리터 언어이다.
 	- **컴파일 언어**란?
 		- 컴파일 언어는 작성된 소스 코드를 컴퓨터가 해석할 수 있도록 **기계어로 번역**한 뒤, 번역된 코드를 한번에 **실행**하는 두 단계를 거쳐 진행된다.
 		- 컴파일 언어의 특징
			- 변수 선언시, 타입 선언이 필요하다.
 			- 컴파일이 오래 걸릴 수 있다.
 				- 프로그램이 일부 수정되더라도 다시 컴파일을 해야한다.
 			- 컴파일이 이미 된 파일이라면 빠른 속도로 실행이 가능하다.
 			- OS의 이식성이 낮다.
 				- OS마다 실행할 수 있는 기계어가 다른 경우가 있다.
 		- 대표적으로 C, C++ 등이 있다.
 	- **인터프리터 언어**란?
		- 소스 코드를 한줄씩, 번역과 실행을 동시에 한다.
			- 번역은 인터프리터를 통해 수행된다.
        - 인터프리터 언어의 특징
        	- 줄 단위로 번역과 실행을 하기 때문에 실행이 느리다.
        		- 다시 다 번역하고 실행을 해야해서
        	- 디버깅이 쉽다.
        		- 오류를 발견하면 해당 코드 밑으로는 번역 및 실행을 못하기 때문에 오류 발견이 쉽다.
        	- 운영체제 이식성이 좋다.
        		- OS마다 호환되는 인터프리터만 준비되어 있다면 바로 실행이 가능하다.
        - 대표적으로 Python, JavaScript 등이 있다.
	- Java는 컴파일 언어이면서 인터프리터 언어로 불린다.
		- **(컴파일 언어 측면)** JAVA는 다른 컴파일 언어들이 작동하듯이 컴파일러를 통해 전체 코드를 한번에 번역한다.  
		  여기서 사용하는 컴파일러를 **Java 컴파일러(Java Compiler, Javac)** 라고 하며,  
          이 Java 컴파일러는 작성한 **Java 코드를 Java 가상 머신(Java Virtual Machine, JVM)** 이 실행시킬 수 있는 **Java 바이트 코드(=class 파일)** 로 번역한다.
		- **(인터프리터 언어 측면)** Java 바이트 코드는 Java 가상 머신(JVM)의 **Java 인터프리터(Java Interpreter)** 를 이용하여 한 줄씩 실행된다.  
		  Java 바이트 코드로 작성되어 있는 내용을 Java 인터프리터가 한 줄씩 읽으면서 컴퓨터가 이해할 수 있는 기계어로 번역한 후, 실행을 시킨다.
        ![JAVA](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FRiA7a%2FbtroWoc4vww%2FBo7RiYJUjc4NFztR2VvEF1%2Fimg.png)
		- 처음에는 인터프리터 언어로써 활용되다가, 성능 향상을 위해 컴파일 언어의 장점을 가져왔다.
 - GC로 인해 사용자가 메모리 관리를 직접 할 필요가 없다.
	- 메모리 관리로부터 free 하다.
 - 객체지향 언어의 특성인 상속을 활용하여 멀티스레드 프로그래밍이 용이하다.
	- 멀티스레드 환경을 제공하기 때문에 동시에 여러 작업을 수행할 수 있어, 사용자에게 매우 빠른 환경을 제공한다.
	- 다른 프로그래밍 언어에서 멀티스레드를 사용하기 위해서는 자원을 같이 사용하거나 하는 사항들로 인해 균등하게 처리하게 한다든지 등의 처리를 해줘야해서 어려움이 다소 있다.  
	  그러나 Java는 메모리와 같은 자원 관리가 능동적으로 되기 때문에 비교적 쉽게 구현 가능하다.
	  	- 스레드가 자원을 공정하게 사용하지 못하면 기아상태가 발생하여 프로그램에 영향이 발생할 수 있다.
	  		- 스레드(Thread) : 프로그램(Process) 내에 실행 단위

### GC(Garbage Collection)
 - Java의 메모리 관리 방법 중의 하나이다.
 - JVM 내에 존재하며, Heap 영역에서 동적으로 할당했던 메모리 중 **필요 없게 된 메모리 객체(Garbage)** 를 모아 주기적으로 제거한다.
 - 프로그램을 개발 하다 보면 **유효하지 않은 메모리**인 Garbage가 생성된다.  
   c언어와 같은 프로그래밍 언어에서는 수동으로 메모리 초기화를 해줘야 하나, Java는 GC가 메모리를 주기적으로 감시하여 메모리 초기화를 해준다.
 - GC로 인해 Java는 높은 성능을 유지 할 수 있다.

### Java 컴파일
 1. .java 파일 생성 및 내용 작성
 2. javac 명령어로 컴파일 진행
 	- 이 때, 컴파일을 함으로써 바이트 코드(=.class) 파일이 생성된다.
 	```cmd
 	javac [만든파일명].java
 	```
 3. 실행
 	- .class는 생략
 	```cmd
 	java [만든파일명]
 	``` 


## JDK? JRE?
 - JDK(Java Development Kit)
	- Java를 사용하기 위한 필요한 기능을 모두 갖춘 Java용 SDK이다.
		- SDK(Software Development Kit) : 소프트웨어나 Application 개발할 때 사용하는 도구 모음이다.
	- JRE에 있는 모든 것뿐만 아니라 컴파일러(javac), 인터프리터(JVM)와 jdb, javadoc, 애플릿뷰어, 역컴파일러 등과 같은 도구들도 있다.
		- 즉, JRE의 상위 도구로 JRE의 도구를 모두 포함하고 있다.
	- 즉, JDK는 프로그램을 생성하고 컴파일 할 수 있다.
 - JRE(Java Rumtime Environment)
	- Java 가상머신(JVM), Java 클래스 라이브러리(Java Class Library), Java 명령(Java Command), 클래스 로더, Java API, 런타임 라이브러리 및 기타 인프라를 포함한 컴파일된 Java 프로그램을 실행하는데 필요한 패키지이다.
 - 즉, Java 프로그램을 실행하는데에 초점을 두면 JRE만 설치하면 되고, Java 프로그래밍을 하고자 하면 JDK를 설치해야 한다.
 ![JAVA](https://blog.kakaocdn.net/dn/CV4I1/btrIWNWYpxB/2W71zT3jfJ3PVOtVzUZMDK/img.png)
 ※ 참고 : https://inpa.tistory.com/entry/JAVA-%E2%98%95-JDK-JRE-JVM-%EA%B0%9C%EB%85%90-%EA%B5%AC%EC%84%B1-%EC%9B%90%EB%A6%AC-%F0%9F%92%AF-%EC%99%84%EB%B2%BD-%EC%B4%9D%EC%A0%95%EB%A6%AC

### JVM(Java Virtual Machine)
 - Java를 실행하기 위한 Machine이다.
	- 인터프리터라고 봐도 된다.
 - Java로 작성된 프로그램은 JVM에서만 실행 가능하다.
 - JVM은 JRE에 포함되어 있다.
 - Java는 OS에 종속적이지 않다는 특징을 가지고 있다.  
   OS에 종속받지 않고 실행되기 위해서는 OS 위에서 Java를 실행시킬 무언가가 필요한데 그게 바로 JVM이 하는 역할이다.
	- 위와 같은 JVM의 역할로 인해 Java 코드의 이식성이 좋다고 할 수 있다.
   ![JAVA](https://blog.kakaocdn.net/dn/KQ5T5/btrINvvYlVI/oWQkUmKFpxFK317idKkbN0/img.jpg)


## Java Application 유형
 - Java는 사용되는 유형에 따라 사용되는 기술이나 실행 방식이 다르며, 그에 따라 다양한 환경에서 유연하게 동작 가능하다.
 1. Standalone Application
	- 서버 없이 독립적으로 실행 가능하다.
	- Java의 프로그램의 시작과 끝은 **public static void main(String[] args)** 이며, Standalone Application에서 필요한 메서드이다.
		- Java 실행 시, 제일 먼저 main 메서드를 실행한다.
 2. Client/Server Application
	- Client ↔ Server 간의 통신을 위해 동작하는 Application 이다.
		- Java는 Client/Server 어디서든 구성될 수 있다
	- 예시로 아래와 같은 대상들이 있다.
		- 채팅 서버(Web Socket 기반)
		- Web Application(HTTP 프로토콜 기반)
			- Web Application에서는 Java뿐만 아니라 JSP, Servlet도 활용한다. 
 3. Embeded Application
	- 하드웨어를 제어하거나 임베디드 시스템에서 동작하는 Application 이다.
	- 작은 메모리 공간과 리소스를 가진 장치에서 동작하도록 최적화된 Application 이다.
	- 일반적으로 Java 보다는 C언어를 활용한다.
	  - 하드웨어와 직접적인 연관되어 있기 때문에 Java의 성능보다는 C언어와 같은 언어가 선호된다.
	- Java에서는 JavaME(Java Micro Edition)과 같은 특수한 버전이 활용된다.
	- 예시로 아래와 같은 대상들이 있다.
		- 스마트폰
		- 가전 제품
		- IOT 장치
 4. 분산 Application(Distributed Application)
	- 여러 시스템이나 서버가 분산되어 협력하여 동작하는 Application 이다.
		- 각기 다른 물리적 또는 가상적 위치에 분산된 컴퓨터에서 실행할 수 있다.
	- 시스템 간의 네트워크를 통해 이뤄지며, 일관성 있는 데이터 처리와 트랜잭션 관리가 중요하다.
	- Java는 RMI(Remote Method Invocation), EJB(Enterprise JavaBeans), JMS(Java Message Service) 등의 다양한 분산처리 기술을 지원한다.
	- 예시로 아래와 같은 활용처가 있다.
		- 마이크로서비스 아키텍처 기반의 Application.
		- 대규모 시스템에서 데이터 분산 처리 및 상호작용이 필요한 Application.

### Java 언어 활용처
 - web 기반 Enterprise Application
 - bigdata 저장, 수집, 분석 라이브러리 (분산환경 지워느 hadoop, spark...)
 - mobile app (android...)


## Java 프로그램 작성 규칙 및 기타 특징
 - 대소문자를 구분해야한다.
 - 언어의 실행 문장은 **;** 으로 종료한다.
 - class와 메서드는 **{}** 으로 감싸져 있어야 한다.
 - Java에서 프로그램 구현(실행)단위는 class 이다.
	- 변수를 하나 정의하는 경우에도 class 내에서 정의한다.
	- 독립적인 실행 메서드인 main도 class 내에 정의된다.
 - 주석은 코드의 설명문으로 프로그램 동작에는 영향이 없다.
	```java
	// 한줄 주석입니다.
	/* 여러 줄
	   주석 입니다. */
	```
 - Annotation 사용 시, class/메서드/변수 선언 앞에 @로 표기한다.
	- 어노테이션(Annotation)
		- 주석은 개발자에게 정보를 제공한다.  
		  반면 어노테이션의 경우 JVM에게 정보를 제공한다.
		- 즉, 개발자가 프로그램을 작성하지 않더라도 어노테이션을 통해 JVM에 제공한 정보를 토대로 프로그램 동작을 할 수 있도록 한다.
			- JVM 동작에 대해 간접적으로 영향을 주게 되는 것이다.
 - 모든 OS와 관련 없이 표준 출력(=모니터 출력)은 System.out을 사용한다.
 - Java에서 프로그램 구현 단위, 실행 단위는 class 이다.
- 변수를 선언하는 경우 class 내에서 선언이 되어야 한다.
	- 즉, class 외부에서 변수 선언이 이뤄질 수 없다.
- main 메서드는 class와 무관하게 독립적으로 실행 가능한 메서드이다.
	- 그러나 독립적으로 선언은 불가하여 main 메서드 또한 class 내에 선언된다.


## Java Package/Module
 - package : 객체 유형을 grouping 하는 개념
	- 모두 소문자여야 한다.
	- 절대 java 로 문자가 시작되면 안된다.
	- 하위 패키지도 포함하는 경우 중첩하여(.으로 구분) 사용할 수 있다.
	```text
	상위패키지.하위패키지.클래스
	ex) com.samsung.login
	```
 - Module : 외부에서 재사용 할 수 있는 Package를 묶어 놓은 것을 말한다.


## Java 소스 코드의 구조
```java
package com.samsung;
 // 선언하거나 안할 수 있다.
 // 선언할 경우에는 한번만 선언 가능하다.

import java.util.Scanner;
 // 선언하거나 안할 수 있다.
 // 여러 모듈을 import 하는 경우에는 java.util.*; 으로도 작성 가능하다.
 /* java.lang.* 내의 모듈들은 선언하지 않아도 자동으로 import 된다.
    예시로 String과 같은 Class는 별도 import 없이 사용 가능하다.
	java.lang.* 외에 다른 패키지는 명시적으로 import가 필요하다. */

public class A {

}

class B {
	/* class는 1개 이상 여러개 정의할 수 있다.
	   단, 여러개 정의 할 경우, public class는 하나여야 한다.
	   main 메서드의 경우에는 public class 내에 존재해야한다. */
	// A.java 로 파일이 작성된 경우 JVM은 A라는 파일 명칭에 따라 A라는 class를 우선으로 찾아 그 하위에 main 메서드를 동작 시킨다.
		// 위 특성 때문에 public class 명칭 또한 파일명과 일치하도록 작성하는 것을 권장한다.
		// 모두가 그런건 아니지만 대부분의 IDE와 Framework가 그렇다.
}
```


## Java 데이터 타입
 - 데이터 유형
 	- 문자열 Data : String 참조자료형(객체)
	- 수치 Data : byte, short, int, long, float, double 기본 자료형
	- 날짜 Data : Date, Callendar 참조자료형(객체)
	- 복합 Data : 배열, 사용자 정의 object(class)
 
 - 기본 타입(Primitive Type)
	- 변수선언, 할당 연산자(=)와 함께 사용된다.
	- 종류는 아래와 같다.
		- 논리값(boolean)
		- 정수(byte, short, int, long)
		- 실수(float, double)
		- 문자(char)
	- 추가로 Java에서 String은 기본 타입이 아닌 참조 타입. 즉, 별도의 객체이다.
 - 참조 타입(Reference Type)
	- new 키워드를 이용해서 생성한다.
	- 종류는 아래와 같다.
		- class
		- interface
		- 배열
		- enum
			- enum은 상수 객체들의 모음이다.
		- String
			- String은 별도 타입이라기 보다는 class에 포함되긴 한다.
			- 이해를 위해 별도 표기
	```java
	Scanner input = new Scanner(System.in); // 객체 생성 및 핸들변수(input) 선언
	```
	- 객체 유형을 말하기도 한다.
	- 핸들변수.속성 = 값 / 핸들변수.메서드() 등과 같이 주로 . 연산자와 함께 사용된다.
	```java
	String name = input.next(); // 핸들변수(input)의 메서드(next())사용
	```
 - boolean 타입 특성
 	```java
	boolean = true; // 0과 1도 boolean을 의미하지만 java에서는 정수값을 boolean 타입에 사용하는 것을 허용하지 않는다.
	```
 - 정수 타입 특성
 	- 데이터는 Binary 타입으로 활용된다.
	- java의 기본 정수 타입은 int이기 때문에 Long 타입 사용시에는 값의 맨 뒤에 L 또는 l로 Long 타입임을 알려줘야 한다.
	```java
	Long n1 = 2147483648L;
	```
	- 정수에 대한 산술 연산은 순환되어 처리된다.
	```java
	int n1 = 2147483647; // 4byte 할당 -2147483648 ~ 2147483647
	System.out.println(n1);
	n1 = n1+1;
	 /* 2진수상 +1은 맨앞에 bit를 1로 바꾸게 되는 결과가 된다.(011 → 100이 되는 것 같은 개념)
	    이는 정수에 대한 산술 연산은 binary값이 순횐되어 처리된다는 것을 알 수 있다.
	 */
	System.out.println(n1);
	```
 - 실수 타입 특성
	- java의 기본 실수 타입은 double이기 때문에 float 타입 사용시에는 값의 맨 뒤에 F 또는 f로 float 타입임을 알려줘야 한다.
	```java
	float f1 = 0.5F;
	```
	- 부동수소점 개념이 있어 지수부와 가수부가 나뉜다.
 - 문자 타입 특성
	- 문자는 I/O 에서 설계된 최소 단위의 범위를 사용한다.
	- 유니코드를 지원한다. (ASCII 코드를 포함한다.)
		- 모든 문자의 인코딩 값은 숫자 이다.

### Java 데이터 타입 - Promotion과 Casting
 - Promotion(자동 타입 변환)
 	- 묵시적으로, 자동으로 데이터 타입이 변환하는 것을 의미한다.
 	- 값의 Range(허용 범위)가 작은 타입이 허용 범위가 큰 타입으로 대입될 때 발생한다.
	```java
	short s1 = 127;
	int n1 = s1; // short → int로의 자동 형변환이 발생한다. (Promotion)
	```
 - Casting(강제 타입 변환)
	- 큰 Range의 타입은 작은 Range의 타입으로 자동 타입 변환이 될 수 없는데, 이를 이행하고자 할 때 강제 타입 변환을 수행하게 된다.
	- Casting은 () 연산자를 사용한다.
	```java
	int n1 = 127;
	byte b1 = (byte)n1; // int → byte의 강제 형변환 진행. (Casting)
	```
 - Range(허용범위)란 데이터 타입이 가질 수 있는 값의 범위를 말한다.
	- int : -2,147,483,648 ~ 2,147,483,647
 - 예외로 특수한 경우가 몇몇가지 있다.
	- boolean ↔ 정수는 서로 호환되지 않는다.
	- short ↔ char는 서로간의 타입이 달라 casting을 해야한다.


### String
 - java.lang.String 클래스가 상수 문자열 데이터를 다루기 위해 설계된 참조 타입
	- 참조 타입은 new 키워드를 통해 객체 생성이 가능하기 때문에 String 또한 객체로 생성 가능하다.
	- String의 경우에는 new 키워드 없이도 객체 생성이 가능하다.
		- 단, 어떤 방식으로 객체를 만드냐에 따라 메모리 생성 위치가 달라진다.
	```java
	String str1 = new String("java"); // heap 메모리에 생성된다.
	String str2 = "java"; // 상수 pool 메모리에 생성된다.

	"java".length();
	// 참고로 String은 literal 값 또한 객체로 판단하여 String 클래스의 메서를 활용 가능하다.
	// 리터럴(literal)이란? 데이터(값) 자체를 의미한다.
	```
	```java
	String s = new String("자바 프로그램");
	 // String은 상수 문자열을 위해서 설계되어서 변경이 되지 않는다.
	 // 즉, 원래 String은 자기가 가지고 있는 문자열을 변경하지 않는다.
	s.replace("자바", "Java");
	String result = s.replace("자바", "Java");
	 // String은 값 변경되지 않기 때문에 새로 선언해야 한다.
	System.out.println(s);
	System.out.println(result);
	```

## 변수
 - 변수는 데이터가 저장된 메모리 주소 대신 참조하는 이름(identifier, 식별자)을 말한다.
	- 메모리 주소에 직접 Access 할 수 없기 때문에 이름을 부여한다고 생각하면 된다.
 - 정해진 Naming Rule이 있다.
	- 영문자로 시작
	- 특수문자로 시작 가능(_ 혹은 $ 만 허용)
	- 두번째 문자부터는 숫자 허용
	- 길이 제한이 없다.
		- 그러나 쉽게 알아볼 수 있게 하기 위해 간략하게 만드는 편이다.
	- 키워드(예약어) 불가
	- 이미 제공되는 class 이름을 쓸 수 없다.
		- 일반적인 경우에는 상관 없으나 java.lang 패키지는 자동 import 되는 것과 마찬가지 이기 때문에 java.lang 패키지에 있는 class 명은 변수명으로 지정하면 안된다.
		- java.lang 패키지 외에도 추가적인 패키지를 import 하면 그 패키지 내부에 있는 class 명칭도 변수로 사용하면 안된다.
 - 변수의 종류는 아래와 같이 있다.
	- 멤버 변수(선언 위치 : 클래스 영역)
		- 클래스 영역에 선언된 변수
		- 별도로 초기화 하지 않아도 자동으로 초기화 된다.
		- **클래스 변수, 인스턴스 변수**를 통틀어 칭한다.
	- 인스턴스 변수(선언 위치 : 클래스 영역)
		- 객체마다 고유한 속성값을 가지는 변수이다.
			- 값을 변경 가능하다.
		- 클래스 영역에 선언되고 인스턴스 생성 시에 만들어진다.
		- 인스턴스 값의 변수를 활용하고자 하면 인스턴스를 먼저 생성해야한다.
			- new를 통한 객체(=인스턴스) 생성
	- 클래스 변수(선언 위치 : 클래스 영역)
		- 전역변수라고 한다.
		- 인스턴스 변수 앞에 static을 붙이기만 하면 된다.
		- 인스턴스 변수는 인스턴스 마다 고유한 값을 가지나, 클래스 변수는 모든 인스턴스가 공통된 값을 공유하게 된다.
			- 하나의 클래스로부터 생성된 모든 객체들이 공유하는 변수이다.
		- 클래스 로딩 될 때, 생성된다.
			- 따라서 메모리에 딱 한번만 올라간다.
				- 즉, 아무리 객체를 생성해도 메모리에 새로 올라가지 않는다.
			- 클래스 영역의 메모리에 저장이 되기 때문에 Heap에 객체가 저장되지 않는다.
			- 값은 그대로 Stack 영역에 저장된다.
		- public을 붙이면 같은 프로그램 내에 어디서든 접근 가능한 **전역 변수**가 된다.
		- 인스턴스 변수의 접근법(new로 객체 생성)과 달리 인스턴스 생성 없이 **클래스이름.변수이름** 을 통해 접근 가능하다.
	- 상수
		- 객체의 변경 불가한 값
		- 객체 생성시점에 반드시 초기화되어야 한다.
		- 하나의 클래스로부터 생성된 모든 객체들이 동일한 값의 속성을 가져야 하는 경우 사용.
	- 로컬 변수(선언 위치 : 메서드 영역)
		- 메서드 내에 선언되며 , 메서드 안에서만 사용 가능한 변수이다.
		- 자동 초기화가 되지 않아, 명시적 초기화 후에 참조 및 사용 가능하다.
			- 단, 배열은 제외
		- 메서드 실행 시, 생성(메모리 할당)되며, 메서드가 종료되면 메모리상에서도 삭제되어 사용할 수 없게 된다.
	- 매개 변수(선언 위치 : 메서드 영역)
		- 메서드에서 입력값을 받을 때 사용되는 변수이다.
		- 메서드 내에 선언된 것으로 간주하므로 지역변수와 동일하다.

### 인스턴스 변수의 개념
```java
public class ClassEx1 {
	public int num; // 인스턴스 변수
	 // 생성자 메서드를 정의하지 않으면 자동으로 컴파일 시점에 파라미터가 없는 default 생성자가 추가(생성)된다.
		// 즉, 생성자 구성 없이 객체를 생성하여 쓸수 있다
	 // 단, 생성자 메서드를 명시적으로 정의하면 default 생성자가 추가(생성)되지 않는다.
	public static void main(String[] args) {
		ClassEx1 ex = new ClassEx1();
		System.out.println(ex.num); // 0
		ex.num = 1;
		System.out.println(ex.num); // 1
		
		ClassEx1 ex2 = new ClassEx1();
		System.out.println(ex2.num); // 0
		ex2.num = 100;
		System.out.println(ex2.num); // 100
		
		ClassEx1 ex3 = new ClassEx1();
		System.out.println(ex3.num); // 0
		ex3.num = 500;
		System.out.println(ex3.num); // 500
		
		ex = new ClassEx1();
		 // 최초로 객체 생성하였던 ex와는 다른 메모리 주소로 저장된다.
		 // 최초로 객체 생성하였던 ex는 누가 더 참조하지 않는한 GC에서 제거하게 된다.
		    // 이것이 인스턴스 변수의 특성이다.
		System.out.println(ex.num); // 0
	}
}
```

### 상수 변수의 개념
```java
public class ClassEx2 {
	public final int PORT = 9090; // 상수 변수
	 // 생성자 메서드에서 상수를 초기화 할 수 있다.
	 // 생성자 메서드가 명시적으로 정의되지 않은 경우, 상수는 선언시에 초기화해야 한다.
	public static void main(String[] args) {
		ClassEx2 ex = new ClassEx2();
		System.out.println(ex.PORT); // 9090
		// ex.PORT = 5000; // 변경 불가(에러 발생)
		
		ClassEx2 ex2 = new ClassEx2();
		System.out.println(ex2.PORT); // 9000
		 // 객체를 아무리 많이 생성해도 상주는 모두 동일한 값을 가진다.
	}
}
```

### 클래스(전역, static) 변수의 개념
```java
public class ClassEx3 {
	public static int ticket = 1000; // 클래스(전역) 변수
	 // 클래스(전역) 변수는 객체 생성 없이 클래스 이름으로 변수를 사용할 수 있다.
	public static void main(String[] args) {
		System.out.println(ClassEx3.ticket); // 1000
		ClassEx3.ticket -=5;
		System.out.println(ClassEx3.ticket); // 995
		
		ClassEx3 ex = new ClassEx3();
		System.out.println(ex.ticket); // 995 
		ex.ticket -=5;
		System.out.println(ex.ticket); // 990
		
		ClassEx3 ex2 = new ClassEx3();
		System.out.println(ex2.ticket); // 990
		ex2.ticket -=5;
		System.out.println(ex2.ticket); // 985
		
		System.out.println(ticket); // 985
		 // 메서드 내부에 동일한 변수가 없다면 Class 명칭 없이도 변수 사용이 가능하다.
		 // 단, 현재 위치한 클래스 내부에 변수가 존재해야한다.
		    // 다른 클래스에서 참조할 때는 불가하다는 얘기이다.
			// 다른 클래스에서 참조할 때는 객체를 생성하든, 클래스 이름으로 참조하든 해야한다.
		ticket -= 5;
		
		ex = new ClassEx3();
		System.out.println(ex.ticket); // 980
		ex.ticket -= 10;
		System.out.println(ex.ticket); // 970
		System.out.println(ClassEx3.ticket); // 970
		System.out.println(ex2.ticket); // 970
		
		/* 클래스 변수는 메모리에 딱 한번만 올라가기 때문에
		   객체를 여러번 생성해도 동일한 객체를 참조하는 것을 확인할 수 있다. */
	}
}
```

### 기타 - Main 메서드의 특성 및 멤버변수 사용 관련
 - JVM에서 Access해야하기 때문에 public이여야 한다.
 - 전체 영역에서 유일하게 하나여야 한다. (static)
	- 다수의 Main이 존재할 경우, JVM이 실행시킬 Main을 찾지 못한다.
 - Standalone Application에서 시작 및 끝 지점이기 때문에 별도 데이터 반환이 불필요하다. (void)
 - main 메서드는 class 소유의 메서드가 아니기 때문에 멤버 변수를 활용하지 못한다.
	- 아래 내용에서 main 메서드가 멤버 변수를 사용하지 못하는 이유에 대해서는 다음과 같다.
		- main 메서드는 Test 클래스의 멤버 메서드가 아니다.
		- main 메서드는 static이므로 non-static 변수는 객체를 생성해서 사용해야 한다.
	```java
	public class Test {
		boolean success; // 멤버 변수(인스턴스 변수)
		public static void main(String[] args) {
			//System.out.println(success); // 변수를 찾지 못해 오류 발생.
			
			Test ex1 = new Test();
			// main 메서드에서 멤버 변수를 사용하기 위해서는 별도로 객체 생성을 해줘야 한다.
			System.out.println(ex1.success);
		}
	}
	```


## Java의 메모리 종류
 - Java 프로그램을 실행 하게되면 JVM은 OS로부터 메모리를 할당받는다.  
   할당 받은 메모리는 Java 프로그램에 맞게 여러 영역으로 나눠 쓴다.
 - 각 영역은 목적에 맞게 사용되고, Application의 성능에 영향을 미친다.
   간략하게 메모리를 관리하지 않으면 StackOverFlow가 발생하여 Application이 강제 종류 할 수 있다.
	- StackOverFlow : 할당 받은 메모리 대비 Application이 더 많은 메모리를 사용하게 되는 경우
 - 대표적인 메모리 종류는 아래와 같다.
	- Heap 영역
		- 인스턴스를 생성할 때, 사용되는 메모리 영역이다.
			- **인스턴스 = 객체** 라고 생각하면 된다.
		- 참조형 데이터 객체의 실제 데이터가 저장되는 공간이다.
		- 객체 호출이 종료되도 삭제되지 않으며, GC에 의해 메모리에서 삭제된다.
		- 스레드 몇개가 존재하든, 단 하나의 영역만 존재한다.
		- new 키워드로 객체를 생성할 때, Heap에는 생성된 객체가 저장되고, Stack 영역에 생성된 객체에 대한 주소 값이 저장된다.
		```java
		Scanner input = new Scanner(System.in);
		 // input : Stack 영역
		 // Scanner(System.in) : Heap 영역
		```
	- Stack 영역
		- 기본 자료형(Primitive Type), 지역변수, 매개변수가 저장되는 메모리
			- int, double, boolean, byte 등등
		- 메서드가 호출될 때 메모리에 할당, 메서드 종료 시 메모리에서 삭제됨.
		- 스레드 개수 별로 1개씩 생성된다.
	- Static(Method) 영역
		- JVM이 동작해서 class가 로딩될 때 생성.
		- JVM이 읽어들인 class와 interface에 대한 런타임 상수 풀, 멤버 변수(필드), 클래스 변수(Static 변수), 상수(final), 생성자(constructor)와 메소드(method) 등을 저장하는 공간.
		- 어느곳에서나 접근이 가능하다.
		- 데이터는 프로그램이 시작부터 종료될 때까지 메모리에 남아있다.
	- 참고 : https://inpa.tistory.com/entry/JAVA-%E2%98%95-%EA%B7%B8%EB%A6%BC%EC%9C%BC%EB%A1%9C-%EB%B3%B4%EB%8A%94-%EC%9E%90%EB%B0%94-%EC%BD%94%EB%93%9C%EC%9D%98-%EB%A9%94%EB%AA%A8%EB%A6%AC-%EC%98%81%EC%97%AD%EC%8A%A4%ED%83%9D-%ED%9E%99
		- 각 상황별 메모리 저장되는 그림 참조


## Java 출력 메서드
 - 화면 출력(표준 출력)
	- 표준 출력 객체로 System.out과 System.err이 있다.
	```java
	public class Test {
		public static void main(String[] args) {
			System.out.println("Test1"); // 줄바꿈과 함께 입력값 출력
			System.out.print("Test2"); // 줄바꿈 없이 입력값 출력
			System.out.printf("이름은 %s 입니다.", "홍길동");
			 // 지시자를 통해 입력값을 여러 가지 형식으로 변환하여 출력
		}
	}
	```
	printf 지시자 종류|설명
   ---|---
   %b|boolean 형식으로 출력
   %d|정수 형식으로 출력
   %o|8진수 형식으로 출력
   %x 또는 %X|16진수 형식으로 출력
   %f|소수점 형식으로 출력
   %c|문자 형식으로 출력
   %s|문자열 형식으로 출력
   %n|줄바꿈
   %e 또는 %E|지수 표현식의 형식으로 출력
 - File로 출력
 - Socket을 이용해서 출력
	- Socket에 연결된 Target으로 출력이 전송됨.
	- java.net Socket으로부터 stream 객체를 받아와서 stream에 write


## Java 입력 메서드
 - 키보드 입력(표준 입력)
	- 표준 입력 객체로 System.in 이 있다.
	- I/O는 JRE 외부(OS, 키보드, 마우스 등)에서 발생하는 오류에 대해서 message로 전달받아서 처리애햐 하므로 예외처리가 필수이다.
	- 매번 예외처리를 하는 것이 번거로워 JDK5 버전에서 예외처리없이 입력을 받아올 수 있는 class(java.util.Scanner)가 추가되었다.
		- java.util.Scanner를 통해 키보드/마우스/File/Socket 등등에 대해 예외처리 구성을 안하고도 데이터를 받을 수 있다.
		- java.util.Scanner(키보드 | 파일 | Socket 객체)를 사용합니다.
	```java
	import java.util.Scanner;

	public class inputTest {
		public static void main(String[] args) {
			Scanner input = new Scanner(System.in);
			 // Scanner 라는 class 타입을 객체로 활용. (즉, 참조 타입이다)
			 // new를 통해 객체 생성
			 // System.in 은 키보드를 통해 받는 객체
			System.out.println("이름을 입력하세요 >> ");
			String name = input.next();
			System.out.println(name+"님");
		}
	}
	```
 2. File로부터 입력 : java.io.FileInputStream, java.io.FileReader
 3. Socket으로부터 입력 : java.net Socket으로부터 stream 객체를 받아와서 stream에서 read


## 연산자 분류
 - 단항 연산자(피연산자 1개) : +, -, ++, --, (), ~, !
	- ~ : 1의 보수 연산자
	- ! : 부정 연산자
	```java
	public static void main(String[] args) {
		int a = 3, b = 5;
		int result = ++a+ ++b;
		System.out.printf("a=%d, b=%d, result=%d \n", a, b, result);
		 // a=4, b=6, result=10 
		result = a++ + b++;
		System.out.printf("a=%d, b=%d, result=%d \n", a, b, result);
		 // a=5, b=7, result=10 
		System.out.printf("~a=%d \n", ~a); // 1의 보수 연산자
		 // ~a=-6 
		System.out.printf("!a=%d \n", !a); // 에러
         // 논리부정 연산자는 조건식 또는 boolean 타입에만 적용 가능하다.
		
		boolean success = false;
		System.out.printf("!success=%b \n", !success);
		 // !success=true 
		
		b = b+3; // 대입연산자
		b+=3; // 위 연산자와 동일한 의미 (성능 차이는 없음)
		System.out.printf("b=%d \n", b);
		 // b=10 
	}
	```
 - 이항 연산자(피연산자 2개) : 산술연산자, 비교연산자, 비트연산자, shift 연산자, 논리 연산자, 대입(할당) 연산자
 - 삼항 연산자(피연산자 3개) : (조건식? true표현식 : false 표현식)

### 비교 연산자
 - 종류 : >, <, >=, ...==, !=
 - 데이터의 반환은 항상 boolean 타입을 반환한다.
 - == 연산자의 경우, 기본 타입은 값을 비교하고 참조 타입은 메모리 주소 값을 비교한다.
	```java
	public static void main(String[] args) {
		int a = 3;
		int b = 5;
		System.out.println(a==b); // false
		System.out.println(a>b); // false
		System.out.println(a<b); //true
		System.out.println(a!=b); // true
		
		String st = new String("java"); // 참조 타입 저장소에 저장됨.
		String st1 = "java"; // 기본 타입 저장소에 저장됨.
		System.out.println(st == st1); // false

		String st2 = new String("java");
		String st3 = "java";
		System.out.println(st == st2); // false
		System.out.println(st1 == st3); // true
	}
	```

### 산술 연산자
 - 종류 : +, -, *, / , %
   ```java
   /* 9867원을 500원, 100원, 10원, 5원, 1원 동전의 최소 개수로 거슬러주려고 합니다.
   각가의 동전 개수를 출력하는 코드를 구현하세요 */
   public static void main(String[] args) {
		int money = 9867;
		int coin500 = 0;
		int coin100 = 0;
		int coin10 = 0;
		int coin5 = 0;
		int coin1 = 0;
		
		coin500 = money/500;
		coin100 = (money%500/100);
		coin10 = (money%500%100/10);
		coin5 = (money%500%100%10/5);
		coin1 = (money%500%100%10%5/1);
		System.out.println(coin500); // 19
		System.out.println(coin100); // 3
		System.out.println(coin10); // 6
		System.out.println(coin5); // 1
		System.out.println(coin1); // 2
	}
   ```

### 비트 연산자
 - 종류 : &, |, ^
 - 정수타입과 boolean 타입에 연산 적용
 - binary로 해서 bit간의 연산 진행
	```java
	public static void main(String[] args) {
		boolean b1 = true, b2 = false, b3 = true, b4 = false;
		System.out.println(b1&b2); // false
		System.out.println(b1&b3); // true
		System.out.println(b4&b2); // false
		System.out.println(b1|b2); // true
		System.out.println(b1|b3); // true
		System.out.println(b4|b2); // false
		System.out.println(b1^b2); // true
		System.out.println(b1^b3); // false
		System.out.println(b4^b2); // false
	}
	```

### Shift 연산자
 - 종류 : <<, >>, >>>
	```java
	public static void main(String[] args) {
		int x = 8, y = 3;
		System.out.println(x << y); // 64
		 // X << Y 비트를 왼쪽 이동, 오른쪽 비트는 0으로 채움
		x = 256;
		System.out.println(x >> y); // 32
		 // X >> Y 비트를 오른쪽 이동, 왼쪽 비트는 X의 sign(양/음수) 비트로 채움
		System.out.println(-x >> y); // -32
		
		System.out.println(x >>> y); // 32
		 // X >>> Y 비트를 오른쪽 이동, 왼쪽 X의 무조건 0 비트로 채움
		System.out.println(-x >>> y); // 536870880
	}
	```

### 논리 연산자
 - 종류 : &&, ||
 - &&는 조건식1이 false이면 조건식 2을 수행하지 않고 false를 리턴
 - ||는 조건식 1이 true이면 조건식 2을 수행하지 않고 true를 반환
 	- 위와 같이 전체 구문을 실행하는 것이 아닌 일부만 실행하고 결과를 빠르게 리턴하는 것을 **short circuit 연산자**라고 한다.
	```java
		public static void main(String[] args) {
		String s = null;
		 // 참조자료형에 한해서 데이터가 결정되지 않으면 null을 넣을 수 있다.
		 // 참조 변수만 선언하고 객체가 생성되지 않음.
		System.out.println((s.length()==0 && s==null)); // 에러
		System.out.println((s.length()==0 || s==null)); // 에러
		System.out.println((s==null && s.length()==0)); // 에러
		 // 위 3개는 객체가 생성되지 않고 사용(s.length())하려고 해서 NullPointerExeption 에러 발생
		 // NullPointerExeption는 Runtime 에러가 발생함.
		 	// Runtime 에러 : 프로그램 실행시점에 발생하는 오류 
		System.out.println((s==null || s.length()==0));
		 // s==null이 true이기 때문에 s.length가 실행될 필요가 없어 오류가 미발생.
	}
	```

### 삼항 연산자
```java
public static void main(String[] args) {
	int a = 3, b = 5;

	// 조건식? True 표현식1 : False 표현식2
	int result = (a > b ? 99.9 : 90); // 에러
	 // 연산식이 여러개인 경우(조건식 제외) 자동으로 가장 큰 타입으로 promotion 발생
	 // int → double로 promotion이 발생하는데 result가 double 타입이 아니기 때문에 에러 발생
	double result2 = (a > b ? 99.9 : 90);
     // a가 b보다 큰 경우, result2에 99.9 할당
	 // a가 b보다 크지 않은 경우, result2에 90 할당
```

### 기타 연산자 문제
```java
/* 삼항연산자 또는 논리연산자를 이용해 정수가 짝수인지 홀수인지 평가해서 출력하기 */
public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.println("정수를 입력하세요 >> ");
		
	int a = input.nextInt();
	String str = (a%2==0 ? "짝수" : "홀수");
	System.out.println(str);
}
```


## 제어문
 - 조건문 : if, else, switch, case, default
 - 제어문 : break, continue 

### 조건문(if)
```textpain
// 조건문
if(조건) {
	문장;
	...
}

// 조건문 + else
if(조건) {
	문장;
	...
} else {
	문장;
	...
}

// 다중 조건문
if(조건) {
	문장;
	...
} else if(조건) {
	문장;
	...
} else if(조건) {
	문장;
	...
} else {
	문장;
	...
}

// 중첩 조건문
if(조건) {
	if(조건) {
		문장;
  	} else {
 		문장;
	}
} else {
	문장;
}
```
```java
/* 조건문을 이용해 정수가 짝수인지 홀수인지 평가해서 출력하기 */
public static void main(String[] args) {
		Scanner input = new Scanner(System.in);		
		 System.out.print("정수를 입력하세요>>");
		 int num = input.nextInt();
		 if(num%2==0) {
			 System.out.println(num+"짝수");			 
		 }else {
			 System.out.println(num+"홀수");
		 }
	}
```
```java
/* 여러 조건에 우선순위 평가가 필요한 경우
    예) 점수에 대한 학점 평가 */
public static void main(String[] args) {
		Scanner input = new Scanner(System.in);		
		 System.out.print("점수(0~100)를 입력하세요>>");
		 int jumsu = input.nextInt();
		 if( jumsu >89 ) {
			 System.out.println(jumsu+" : A학점");			 
		 } else if( jumsu >79){
			 System.out.println(jumsu+" : B학점");	
		 } else if( jumsu >69){
			 System.out.println(jumsu+" : C학점");	
		 } else if( jumsu >59){
			 System.out.println(jumsu+" : D학점");	
		 } else  {
			 System.out.println(jumsu+" : F학점");	
		 }
	}
```
```java
/* 년도 4자리 정수를 입력받아서  윤년, 평년 평가하고  출력 합니다.
   년도 % 4 == 0 이면 윤년
   년도 % 100 == 0 이면 평년
   년도 % 400 == 0 이면 윤년 */
public static void main(String[] args) {
		Scanner  input = new Scanner(System.in);		 
		System.out.print("4자리 정수로 년도를 입력하세요>>");
		int year = input.nextInt();
		if (year%4==0 ) {
			if(year%400==0 ) {
				System.out.println(year+"은 윤년");
			} else if (year%100==0){
				System.out.println(year+"은 평년");
			} else {
				System.out.println(year+"은 윤년");
			}
		} else {
			System.out.println(year+"은 평년");
		}
		
		// 또다른 방법
		if (year%4==0  && year%400==0) {		 
			   System.out.println(year+"은 윤년");
		} else if (year%4==0  &&year%100==0){
			   System.out.println(year+"은 평년");
		} else if (year%4==0 ){
			   System.out.println(year+"은 윤년");		
		} else {
				System.out.println(year+"은 평년");
		}
	}
```
```java
/* 사용자로부터 아이디와 비밀번호를 입력받아 로그인 검증을 수행하는 프로그램을 작성하세요.
   아이디는 "admin"이어야 하고, 비밀번호는 "1234"여야 로그인 성공
   아이디가 틀렸을 경우 → "아이디가 올바르지 않습니다." 출력
   아이디가 맞지만 비밀번호가 틀렸을 경우 → "비밀번호가 틀렸습니다." 출력
   아이디와 비밀번호가 모두 맞으면 → "로그인 성공!" 출력
    ※ 문자열 내용을 비교는  객체.equals("비교문자열") 
 */
public static void main(String[] args) {		 	 
	Scanner  input = new Scanner(System.in);		 
	System.out.print("아이디 입력하세요>>");
	String uid = input.nextLine();
	System.out.print("비밀번호 입력하세요>>");
	String upass = input.nextLine(); 

	if (uid.equals("admin")  && upass.equals("1234")) {	
		System.out.println("로그인 성공!");
	} else if (uid.equals("admin")  && !upass.equals("1234")){
			System.out.println("비밀번호가 틀렸습니다.");
	} else if (!uid.equals("admin") ){
		System.out.println("아이디가 올바르지 않습니다.");
	} else {
		System.out.println("Unkown Error");
	} 
}
```

### 조건문(switch)
 - 다중 조건문을 switch ~ case문으로 처리할 수 있습니다.
 - switch인수로 byte, short, char, int, String 만 허용됩니다.
 - case의 선언된 값은 switch인수로 전달된 값과 == 로 비교합니다.
 - case의 선언된 값은 중복 선언될 수 없습니다.
 - default의 경우 switch 블럭의 마지막에 정의되면 break 생략합니다
 - switch 블럭의 중간에 default를 선언한 경우 break 선언해야 switch 블럭을 탈출합니다
	```plaintext
	// switch문(기본)
	switch(표현식 | 변수 | 메서드) {
		case 값1: 문장; break;
		case 값2: 문장; break;
		.....
		default: 문장;
	}

	// switch문(switch expression) - 1
	switch (정수|문자열) {
		case 값1, 값2 -> {문장; }
		....
		default -> {문장;}
	}

	// switch문(switch expression) - 1
	변수 = switch (정수|문자열) {
		case 값 -> 문장;   
		....
		default -> {
			yield 문장;
		}
	}
	```
	```java
	/* 여러 조건에 우선순위 평가가 필요한 경우
        예) 점수에 대한 학점 평가 */
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);		
		 System.out.print("점수(0~100)를 입력하세요>>");
		 int score = input.nextInt();
		switch(score/10){
		case 10:
		case 9 :
			System.out.println(score+" : A학점");  break;
		case 8 :			 
			 System.out.println(score+" : B학점"); break;	
		case 7 :
			 System.out.println(score+" : C학점"); break;	
		case 6 : 
			 System.out.println(score+" : D학점");	break;
		default :
			 System.out.println(score+" : F학점");	
		 }
	}
	```
	```java
	/* 입력받은 연산자에 따라 계산 및 결과를 출력 */
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);
		System.out.println("정수를 입력하세요 >>");
		int num1 = input.nextInt();
		System.out.println("정수를 입력하세요 >>");
		int num2 = input.nextInt();
		System.out.println("연산자(+, -, *, /, %)를 입력하세요 >>");
		char op = input.next().trim().charAt(0);
		int result = 0;
		boolean flag = true;
		switch(op) {
		case '+': result = num1 + num2; break;
		case '-': result = num1 - num2; break;
		case '*': result = num1 * num2; break;
		case '/': result = num1 / num2; break;
		case '%': result = num1 % num2; break;
		default:
			System.out.println("지원하지 않는 연산자입니다.");
			flag = false;
		}
		if(flag) {
			System.out.printf("%1$d %2$s %3$d = %4$d", num1, op, num2, result);
		}
	}
	```
	```java
	/* 입력받은 연산자에 따라 계산 및 결과를 출력 */
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);
		System.out.println("정수를 입력하세요 >>");
		int num1 = input.nextInt();
		System.out.println("정수를 입력하세요 >>");
		int num2 = input.nextInt();
		System.out.println("연산자(+, -, *, /, %)를 입력하세요 >>");
		char op = input.next().trim().charAt(0);
		int result = switch(op) {
			case '+' -> num1 + num2;
			case '-' -> num1 - num2;
			case '*' -> num1 * num2;
			case '/' -> num1 / num2;
			case '%' -> num1 % num2;
			default -> 0;
		};
		// Java13 버전부터 사용 가능한 새로운 방식
		// Python과 같은 언어에 영향을 받아 심플하게 사용하려고 지향해서 새로운 방식을 만듦.
		if(result != 0) {
			System.out.printf("%1$d %2$s %3$d = %4$d", num1, op, num2, result);
		} else {
			System.out.println("지원하지 않는 연산자입니다.");
		}
	}
	```


## 반복문
 - 종류 : for, while, do ~ while
 - for : 반복횟수를 알고 있을 때
 - while 반복 수행 조건을 알고 있을 때
 	- 선 조건 체크 후 반복 수행 여부 결정
 - do ~ while : 선 수행 후 조건 체크하고 계속 수행 여부 결정

### 반복문(for)
```plaintext
for(초기화식 ; 조건식 ; 증감식) {

}
```
```java
for(int i=0; i<5; i++) {
	// i는 for문안의 로컬 변수로 활용되어서 for문 밖에서는 사용 불가능하다.
	System.out.println(i);
}
```
```java
/* for문을 사용해서 1~10까지의 누적합을 출력하는 코드 구현하세요 */
int hap = 0;
for(int i=0; i<10; i++) {
	hap += (i+1);
}
System.out.println("1~10까지의 누적합 : " + hap);
```
```java
/* 1~10까지의 정수에서 홀수만 역순으로 출격하는 코드 구현하세요 */
for(int i=10; i>0; i--) {
	if(i%2 == 1) {
		System.out.println(i);
	}
}
```
```java
/* for문을 사용해서 A~Z까지의 출력하는 코드 구현하세요 */
for (char ch='A'; ch<='Z'; ch++) {
	System.out.println(ch);
} // char를 활용한 방법

System.out.println();

for (int i=65; i<91; i++) {
	System.out.println((char)i);
} // ASCII 코드를 활용한 방법
```
```java
// 2차원의 데이터를 처리할 때 for문 내부에 for문을 정의할 수 있다.
// outer for문은 행수만큼 반복, inner for문은 열수만큼 반복 수행시킵니다.
for(int i=0; i<5; i++) {
	for(int j=0; j<5; j++) {
		System.out.println(j+i+" ");
	}
	System.out.println();
}
```
```java
/* 구구단 2~9단 가로로 출력 */
for(int row=1; row<10; row++) {
	for(int col=2; col<10; col++) {
		System.out.printf("%1$dX%2$d=%3$2d ", col, row, (row*col));
	}
	System.out.println();
}
```
```java
/* for문에서의 break, continue 이해 */
a1: // a1라는 명칭의 SavePoint 지정
for(int i=0; i<3; i++) {
	a2: // a2라는 명칭의 SavePoint 지정
	for(int j=0; j<3; j++) {
		if(j==1) continue;
		 // j가 1일 경우, 현재 반복을 SKIP 하고 다음 반복 진행.
		if(j==1) break;
		 // j가 1일 경우, 현재 반복을 탈출(=for문 강제 종료)
		if(j==1) break a1;
		 // j가 1일 경우, 현재 반복을 탈출하여 a1 지점으로 이동
		 // SavePoint 개념
		System.out.println("i="+i+", j="+j);
	} // break, continue 각각 주석해보면서 결과 확인 필요.
}     // j가 1일 때의 결과값이 모두 다르게 나오는 것을 확인 가능.
```
```java
/* 1~100사이의 Prime Number(소수)와 개수를 출력 */
int count = 0;
for(int su=2; su<100; su++) {
	boolean flag = true;
	for (int div=2; div < su/2; div++) {
		// su 값 전체를 계산해보지 않아도 절반만 해도 결과가 나오기 때문에 /2 추가(최적화라고 생각하면 될 듯)
		if(su%div==0) {
			// 실제로 su 값을 나눔에 따라 소수값이 나오게 됨.
			flag = false;
			break;
		}
	}
	if(flag) {	
		System.out.print(su+", ");
		count += 1;	
	}
}
System.out.println();
System.out.println("Prime Number의 개수 : " + count);
```

### 반복문(while)
```plaintext
while(조건) {
	반복수행 문장;
}
```
```java
/* while문을 사용해서 1~10까지의 누적합을 출력하는 코드 구현하세요 */
int hap=0, i=0;
while(i<10) {
	hap+=(i+1);
	i++;
}
System.out.println("1~10까지의 누적합 : " + hap);
```

### 반복문(do ~ while)
```plaintext
do {
	반복수행 문장;
} while(조건);
```
```java
// false 조건의 내용이나, 결과값이 한번이라도 나오는 것을 확인 가능하다.
int hap=0, i=0;
do {
	hap+= (i+1);
	i++;
	System.out.println("do~while 내부");
} while(i>100);
```
```java
/* UpDown게임 (do~while문)
	컴퓨터가 생성한 (1~100)사이의 수를 사용자(도전자)는 5회 내에 맞추어야 합니다.
	사용자가 입력한 수보다 컴퓨터가 생성한 수가 낮으면 "Down"을 출력
	사용자가 입력한 수보다 컴퓨터가 생성한 수가 높으면 "Up"을 출력
	5회 내에 사용자가 수를 맞추면 "You Winer!!!" 출력
	5회 내에 사용자가 수를 맞추지 못하면 "You Loser!!!" 출력 */

//1~100 사이의 랜덤한 난수를 만드는 방법
System.out.println((int)(Math.random()*100+1)); // 방법1 : Math 객체 사용
Random r = new Random();
System.out.println(r.nextInt(100)+1); // 방법2 : Random 객체 사용

/////////////////////////////////////////////////////////////////
int cnt=0;
int random = (int)(Math.random()*100+1);
	// Math.random()*100+1 을 통해 1<= ~ <100의 랜덤 난수 생성
Scanner input = new Scanner(System.in);
System.out.println(random);
do {
	cnt++;
	System.out.printf("수를 입력하세요(현재 %d번쨰)>>", cnt);
	int num = input.nextInt();
	
	if (num == random) {
		System.out.println("You Winer!!!");
		break;
	} else if (cnt==5) {
		System.out.println("You Loser!!!");
	} else if(num > random) {
		System.out.println("Down");
	} else if (num < random) {
		System.out.println("Up");
	} 
} while(cnt<5);
```


## 배열(Array)
 - 동일한 타입의 값 또는 객체를 여러개 하나의 변수로 저장할 수 있는 유형
 - 참조 타입(reference Type)이다.
 - **선언 → new 생성 → 초기화**과정으로 객체 생성된 후에 사용해야한다.
 - 배열을 초기화 할 때, 크기를 반드시 정의해야 한다.
 - length 멤버 변수가 자동 생성되면서 배열의 크기가 저장된다.
 - 메서드 내부에 로컬 변수로 선언하더라도 자동 초기화가 된다.
 - 배열의 요소들은 Index가 0부터 시작한다.
	- Zero-Based Numbering
 - 배열은 새로운 배열로 복사 할 수 있다.
	- 근데 참조자료형은 복사 시, 얕은 복사와 깊은 복사가 있다.
		- 얕은 복사
		- 깊은 복사
```plaintext
// 1차원 배열 선언 방법
타입[] 변수;
타입 변수[];
타입 []변수;

변수 = new 타입[size];
변수 = new 타입[ ]{값, .....};

// 2차원 배열 선언 방법
int[][] nums;
int[] nums[];

nums = new int[5][7];
nums = new int[5][]; // 가능
nums = new int[][5]; // 에러 발생
nums = new int[][] {{1,2}, {4,5,6,7}, {8,9,10,11,12}};
```
```java
public static void main(String[] args) {
	int[] nums = new int[5];
		// 5개의 공간을 가진 배열 객체 생성
		// 로컬 변수이지만 초기화 하지 않아도, 자동 초기화 되어 모두 값이 0으로 들어감
			
	/* 배열의 값을 하나씩 다루기 위한 방법(for문) */
	for(int idx=0; idx<nums.length; idx++) {
		System.out.println(nums[idx]);
	}
	System.out.println();
	/* 배열의 값을 하나씩 다루기 위한 방법(foreach문) */
	for(int n : nums) {
		System.out.println(n);
	}
}
```
```java
public static void main(String[] args) {
	int[] nums = new int[] {11, 22, 44, 55, 66, 77, 88};
		// Index를 지정하지 않아도, 값이 할당되면 값의 수량만큼 공간이 확보됨.
	
	for(int n : nums) {
		System.out.println(n);
	}

	System.out.println(nums[7]);
	 // ArrayIndexOutOfBoundsException 에러 발생
	 	// RunTime Exception이다.
	 // 배열의 지정된 index 범위 밖의 항목을 찾을 때, 발생하는 오류이다.
}
```
```java
public static void main(String[] args) {
	String[] strings = new String[5];
	 // String은 기본 4byte를 차지하기 때문에 Heap메모리에 20byte가 확보된다.
	strings[0] = new String("korea");
	 // strings index 0번에 korea라는 값 할당

	System.out.println(strins[1]);
	 // index 1번에는 할당된 값이 없어서 Null
	System.out.println(strins[1].length);
	 // Null에 대한 조회를 했기 때문에 NullPointerException 에러 발생.

	String[] strings2 = new String[] {new String("korea"), new String("seoul")};
	 // 위와 같이도 Heap 메모리에 데이터를 할당 할 수도 있다.
	
	String[] strings3 = new String[] {"korea", "seoul"};
	 // 위와 같이 할당하면 Heap 말고 Stack 영역에 데이터가 할당된다.
	 // 다른 참조 객체는 불가하나, String 객체는 데이터 초기화 방식에 따라 Heap/Stack 각 영역에 데이터를 할당 할 수 있어 가능한 부분이다.
}
```
```java
/* 2차원 배열 다루기 */
public static void main(String[] args) {
		int[][] nums;
		nums = new int[5][7];
		
		/* 2차원 배열에 대한 for문 */
		for(int row=0; row<nums.length; row++) {
			for(int col=0; col<nums[row].length; col++) {
				System.out.print(nums[row][col] + " ");
			}
			System.out.println();
		}

	}
```
```java
public static void main(String[] args) {
	int[][] nums;
	nums = new int[5][7];

	nums = new int[5][];
	 // 배열에 저장된 1차원 배열의 size는 가변적으로 생성 할 수 있다.
	 // 객체 생성 시, Index가 지정되지 않았기 때문이다.
	nums = new int[][] {{1,2}, {4,5,6,7}, {8,9,10,11,12}};
	 // 1,2차언 배열 둘다 size는 가변적으로 활용 할 수 있다.
	System.out.println(nums.length); // 3
	System.out.println(nums[0].length); // 2
	System.out.println(nums[1].length); // 4
	System.out.println(nums[2].length); // 5
	 // 각 Index마다 size가 모두 다른 것을 확인 가능하다.
}
```
 - 배열의 타입이 객체이면 배열의 요소로 상속관계가 있는 자식 객체들을 저장할 수 있다.
```java
Object[] objects = new Object[5];
 // Object는 Java에서 Root Class이다.
objects[0] = new String("Java");
objects[1] = 3;
 // JVM이 Integer.valueof(3) 으로 받아들인다. (Boxing이라고 하다)
objects[2] = Integer.valueOf(3);
 // objects[1] 문법만 다를 뿐 동일한 의미이다.
objects[3] = System.in;
 // Object는 Root Class이기 때문에 어떠한 객체들이든 저장할 수 있다.
```
```java
/* Arrays 객체를 활용한 배열의 데이터 정렬 */
public static void main(String[] args) {
	int[] nums = null;
	nums = new int[] {33, 1, 55, 14, 88, 32};
	
	String[] strings = new String[] {
			"서울", "seoul", "대한민국", "korea", "부산", "busan"
	};
	
	Arrays.sort(nums);
	for(int n : nums) {
		System.out.println(n);
	}
	
	Arrays.sort(strings);
	for(String s : strings) {
		System.out.println(s);
	} // String의 경우 ASCII 의 숫자 기준으로 정렬된다.
}
```


## 열거(Enum) 타입
 - 데이터 중에는 몇가지로 한정된 값을 가지는 경우가 있다.
	- 예를 들어 **봄, 여름, 가을, 겨울** 같이 변경이 안되는 데이터
 - 위와 같이 한정된 값을 갖는 타입을 열거(Enum) 타입이라고 한다.
 - 대표적인 사용처로는 아래와 같은 예시가 있다.
	- Client ↔ Server 간의 Socket으로 통신을 하고자 한다.
	- 이때, 서로 통신을 위해 아래와 같은 규칙을 세울 수 있다.
		- 1번은 채팅방 연결
		- 2번은 귓속말
		- 3번은 공개 채팅
	- 이 처럼 상수로 데이터 목록을 정의해두고 서로간의 통신을 하는 경우가 대표적인 예시가 될 수 있다.
		- Socket 통신 말고도 라이브러리 사용 시, 지정된 사용 방법을 정의한다든지 등의 사항도 예가 될 수 있다.


## 클래스(Class)
 - 현실의 모든 것은 소프트웨어 관점에서 필요한 **속성(Data) + 기능**을 캡슐화하여 객체로 설계할 수 있다.
	- 이는 곳 클래스를 말한다.
 - 클래스는 객체(인스턴스)의 설계도라고 한다.
	- ex) 클래스는 붕어빵틀 / 객체는 붕어빵
 - 클래스의 구성 요소
	- 클래스 선언
		```plaintext
		AccessModifier [Modifier] class 클래스이름 [extends 부모클래스] [implements 인터페이스, 인터페이스...] {...}
		```
		- AcessModifier를 필수적으로 선언해줘야 한다.
			- public
			- default
				- 아무것도 적지 않을 때
		- Modifier는 선택적으로 선언 가능하다.
			- Modifier는 클래스의 종류를 의미한다.
			- final
			- abstract
		- extends 부모클래스 선언을 생략하면 자동으로 Object를 상속받습니다.
		- extends 부모클래스 선언은 1개의 부모클래스만 상속받을 수 있다.
			- 다중 상속 불가
		- 인터페이스는 구현되지 않은 기능을 구현하는 방식으로 다중 상속을 지원하는 참조 타입이다.
	- 클래스 멤버 필드(변수) (속성, Data)
		```plaintext
		AccessModifier [Modifier] 타입 변수명;
			// 선언만 한 경우에는 default 값으로 초기화됨.
		AccessModifier [Modifier] 타입 변수먕 = 초기값;
		```
		- AccessModifier를 필수적으로 선언해줘야 한다.
			- public
			- protected
			- default
				- 아무것도 적지 않을 때
			- private
		- Modifier는 선택적으로 선언 가능하다.
			- static
			- final
			- transient
		- 타입
			- Primitive Data Type
			- Reference Data Type
	- 생성자 메서드 (객체를 생성할 때 초기화)
		```plaintext
		AccessModifier 클래스이름([타입 변수명, ...]) {...}
		```
	- 클래스의 멤버 메서드 (기능, 동작)
		```plaintext
		AccessModifier [Modifier] 리턴타입 메서드명([타입 변수명, ...]) [throws 예외클래스타입] {...};
		```
		- 리턴타입은 필수적으로 선언해줘야 한다.

### 기타 - 프로그램의 발전(왜 Java에서는 Class라는 것을 쓰는가?)
 1. 최초에는 절차적인 언어를 활용하였다.
	- 알고리즘, 기능 중심
	- 기능 변경 시, 전체적인 코드를 손대하는 단점이 있었다.
 2. 절차지형 언어의 단점을 보완하기 위해 객체지향 언어가 등장하였다.
	- 객체 중심
	- 기능 변경 시, 해당되는 객체만 손대면 되서 유지보수가 더욱 용이하게 되었다.
		- Java로 치면 신규 기능은 Class만 추가하거나, 기능 변경은 특정 Class하나만 수정하면 된다.
			- 만일 기능 확장이 필요하면 상속으로 통한 신규 기능도 가능하다.
 3. 기능들을 라이브러리화하였다.(컴포넌트화)
 4. 컴포넌트만으로는 기본이 되는 틀이 필요해서 framework 개발을 하였다.
	- 즉, 프로그램은 코드의 재사용성을 지속적으로 추가하고 있다는 것을 알 수 있다.

### 은행 입출금 로직 구성
```java
public class Account { // 클래스 선언
	private int balance; // 클래스 멤버 필드
	public Account(int balance) { // 생성자 메서드
		this.balance = balance;
		 // this.balance 는 class의 멤버 필드를 의미
		 // this는 special한 reference 변수이다.
		    // 클래스 내부에서 자신을 참조할 때 사용하는 참조 변수이다.(자동 생성된다.)
		    // this는 static과 함께 사용될 수 없다.
		//System.out.println("생성자 메서드 Called");
		 // 생성자 메서드가 정상 호출됬는지 확인
	}
	public int getBalance() {
		// 클래스의 멤버 메서드(멤버 필드 값을 리턴하는 메서드이다.)
		return balance;
		 // 메서드 내부에 참조하고자 하는 변수가 없으면 class에서 변수를 찾는다.
		 // 즉, this 키워드를 생략해도 클래스의 변수를 참조할 수 있다.
	}
	public void setBalance(int balance) {
		// 클래스의 멤버 메서드(멤버 필드 값을 변경하는 메서드이다.)
		this.balance = balance;
	}
	public boolean deposit(int amount) {
		// 클래스의 멤버 메서드(입금 용도의 메서드)
		if(amount > 0) {
			balance += amount;
			 // 양수만 처리할 수 있도록 Validation Check
			return true;
		} else {
			return false;
		}
	}
	public boolean withdraw(int amount) {
		// 클래스의 멤버 메서드(출금 용도의 메서드)
		if(amount < balance) {
			balance -= amount;
			return true;
		}
		return false;
	}
}
```
```java
public class AccountTest {

	public static void main(String[] args) {
		Account a1 = new Account(10000);
		 // Account에 대한 객체 생성
		
		System.out.println(a1.getBalance()); // 10000
		 // 생성자 메서드에서 인수로 준 값을 getBalance 메서드를 통해 호출
		
		a1.setBalance(30000);
		System.out.println(a1.getBalance()); // 30000
		 // setBalance 메서드로 값 변경 진행
		
		if(a1.deposit(-10000)) { // 양수로 바꿔보기
			System.out.println(a1.getBalance());
		} else {
			System.out.println("입금 처리에 오류가 있습니다.");
		}
		
		if(a1.withdraw(50000)) { // 양수로 바꿔보기
			System.out.println(a1.getBalance());
		} else {
			System.out.println("출금 처리에 오류가 있습니다.");
		}
	}
}
```

## 기타 - main 메서드에 인수 주기
```java
public class ArrayEx5 {
	public static void main(String[] args) {
		int num = Integer.parseInt(args[0]);
		 // Integer.parseInt는 데이터를 int 타입으로 parsing 해주는 메서드이다.
		if(num%2 == 0) {
			System.out.println("짝수");
		} else {
			System.out.println("홀수");
		}
	} // Eclipse에서 그냥 실행 시키면 ArrayIndexOutOfBoundsException 오류가 발생한다.
}     // main 메서드에 값을 전달 할 때는 cmd에서 "java ArrayEx5 123" 과 같이 전닳해줘야 한다. 
      // Eclipse에서는 "Run AS → Run Configuration → Arguments → Program arguments" 에 값을 넣어주면 된다.
```