---
layout: post
title: "[Java] 변수선언, 주석처리"
categories: Java
tags: [java]
---

~~~java
//한줄주석
/*여러줄 주석*/
주석바로달기 ctrl+/
- 변수를 만들 때 - 용도 , 이름, 초기값
- 숫자, 문자, 참거짓

package chap01.ex01.define;
public class Variable {
 public static void main(String[] args) {
 
  boolean varBool=true; //노란 밑줄 -> 안쓰이는 변수인데 지워야 되는거 아냐?
  System.out.println(varBool);
  
  int varInt=0; //일반적인 정수
  long varLong=10000000; //연봉 혹은 월급 계산과 같은 큰 숫자 int<long
  
  float varFloat=0.01f; //소숫점(일반적으로 사용)
  double varDouble=0.0000001; //큰소수점(좌표계)
  
  System.out.println(varFloat);
  System.out.println(varDouble);
  
  //문자용도(문자, 문자열)
  char varChar='A'; //char는 무조건 한글자
  String varString="ABCEDG"; //string은 여러 글자 가능
 }
}
 
 
package chap01.ex02.scope;
public class VarScope {
 // 변수는 외부에서 생성되면 사용가능
 // 내부 생성되면 외부 사용 불가능
 // 장바구니와 마트 바구니 차이
   
 static String str="장바구니"; //전역변수(외부에서도 사용가능)
 
 public static void main(String[] args) {
  // TODO Auto-generated method stub
  System.out.println(str);
  int num=123;//지역변수(내부는 외부에 사용될수 없다)
  for(int i=0;i<=5;i++) {
   System.out.println(i+":"+num);
  }
  
 
 }
}
~~~