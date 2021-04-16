---
layout: post
title: "[Java] 인터페이스"
categories: Java
tags: [java]
---

-   추상화 메서드를 통해 공동 작업 시 규격을 잡아주는 역할
-   모든 메소드가 추상메소드인 경우
-   인터페이스는 객체를 만들지 못한다.
-   인터페이스는 모든 메소드가 추상 메소드라서 abstract를 따로 붙이지 않는다!

---
<br/>
**\- Main Class**

```java
package chapter06.exam03.inter;
public class Main {
 public static void main(String[] args) {
  
  Window win = new Window();
  Linux linux = new Linux();
  Mac mac = new Mac();
  
  win.click(1);
  win.dbClick(2);
  linux.click(3);
  linux.dbClick(4);
  mac.click(5);
  mac.dbClick(6);
  
  //일반 메서드
  mac.wheel(44);//인터페이스는 객체를 만들지 못한다.
           //따라서 구현된 다른 클래스를 이용
  
  //static 사용
  MouseEvent.setDpi(50);
  
  //Linux , Mac
  
  
  //다형성 사용
  MouseEvent mou = null;
  mou = new Linux();
  mou.click(1);
  mou.dbClick(2);
  mou = new Mac();
  mou.click(3);
  mou.dbClick(4);
  mou = new Window();
  mou.click(5);
  mou.dbClick(6);
  
 }
}

```

**\- MouseEvent Interface**

```java
package chapter06.exam03.inter;
public interface MouseEvent {
 // 인터페이스에서는 추상메서드에서 abstract를 붙이지 않는다.
 public void click(int btn);
 public void dbClick(int btn);
 public double[] move();
 // 인터페이스에서는 일반 메서드를 사용할 수 없다.
 // JDK 1.8 부터는 가능
 // default 안붙이면 추상 메소드 라고 인식
 public default void wheel(int i) {
  if (i == 1) {
   System.out.println("윗 방향으로 스크롤");
  } else {
   System.out.println("아랫 방향으로 스크롤");
  }
 }
 
 
 public static void setDpi(int dpi) {
  System.out.println("감도 조절 : "+dpi);
 }
 
 
}

```

**\- Window MouseEvent  구현**

```
package chapter06.exam03.inter;
//implements = 구현 / 구현은 인터페이스를 대상으로 한다.
public class Window implements MouseEvent {
 @Override
 public void click(int btn) {
  System.out.println(btn+"번 버튼 클릭");
  
 }
 @Override
 public void dbClick(int btn) {
  System.out.println(btn+"번 버튼 더블 클릭");
 }
 @Override
 public double[] move() {
  
  return null;
 }
}

```

**\- Mac MouseEvent 구현**

```
package chapter06.exam03.inter;
public class Mac implements MouseEvent {
 @Override
 public void click(int btn) {
  System.out.println(btn+" 번 버튼 클릭");
 }
 @Override
 public void dbClick(int btn) {
  System.out.println(btn+" 번 버튼 더블 클릭");
 }
 @Override
 public double[] move() {
  // TODO Auto-generated method stub
  return null;
 }
}

```

**\- Linux MouseEvent 구현**

```
package chapter06.exam03.inter;
public class Linux implements MouseEvent {
 @Override
 public void click(int btn) {
  System.out.println(btn+" 번 버튼 클릭");
 }
 @Override
 public void dbClick(int btn) {
  System.out.println(btn+"번 버튼 더블 클릭");
 }
 @Override
 public double[] move() {
  // TODO Auto-generated method stub
  return null;
 }
}

```