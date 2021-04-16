---
layout: post
title: "[Java] 상속"
categories: Java
tags: [java]
---

##### 1\. 상속이란?  
기존의 클래스를 재사용하여 새로운 서브 클래스 작성하는 것을 말한다.  
멤버의 모호성을 없애기 위해 , 다중 상속은 허용 불가   
(한번에 다중 상속 불가 여러 대에 걸쳐는 가능)  
 ex) 클래스 + extends + 상속받을 부모 클래스 이름  
  
자식 클래스는 부모의 메소드를 상속받아 사용이 가능하다.   
단, **private멤버**는 상속을 받을 수는 있지만 자식클래스에서 접근은 불가능하다.  

---

**< 상속 응용 >**

\- Main Class

~~~java
package chap05.exam01.inherit;
public class Main {
 public static void main(String[] args) {
  Person person = new Person(); //person 객체생성
  /*Mamal의 메서드->Person은 Mamal을 상속 받았기 때문에 mamal 메서드 사용 가능 */
  person.birth();
  person.eat();
  
  /*Person의 메서드*/ 
  person.social();
  person.talk();
  person.useTool();
 }
}

~~~

\- Birds Class

~~~java
package chap05.exam01.inherit;
public class Birds {
 
 public void birth() {
  System.out.println("알을 낳다.");
  
 }
 
 public void fluttering() {
  System.out.println("날개짓 하다.");
 }
}

~~~

\- Mamal Class

~~~java
package chap05.exam01.inherit;
public class Mamal {
 
 public void birth() {
  System.out.println("새끼를 낳다.");
  
 }
 
 public void eat() {
  System.out.println("음식을 먹다.");
 }
}

~~~

\- Mamal을 상속받은 Person Class

~~~java
package chap05.exam01.inherit;
public class Person extends Mamal{
 public void useTool() {
  System.out.println("도구를 쓴다.");
 }
 public void social() {
  System.out.println("사회생활을 한다.");
 }
 public void talk() {
  System.out.println("대화를 한다.");
 }
}

~~~