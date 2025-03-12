# 목차
 1. [JAVA란?](#java란) 
 2. [JAVA의 특징](#java의-특징)  
	2-1. [객체지향 프로그램의 특성](#객체지향-프로그램의-특성)  
	2-2. [GC(Garbage Collection)](#gcgarbage-collection)  
	2-3. [Java 컴파일](#java-컴파일)
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
	16-1. [2차원 배열 프로그램](#2차원-배열-프로그램)  
	16-2. [Banking 시스템](#banking-시스템)
 17. [열거(Enum) 타입](#열거enum-타입)
 18. [클래스(Class)](#클래스class)  
	18-1. [프로그램의 발전(왜 Java에서는 Class라는 것을 쓰는가?)](#기타---프로그램의-발전왜-java에서는-class라는-것을-쓰는가)  
	18-2. [은행 입출금 로직 구성](#은행-입출금-로직-구성)  
	18-3. [은행 입출금 로직 구성 - 추가](#은행-입출금-로직-구성---추가)  
	18-4. [로또 번호 추첨 로직 구성](#로또-번호-추첨-로직-구성)  
	18-5. [get, set 메서드 관련](#get-set-메서드-관련)  
	18-6. [static](#static)  
	18-7. [final](#final)  
	18-8. [추상 클래스](#추상-클래스)
 19. [가변 파라미터](#가변-파라미터)
 20. [Overload(중복 정의)](#overload중복-정의)
 21. [접근제어자](#접근제어자)  
	21-1. [싱글톤 패턴(Singleton Pattern)](#싱글톤-패턴singleton-pattern)
 22. [상속(Inheritance)](#상속inheritance)  
	22-1. [UpCasting, DownCasting 및 다형성 개념](#upcasting-downcasting-및-다형성-개념)
 23. [오버라이딩(Overriding)](#오버라이딩overriding)
 24. [인터페이스(interface)](#인터페이스interface)
 25. [클래스 중첩 선언](#클래스-중첩-선언)
 - [기타 - main 메서드에 인수 주기](#기타---main-메서드에-인수-주기)
 - [기타 - Java의 메서드 호출 방식](#기타---java의-메서드-호출-방식)

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

### 객체지향 프로그램의 특성
 - 상속(Inheritance)
	- 부모 클래스의 속성과 메서드를 자식 클래스에서는 자신의 멤버 속성과 메서드처럼 사용 가능하다.
	- 이는 코드의 재사용성을 높이고, 유지보수를 쉽게 한다
 - 다형성(Polymorphism) : 여러 형태를 가진다.
	- 오버로딩(Overloading)
		- 같은 클래스에서 같은 이름의 메서드를 매개변수만 다르게 정의하여 활용.
	- 오버라이딩(Overriding)
		- 부모로부터 상속받은 메서드를 자식 클래스에서 재정의
 - 캡슐화(Encapsulation)
	- private, protected, public 같은 접근 제한자를 사용하여 데이터를 보호한다.
	- 데이터를 직접 변경하는 것이 아니라, 메서드를 통해 접근하도록 설계할 수 있다.
		- 이는 데이터의 보안, 유지 보수성을 높일 수 있다.
	- 완전 캡슐화
		- 클래스의 인스턴스 필드를 모두 private로 선언
		- 보안 관점에서 get 메서드는 public으로 선언
		- set 메서드는 default, protected, public 접근 제한자를 사용하여 데이터를 보호

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
		- 얕은 복사(Shallow Copy)
			- 단순한 변수 선언을 통한 복사
			- 복사하려는 배열의 주소값을 가져오게 된다.
			- 즉, 기존 배열과의 주소값이 같다.
		- 깊은 복사(Deep Copy)
			- 원래 배열을 그대로 가져와 새 배열에 덮어쓰기 하는 것이다.
			- 즉, 기존 배열과의 주소값이 달라지게 된다.
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
 // 1차원 배열의 개수를 고정시키고, 각각의 2차원 배열 개수를 동적으로 생성할 수 있다.
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

### 2차원 배열 프로그램
 - 2개의 2차원 배열을 생성한 후, Random하게 셋팅된 배열의 데이터를 출력하고, 2개의 배열에서 일치하는 숫자가 있는지 찾아보는 프로그램을 만들자.
	```java
	import java.util.Random;

	public class Array {
		private String title;
		private int row;
		private int col;
		private int[][] array;
		public Array(String title, int row, int col ) {
			super();
			this.title = title;
			this.row = row;
			this.col = col;
			this.array = new int[row][col];
		}
		public int getRow() {
			return row;
		}
		public void setRow(int row) {
			this.row = row;
		}
		public int getCol() {
			return col;
		}
		public void setCol(int col) {
			this.col = col;
		}
		public int[][] getArray() {
			return array;
		}
		public void setArray(int[][] array) {
			this.array = array;
		}
		public void makeArrayData() {
			for(int i=0;i<array.length;i++) {
				for (int j=0;j<array[i].length;j++) {
					array[i][j] = getRandomNumber();
				}
			}		
		}
		private int getRandomNumber() {
			Random rand = new Random();
			return rand.nextInt(row*col)+1;
		}
		public void printArray() {
			System.out.println("## "+title+" Array 출력");
			for(int i=0;i<array.length;i++) {
				for (int j=0;j<array[i].length;j++) {
					System.out.print(array[i][j]+"  ");	
				}
				System.out.println();
			}	
		}
		public void findMatchNumber(Array src, Array desc) {
			int[][] ar1 = src.getArray();
			int[][] ar2 = desc.getArray();
			int count = 0;
			for(int i=0;i<ar1.length;i++) {
				for (int j=0;j<ar1[i].length;j++) {
					if (ar1[i][j]==ar2[i][j]) {
						count++;
						System.out.printf("## 일치하는 숫자 : [%d][%d]=%d, ", i, j,ar1[i][j] );
					}
				}
			}
			System.out.println("\n## 일치하는 숫자 갯수: "+count);		
		}
	}
	```
	```java
	public class ArrayTest {
		public static void main(String[] args) {
			Array array = new Array("1st", 3, 4);
			array.makeArrayData();
			array.printArray();
			
			Array array2 = new Array("2nd", 3, 4);
			array2.makeArrayData();
			array2.printArray();
			
			array.findMatchNumber(array, array2);
		}
	}
	```

### Banking 시스템
 - Customer는 여러 개의 Account(계좌)를 가질 수 있고, Bank는 여러 명의 Customer를 가질 수 있다.  
   즉, Customer:Account = 1:n, Bank:Customer = 1:n 관계가 성립한다.
   ```java
    public class Account {
		private String accountName;
		private int balance;

		public Account(String accountName, int balance) {
			this.accountName = accountName;
			this.balance = balance;
		}
		public String getAccountName() {
			return this.accountName;
		}
		public void setAccountName(String accountName) {
			this.accountName = accountName;
		}
		public int getBalance() {
			return balance;
		}
		public void setBalance(int balance) {
			this.balance = balance;
		}
		public boolean deposit(int amount) {
			boolean flag = true;
			if (amount <= 0) {
				flag = false;
			} else {
				this.balance += amount;
			}
			return flag;
		}
		public boolean withdraw(int amount) {
			boolean flag = true;
			if (amount <= 0) {
				flag = false;
			} else if (amount > this.balance) {
				flag = false;
			} else {
				this.balance -= amount;
			}
			return flag;
		}
	}
   ```
   ```java
    public class Customer {
		private String ssn;
		private String name;
		private Account[] accounts;
		private int numberOfAccounts;
		
		public Customer(String ssn, String name) {
			this.ssn = ssn;
			this.name = name;
			this.accounts = new Account[5];
		}
		public String getSsn() {
			return this.ssn;
		}
		public void setSsn(String ssn) {
			this.ssn = ssn;
		}
		public String getName() {
			return this.name;
		}
		public void setName(String name) {
			this.name = name;
		}
		public int getNumberOfAccounts() {
			return this.numberOfAccounts;
		}
		public Account[] getAccounts() {
			return this.accounts;
		}
		public void addAccount(Account account) {
			if (numberOfAccounts >= 5) {
				System.out.println("계좌를 더 이상 개설할 수 없습니다.!!");
			} else {
				this.accounts[numberOfAccounts++] = account;
			}
		}
	}
   ```
   ```java
    public class Bank {
		private Customer[] customers;
		private int numberOfCustomers;
		
		public Bank() {
			customers = new Customer[10];
		}
		public Customer[] getCustomers() {
			return this.customers;
		}
		public int getNumberOfCustomers() {
			return this.numberOfCustomers;
		}
		public void addCustomer(Customer customer) {
			if (numberOfCustomers >= 10) {
				System.out.println("고객을 더 이상 등록 할 수 없습니다!!");
			} else {
				customers[numberOfCustomers++] = customer;
			}
		}	
	}
   ```
   ```java
    public class BankingTest {
		public static void main(String[] args) {
			Customer c1 = new Customer("111-111", "홍길동");
			c1.addAccount(new Account("청약저축", 10000));
			c1.addAccount(new Account("종합저축", 20000));
			c1.addAccount(new Account("1억만들기펀드", 30000));
			c1.addAccount(new Account("1억만들기펀드1", 30000));
			c1.addAccount(new Account("1억만들기펀드2", 30000));
			
			Customer c2 = new Customer("222-222", "홍길자");
			c2.addAccount(new Account("입출금통장", 10000));
			c2.addAccount(new Account("CMA", 20000));
			
			Bank bank = new Bank();
			bank.addCustomer(c1);
			bank.addCustomer(c2);
			
			for(int i=0; i<bank.getNumberOfCustomers(); i++) {
				int total = 0;
				System.out.println("------------------------------------------------");
				System.out.print("주민등록번호 : " + bank.getCustomers()[i].getSsn());
				System.out.print(" 성명 : " + bank.getCustomers()[i].getName());
				System.out.print(", 보유계좌수 : " + bank.getCustomers()[i].getNumberOfAccounts() + "\n");
				System.out.println("------------------------------------------------");
				Account[] accounts = bank.getCustomers()[i].getAccounts();
				for(int j=0; j<bank.getCustomers()[i].getNumberOfAccounts(); j++) {
					System.out.print((j+1) + ". 계좌명: " + accounts[j].getAccountName());
					System.out.println(", 잔액: " + accounts[i].getBalance() + "원");
					total += accounts[j].getBalance();
				}
				System.out.println("------------------------------------------------");
				System.out.println("전체 총 잔액:" + total + "원");
				System.out.println("------------------------------------------------");
			}
		}
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
		- 멤버필드들은 명시적으로 초기화하지 않으면 default값으로 초기화된다.
			- boolean 타입은 false
			- 정수와 실수 타입은 0
			- char 타입은 '\u0000'
				- 유니코드 기준으로 처리됨.
			- 참조자료형은 null
		```plaintext
		AccessModifier [Modifier] 타입 변수명;
			// 선언만 한 경우에는 default 값으로 초기화됨.
		AccessModifier [Modifier] 타입 변수명 = 초기값;
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
		- 객체가 메모리에 생성될 때 객체의 멤버필드들을 초기화 한다.
		- 생성자를 명시적으로 정의하지 않으면 default 생성자를 컴파일시점에 자동 생성한다.
		- 리턴타입을 정의하지 않는다.
			- void도 선언하지 않는다.
		- 메서드 이름은 반드시 클래스 이름과 대소문자 모두 동일해야한다.
		- 생성자 메서드도 파라미터 순서, 개수, 타입을 다르게 선언해서 overload 할 수 있다.
		- 생성자 메서드에서 생성자 메서드를 호출할 때 this()를 사용한다.
		- 모든 생성자 메서드에서는 명시적으로 다른 생성자를 호출하지 않으면 부모클래스의 default 생성자를 호출하는 super()가 자동으로 컴파일시점에 추가된다.
		```plaintext
		AccessModifier 클래스이름([타입 변수명, ...]) {...}
		```
		- AccessModifier를 필수적으로 선언해줘야 한다.
			- public
			- protected
			- default
				- 아무것도 적지 않을 때
			- private
	- 클래스의 멤버 메서드 (기능, 동작)
		- 멤버 메서드는 클래스의 멤버필드를 처리하는 기능을 위해 정의한다.
		```plaintext
		AccessModifier [Modifier] 리턴타입 메서드명([타입 변수명, ...]) [throws 예외클래스타입] {...};
		```
		- AccessModifier를 필수적으로 선언해줘야 한다.
			- public
			- protected
			- default
				- 아무것도 적지 않을 때
			- private
		- Modifier는 선택적으로 선언 가능하다.
			- abstract
			- final
			- static
			- synchronized
			- native
				- native는 java 메서드가 아니라 C와 같은 메서드를 로드하는데 쓰는거라 거의 안쓴다고 할 수 있다.
		- 리턴타입은 필수적으로 선언해줘야 한다.
			- Primitive Data Type
			- Reference Data Type
			- void
				- 리턴타입이 없을 경우, 사용.
		- throws 예외클래스타입은 선택적으로 선언 가능하다.
			- 기능 동작 시, 에러가 발생하는 경우가 있는데 에러로 인해 프로그램이 멈추는 것이 아닌 에러 메세지를 반환해주고자 할 때 사용.
 - 객체 생성 및 사용
	```plaintext
	클래스타입 객체 = new 생성자(); // 객체 생성
	 // 추가로 멤버 메서드에서 같은 클래스의 다른 멤버 메서드는 객체 생성 없이 호출가능하다. 
	객체.멤버필드 // 객체 사용
	객체.메서드() // 객체 사용
	```

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

### 은행 입출금 로직 구성 - 추가
```java
package lab.java.basic;

public class Account {
	private int balance;
	public Account(int balance) {
		this.balance = balance;
	}
	public int getBalance() {
		return balance;
	}
	public void setBalance(int balance) {
		this.balance = balance;
	}
	public boolean deposit(int amount) {
		if(amount > 0) {
			balance += amount;
			return true;
		} else {
			return false;
		}
	}
	public boolean withdraw(int amount) {
		if(amount < balance) {
			balance -= amount;
			return true;
		}
		return false;
	}
}
```
```java
package lab.java.basic;

public class Customer {
	private String ssn;
	private String name;
	private Account account;
	public Customer(String ssn, String name) {
		super();
		this.ssn = ssn;
		this.name = name;
	}
	public String getSsn() {
		return this.ssn;
	}
	public void setSsn(String ssn) {
		this.ssn = ssn;
	}
	public String getName() {
		return this.name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public Account getAccount() {
		return this.account;
	}
	public void setAccount(Account account) {
		this.account = account;
	}
	public String toString() { // toString 메서드 추석처리 해보기
		return this.name + "님의 현재 잔액 : " + this.account.getBalance() + "원";
	}
}
```
```java
package lab.java.basic;

public class BankingTest {
	public static void main(String[] args) {
		Customer cust1 = new Customer("0001", "홍길동"); // 고객 객체
		Account acct = new Account(10000); // 계좌 객체
		cust1.setAccount(acct);
		// cust1.setAccount(new Account(10000)); // 객체 생성에 대해서는 이렇게 처리할 수도 있다.
		System.out.println(cust1); 			  // lab.java.basic.Customer@2f92e0f4
			// 객체를 별도 메서드 지정 없이 호출하면 자동으로 toString 메서드가 지정된다.
		System.out.println(cust1.toString()); // lab.java.basic.Customer@2f92e0f4
			// Customer에 toString 메서드를 만들지 않으면 위와 같이 "package.class@메모리주소값" 이 나오게 된다.
			// 이는 Customer의 부모클래스(Object)의 toString 메서드가 호출된 것이다.
				// @ 뒤에 값은 cust1의 메모리 주소 값은 16진수로 변환되서 나온 것이다.
			// Object 클래스의 toString 메서드는 해당 인스턴스(객체)에 대한 정보를 문자열로 반환한다.
		
		if(cust1.getAccount().deposit(1000)) {
			System.out.println("입금 성공");
		};
		System.out.println(cust1);
		if(cust1.getAccount().withdraw(5000)) {
			System.out.println("출금 성공");
		};
		System.out.println(cust1);
		if(cust1.getAccount().withdraw(7000)) {
			System.out.println("출금 성공");
		} else {
			System.out.println("출금 실패");
		}
		System.out.println(cust1);
	}
}
```

### 로또 번호 추첨 로직 구성
```java
import java.util.Arrays;
import java.util.Random;

public class Lotto {
	private final static int LOTTO_NUM_CNT = 6;
	public int[] generateLottoNumbers() {
		/* 6개의 요소를 저장할 정수 배열 생성
		   getRandomNumber(); // 호출로 반환되는 정수를 가져와 배열에 이미 저정되어 있는 요소 값 비교해서
		   중복되지 않으면 배열의 요소로 저장, 중복되면 getRandomNumber(); 호출로 다시 난수를 가져옴.
		   로또 번호 6개 저장된 배열을 리턴 */
		int[] lottos = new int[LOTTO_NUM_CNT];
		for(int i=0; i<LOTTO_NUM_CNT; i++) {
			boolean flag = false;
			lottos[i] = getRandomNumber();
			 // 같은 클래스에 메서드가 있기 때문에 그냥 호출 가능.
			for(int j=0; j<i; j++) {
				if(lottos[j] == lottos[i]) {
					flag = true;
					break;
				}
			}
			if(flag) {
				--i;
			}
		}
		return lottos;
	}
	public void displayLottoNumbers(int[] lottoNumbers) {
		// 파라미터로 전달된 로또 번호 즉, 저장된 배열을 출력
		for(int n : lottoNumbers) {
			System.out.println(n + " ");
		}
	}
	public void sortLottoNumbers(int[] lottoNumbers) {
		// 파라미터로 전달된 로또 번호 즉, 저장된 배열을 정렬
		Arrays.sort(lottoNumbers);
	}
	private int getRandomNumber() {
		Random r = new Random();
		return r.nextInt(45)+1;
	}
}
```
```java
public class LottoTest {

	public static void main(String[] args) {
		Lotto lotto = new Lotto();
		int[] lottos = lotto.generateLottoNumbers();
		 // 같은 클래스에 없는 메서드이기 때문에 별도 객체 생성 필요.
		lotto.sortLottoNumbers(lottos);
		lotto.displayLottoNumbers(lottos);
	}

}
```

### get, set 메서드 관련
 - 클래스의 멤버 필드들의 데이터를 다루기 위해서는 get과 set 메서드를 만들어준다.
	- get은 멤버 필드의 데이터를 반환.
	- set은 멤버 필드의 데이터를 변환.
 - 근데 get, set 메서드는 멤버 필드 수량만큼 만들어줘야해서 양이 많아지면 번거롭다.
 - 이를 편하게 할 수 있게하기 위해 get, set 명칭 뒤에 멤버필드명을 대문자로 시작하게 넣어주면 JVM이 get, set 메서드로 인식해서 동작하도록 하는 방법이 있다.
	- ex) 멤버 필드가 name이면 getName, setName과 같이 메서드명을 작성.
	- Lombok을 사용하면 어노테이션으로 처리 할 수 있고,
	  혹은 IDE 기능을 사용해서 일괄로 자동으로 만들어줄 수 있다.
	  	- Eclipse 같은 경우 소스 코드에서 "우클릭 → Source → Generate Getters and Setters" 로 자동 생성 할 수 있다.
			- 참고로 생성자도 "우클릭 → Source → Generate Constructor to invoke" 로 자동 생성 할 수 있는 듯하다.

### static
 - 클래스의 멤버 필드에 선언
	- 클래스(전역) 변수에 사용됨.
	- 객체 생성 없이 클래스이름으로 필드를 사용 가능하다.
 - 클래스의 멤버 메서드에 선언
	- 클래스(전역) 변수에 대한 처리를 위해서 기능을 전역으로 객체들간에 공유할 목적으로 활용.
	- 객체 생성 없이 클래스이름으로 메서드 호출이 가능하다.
	- 외부 메서드 내부에서 외부 필드 또는 메서드를 사용할 경우 static 이거나 non-static인 경우에는 객체를 생성해서 사용해야 한다.
	- static initialize block은 static {...} 와 같이 생성한다.
		- static 메서드보다 수행이 먼저 이뤄진다.
	```java
	public class StaticEx {
		int n1;
		static int n2;
		static { // static initialize block
			n2+=100;
		}
		public void method() {
			System.out.println(n1+ ", " + n2);
			//staticMethod();
			// non-static에서는 static 메서드 호출 가능
			// 프로그램 실행 시, 무한루프로 StackOverFlow 발생할 수 있으니 주석처리 진행.
		}
		public static void staticMethod() {
			StaticEx ex = new StaticEx();
			// static 메서드에서 non-static 필드를 활용하기 위해서는 객체를 생성해야 한다.
			System.out.println(ex.n1+ ", " + n2);
			ex.method();
			// 메서드 또한 non-static 이기 때문에 객체 생성 안하면 호출 불가.
		}
		public static void main(String[] args) {
			//System.out.println(StaticEx.n1);
			// main에서도 동일하게 non-static 메서드 호출 불가.
			// 클래스명 안붙여도 호출은 가능하나, 그냥 붙임.
			System.out.println(StaticEx.n2); // 1
			
			StaticEx.n2 *=5;
			System.out.println(StaticEx.n2); // 5
			// 수행 순서 : 클래스로드 → static 필드 초기화 → static initialize block → static 메서드
			// 하여 결과값이 5가 된다.
		}
		static { // static initialize block (여러개 생성 가능)
			n2/=100;
		}
	}
	```
 - 내부 클래스에 선언

### final
 - 클래스에 선언
	- 종단 클래스라는 의미가 된다.
		- 즉, 하위에 상속 및 확장이 불가능하다.
		- Java는 최상위 클래스(Object)에서 하위로 상속받아 확장이 되는 개념이 있다는 것을 인지해둬야한다.
	```java
	class Parent4 {
		
	}
	class Child4 extends Parent4 {
	 // Parent4 class에 final 선언 시, 종단 클래스로 지정되어 상속 불가가 됨.
	}
	```
 - 클래스의 필드에 선언
	- 상수로 활용된다.
		- 선언시에 값을 초기화해야하며, 초기화하지 않으면 생성자에서 초기화해줘야 한다.
 - 클래스의 메서드에 선언
	```java
	class Parent5 {
	public final void handle() {
		
		}
	}
	class Child5 extends Parent5 {
		public void handle();
		 // final이 선언된 메서드는 override가 불가능하다.	
	}
	```
 - 로컬 변수에 유일하게 선언할 수 있는 Modifier 이다.
 	```java
	public class FinalEx {
		public void run() {
			final int local = 100;
			// 로컬 변수에는 AccessModifier나 static이 작성될 수 없다.
				// static은 인스턴스가 먼저 올라와야하나, 메서드가 non-static이면 논리적으로 앞뒤가 맞지 않는 경우가 있다.
			/* 메서드 내부에 클래스를 정의한 경우, 내부 클래스에서 로컬 변수를 access 할 경우,
				변경 가능성이 있기 때문에 프로그램 제어에 문제, 보안 문제가 발생할 수 있다. */
			// 내부 클래스에서 로컬 변수를 안전하게 access 할 수 있도록 final로 선언한다.
		}
	}
	```

### 추상 클래스
 - 추상 클래스는 소프트웨어 관점으로 관리해야하는 대상 객체들이 공통되는 필드와 메서드를 추상화할 수 있고, 부모클래스로 정의할 수 있다.
 - 부모클래스에 정의되는 메서드 중에서는 부모가 구현해서 상속해주는 메서드도 있지만, 자식클래스에서 상속받은 메서드를 반드시 재정의(Override)해서 사용하도록 강제시킬 수 있는 메서드를 정의할 수 있다.
	- 이러한 메서드는 추상 메서드라고 한다.
 - abstract가 선언된 메서드는 {} 없이 ;으로 메서드 선언을 종료한다.
 - 구현 body가 없는 abstract 메서드는 객체 생성이 불가하다.
	- 하여, 클래스 선언에 객체 생성을 할 수 없다고 선언을 해줘야 한다.
		- class에 abstract를 지정하는 것을 말한다.
	```java
	public abstract class Animal {
		int eyes, hands, feet, wings;
		public abstract void action();
		public void eat() {
			System.out.println("water");
		}
	}
	class Dog extends Animal {
		// Dog는 abstract 지정을 안하였기 때문에 객체 생성이 가능하다.
		// 객체 생성을 위해 Animal을 상속받은 새로운 class를 만들었다고 생각하면 된다.
		// Animal의 메서드는 오버라이드 해서 사용하면 된다.
		@Override
		public void action() {
			System.out.println("all action!!");
		}
	}
	class Dolphin extends Animal {
		@Override
		public void action() {
			System.out.println("swimming");
		}
	}
	```
	```java
	public class AbstractTest {
		public static void main(String[] args) {
			// Animal dog = new Animal(); // 추상 클래스는 객체 생성이 안된다.
			Animal dog = new Dog(); // 다형성 객체
			dog.action(); // override된 메서드 호출
			dog = new Dolphin();
			dog.action();
		}
	}
	```


## 가변 파라미터
 - 메서드의 파라미터중에서 동일한 타입의 파라미터 개수가 실행시점에 동적으로 결정되는 경우에 사용한다.
	```java
	public class VarArgsEx {
		public void add(double d, int ... a) {
			// 메서드 내부에 int ... a는 int[] a로 생성된다.
			if (a == null) {
				System.out.println("add Called");
			} else {
				System.out.println(a.length);
				int sum = 0;
				for (int n : a) {
					sum += n;
				}
				System.out.println("누적 합 : "+sum);
			}
		}
		//public void minus(int ... a, double d) {} // 오류
			// 가변 파라미터는 다른 파라미터(필수 파라미터)를 선언한 후에 선언해야한다.
			// 즉, 가변 파라미터는 맨 앞에 선언될 수 없다.
		public static void main(String[] args) {
			VarArgsEx ex = new VarArgsEx();
			ex.add(0.5, null);
			ex.add(0.5);
			ex.add(0.5, 3, 5, 7, 9, 11, 13, 17, 19);
			 // 가변 파라미터는 메서드의 이름 재사용성이 높아진다는 것을 알 수 있다.
		      // view layer의 인터페이스 구현이 simple 해진다고 볼 수 있다.
		}
	}
	```


## Overload(중복 정의)
 - 객체지향의 특성 중 **다형성**에 해당 된다.
 - 동일한 기능에 대해 메서드 이름을 재사용함으로써 일관성을 가질 수 있다.
 - 작성 규칙
 	- AccessModifie는 동일하거나 동일하지 않아도 된다.
	- 리턴타입은 동일하거나 동일하지 않아도 된다.
	- 메서드 이름은 동일해야한다.
	- 파라미터의 순서, 타입, 개수 중에 하나는 반드시 달라야한다.
		- 파라미터의 순서, 타입, 개수는 모두 일치하면서 리턴타입만 다르게 선언하면 에러이다.
	```java
	public class OverloadEx {
		public void add(int a, int b) {
			System.out.println("add(int, int) called");
		}
		double add(double a, double b) {
			System.out.println("add(double, double) called");
			return 0;
		}
		protected void add(String s, int a, int b) {
			System.out.println("add(String, int, int) called");
		}
		float add(float a, boolean b) {
			System.out.println("add(float, boolean) called");
			return 0;
		}
		public static void main(String[] args) {
			OverloadEx ex = new OverloadEx();
			ex.add(1, 2);
			ex.add('A', 3.14F);
			// char, float 보다 큰 타입은 메서드(double add)를 호출한다.(promotion)
		}
	}
	```


## 접근제어자
 - public
	- 누구나 어디서든 접근 가능하다.
 - protected
	- 같은 패키지 내에 있는 대상은 접근 가능하다.
	- 상속 관계에 있는 대상만 접근 가능하다.
 - default
	- 같은 패키지 내에 있는 대상만 접근 가능하다.
	- 상속관계에 있는 대상도 접근 불가능하다.
 - private
	- 같은 클래스 내에서만 접근 가능하다.
	- private 멤버필는 상속되지 않는다.
	- private 메서드 또한 상속되지 않는다.
	- private에 대해서 자식, 외부 class에서 접근시에는 get, set 메서드가 필요하다.
	![접근제어자](https://blog.kakaocdn.net/dn/cRaz6Q/btrG4eRRFlu/RQ24UziUBaMQ6c3Be9KO60/img.png)  
	![접근제어자2](https://hongong.hanbit.co.kr/wp-content/uploads/2021/09/01-%EC%9E%90%EB%B0%94%EC%9D%98-%EC%A0%91%EA%B7%BC-%EC%A0%9C%ED%95%9C%EC%9E%90_public_private-768x394.png)
	```java
	package lab.java.pkg1;

	public class Super {
		public String name;
		protected String name2;
		String name3;
		private String name4;
	}
	```
	```java
	package lab.java.pkg1;

	public class Other {
		public void method() {
			Super s = new Super();
			s.name3 = "seoul"; // default는 상속관계가 있든 없든 같은 패키지 내에서만 access 가능하다.
			System.out.println(s.name3);
		}
		public static void main(String[] args) {
			Other ot = new Other();
			ot.method();
		}
	}
	```
	```java
	package lab.java.pkg2;

	import lab.java.pkg1.Super;

	public class Other2 {
		public void method() {
			Super s = new Super();
			s.name = "seoul"; // public은 누구나 access 가능
			//s.name2 = "busan" // 오류. protected는 상속관계에 있는 대상만 access 가능
			System.out.println(s.name);
		}
		public static void main(String[] args) {
			Other2 ot = new Other2();
			ot.method();
		}
	}
	```
	```java
	package lab.java.pkg2;

	import lab.java.pkg1.Super;

	public class Sub2 extends Super {
		public Sub2() {
			name = "dongtan";
			// 부모클래소부터 상속을 받았기 떄문에 Sub2에 존재하지 않은 name 변수를 사용 가능하다.
			// name 변수는 다른 패키지 및 클래스에 있지만 상속을 통해 자신의 것처럼 사용 가능하다.
			name2 = "inchon";
			// 접근제어자가 protected 여도 Sub2는 상속관계에 있기 때문에 사용 가능
			// name3 = "kkk"; // 오류. default는 상속관계여도 Access 불가
			// name4 = "jjj"; // 오류. private는 상속되지 않는다. 하여, Access 불가
			System.out.println(name);
			System.out.println(name2);
		}
		public static void main(String[] args) {
			Sub2 s2 = new Sub2();
		}
	}
	```

### 싱글톤 패턴(Singleton Pattern)
 - 일반적으로 객체를 생성하는것에 제한은 없다. 그러나 class 내에 객체가 딱 하나만 생성되어 관리되어야 하는 경우가 있다. 
	- 예를 들어 rdbms 연결 시에 연결 수량, 메모리 등을 관리해야할 경우 등등
 - Application 전체에서 단 한개의 객체만 생성해서 사용하고자 하는 경우에 사용한다.
 - 싱글톤 패턴의 핵심은 생성자를 private 접근 제한해 외부에서 new 연산자로 생성자를 호출할 수 없도록 막는 것이다.
```java
// Student는 그냥 객체 생성에 따른 메모리 주소가 다름을 표현하기 위한 용도로 싱글톤 패턴과는 무관하게 봅시다.
package lab.java.basic;

public class Student {
    private String sno;
    private String name;
    private int kor;
    private int math;
    private int eng;
    public Student() {
    	System.out.println("Student() called");
    }
    public Student(String sno, String name) {
    	   this.sno=sno;
    }
    
    public Student(String sno,String name, int kor, int math,int eng) {
    	this();
    }
    
    public void method1() {
    	method2();
    }
    public void method2() {
    	System.out.println("method2() called");
    }   
    
	public static void main(String[] args) {
   		// Student s1 = new Student();
		// s1.method1();
		Student s1 = new Student("s001", "kim", 88,80,95);
		
	}
}
```
```java
package lab.java.basic;

public class Test {
	public static void main(String[] args) {
		Student s1 = new Student("0001", "kim");
		Student s2 = new Student("0001", "kim");
		System.out.println(s1 == s2);
		 // false (서로 다른 Heap 메모리에 저장되어 불일치)
		
		//DBConnect con1 = new DBConnect();
		 // 오류. 생성자가 private이기 때문에 객체 생성이 불가하다.
		DBConnect con1 = DBConnect.getInstance();
		 // static으로 선언된 메서드를 호출하여 객체 생성 진행.
		DBConnect con2 = DBConnect.getInstance();
		System.out.println(con1 == con2); // true
		System.out.println(con1); // lab.java.basic.DBConnect@28a418fc
		System.out.println(con2); // lab.java.basic.DBConnect@28a418fc
		 // 싱글톤 패턴에서 만든 객체는 모두 메모리 주소 값이 같다.
	}
}
```
```java
package lab.java.basic;

// 이 클래스로부터는 객체가 1개만 생성된다. (=싱글톤 패턴)
public class DBConnect {
	private static DBConnect conn = new DBConnect();
	
	private DBConnect() {
		System.out.println("RDBMS에 실제 연결은 아닙니다.");
	}
	
	public static DBConnect getInstance() {
		// 외부에서 DBConnect에 대해 객체를 생성할 수 없어, getInstance 메서드 또한 호출이 불가하다.
		// 하여, 객체 생성 없이 메서드를 호출할 수 있도록 하기 위해 static 을 붙여줘야 한다.
		return conn;
	}
}
```


## 상속(Inheritance)
```java
package lab.java.basic;

class Parent {
	int num = 0;
	
	public Parent() {
		System.out.println("Parent() called");
	}
	
	public void ParentMethod() {
		System.out.println("ParentMethod() called");
	}
}
class Child extends Parent {
	public Child() {
		// super(); // 부모클래스의 생성자를 별도로 명시하지 않으면 super()가 자동으로 추가되어 실행된다. 
		System.out.println("Child() called");
	}
}

public class ExtendsTest {
	public static void main(String[] args) {
		Child c1 = new Child();
		 // 부모클래스의 생성자 메서드가 먼저 호출된다.
		 // 이는 자식클래스의 생성자에 부모클래스에 생성자에 대한 호출을 하지 않으면 super()가 자동으로 추가된다.
		    // 위 내용을 통해 부모클래스가 먼저 로드되고, 자식클래스가 로드된다는 것을 알 수 있다.
		    // 또한 Heap 메모리 상에서도 자식객체가 생성되기전에 부모객체가 먼저 생성된다는것도 알 수 있다.
		c1.num  += 100;
		System.out.println(c1.num);
		c1.ParentMethod();
	}
}
```
```java
package lab.java.basic;

class Parent {
	int num = 0;
	
	public Parent(int num) {
		this.num = num;
		System.out.println("Parent() called");
	}
	
	public void ParentMethod() {
		System.out.println("ParentMethod() called");
	}
}
class Child extends Parent {
	public Child() {
		// super();
		 // 오류. 부모클래스의 생성자의 값은 자동으로 추가가 안되어 오류가 발생한다.
		 // 부모클래스에 default 생성자가 없는 경우 자식 객체를 생성할 때 오류 발생
		   // 오류 해결방법 1. 부모클래스에 default 생성자 정의
		   // 오류 해결방법 2. 부모클래스에 정의된 생성자를 자식 클래스의 생성자 메서드에서 호출
		super(3); // 오류 해결 방법2에 해당. 주석 혹은 삭제 해보기
		System.out.println("Child() called");
	}
}

public class ExtendsTest {
	public static void main(String[] args) {
		Child c1 = new Child();
		c1.num  += 100;
		System.out.println(c1.num);
		c1.ParentMethod();
	}
}
```
```java
package lab.java.basic;

class Parent2 {
	int num = 0;
	
	
}
class Child2 extends Parent2 {
	int num = 1;
	public void method(int num) {
		System.out.println(num); // 100
		 // 로컬변수가 더 우선시 된다.
		System.out.println(this.num); // 1
		 // 인스턴스 변수를 참조
		System.out.println(super.num); // 0
		 // super는 부모 클래스를 지칭
		 // 즉, 부모클래스의 인스턴스 변수를 참조
	}
}

public class ExtendsTest2 {
	public static void main(String[] args) {
		Child2 c2 = new Child2();
		c2.method(100);
	}
}
```
```java
package lab.java.basic;

class Parent2 {
	int num = 0;
	
	public Parent2() {
		System.out.println("Parent2() called");
	}
	public Parent2(int num) {
		this.num = num;
		System.out.println("Parent2(int) called");
	}
}
class Child2 extends Parent2 {
	int num = 1;
	
	public Child2() {
		//System.out.println("Child Called"); // 주석 혹은 삭제
		super(333);
		 // 생성자 메서드에서 부모 또는 자신의 다른 생성자 메서드를 호출할 때는 생성자 메서드 내부의 첫번째 줄에서만 호출할 수 있다.
		super(); // 오류
		 // 생성자 메서드에서 부모 또는 자신의 다른 생성자 메서드를 호출할 때는 한번만 호출할 수 있다.
	}
	
	public void method(int num) {
		System.out.println(num); // 100
		System.out.println(this.num); // 1
		System.out.println(super.num); // 0
	}
}

public class ExtendsTest2 {
	public static void main(String[] args) {
		Child2 c2 = new Child2();
		c2.method(100);
	}
}
```
```java
class MyMath extends Math {}
class MySystem extends System {}
 // 시스템 동작에 영향을 끼칠 수 있는 대상에 대해서는 상속이 불가능하다.
```

### UpCasting, DownCasting 및 다형성 개념
 - UpCasting
	- 자식클래스가 부모클래스로 Casting 되는 것을 말함.
 - DownCasting
	- 부모클래스가 자식클래스로 Casting 되는 것을 말함.
	```java
	package lab.java.basic;

	class Parent5 {
		int a=1, b=2;
		public void method1() {
			System.out.println("Parent5's method1() called");
		}
		public void method2() {
			System.out.println("Parent5's method2() called");
		}
	}
	class Child5 extends Parent5 {
		int a=3, x=4;
		public void method1() {
			System.out.println("Child5's method1() called");
		}
		public void method3() {
			System.out.println("Child5's method3() called");
		}
	}
	public class ExtendsTest5 {
		public static void main(String[] args) {
			Parent5 p = new Parent5();
			// 부모클래스 타입의 객체는 자식클래스의 멤버와 메서드를 호출할 수 없습니다.
			// 부모클래스 타입으로 선언되고 생성된 객체는 DownCasting 되지 못한다.
			Child5 c = new Child5();
			// 부모로부터 상속받은 필드와 메서드를 호출 및 사용할 수 있기 때문에 UpCasting은 필요하지 않다.
			System.out.println(c.a);
			c.method1();
			p = new Child5();
			// 이 때, p 객체는 다형성 객체이다.
				// 생성된 자식 객체가 부모타입으로 UpCasting 됨.
			// 즉, 부모클래스는 객체 생성 시, 자식클래스 중 하나로 객체를 생성할 수 있다.
			System.out.println(p.a); // 1, 멤버필드는 선언자 우선
			p.method1(); // Child5's method1() called, override 메서드 우선
			System.out.println(((Child5)p).x);
			((Child5)p).method3();
			// DownCasting을 하지 않으면, p는 Child5가 아닌 Parent5를 참조한다.
			// UpCasting 된 객체는 DownCasting이 가능하다.
			
			// 아래 내용을 보고 생각해보자. (아래 내용 모두 위와 같은 다형성 객체이다.)
			Parent5 p1 = new Child5();
			Object o = new String();
			o = Integer.valueOf(3);
		}
	}
	```
	```java
	package lab.java.basic;

	public class PloyTest {
		public void method(Object o) { // 자식객체가 전달될 경우 자동으로 UpCasting 된다.
			//o.length(); // 오류. UpCasting이 되었기 때문에 String 객체의 메서드를 쓸 수 없다.
			if(o instanceof String) {
				/* o가 String인지? Student인지? 알 수 없기 때문에
				instanceof 라는 연산자를 통해 String 객체인지 검사한다. */
				System.out.println(((String)o).length());
				// Object → String으로 DownCasting 진행.
				// 역시 UpCasting이 되었기 때문에 DownCasting이 가능하다.
			} else if (o instanceof Student) {
				
			}
		}
		public static void main(String[] args) {
			PloyTest test = new PloyTest();
			test.method(new String("java")); // Object 자식클래스인 String을 전달한 것이다.
			test.method(new Student());
			
			// instanceof 연산자 활용
			Object o = new Object();
			String s = new String("Java");
			Student s1 = new Student();
			System.out.println(o instanceof Object);
			// true
			// 객체가 자기 자신을 검사하면 true
			System.out.println(o instanceof String);
			// false
			// 부모객체는 자식클래스 타입이 될 순 없다.
			// 부모객체 is not a 자식클래스타입
			System.out.println(s instanceof Object);
			// true
			// 상속관계가 있으면 true
			// 부모 자식 관계를 is a 관계라고 한다.
			// 자식객체 is a 부모클래스타입
			//System.out.println(s1 instanceof String);
			// 상속관계가 아니기 때문에 호환되지 않는 타입이라 컴파일 오류 발생.
		}
	}
	```


## 오버라이딩(Overriding)
 - 기존 사용중인 프로그램은 유지하면서 기능을 덧붙여서 새로운 기능을 만들어야하는 사항의 개념에서 활용 가능하다.
 - 규칙
 	- AccessModifier는 동일하거나 access 범위가 더 넓은 modifier 선언
	- 리턴타입은 반드시 동일해야 한다.
	- 메서드이름은 반드시 동일해야 한다.
	- 파라미터의 순서, 개수, 타입도 동일해야 한다.
	- 부모클래스에 throws 예외클래스가 선언된 경우, 자식클래스에서 throws 예외클래스 선언을 생략할 수 있다.
		- throws 예외클래스를 선언하는 경우에는 부모클래스와 동일하게 선언해야 하다.
		- 선언된 예외클래스보다 상위 예외 클래스를 선언할 수 없다.
	- 자식클래스에서 오버라이딩(Overriding) 메서드 1개만 정의할 수 있다.
	```java
	package lab.java.basic;

	class Parent3 {
		public void action() {
			
		}
		public void action2(int type, String msg) {
			System.out.println("Parent's action2() called");
		}
	}
	class Child3 extends Parent3 {
		//private void action() {
		// 더 좁은 AccessModifier 이기 때문에 오류.
		//public int action() {
		// 리턴 타입이 다르기 때문에 오류
		//public void action2() {
		// 메서드 이름이 다르면 오버라이딩이 아닌 그냥 다른 메서드이다.
		public void action() {	
		
		}
		
		public void action2(String msg, int type) {
		// 오버라이드 메서드가 아니며, 오버로드 메서드이다.
		// 비록 다른 클래스지만 상속관계이기 때문에 오버로딩이 가능하다.
		   // 부모클래스의 데이터도 자신의 클래스처럼 쓰기 때문에..
			System.out.println("Child's overload action2() called");
		}
		
		public void action2(int type, String msg) {
		// 오버라이드 메서드이다.
			System.out.println("Child's override action2() called");
		}
	}
		
	public class ExtendsTest3 {
		public static void main(String[] args) {
			Child3 c3 = new Child3();
			c3.action2(0, null); // 오버라이드 메서드 호출
			c3.action2(null, 0); // 오버로드 메서드 호출
		}
	}
	```


## 인터페이스(interface)
 - 프린터가 있을 때, 장치는 같아도 회사별로 드라이버는 달리 쓰는 경우가 있다.
	- 이러한 경우에, 회사별로 매번 프로그램을 새로 만드는 것도 상당한 낭비가 있다.
	- 하여, 장치는 같기 때문에 기본적인 프로그램은 같이 쓰고 회사별로(=드라이버별로) 각각에 맞게 프로그램만 별도로 개발하는 것이 훨씬 낭비가 적다.
		- 이러한 개념을 인터페이스(interface)라고 한다.
 - 선언과 구현을 나눠 인터페이스로 표준을 수립하고, 각각의 상황에 맞게 구현을 하는 개념이다.
	- 추가적인 예시로는 프렌차이즈 음식점도 예를 들 수 있다.
		- 지역마다 약간의 차이는 있을지언정 대체로 맛은 동일하다.
	- 또 다른 예시로는 대표적으로 jdbc driver는 대부분 인터페이스로 구현되어 있다.
		- DB의 종류마다 특성이 달라도 모두 jdbc driver가 기반이다.
 - 인터페이스는 결합도가 낮다.
	- 결합도가 낮기 때문에 변경, 확장, 유지보수가 용이하다.
 - 특징(JDK8 이전)
	- 멤버필드는 public final static 필드만 가능하다.
	- 오직 추상 메서드만 선언 할 수 있다.
 - 특징(JDK8 이후)
	- 함수적 프로그래밍 언어(데이터 분석, 전처리 등)의 기능을 위해서 default 선언되는 메서드(구현 body를 가질 수 있다.) 를 정의할 수 있게 되었다.
		- 또한 static 선언되는 메서드(구현 body를 가질 수 있다.)도 정의할 수 있다.
		- private 메서드도 정의할 수 있다.
 - 특징(공통)
	- 인터페이스는 클래스는 상속받을 수 없다.
	- 인터페이스는 
 - 선언 방식
	```plaintext
	AccessModifier inteface 인터페이스이름 {...}
	AccessModifier inteface 인터페이스이름 extends 부모인터페이스, 부모인터페이스... {...}
	```
	```java
	public interface TV {
		String TYPE = "4K";
		 // 컴파일시점(바이트코드를 생성할 때) 자동 public static final 필드로 선언된다.
		public void on();
		 // 컴파일시점에 자동으로 abstract가 선언이 되어 body를 가질 수 없다.
		public void off();
		public default void defaultMethod() {
			System.out.println("인터페이스의 default 메서드");
		}
		public static void staticMethod() {
			System.out.println("인터페이스의 static 메서드");
		} // default, static은 추상메서드로 동작 안해서 body를 가질 수 있다.
	}
	```
	```java
	public class InterfaceTest {
		public static void main(String[] args) {
			System.out.println(TV.TYPE);
			 /* 객체 생성 없이, 인터페이스 이름으로 접근하였기 때문에
				static으로 자동 선언되는 것을 알 수 있다. */
			 //TV.TYPE = "RGB"; // 오류.
			 // 별도 선언 없이도 final로 동작하는 것을 알 수 있다.
			
			//TV tv = new TV(); // 오류.
			 // 구현 body가 없는 추상 메서드 때문에 인스턴스(객체) 생성이 불가하다.
			
			TV tv = new SamSungTV();
			 // 인터페이스에 대한 인스턴스를 생성하려면 구현 클래스로 생성해야 한다.
			 // abstract 다루듯이, 별도의 class로 생성해서 override 된 메서드를 호출해야한다는 얘기이다.
			tv.defaultMethod();
			tv.on();
		}
	}
	```
	```java
	public class SamSungTV implements TV {
		@Override
		public void on() {
			System.out.println("전원켜짐");
		}
		@Override
		public void off() {
			System.out.println("전원꺼짐");
		}
	}
	```
	- 아래는 다른 예제임.
	```java
	interface Vehicle {

	}
	interface Car {
		
	}
	public interface Bus extends Vehicle, Car {
		// 인터페이스는 다중 상속이 가능하다.
		// 클래스를 상속 받는게 아니라 인터페이스를 상속 받아야한다.
		   // 인터페이스는 인터페이스만 상속이 가능하다.
	}
	```


## 클래스 중첩 선언
 - 클래스 내부에 클래스를 정의할 수 있다.
 - 클래스의 멤버로서 클래스 정의 할 수 있다.
 	- Inner Member 클래스, static inner 클래스
	- Inner Member 클래스는 Outer 클래스의 모든 멤버에 제한 없이 access 가능하다.
	- Outer 클래스에서 Inner Member 클래스의 멤버를 사용하려면 객체를 생성해서 객체로 access 해야한다.
	- Inner Member 클래스는 protected 또는 private을 선언할 수 있다.
	```java
	package lab.java.basic;

	class Outer {
		// OuterClass는 default 외에 어떠한 접근제어자도 선언될 수 없다. 
		private int a=5;
		protected class Inner {
			// Inner는 MemberClass이기 때문에 접근제어자 선언이 가능하다.
			private int a=5;
			public void innerMethod() {
				System.out.println(a); // 5
				System.out.println(Outer.this.a); // 2
				 // static은 아니지만 outer class에 접근할때는 위와 같이 해야한다.
				outerMethod();
				 // inner class는 객체 생성 없이 outer class에 접근 가능하다.
				 // 변수 a는 inner와 outer 둘다 존재하기 때문에 this 를 쓴것이다.
			}
		} // 컴파일되면 Outer$Inner.class로 생성된다.
		public void outerMethod() {
			//innerMethod();
			 // 오류. outer class에서 inner class에 접근할 때는 객체를 생성해야 한다.
			Inner inn = new Inner();
			inn.innerMethod();
		}
	}
	public class InnerClassTest {
		public static void main(String[] args) {
			Outer o = new Outer();
			Outer.Inner inner1 = new Outer().new Inner(); // 방법1
			Outer.Inner inner2 = o.new Inner(); // 방법2
			 // inner 메서드는 outer 클래스 내부에 있기 때문에 객체 생성 시, 위와 같이 해야 한다.
		}
	}
	```
	```java
	class Outer2 { 
		private int a=5;
		static int b = 3;
		static class Inner2 {
			// Inner는 MemberClass이기 때문에 static 선언이 가능하다.
			static int num=5;
			public static void innerMethod() {
				//System.out.println(a); // non-static이기 때문에 호출 불가
				System.out.println(b);
			}
		}
		public void outerMethod() {
			Inner2.innerMethod();
		}
	}
	public class InnerClassTest2 {
		public static void main(String[] args) {
			Outer2.Inner2.innerMethod();
			// static이기 때문에 class명으로 호출 가능하다.
		}
	}
	```
 - 클래스의 멤버 메서드 내부에 클래스 정의 할 수 있다.
 	- Inner Local 클래스
	- Inner Local 클래스는 선언된 메서드 내부에서만 객체 생성할 수 있고, 사용할 수 있다.
	```java
	class Outer3 { 
		private int a=2;
		public void outerMethod() {
			int local = 100;
			class Inner {
				int num = 5;
				public void innerMethod() {
					System.out.println(num);
					System.out.println(local);
				}
			}
		}
		public void outerMethod2() {
			//Inner in = new Inner();
			 // 오류. 위 Inner Class는 로컬 변수와 동일한 의미로 활용되기 때문에 객체 생성이 불가하다.
		}
	}
	public class InnerClassTest3 {
		public static void main(String[] args) {
			
		}
	}
	```
 - 클래스는 **선언 → 구현 → 객체** 생성 과정에서 선언을 생략하고 이름 없는 클래스로써 객체 생성과 동시에 구현 할 수 있다.
 	- 익명 클래스
	```java
	public class AnonymousTest {
		public static void main(String[] args) {
			TV lg = new TV() {
				// 추상 클래스에 대해서 객체 생성과 초기화를 익명 클래스로 진행
				@Override
				public void on() {
					
				}
				@Override
				public void off() {
					
				}
			};
			lg.on();
			lg.off();
			Animal bird = new Animal() {
				@Override
				public void action() {
					
				}
			};
			bird.action();
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


## 기타 - Java의 메서드 호출 방식
 - Java에서는 포인터라는 개념이 없는 대신 아래와 같은 방식들이 있다.
	- CallByValue 방식
		- 메서드 호출할 때 값을 복사해서 전달
		- JVM이 호출하는 메서드의 파라미터가 Primitive Data Type이면 CallByValue 방식으로 전달(=값을 복사해서 전달)
	```java
	public class CallByValueEx {
		public void change(int a, int b) {
			System.out.println("a="+a+", b="+b); // a=10, b=50
			int temp = a;
			a = b;
			b = temp;
			// primitive data type이기 때문에 값의 변화가 있고, 메모리 주소상의 변화는 없다.
			System.out.println("a="+a+", b="+b); // a=50, b=10
		}
		public static void main(String[] args) {
			int x = 10, y = 50;
			// primitive data type이기 때문에 stack 영역에 저장
			CallByValueEx ex = new CallByValueEx();
			// class 영역에 객체가 생성됨.
			ex.change(x, y);
			// stack 영역에 change 메서드가 저장되었다가 메서드 종료 후, GC가 삭제함.
			System.out.println("x="+x+", y="+y); // x=10, y=50
		}
	}
	```
	- CallByReference 방식
		- 메서드 호출할때 주소를 전달
		- JVM이 호출하는 메서드의 파라미터가 Reference Data Type이면 주소를 전달합니다.
	```java
	public class CallByReferenceEx {
		public void change(int[] a, int[] b) {
			System.out.println("a[0]="+a[0]+", b[0]="+b[0]); // a[0]=10, b[0]=50
			int temp = a[0];
			a[0] = b[0];
			b[0] = temp;
			// 값이 아닌 메모리 주소를 a, b에 저장하였다.
			// x, y가 a, b와 메모리 주소가 같아 값이 같이는 것처럼 보인다.
			System.out.println("a[0]="+a[0]+", b[0]="+b[0]); // a[0]=50, b[0]=10
		}
		public static void main(String[] args) {
			int[] x = {10};
			int[] y = {50};
			// stack에 값이 아닌 메모리 주소가 저장됨.
			CallByReferenceEx ex = new CallByReferenceEx();
			ex.change(x, y);
			// stack 영역에 change 메서드가 저장되었다가 메서드 종료 후, GC가 삭제함.
			System.out.println("x[0]="+x[0]+", y[0]="+y[0]); // x[0]=50, y[0]=10
		}
	}
	```