---
layout: post
title: "[Java] 추상화"
categories: Java
tags: [java]
---

-   추상은 여러 객체의 공통되는 특성만을 추출한 것
-   추상화는 **abstract** 가 붙는다.
-   추상 클래스는 객체화가 불가능 하다. ( 단, 자식이 오버라이드 하여 사용 할 수 있음 )
-   추상 클래스는 실체 클래스와 **상속**관계!

**\- Main Class**

```java
package chapter06.exam02.absmethod;
public class Main {
 public static void main(String[] args) {
  Child drum = new Child();
  //추상 메서드를 구현한 내용은 자식으로 오버라이드 받아 사용해야함
  drum.세탁();
  drum.헹구기();
  drum.탈수하기();
  //추상 클래스의 일반 메서드 호출
  drum.건조하기();
  
 }
}
```

**\- Child Class**

```java
package chapter06.exam02.absmethod;
public class Child extends Laundry {
 @Override
 public void 세탁() {
  System.out.println("세탁하기");
 }
 @Override
 public void 헹구기() {
  System.out.println("헹구기");
 }
 @Override
 public void 탈수하기() {
  System.out.println("탈수하기");
 }
 @Override
 public void 건조하기() {
  System.out.println("건조하기");
  
 }
}

```

**\- Laundry Class**

```java
package chapter06.exam02.absmethod;
public abstract class Laundry {
 //무조건 만들어야 하는 기능들
 public abstract void 세탁();
 public abstract void 헹구기();
 public abstract void 탈수하기();
 public abstract void 건조하기();
}

```

**\- Abs Class**

```java
package chapter06.exam02.absmethod;
public abstract class Abs {
 // 추상 메서드 - 오버라이드 해서 사용 가능
 public abstract void must1();
 public abstract void must2();
 
 //자식이 그냥 쓰는게 가능, 오버라이드 해서 사용 가능
 public void parent() {
  System.out.println("부모 메서드");
 }
}

```

**\- Concrete Class**

```java
package chapter06.exam02.absmethod;
public class Concrete extends Abs {
 @Override
 public void must1() {
  
 }
 @Override
 public void must2() {
  
 }
}

```