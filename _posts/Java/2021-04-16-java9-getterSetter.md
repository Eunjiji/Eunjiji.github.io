---
layout: post
title: "[Java] Getter, Setter"
categories: Java
tags: [java]
---

**\- Getter : 값을 가져오는 메서드**  
**\- Setter : 값을 지정해 주는 메서드( 값 변경 할 때 사용)**

---

**< Getter, Setter 응용 >**

\- Main Class

~~~java
package chap04.exam12.prv;
import java.util.Scanner;
public class Main {
 public static void main(String[] args) {
  // 전원켜기 , 전원 상태 보기, 팬 속도 보기, 팬 속도 조절 , 온도 확인
    Computer com = new Computer(); //컴퓨터 객체 생성
    System.out.println("전원을 켜시겠습니까? : (Y/N) ");
    Scanner scan = new Scanner(System.in); //사용자에게 입력받을 때 사용
    String a = scan.nextLine(); //String 입력 : nextLine() / int 입력 : nextint()
    if (a.equals("Y")) { // 입력받은 a가 "Y"와 같다면
     //전원 켜기
     com.setPower(true); //setPower 메서드에 true 입력
     //전원 상태 보기
     System.out.println(com.isPower());
     //팬 속도 조절
     com.setPanSpeed(100);
     //팬 속도 보기
     System.out.println("팬 속도  ");
     System.out.println(com.getPanSpeed());
     //온도 확인
     System.out.println("PC 온도 : "+com.getTemp());
   
    }
    
    else if (a.equals("N")) {
     com.setPower(false);
    }
 }
}

~~~

\- Computer Class

~~~java
package chap04.exam12.prv;
public class Computer {
 private boolean power=false;// 외부에서 보기/수정 가능
 private int panSpeed; // 외부에서 보기/수정 가능
 private int temp=80;// 외부에서는 조절 불가/보기 가능(setter X)
  
 public boolean isPower() { //Power의 Getter
  return power;
 }
 public void setPower(boolean power) { //Power의 Setter
  this.power = power;
  if(this.power) {
   panSpeed = 50;
   temp = 60;
  }
  
  
 }
 public int getPanSpeed() { //PanSpeed의 Getter
  return panSpeed;
 }
 public void setPanSpeed(int panSpeed) { //PanSpeed의 Setter
  this.panSpeed = panSpeed;
  //내부적 합의 : 110-팬속도 = 온도
  temp = 110 - this.panSpeed;
 }
 public int getTemp() { //temp의 Getter
  return temp;
 }
 
}

~~~