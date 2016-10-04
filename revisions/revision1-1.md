### 테스트 클래스 안의 멤버변수의 생존주기 (52페이지 내용)
52페이지에 아래와 같은 내용이 있는데 잘못된 내용입니다.

> @Before 애노테이션을 사용하지 않고 필드로 구현하는 방법은 CalculatorTest의 인스턴스가 생성될 때 Calculator 인스턴스가 생성되어 모든 테스트 메서드가 재활용하는 방식으로 동작한다. 이와 같이 Calculator 인스턴스가 재사용될 경우 ...

테스트 결과 각 테스트 메소드마다 매번 새로운 Calculator 인스턴스가 생성되어 동작합니다.
제보와 테스트 코드는 https://github.com/slipp/jwp-book/issues/1 에서 확인할 수 있습니다.

### java.lang.String.startsWith() 사용에 관하여 (125페이지 예제)
> // url = "/user/create?userId=test&password=pass&name=tester&email=a@b.com"

> if ("/user/create".startsWith(url))

위와 같이 구현한 예제의 경우 GET 방식으로 구현하는 경우 항상 false 값이 반환되므로 정상 동작하지 않습니다. 이 경우 다음과 같이 구현하는 것이 맞습니다.

// url = "/user/create?userId=test&password=pass&name=tester&email=a@b.com"

if (url.startsWith("/user/create"))

### 4.2.1.5 요구사항 5 - 로그인하기 - logined=false 구현 부분(133페이지 내용)
> '4.2.1.5 요구사항 5 - 로그인하기'의 요구사항 마지막 줄에 '로그인이 실패하면 Cookie 헤더값이 logined=false로 전달되어야 한다.' 라고 쓰여져 있는데요, 4장의 코드에서 로그인 실패시 logined=false로 만들어 주는 부분을 찾지 못하겠습니다.

요구사항은 위와 같이 제시되어 있지만 구현 코드는 logined=false를 구현하지 않고 있다. 이와 같이 구현한 이유는 Cookie의 logined 값이 true 인 경우에만 로그인 상태로 판단하고 나머지는 로그인이 실패한 것으로 판단했기 때문이다.

만약 위 요구사항에 따라 logined=false 값을 전달하는 예제를 확인하고 싶다면 https://github.com/slipp/jwp-book/issues/4 문서를 참고할 수 있다.

### @FuncationalInterface 관련 설명(273페이지 내용)
> 람다를 사용하려면 RowMapper와 같이 인터페이스의 메서드가 하나만 존재해야한다. 람다 표현식으로 사용할 인터페이스라고 지정하려면 이터페이스에 @FuntionalInterface 애노테이션을 추가해야한다.

메소드가 하나만 존재해야한다라고 표현하고 있는데 추상 메소드가 하나만 존재해야 한다는 의미이다. 자바 8에서 추가한 디폴트 메소드를 존재할 수 있다. @FuntionalInterface 애노테이션의 경우 해당 인터페이스가 람다로 사용할 수 있다는 의미를 부여하는 것이지 반드시 추가해야 하는 것은 아니다. @FuntionalInterface 애노테이션이 없어도 얼마든지 람다로 사용할 수 있다.

이와 관련한 더 자세한 설명은 https://github.com/slipp/jwp-book/issues/3 또는 [FunctionalInterface javadoc](https://docs.oracle.com/javase/8/docs/api/java/lang/FunctionalInterface.html) 문서를 참고한다.