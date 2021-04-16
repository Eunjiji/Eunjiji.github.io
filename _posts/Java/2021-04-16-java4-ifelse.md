---
layout: post
title: "[Java] 조건문(if, else if, else)"
categories: Java
tags: [java]
---

~~~java
/* if문 예시 */
package chap02.ex04.ifstate;public class StmtIf {
 public static void main(String[] args) {
  
  System.out.println("철수가 두부를 사러간다.");
  int tubuBox =0;
  if(tubuBox>0) {// 두부가 있을 경우에만 실행
   System.out.println("두부를 산다.");
  }
  
  if(tubuBox<=0) {// 두부가 없을 경우에만 실행
   System.out.println("순두부를 산다.");
  }
  
  System.out.println("집에 온다.");
 }
}



/* else if문 예시 */
package chap02.ex04.ifstate;
import java.util.Scanner;
public class StmtElseif {
 public static void main(String[] args) {
  
  System.out.println("음료를 입력하세요 :");
  Scanner scan = new Scanner(System.in);
  String item = scan.nextLine();
  System.out.println(item + "을 선택 하셨습니다.");
  //콜라, 생수, 주스, 사이다
  //00가 나왔습니다.
  
  if(item.equals("콜라")) {
   System.out.println("콜라가 나왔습니다.");
  }
  
  else if(item.equals("생수")) {
   System.out.println("생수가 나왔습니다.");
  }
  
  else if(item.equals("주스")) {
   System.out.println("주스가 나왔습니다.");
  }
  
  else if(item.equals("사이다")) {
   System.out.println("사이다가 나왔습니다.");
  }
  
  else {
   System.out.println("주문하신 음료는 저희 메뉴에 없는 메뉴입니다.");
  }
  
  
 }
}



/* else문 예시 */
package chap02.ex04.ifstate;
public class StmtElse {
 public static void main(String[] args) {
  // 두부가 있으면 사오고 없으면 순두부 사오고
  
  int tudu=0;
  System.out.println("찰스가 두부를 사러 간다.");
  if(tudu>0) {
   System.out.println("두부를 산다.");
  }
  
  else {
   System.out.println("순두부를 산다.");
  }
  System.out.println("집에 가자!");
 }
}
~~~