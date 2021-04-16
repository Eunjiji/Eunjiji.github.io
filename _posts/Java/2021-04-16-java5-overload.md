---
layout: post
title: "[Java] 생성자 오버로드, this 사용"
categories: Java
tags: [java]
---

\- 생성자 오버로드 : 다양한 방법으로 객체 생성 가능  
\- 오버로딩은 철저히 사용자의 편의를 위해 만들어짐  
\- **<span style="color:red">인자값의 개수나 타입이 달라야 한다.</span>**

~~~java
/* 생성자 오버로딩 */
package chap04.exam03.cons;public class Robot {
 
 public String name;
 public String goal;
 public Robot() {
  
 }
 
 public Robot(String name) {
  name=name;
 }
 
 
 public Robot(String name,String goal) {
  //객체화 하면 생성자가 가장 먼저 실행됨
  System.out.println(" 음 ~ 칰힌 롸봐트 생성");
  //초기화
  name=name;
  goal=goal;
  
 
 }
}



/* 생성자 + this */
package chap04.exam04.overload;
public class NoteBook {
 
 String model;
 int price;
 String color;
 public NoteBook() {
  // TODO Auto-generated constructor stub
 }
 
 public NoteBook(String model) {
  this.model=model;
  //this 뒤의 값이 맨위 변수 선언한 이름
  //내가 메인에서 입력받은 값 내 변수에 넣어줌
 }
 public NoteBook(String model, int price) {
  this.model=model;
  this.price=price;
 }
 public NoteBook(int price) {
  
  this.price=price;
 }
 public NoteBook(String model, String color) {
  this.model=model;
  this.color=color;
 }
 public NoteBook(int price, String color) {
  
  this.price=price;
  this.color=color;
 }
 public NoteBook(String model, int price, String color) {
  
  this.model=model;
  this.price=price;
  this.color=color;
 }

}
 
 

package chap04.exam05.memnerCall;
public class Main {
 public static void main(String[] args) {
  
  Car car=new Car();
  Car car2=new Car();
  Car car3=new Car();
  Car car4=new Car();
  //위 네개의 객체는 모두 다르다.(같은 원본이지만 복사본이기 때문)
  
  car.Start(); //
  car.Start();
  car.change(3);
  car.change(4);
  car.change(5);
  
 }
}

~~~