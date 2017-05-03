---
title: "Platform::Type 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Type 클래스"
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::Type 클래스
특정 형식에 대한 런타임 정보\(문자열 이름 및 형식 코드\)를 포함합니다. 임의의 개체에 대해 [Object::GetType 메서드](../cppcx/object-gettype-method.md)를 호출하거나 클래스 또는 구조체 이름에 대해 [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) 연산자를 사용하여 가져옵니다.  
  
## 구문  
  
```cpp  
public ref class Platform::Type :      Platform::Object,      Platform::Details::IEquatable,      Platform::Details::IPrintable  
```  
  
## 설명  
 `Type` 클래스는 개체의 런타임 형식을 기반으로 분기하는 `if` 또는 `switch` 문을 사용하여 처리를 지시해야 하는 응용 프로그램에서 유용합니다. 형식 범주를 설명하는 형식 코드는 [Type::GetTypeCode 메서드](../cppcx/type-gettypecode-method.md) 멤버 함수를 사용하여 검색합니다.  
  
## public 메서드  
  
|||  
|-|-|  
|[Type::GetTypeCode 메서드](../cppcx/type-gettypecode-method.md)|개체의 [Platform::TypeCode 열거형](../cppcx/platform-typecode-enumeration.md) 값을 반환합니다.|  
  
## public 속성  
  
|||  
|-|-|  
|[Type::FullName 속성](../cppcx/type-fullname-property.md)|형식의 정규화된 이름을 나타내며 ::\(콜론 두 개\) 대신 .\(점\)을 구분 기호로 사용\(예: "MyNamespace.MyClass"\)하는 [Platform::String 클래스](../cppcx/platform-string-class.md)^을 반환합니다.|  
  
## 변환 연산자  
  
|||  
|-|-|  
|[연산자 Type^](../cppcx/operator-subtracttype-hat.md)|`Windows::UI::Xaml::Interop::TypeName`을 `Platform::Type`으로 변환할 수 있습니다.|  
|[연산자 Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)|`Platform::Type`을 `Windows::UI::Xaml::Interop::TypeName`으로 변환할 수 있습니다.|  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)