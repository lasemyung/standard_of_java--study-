# instanceof 연산자

- 참조변수의 형변환 가능 여부 확인에 사용, 가능하면 ture 반환
- 형 변환 전에 반드시 instanceof로 확인 해야 함

```java
void doWorkd(Car c) {
 	if (c instanceof FireEngine) {			// 형변환이 가능한지 확인
 		FireEngine fe = (FireEngine)c;		// 형변환
 		fe.wtaer();
 	}
}
```

```java
FireEngine fe = new FireEngine();
System.out.println(fe instanceof Object); // true  조상
System.out.println(fe instanceof Car);    // true  조상
System.out.println(fe instanceof FireEngine);  // true 자기 자신

// FireEngine -> car -> object 

Object obj = (Object)fe;  // 가능
Car     c  = (car)fe;     // 가능
```

