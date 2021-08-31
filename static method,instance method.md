# static 메소드 / 인스턴스 메소드



- 인스턴스 메소드 : 인스턴스 변수 사용 

  ​						  참조변수.메서드이름 -> 호출방법

  

- static 메소드 :  인터턴스 변수 사용 불가능

  ​						   객체 생성없이 클래스.메소드이름() -> 호출 방법

  ​							인스턴스 멤버와 관련없는 작업을 진행

```java
class MyMath2 {
	long a, b;   // 인스턴스 변수
	
	long add() {  //인스턴스 메소드 ( iv 사용)
        return a + b ;
    }
    
    static long add ( long a, long b ) { // 클래서 메서드(static 메서드)
        return a + b;   // 지역변수임 매개변수로 받기 때문에 인터스턴스 변수 필요 X
    }
}

class MyMathTest2 {
	public static void main(String args[]) {
						  // 클래스 이름.메소드이름();
        system.out.println ( MyMathTest2.add(200L,100L)); // static 메소드 호출
        MyMath2 mm = new MyMath2();  //인스턴스 생성
        mm.a = 200L ;
        mm.b = 100L;
        System.out.println(mm.add()); // 인스턴스메소드 호출 
	}                    // 참조변수.메소드이름();
}
```

