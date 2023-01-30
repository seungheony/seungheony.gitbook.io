# 기본 (The Basics)

Swift는 `Int`, `Double`, `Float`, `Bool`, `String`과 같은 딱 봐도 그 타입을 알 수 있는 잘 알려진 기초 타입도 있지만, `Array`, `Set`, `Dictionary`와 같은 기본 콜렉션 타입도 제공하고 있다.&#x20;

또한 값이 변경될 수 있는 변수와 더불어 '상수'라는 개념이 있는데 이는 보다 명확하게 해당 변수의 값이 변경되지 않을 것이라는 확신을 주며, 코드를 보다 안전하고 명확하게 만들 수 있다.&#x20;

Swift에는 위에서 언급한 익숙한 개념도 있는가 하면 튜플(tuple)이라는 고급 타입이 있다. <mark style="background-color:purple;">튜플은 값을 그룹화해서 생성하거나 전달할 수 있다. 튜플을 사용해서 함수에서 발생할 수 있는 여러 타입의 값을 하나의 타입으로 모아서 리턴할 수 있다.</mark>&#x20;

옵셔널(Optional)은 "값이 있고 그 값은 X와 같다" 또는 "값이 없다"로 해당 변수의 값을 표현한다.&#x20;

Swift는 타입-세이프 (Type-Safe) 언어이다. 예를 들어 String을 요구하는 코드에서 Int가 전달되는 것을 코드 단에서 막아준다. 이는 개발 단계에서 빠르게 에러를 찾고 고칠 수 있게 도와준다.&#x20;

## 상수와 변수 (Constants and Variables)

상수와 변수는 모두 이름과 특정 타입의 값(Optional일 경우 `nil`도 가능)이 연결되어 만들어진다. 둘의 차이점으로 상수의 값은 최초 지정 후 변경이 불가능하지만 변수는 다른 값으로 변경이 가능하다.&#x20;

### 상수와 변수 선언 (Declaring Constants and Variables)

상수와 변수는 각각 `let`, `var`키워드로  선언할 수 있다. 다음의 예제에서 변경되지 말아야 할 값인 '최대 로그인 횟수'와 상시로 바뀌는 '현재 총 로그인 횟수'를 각 목적에 맞게 상수와 변수로 선언하고 있다.&#x20;

```swift
let maximumNumberOfLoginAttempts = 10
var currentLoginAttempt = 0
```

추가적으로 콤마(,)를 사용해 다음과 같이 여러개의 상수, 또는 변수를 선언할 수 있다.&#x20;

```swift
var x = 0.0, y = 0.0, z = 0.0
```

### 타입 명시 (Type Annotations)

상수 또는 변수를 선언할 때 저장할 수 있는 값의 종류를 명확하게 하기위해 _타입 명시 (Type Annotation)_ 를 제공할 수 있다. 타입 명시는 상수 또는 변수 이름 뒤에 콜론과 공백 한칸 뒤에 사용할 타입 이름을 적어 사용한다.&#x20;

```swift
var welcomeMessage: String
```

> NOTE\
> 실제로 타입 명시가 필요한 경우는 드뭅니다. 상수 또는 변수를 선언할 때 초기값을 지정하면 Swift는 [타입 세이프티와 타입 추론 (Type Safety and Type Inference)](undefined.md#type-safety-and-type-inference) 에서 나와있는대로 해당 상수 또는 변수에 사용될 타입을 거의 항상 유추할 수 있습니다. 위의 `welcomeMessage` 예제에서 초기값을 지정하지 않았으므로 `welcomeMessage` 변수의 타입은 초기값에서 유추되지 않고 타입을 명시 하였습니다.

### 상수와 변수의 이름 (Naming Constants and Variables)

일반적인 변수 선언과 동일하나 한글 변수도 가능하다. 하지만 영어를 사용하도록 하자 ㅎ

또한 Swift 카워드와 동일한 이름을 사용하고자 할 때에는 이름을 백틱 (\`)으로 묶어야 한다. 그래도 되도록이면 쓰지 말도록 하자.&#x20;

### 상수와 변수 출력 (Printing Constants and Variables)

기존에 많이 사용하듯이 `print()` 함수를 사용하면 된다. 그런데 Swift의 `print`는 기본적으로 줄바꿈 문자를 뒤에 포함하도록 하기 때문에 이를 변경하고자 한다면, `print(someValue, terminator: "")` 와 같이 `terminator` 에 빈 문자열을 넘겨주면 된다. 이상 미세먼지 팁이었다.&#x20;

그리고 문자열 중간에 상수나 변수 값을 넣고 싶을 때에는 다음 예제 코드와 같이 `\()`를 사용하면 된다.&#x20;

```swift
print("The current value of friendlyWelcome is \(friendlyWelcome)")
// Prints "The current value of friendlyWelcome is Bonjour!"
```

> NOTE\
> 문자열 삽입에서 사용할 수 있는 모든 옵션은 [문자열 삽입 (String interpolation)](broken-reference) 에 자세히 설명되어 있습니다.

## 주석 (Comments)

