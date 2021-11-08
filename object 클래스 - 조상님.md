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


object 클래스의 메서드	설명
protected Object Clone()	객체자신의 복사본은 반환한다
public boolean equals(Object obj)	객체 자신과 객체 obj가 같은 객체인지 알려줌
protecedvoid finalize() (잘안씀)	객체가 소멸될 때 가비지 컬렉터에 의해 자동적으로 호출된다. 이 대 수행되어야 하는 코드가 있을 때 오버라이딩 한다
public Class getClass()	객체 자신의 클래스 정보를 담고 있는 Class인스턴스를 반환한다
pbulic int hashCode()	객체 자신의 해쉬코드를 반환한다
public void notify()	객체 자신을 사용하려고 기다리는 쓰레드를 하나만 깨운다
public String toString()	객체 자신의 정보를 문자열로 반환한다
public void notifyAll()	객체 자신을 사용하려고 기다리는 모든 쓰레드를 깨운다
public void wait()	다른 쓰레드가 notify()나 notifyAll()을 호출할 때까지 현재 쓰레드를 무한히 또는 지저오딘 시간 동안 기다리게 한다.
public void wait(long timeout)	

