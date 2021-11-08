# StringBuilder (동기화 X)

- StringBuufer는 동기화 되어 있다. 멀티 쓰레드에 안전(thread-safe) 

- 멀티 쓰레드 프로그램이 아닌 경우, 동기화는 불필요한 성능 저하

  이럴 땐 StringBufffer 대신 StringBuilder를 사용하면 성능 향상

  동기화 : 멀티 스레드에서 진행되고 있는 일에 다른 스레드가 들어와서 꼬이지 않게 함

  ![1](https://user-images.githubusercontent.com/86362202/140769882-534e0628-6912-4fd5-98db-6501295918a3.png)



## Math클래스

- 수학 관련 static메서드의 집합 (iv가 없으니까 객체를 만들필요가 없어서 static메서드만 있음)

  ```java
  public static final double E = 2.718218192343284234; //자연로그의 밑
  public Static final double PI = 3.14159283483292346; //원주율
  ```

  - round()로 원하는 소수점 아래 세번째 자리에서 반올림하기

![1](https://user-images.githubusercontent.com/86362202/140770703-11742bf4-4394-4f91-b124-8c8932559dc8.png)



## Math클래스의 메서드

![1](https://user-images.githubusercontent.com/86362202/140773466-6034c6ed-98ec-44ce-8b5b-12d8a2921c4a.png)

![1](https://user-images.githubusercontent.com/86362202/140773789-3e781094-b9c1-4cf6-b147-8bd66b042f5f.png)

