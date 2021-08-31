# 생성자 this

- 생성자에서 다른 생성자 호출 할 때 사용

- 첫 줄에서만 사용 가능

  ```java
  class Car {
  	String color;		// 색상
  	String gearType;	// 변속기 종류 - auto(자동), manual(수동)
  	int door;			// 문의 개수
  
  	Car() {
  		color    = white;
  		gearType = auto;
  		door     = 4;	// 
  	}
  	// Car() { this ("white","auto",4) } 깔끔한 코드 
      
  	Car(String c, String g, int d) {
  		color    = c;
  		gearType = g;
  		door     = d;
  	}
  }
  ```

  

# 참조변수 this

- 인스턴스 자신을 가리키는 참조변수

- 인스턴스 메서드(생성자 포함)에서 사용 가능
- 지역변수와 인스턴스 변수를 구별할 때 사용

```java
Car ( String c, String g, int d) { // c,g,d 는 지역변수 lv
	color = c;  // color는 iv, c는 lv
	gearType = g;  // 원래 this. 을 붙어야하나 같은 클래스에서 생략 가능
	door = d;
}

Car ( String color, String gearType, int door) {
    this.color = color;  // this.color = iv , color =  lv
    this.gearType = gearType;
    this.door = door;
}
```



# 참조 변수 this와 생성자 this 정리

- this  :  인스턴스 자신을 가리키는  참조변수, 인스턴스의 주소가 저장되어 있다.

  ​           모든 인스턴스 메서드에 지역변수로 숨겨진 채로 존재한다

- this (), this(매개변수) : 생성자, 같은 클래스의 다른 생성자를 호출 할 때 사용한다



```java
class MyMath2 {
	long a, b // this.a this.b = iv의 진짜 이름  (long a, b) 는 iv
        
        MyMath2 ( int a, int b ) { // 생성자
        this.a = a;  // a,b 는 lv
        this.b = b;  // this 로 iv , lv 구분  
    }
    
    long add() {   // 인스턴스 메서드  -> this 사용 가능
 		return a + b ; // return this.a + this.b ( 생략 가능 ) , 원래는 붙여야 함  
    }
    
 	static long add ( long a, long b ) {  // 클래스 메서드(static 메서드) 
        return a + b;  // a,b 는 lv  , iv 사용불가, this 사용불가 ( 객체 자신이 없을        수도 있으니까)
    }
    }
}
```



## 생성자랑 인스턴스 메서드 = this 사용 가능 , static에선 불가능
