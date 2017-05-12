---
title: "Platform::Exception 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Exception 클래스"
ms.assetid: ca1d5a67-3a5a-48fe-8099-f9c38a2d2dce
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Platform::Exception 클래스
응용 프로그램을 실행할 때 나타나는 오류를 나타냅니다. 사용자 지정 예외 클래스는 `Platform::Exception`에서 파생될 수 없습니다. 사용자 지정 예외가 필요한 경우 `Platform::COMException`을 사용하고 앱 관련 HRESULT를 지정할 수 있습니다.  
  
## 구문  
  
```cpp  
public ref class Exception : Object,    IException,    IPrintable,    IEquatable  
```  
  
## 멤버  
 `Exception` 클래스는 `Object` 클래스 및 `IException`, `IPrintable`, `IEquatable` 인터페이스에서 상속됩니다.  
  
 `Exception` 클래스에는 다음과 같은 종류의 멤버도 있습니다.  
  
### 생성자  
  
|멤버|설명|  
|--------|--------|  
|[Exception::Exception 생성자](../cppcx/exception-exception-constructor.md)|`Exception` 클래스의 새 인스턴스를 초기화합니다.|  
  
### 메서드  
 `Exception` 클래스는 `Equals()`의 `Finalize()`, `GetHashCode()`,`GetType()`,`MemberwiseClose()`,`ToString()` 및 [Platform::Object 클래스](../cppcx/platform-object-class.md) 메서드에서 상속됩니다.`Exception` 클래스에는 다음 메서드도 있습니다.  
  
|멤버|설명|  
|--------|--------|  
|[Exception::CreateException 메서드](../cppcx/exception-createexception-method.md)|지정된 HRESULT 값을 나타내는 예외를 만듭니다.|  
  
### 속성  
 Exception 클래스에는 다음과 같은 속성도 있습니다.  
  
|멤버|설명|  
|--------|--------|  
|[Exception::HResult 속성](../cppcx/exception-hresult-property.md)|예외에 해당하는 HRESULT입니다.|  
|[Exception::Message 속성](../cppcx/exception-message-property.md)|예외를 설명하는 메시지입니다. 이 값은 읽기 전용이며 `Exception`이 생성된 후 수정될 수 없습니다.|  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)