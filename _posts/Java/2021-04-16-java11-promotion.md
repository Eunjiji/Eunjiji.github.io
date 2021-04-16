---
layout: post
title: "[Java] 다형성, 프로모션"
categories: Java
tags: [java]
---

**1\. 다형성이란?**  
> 하나의 Type에 여러 객체를 관리 하는것

**\- Main Class**

```java
package chap05.exam05.poly;
public class Main {
 public static void main(String[] args) {
  // 5개의 클래스를 객체화 하여 useRoom 메소드를 호출
  Child child1 = new Child();
  child1.useRoom();
  ChildOne child2 = new ChildOne();
  child2.useRoom();
  ChildTwo child3 = new ChildTwo();
  child3.useRoom();
  ChildThree child4 = new ChildThree();
  child4.useRoom();
  ChildFour child5 = new ChildFour();
  child5.useRoom();
  
  System.out.println();
  /*
   * 위에서는 각 객체를 호출 할 때 마다 거기에 맞는 변수를 선언
   * 만약 그 객체가 30~40개 라면?? -> 30~40 개 변수 선언
   * 코드가 길어진다 , 힙 영역이 낭비된다.
   * 그래서 우리는 한번에 다 수용 할 수 있는 변수를 만들어야 한다. = 다형성!
   */

  //다형성을 통해 공통점이 있는 형태 로 담는다.
  ParentHouse house = null; //딱 하나의 변수 선언
  house = new Child();
  house.useRoom();
  
  house = new ChildOne();
  house.useRoom();
  
  house = new ChildTwo();
  house.useRoom();
  
  house = new ChildThree();
  house.useRoom();
  
  house = new ChildFour();
  house.useRoom();
 }
}

```

**\- Child Class**

```java
package chap05.exam05.poly;
//하나의 파일에 하나의 대표 클래스(public이 붙은 클래스)만이 존재 해야 한다.
public class Child extends ParentHouse {
 @Override
 public void useRoom() {
  System.out.println("첫째 방 사용");
 }
}
//대표를 제외한 나머지 클래스는 public이 붙지 않는다.
class ChildOne extends ParentHouse {
 @Override
 public void useRoom() {
  System.out.println("둘째 방 사용");
 }
}

class ChildTwo extends ParentHouse {
 @Override
 public void useRoom() {
  System.out.println("셋째 방 사용");
 }
}

class ChildThree extends ParentHouse {
 @Override
 public void useRoom() {
  System.out.println("넷째 방 사용");
 }
}

class ChildFour extends ParentHouse {
 @Override
 public void useRoom() {
  System.out.println("다섯째 방 사용");
 }
}
 
 
package chap05.exam05.poly;
public class ParentHouse {
 public void useRoom() {
  System.out.println("안방을 사용한다.");
 }
}

```

---

**2\. 프로모션이란?**   
> 작은것을 큰그릇에 담는 다는 개념

**\- Promotion Class**

```java
package chap05.exam06.promotion;

/*
 *                 Vertebrate : 척추 동물
 *                  /         |
 *              birds       Mamal
 *              /     |   /     |
 *    Chicken   Duck   Dog    Cat
 */
class Vertebrate{ }//척추동물
class Birds extends Vertebrate{ }//조류
class Mamal extends Vertebrate{ }//포유류
class Chicken extends Birds{ }//치킨
class Duck extends Birds{ }//오리
class Dog extends Mamal{ }//개
class Cat extends Mamal{ }//고양이

public class Promotion {
 public static void main(String[] args) {
  Vertebrate 척추동물; //척추동물이 가장 큰 개념
  척추동물 = new Dog(); // 작은것(강아지)을 큰그릇(척추동물)에 담는다!
  척추동물 = new Cat();
  척추동물 = new Duck();
  척추동물 = new Chicken();
  
  Mamal 포유류;
  포유류 = new Dog();
  포유류 = new Cat();
  //포유류를 상속받지 않았기 때문에 Promotion 불가
  //포유류 = new Chicken();
 }
}

```