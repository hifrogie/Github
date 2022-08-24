## 9. Generic
### 1. 제네릭이 뭐지?
1. 제네릭은 형 변환에서 발생할 수 있는 문제점을 사전에 없애기 위해서 만들어졌다.
2. 실행시에 예외가 발생하는 것을 처리하는 것이 아니라 컴파일할 때 점검할 수 있도록 한 것이다.
```java
package d.generic;

import java.io.Serializable;

public class CastingGenericDTO<T> implements Serializable{
    private T object;
    public void setObject(T obj){
        this.object=obj;
    }
    public T getObject(){
        return object
    }
}
```
3. 코드 해석
    1. 클래스 선언문에 <>를 볼 수 있다. 타입 부분이 전부 T로 바뀌었다.
    2. T는 아무 이름이나 지정해도 되고 현재 존재하는 클래스를 사용해도 되지만 클래스 명명 규칙과 동일하게 지정하는 것이 좋다.
```java
package sec01.exam01;

import java.io.Serializable;

public class CastingGenericDTO<T> implements Serializable {
	private T object;
	public void setObject(T obj) {
		this.object=obj;
	}
	public T getObject() {
		return object;
	}
}
```

```java
package sec01.exam01;

public class GenericSample {

	public static void main(String[] args) {
		GenericSample sample = new GenericSample();
    }
public void checkGenericDTO() {
		CastingGenericDTO<String> dto1 = new CastingGenericDTO<String>();
		dto1.setObject(new String());
		CastingGenericDTO<StringBuffer> dto2 = 
				new CastingGenericDTO<StringBuffer>();
		dto2.setObject(new StringBuffer());
		CastingGenericDTO<StringBuilder> dto3 = 
				new CastingGenericDTO<StringBuilder>();
		dto3.setObject(new StringBuilder());
	}
}
```
4. dto1 ~ dto3까지 객체의 getObject() 메소드를 사용하여 객체를 가져올 때는 형변환을 할 필요 없이 다음과 같이 간단해진다.
    - String temp1 = dto1.getObject();
    - StringBuffer temp2 = dto2.getObject();
    - StringBuilder temp3 = dto3.getObject();

### 2. 제네릭 타입의 이름 정하기
1. 꺾쇠 안에 어떤 단어가 들어가도 상관은 없지만 자바에서 정의한 규칙은 있다.
2. 다른 사람이 보더라도 이해하기 쉽기 위해서 사용한다.
- E : 요소(Element)
- K : 키
- N : 숫자
- T : 타입
- V : 값
- S,U,V : 두 번째, 세 번째, 네 번째에 선언된 타입

### 3. wildcard 타입
```java
public void wildcardStringMethod(WildcardGeneric<?> c){
    Object value = c.getWildcard();
    System.out.println(value);
}
```
1. 다른 타입으로 선언된 WildcardGeneric 객체를 받을 수 있다.
2. 메소드 내부에서는 해당 타입ㅇ르 정확히 모르기 때문에 Object로 처리해야한다.
3. wildcard는 메소드의 매개 변수로만 사용해야한다. 어떤 객체를 wildcard로 선언하고, 그 객체의 값은 가져올 수 있지만 특정 타입으로 값을 지정하는 것은 불가능하다.

```java
public void callWildcardMethod(){
    WildcardGeneric<?> wildcard = new WIldcardGeneric<String>();
    wildcard.setWildCard("A");
    wildcardStringMethod(wildcard);// 컴파일 에러
}
```

### 4. <? extends 타입>
1. 제네릭 타입으로 extends 뒤의 타입을 상속받은 모든 클래스를 사용할 수 있다.
2. 다른 타입을 제네릭타입으로 선언한 객체가 넘어올 수 없다.
```java
public void boundedWildcardMethod(WildcardGeneric<? extends Car> c) {
    Car value = c.getWildcard();
    System.out.println(value);
}
```
### 5. 매개 변수로 사용된 객체에 값 추가
```java
public class GenericWildcardSample {
    public static void main(String args[]){
        GenericWildcardSample sample = new GenericWildcardSample();
    }
    public <T> void genericMethod(WildcardGeneric<T> c, T addValue){
        c.setWildcard(addValue);
        T value = c.getWildcard();
        System.out.println(value);
    }
}
```

1. 리턴 타입 앞에 <>로 제네릭 타입을 선언해놓았다. 그리고, 매개 변수에서는 그 제네릭 타입이 포함된 객체를 받아서 처리한 것을 볼 수 있다.setWildcard()메소드로 값을 할당했다.