---
layout: post
title: "[Java] 명시적, 묵시적 형변환"
categories: Java
tags: [java]
---

##### 1\. 명시적 형변환

\- 사과상자의 크기 > 못상자 크기   
\- 사과상자가 못상자에 들어갈수 있는지 확인해 봐야됨

##### 2\. 묵시적 형변환
\- 작은상자는 볼 것도 없이 큰상자에 들어감  
\- 형변환(변수 공간 활용 최적화)   
\- 같은 크기지만 용도 변경으로 형변환을 하기도 함

~~~java
package chap01.ex03.casting;public class Ex01 {
 public static void main(String[] args) {
  byte byteVal;
  char charVal;
  int intVal;
  long longVal;
  float floatVal = 0;
  double doubleVal;
  
  //크기순서 byte < char < int  일반적으로 utf=3byte(영어 1 한국어 2)
  byteVal=10; //byte는 기본숫자
  charVal='A'; //char는 문자다. (문자는 숫자에 대한 유니코드)
  intVal=byteVal; //가능하다 int>byte 작은걸 큰거에 대입하는건 묵시적 형변환
  intVal=charVal; //묵시적 형변환
  System.out.println(intVal); //A에 대한 유니코드
  
  //long > int
  longVal=intVal;
  
  //double > float
  doubleVal=floatVal;
  
 }
}
 
 
package chap01.ex03.casting;
public class Ex02 {
 public static void main(String[] args) {
  //명시적 형변환 (큰->작,동일 크기 끼리 용도 변환 할때)
  char charVal;
  int intVal;
  long longVal;
  float floatVal;
  double doubleVal;
  
  intVal=44032;
  charVal=(char)intVal; //큰->작 못들어감 명시적 형변환
  
  //명시적 형변환은 이클립스가 보통 알아서 해준다(100%는 아님)
  System.out.println(charVal);
  longVal=500;
  
  //long -> int
  intVal=(int)longVal;
  System.out.println(intVal);
  
  
  doubleVal=3.14;
  
  //double -> float
  floatVal=(float)doubleVal;
  System.out.println(floatVal);
 
 }
}
 
 
package chap01.ex03.casting;
public class Ex03 {
 public static void main(String[] args) {
  System.out.println("byte 최대값 : "+Byte.MAX_VALUE);
  System.out.println("byte 최대값 : "+Byte.MIN_VALUE);
  
  System.out.println("int 최대값 : "+Integer.MAX_VALUE);
  System.out.println("int 최소값 : "+Integer.MIN_VALUE);
  
  //long, float, double 최소 최대
  System.out.println("long 최대값 : "+Long.MAX_VALUE);
  System.out.println("long 최소값 : "+Long.MIN_VALUE);
  
  System.out.println("float 최대값 : "+Float.MAX_VALUE);
  System.out.println("float 최소값 : "+Float.MIN_VALUE);
  
  System.out.println("double 최대값 : "+Double.MAX_VALUE);
  System.out.println("double 최소값 : "+Double.MIN_VALUE);
 }
}
~~~