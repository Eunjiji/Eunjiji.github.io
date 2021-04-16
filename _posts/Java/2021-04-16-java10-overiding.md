---
layout: post
title: "[Java] 오버라이딩"
categories: Java
tags: [java]
---

**1\. 메소드 오버라이딩이란?**  
메소드 재정의라고도 한다. 부모에서 상속받은 메서드 자식에서 다시 정의 하는것을 말한다.  
  
**2\. 정적바인딩****이란?**  
객체의 타입이 컴파일러에 의해 컴파일 되는 시점에 결정되는 것   
ex) private , final , static  
  
**3\. 동적바인딩이란?**  
객체의 타입이 실행 중에 결정되는 것  
ex) 상속의 오버라이딩의 예  
  
**4\. super****와 ****super() ****생성자**  
super = 부모 클래스의 멤버를 지칭할 때 사용  
super() = 부모 클래스의 생성자를 호출할때 사용

---

\- Main Class

```java
package chap05.exam04.tune;
public class Main {
 public static void main(String[] args) {
  MyCar car = new MyCar();
  car.start();// 부모것이 호출
  car.run();// 자식이 오버라이드 했기 때문에 자식의 run이 호출됨
  car.stop();// 부모
  car.sw = true;
  car.stop();//자식이 바꾼 내용
 }
}

```

\- MyCar Class

```java
package chap05.exam04.tune;
public class MyCar extends ParentCar {
 boolean sw = false;
 // 오버라이드
 @Override
 public void run() {
  // super.run();//부모의 run을 가져다 쓰겠다
  // 실행시키면 부모의 run이 실행됨
  System.out.println("시속 100으로 달린다.");
 }
 @Override
 public void stop() {
  if (sw) {
   System.out.println("정지 후 자동 주차");// 새 기능
  } else {
   super.stop();//부모의 기능
  }
 }
}

```

\- ParentCar Class

```java
package chap05.exam04.tune;
public class ParentCar {
 public void start() {
  System.out.println("시동을 건다.");
 }
 public void run() {
  System.out.println("시속 50으로 달린다.");
 }
 public void stop() {
  System.out.println("정지한다.");
 }
 
 //final 키워드가 붙으면 오버라이드 할 수 없다.
 public final void test() {
  System.out.println("자체 점검 ");
 }
}
```