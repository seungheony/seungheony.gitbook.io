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

주석은 쉽다 C에서 사용하던 것과 동일하게 작성하면 된다.&#x20;

그래도 너무 짧으면 좀 그러니까 예제 코드는 아래에 남겨놓는다.&#x20;

```swift
// This is a comment.

/* This is the start of the first multiline comment.
 /* This is the second, nested multiline comment. */
This is the end of the first multiline comment. */
```

## 세미콜론 (Semicolons)

Swift에서는 코드 한줄이 끝날 때, 세미콜론을 붙혀주는게 필수가 아니다. Swift를 사용하면서 이게 참 좋았다.&#x20;

그래도 다음과 같이 여러 구문을 한줄로 작성할 때에는 써주어야 한다.&#x20;

```swift
let cat = "🐱"; print(cat)
// Prints "🐱"
```

## 정수 (Integers)

정수는 사실 너무 당연한 개념들이 많이 포함되어 있어서 길게 적진 않겠지만 몰랐던 개념들이 있어서 그것들만 살펴보고 넘어가보자

Swift는 8, 16, 32 그리고 64bit 형태의 부호가 있는 정수와 부호가 없는 정수를 지원한다. 이는 `UInt8` (Unsigned Int 8Bit)와 같이 C와 비슷한 이름을 가진다.&#x20;

## 부동 소수점 숫자 (Floating-Point Numbers)

이름이 어렵긴 한데 그냥 분수 성분을 가진 소수같은 숫자다. 부동 소수점 숫자를 표현할 수 있는 타입은 두 가지가 있는데 다음과 같다.&#x20;

* `Double`: 64-bit
* `Float`: 32-bit

> NOTE\
> `Double` 은 최소 15자리의 소수점 정확도를 가지고 있는것에 반해 `Float` 는 더 적은 6자리의 정확도를 가진다. 사용할 적절한 부동 소수점 타입은 코드에서 작업해야하는 값의 특성과 범위에 따라 다르다. [<mark style="color:blue;">두 타입 중에는</mark> <mark style="color:blue;"></mark><mark style="color:blue;">`Double`</mark> <mark style="color:blue;"></mark><mark style="color:blue;">이 선호된다.</mark> ](#user-content-fn-1)[^1]<mark style="color:blue;"></mark>

## <mark style="background-color:orange;">타입 세이프티와 타입 유추 (Type Safety and Type Inference)</mark>

먼가 중요해 보이는 개념이다. 자세하게 알아보도록 하자

&#x20;위에서도 언급했듯이 Swift는 타입-세이프(Type-Safe) 언어이다. 각 변수나 인스턴스에 할당된 타입이 아닌 잘못된 타입이 전달될 수 없다. 그래서 Swift에서는 각 값의 타입을 명확하게 알 수 있다.&#x20;

잘못된 타입을 전달 하는지는 컴파일 타임에 타입 검사를 수행해서 일치하지 않는 타입이 전달되면 이를 오류로 표시한다.&#x20;

또한 타입이 명시적으로 선언되지 않는 경우에는 컴파일러가 **타입 유추(Type Infernce)** 를 수행해서 특정 식의 타입을 자동으로 유추할 수 있다.&#x20;

## 숫자 리터럴 (Numeric Literals)

정수 리터럴은 아래와 같이 쓸 수 있다.&#x20;

* 접두사 없는 _10진수_
* `0b` 접두사로 _2진수_
* `0o` 접두사로 _8진수_
* `0x` 접두사로 _16진수_

아래의 예에서 모든 정수 리터럴은 10진수 `17` 의 값을 가진다:

```swift
let decimalInteger = 17
let binaryInteger = 0b10001       // 17 in binary notation
let octalInteger = 0o21           // 17 in octal notation
let hexadecimalInteger = 0x11     // 17 in hexadecimal notation
```

부동 소수점 리터럴은 10진수 (접두사 없음) 또는 16진수 (접두사 `0x`) 일 수 있다. 소수점 양쪽에 항상 숫자 (또는 16진수)가 있어야 한다. 10진수는 대문자 또는 소문자 e로 표시되는 _지수_ 를 가질 수도 있다. 16진수는 대문자 또는 소문자 p로 표시되는 _지수_ 를 가질 수도 있다.

지수가 `exp` 인 10진수는 기본 숫자에 $$10^{exp}$$ 가 곱해진다:

* `1.25e2` 는 1.25 x $$10^2$$, 또는 `125.0`
* `1.25e-2` 는 1.25 x $$10^{-2}$$ , 또는 `0.0125`

지수가 `exp` 인 16진수는 기본 숫자에 $$2^{exp}$$ 가 곱해진다:

* `0xFp2` 는 15 x $$2^2$$ , 또는 `60.0`
* `0xFp-2` 는 15 x $$2^{-2}$$ , 또는 `3.75`

아래의 예에서 모든 부동 소수점 리터럴은 10진수 `12.1875` 를 가진다:

```swift
let decimalDouble = 12.1875
let exponentDouble = 1.21875e1
let hexadecimalDouble = 0xC.3p0
```

숫자 리터럴은 읽기 쉽게 만드는 추가 포맷을 포함할 수 있다. 정수와 부동 소수점 모두 추가 0으로 채워질 수 있으며 가독성을 돕기 위해 밑줄을 포함할 수 있다. 어떤 형식도 리터럴의 기본 값에 영향을 주지 않는다:

```swift
let paddedDouble = 000123.456
let oneMillion = 1_000_000
let justOverOneMillion = 1_000_000.000_000_1
```

##





[^1]: 
