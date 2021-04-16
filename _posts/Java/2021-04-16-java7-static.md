---
layout: post
title: "[Java] Static 초기화, final , 상수선언"
categories: Java
tags: [java]
---

**< static >**

1.  static final 은 절대 바꿀수 없는것을 의미한다 ( ex : 주민등록번호 )
2.  static 영역은 클래스의 원본으로 주소가 이동되지 않는다.

**< final >**

1.  final 은 프로그램이 종료 될 때까지 바꿀수 없다.
2.  final 은 read only의 개념

---  


**< static 초기화 >**

\- Main Class

~~~java
package chap04.exam08.sBlock;
public class Main {
 public static void main(String[] args) {
  System.out.println("Monitor 속성 호출");
  //company, model, price
  System.out.println(Monitor.conpany);
  System.out.println(Monitor.model);
  System.out.println(Monitor.price);
  
 } 
}
~~~

\- Monitor Class

~~~java
package chap04.exam08.sBlock;
public class Monitor {
 static String conpany = "LG";
 static String model = "Wide Curved Monitor";
 static int price;
 //static은 객체화가 불가능 하므로 생성자에서 초기화도 불가능,
 //static block 으로 초기화 한다.
 
 static {
  System.out.println("price 초기화");
  price = 1000000;
 }
 
}

~~~

---

**< final 및 static 초기화 >**

\- Main Class

~~~java
package chap04.exam09.readOnly;
public class Main {
 public static void main(String[] args) {
  // 객체 생성시 초기화
  Person p = new Person("KOREA","바악은지");
  /*final이 붙어 있으면 값 변경이 불가능 하다.
   * person.name = "홍길동";
   */
  System.out.println(p.nation);
  System.out.println(p.name);
  System.out.println(Person.ssn);
 }
}
 

~~~

\- Person Class

~~~java
package chap04.exam09.readOnly;
public class Person {

 final String nation;
 static final String ssn; //상수(CONSTANT)
 final String name;
 
 static {//사실상 초기화가 불가능
  ssn = "180816-1234567";
  
 }
 
 
 public Person(String nation, String name) {
  // final은 생성자에서 초기화 가능
  this.nation = nation;
  this.name = name;
  
 }
}

~~~

---

**< 상수 선언 >**

~~~java
package chap04.exam10.constant;
public class Person {

//상수의 변수는 대문자로 작성 , static final 선언
 static final String NAME;
 static final String SSN;
 static final String GENDER;
 
 static {
  NAME = "PARK EUN JI";
  SSN = "124245-752";
  GENDER = "F";
    
 }
 
}

~~~