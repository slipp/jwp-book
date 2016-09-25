### 테스트 클래스 안의 멤버변수의 생존주기 (52페이지 내용)
52페이지에 아래와 같은 내용이 있는데 잘못된 내용입니다.

> @Before 애노테이션을 사용하지 않고 필드로 구현하는 방법은 CalculatorTest의 인스턴스가 생성될 때 Calculator 인스턴스가 생성되어 모든 테스트 메서드가 재활용하는 방식으로 동작한다. 이와 같이 Calculator 인스턴스가 재사용될 경우 ...

테스트 결과 각 테스트 메소드마다 매번 새로운 Calculator 인스턴스가 생성되어 동작합니다.
제보와 테스트 코드는 https://github.com/slipp/jwp-book/issues/1 에서 확인할 수 있습니다.

### java.lang.String.startsWith() 사용에 관하여 (125페이지 예제)
> // url = "/user/create?userId=test&password=pass&name=tester&email=a@b.com"
if ("/user/create".startsWith(url))

위와 같이 구현한 예제의 경우 GET 방식으로 구현하는 경우 항상 false 값이 반환되므로 정상 동작하지 않습니다. 이 경우 다음과 같이 구현하는 것이 맞습니다.
// url = "/user/create?userId=test&password=pass&name=tester&email=a@b.com"
if (url.startsWith("/user/create"))