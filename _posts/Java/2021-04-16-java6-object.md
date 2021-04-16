---
layout: post
title: "[Java] 객체화, Static"
categories: Java
tags: [java]
---

##### < 객체화와 static\>

1.   '.'  을 찍어서 불러온다.
2.   static 영역은 클래스가 있는 영역이다.
3.  객체에서는 static 영역에 들어갈 수 없다. ( 이는 원본에 따로 표시한 내용을 복사본에서 볼 수 없는 것과 같다. )
4.  그래서 static 을 사용하기 위해서는 클래스로 접근한다.

**< Main Class >**

~~~java
/* Main Class */
package chap04.exam07.sMember;public class Main {
 public static void main(String[] args) {
  Sub s = new Sub(); // 객체화 하는 이유 : 원본을 보호(복사)
  int result = s.multi(6, 4); // 정수를 넣어줘야함 변수 아님
  System.out.println("답은 : " + result);
  System.out.println(Sub.sFiled);
  System.out.println(Sub.plus(5, 4));
  System.out.println(Sub.minus(5, 4));
 }
}
~~~

**< Sub Class >**

~~~java
package chap04.exam07.sMember;
public class Sub {
 
 static int sFiled = 134;
 
 static int plus(int a, int b) {
  return a+b;
 }
 
 static int minus(int a,int b) {
  return a-b;
  
 }
 
 int multi(int a, int b) {
  return a*b;
 }
 

}

~~~



**< 스스로를 객체화 할 수 있음 >**

~~~java
package chap04.exam07.sMember;
public class Inner {
 // static 영역
 public static void main(String[] args) {
  // msg를 쓰기 위해서 스스로를 객체화
  Inner inner = new Inner();
  inner.msg("hello");
 }
 // 객체화로 인해 heap에 있을 예정
 void msg(String msg) {
  System.out.println(msg);
 }
}
~~~

**... Static 부분은 다음글에서 더 자세히 다루겠음!**