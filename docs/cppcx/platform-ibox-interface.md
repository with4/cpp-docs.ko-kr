---
title: "Platform::IBox 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IBox"
dev_langs: 
  - "C++"
ms.assetid: 774df45d-f8a7-45a3-ae24-eecc3c681040
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::IBox 인터페이스
[Platform::IBox](../cppcx/platform-ibox-interface.md) 인터페이스는 `Windows::Foundation::IReference` 인터페이스의 C\+\+ 이름입니다.  
  
## 구문  
  
```cpp  
template <typename T>  
interface class IBox  
```  
  
#### 매개 변수  
 `T`  
 boxed 값의 형식입니다.  
  
## 설명  
 `IBox<T>` 인터페이스는 [값 클래스 및 구조체\(C\+\+\/CX\)](../cppcx/value-classes-and-structs-c-cx.md)에 설명된 바와 같이 null을 허용하는 값 형식을 내부적으로 나타내는 데 주로 사용됩니다. 또한 이 인터페이스는 `Object^` 형식의 매개 변수를 사용하는 C\+\+ 메서드로 전달되는 값 형식을 boxing하는 데 사용됩니다. 입력 매개 변수를 `IBox<SomeValueType>`으로 명시적으로 선언할 수 있습니다. 예제를 보려면 [boxing](../cppcx/boxing-c-cx.md)를 참조하세요.  
  
## 요구 사항  
  
## 멤버  
 `Platform::IBox` 인터페이스는 [Platform::IValueType](../cppcx/platform-ivaluetype-interface.md) 인터페이스에서 상속합니다.`IBox`에는 다음과 같은 멤버가 포함됩니다.  
  
 **속성**  
  
|메서드|설명|  
|---------|--------|  
|값|이 `IBox` 인스턴스에 이전에 저장된 unboxed 값을 반환합니다.|  
  
## 참고 항목  
 [Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)