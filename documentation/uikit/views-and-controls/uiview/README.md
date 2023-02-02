---
description: Class - 화면의 사각형 영역의 내용을 관리하는 개체
---

# UIView

앱개발을 진행하면서 수도 없이 마주쳤던 클래스다. 하지만 이 클래스가 정확히 어떤 역할을 하는지는 이해하지 못하고 있었다. 이번에는 애플 공식 문서를 통해 UIView를 알아보자.

<figure><img src="https://s3.us-west-2.amazonaws.com/secure.notion-static.com/4d5825ab-4b46-46b1-a93d-e1dc501ed0e2/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-02-02_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_9.40.54.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&#x26;X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&#x26;X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20230202%2Fus-west-2%2Fs3%2Faws4_request&#x26;X-Amz-Date=20230202T022459Z&#x26;X-Amz-Expires=86400&#x26;X-Amz-Signature=4533fec5d1ab85183b7f505b1061e01bf7503af86510ef2aa705a8169eedaba6&#x26;X-Amz-SignedHeaders=host&#x26;response-content-disposition=filename%3D%22%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA%25202023-02-02%2520%25E1%2584%258B%25E1%2585%25A9%25E1%2584%258C%25E1%2585%25A5%25E1%2586%25AB%25209.40.54.png%22&#x26;x-id=GetObject" alt=""><figcaption></figcaption></figure>

* Class
* 화면의 사각형 영역의 컨텐츠를 관리하는 객체다.

## Declaration

```swift
@MainActor class UIView : UIResponder
```

## Overview

View는 앱 사용자 인터페이스의 기본 구성 요소이고 `UIView` 는 모든 View의 공통적인 동작을 정의하는 역할을 한다. 모든 View 객체는 사각형 영역 내에서 콘텐츠를 렌더링하고 해당 컨텐츠와의 모든 상호작용을 처리한다. 여기에서 `UIView` 는 예를들어 View 객체의 배경색을 고칠 수 있는 클래스다.

View 객체는 앱과 사용자 간의 상호작용할 수 있는 주요한 방법이기 때문에 많은 역할을 짊어지고 있다. 다음은 그 몇 가지 예시다.

* 그리기와 애니메이션
  * View들은 UIKit이나 Core Graphics를 사용해서 각 View의 사각형 영역에 컨텐츠를 그린다.
  * 일부 View의 속성을 새 값으로 애니메이션화할 수 있다.
* 레이아웃 및 subview 관리
  * view는 여러개의 subview를 포함할 수도 있고 하나도 포함하지 않을 수도 있다.
  * view는 subview의 크기와 위치를 조정할 수 있다.
  * Auto Layout을 사용하여 view 계층 구조의 변경에 따라 view 크기를 조정하고 위치를 변경하는 규칙을 정의한다.
* 이벤트 처리
  * view는 `UIResponder`의 subview이고 화면 터치나 다른 타입의 이벤트들에 반응할 수 있다.
  * view는 일반적인 제스처를 처리하기 위해 제스처 인식기를 설치할 수 있습니다.

***

view는 다른 view 내부에 중첩돼서 view 계층 구조를 생성할 수 있다. 이는 관련된(연결된) 컨텐츠를 구성할 수 있도록 하는 편리함을 제공한다.

view를 중첩하면 중첩된 자식 view(subview라고 함)와 부모 view(superview라고 함) 사이에 부모-자식 관계가 생성된다. 부모 view에는 여러 개의 subview가 포함될 수 있지만 각 subview에는 하나의 superview만 있다.

기본적으로 subview의 보여지는 영역이 superview의 bounds보다 넘어가게 되면 subview의 컨텐츠는 잘리지 않는다. `clipsToBounds`속성을 사용하여 해당 동작을 변경할 수 있다.
