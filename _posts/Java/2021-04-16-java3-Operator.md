---
layout: post
title: "[Java] 연산자"
categories: Java
tags: [java]
---

~~~java
/* 증감 연산자 */
package chap02.ex01.one;
public class One {
 public static void main(String[] args) {
  
  int x=1;
  int y=1;
  
  x++; // 증가가 나중에 2로 증가
  ++y; // 증가가 먼저
  
  System.out.println("X : "+x);
  System.out.println("Y : "+y);
  
  int result = (++x)+10;
  // X가 먼저 2에서 3으로 증가하고 10과 합산 == 13
  int result2 = (y++)+10;
  // y가 먼저 10과 합산되고 뒤늦게 3으로 증가 ==12
  
  System.out.println("result : "+result);
  System.out.println("result2 : "+result2);
  
  
  /* 논리부정 연산자 */
  boolean yn = true;
  System.out.println("YN : "+yn );
  yn = !yn; // '!' 는오로지 boolean에서만 사용됨
  System.out.println("YN : "+yn );
  
 }
}
 

package chap02.ex01.two;
public class Two {
 public static void main(String[] args) {
  //%연산(mod 연산)
  System.out.println("5%2 = "+5%2);
  System.out.println();
  
  //문자열 더하기
  String str1 = "JDK"+8+0.65;
  System.out.println(str1);
  
  String str2 = 8+0.65+ "version";
  System.out.println(str2);
  
  
 }
}
 
/* 대입 연산자 */
package chap02.ex02.two;
public class Substitution {
 public static void main(String[] args) {
  //A += 10 -> A = A+10
  String str = "대입 연산자는 ";
  str += "합 한 값을 ";
  str += "누적하는데 ";
  str += "유용하게 사용 된다.";
  System.out.println(str);
  int num = 1;
  num +=2;
  num +=3;
  num +=4;
  num +=5;
  
  System.out.println(num);
 }
}
 
/* 조건 연산자 */
package chap02.ex03.three;
public class Three {
 public static void main(String[] args) {
  // 값 = 조건? 맞으면 : 틀리면
  int score = 65;
  //score 가 90보다 큰가?
  //맞으면 A 아니면 B가 grade에 들어간다.
  
  /* 2019/04/01 박은지 - 더이상 사용 안함(곽부장님 지시 사항)
  char grade = score > 90 ? 'A' : 'B';
  System.out.println("홍길동의 점수 : "+grade);
  */
  
  //90보다 크면 A, 80보다 크면 B, 나머지는 C
  char grade2 = score > 90 ? 'A' :  (score >80) ? 'B' : 'C';
  System.out.println("홍길동의 점수 : "+grade2);
 
  
  
  
 }
}
~~~