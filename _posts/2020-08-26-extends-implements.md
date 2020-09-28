---
title: 자바 상속(extends, implements) 차이
tags:
- java
---

# **상속**
1. extends
	부모에서 선언/정의를 모두하여 자식은 메소드/변수를 그대로 사용할 수 있다.
2. implements(interface구현)
	부모 객체는 선언만 하며 정의(내용)은 자식에서 오버라이딩 (재정의) 해서 사용해야함
3. abstract
	extends와 interface 혼합. extends하되 몇 개는 추상 메소드로 구현되어 있음

# extends
- 상속의 대표적인 형태다.
- 부모의 메소드를 그대로 사용할 수 있으며 오버라이딩 할 필요 없이 부모에 구현되있는 것을 직접 사용 가능하다.
- 자바는 다중상속을 지원하지 않는다. 대신 implements(인터페이스)가 등장했다.
- 다중상속이란 부모클래스가 두개 이상 존재하는 것
~~~
class Vehicle {
  protected int speed = 10;
  
  public int getSpeed(){
    return speed;
  }
  public void setSpeed(int speed){
    this.speed = speed;
  }
}

class Car extends Vehicle{
  public void printspd(){
    System.out.println(speed);
  }
}

public class ExtendsSample {
  public static main (String[] args){
    Car A = new Car();
    System.out.println(A.getSpeed());
    A.printspd();
  }
}
~~~

# implements
- 부모의 메소드를 반드시 오버라이딩(재정의)해야 한다.
~~~
interface TestInterface{
  public static int num = 8;
  public void fun1();
  public void fun2();
}

class InterfaceExam implements TestInterface{
  @Override
  public void fun1(){
    System.out.println(num);
  }
  
  @Override
  public void fun2() {
    
  }
}

public class InterfaceSample{
  public static void main(String args[]){
    InterfaceExam exam = new InterfaceExam();
    exam.fun1();
  }
}
~~~
