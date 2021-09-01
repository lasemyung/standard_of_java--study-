# object 클래스 : 모든 클래스의 조상

- 부모가 없는 클래스는 자동으로 object 클래스를 상속받게 된다

- 모든 클래스는 object 클래스에 정의된 11개의 메서드를 상속 받는다

  (toStroing(), equals(),hashCode(),)...

```java
Class Tv { // 부모 x
    //...  
}
class SmartTv extends Tv {  부모 o
    //...
}

//----------------------------------------

class Tv extends Object { // 위 Tv 클래스가 컴파일시 왼쪽처럼 자동으로 상속받음
    //...
}

class SmartTv extends Tv {  부모 o
    //...
}

```

