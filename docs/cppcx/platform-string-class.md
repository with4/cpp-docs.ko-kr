---
title: "Platform::String 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String"
ms.assetid: 72dd04a4-a694-40d3-b899-eaa0b503eab8
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::String 클래스
텍스트를 나타내는 데 사용되는 유니코드 문자의 순차적인 컬렉션을 나타냅니다. 자세한 내용과 예제를 보려면 [문자열](../cppcx/strings-c-cx.md)을 참조하세요.  
  
## 구문  
  
```cpp  
  
public ref class String sealed : Object,  
    IDisposable,  
    IEquatable,  
    IPrintable  
```  
  
## 반복기  
 String 클래스의 멤버가 아닌 두 반복기 함수를 `std::for_each` 템플릿 함수와 함께 사용하여 String 개체의 문자를 열거할 수 있습니다.  
  
|멤버|설명|  
|--------|--------|  
|`const char16* begin(String^ s)`|지정된 String 개체의 시작 부분에 대한 포인터를 반환합니다.|  
|`const char16* end(String^ s)`|지정된 String 개체의 끝을 지나는 포인터를 반환합니다.|  
  
## 멤버  
 String 클래스는 Object 및 IDisposable, IEquatable 및 IPrintable 인터페이스에서 상속합니다.  
  
 String 클래스에는 다음 형식의 멤버도 있습니다.  
  
 **생성자**  
  
|멤버|설명|  
|--------|--------|  
|[String::String 생성자](../cppcx/string-string-constructor.md)|String 클래스의 새 인스턴스를 초기화합니다.|  
  
 **메서드**  
  
 String 클래스는 [Platform::Object 클래스](../cppcx/platform-object-class.md)의 Equals\(\), Finalize\(\), GetHashCode\(\), GetType\(\), MemberwiseClose\(\) 및 ToString\(\) 메서드를 상속합니다. String에는 다음 메서드도 있습니다.  
  
|메서드|설명|  
|---------|--------|  
|[String::Begin 메서드](../cppcx/string-begin-method.md)|현재 문자열의 시작 부분에 대한 포인터를 반환합니다.|  
|[String::CompareOrdinal 메서드](../cppcx/string-compareordinal-method.md)|개체가 나타내는 두 문자열 값에서 해당 문자의 숫자 값을 계산하여 두 `String` 개체를 비교합니다.|  
|[String::Concat 메서드](../cppcx/string-concat-method.md)|두 String 개체의 값을 연결합니다.|  
|[String::Data 메서드](../cppcx/string-data-method.md)|현재 문자열의 시작 부분에 대한 포인터를 반환합니다.|  
|[String::Dispose 메서드](../cppcx/string-dispose-method.md)|리소스를 확보하거나 해제합니다.|  
|[String::End 메서드](../cppcx/string-end-method.md)|현재 문자열의 끝을 지나는 포인터를 반환합니다.|  
|[String::Equals 메서드](../cppcx/string-equals-method.md)|지정된 개체가 현재 개체와 같은지 여부를 나타냅니다.|  
|[String::GetHashCode 메서드](../cppcx/string-gethashcode-method.md)|이 인스턴스의 해시 코드를 반환합니다.|  
|[String::IsEmpty 메서드](../cppcx/string-isempty-method.md)|현재 String 개체가 비어 있는지 여부를 나타냅니다.|  
|[String::IsFastPass 메서드](../cppcx/string-isfastpass-method.md)|현재 String 개체가 *빠른 전달* 작업에 참여하고 있는지를 나타냅니다. 빠른 전달 작업에서는 참조 횟수가 일시 중단됩니다.|  
|[String::Length 메서드](../cppcx/string-length-method.md)|현재 String 개체의 길이를 검색합니다.|  
|[String::ToString 메서드](../cppcx/string-tostring-method-c-cx.md)|현재 문자열과 같은 값을 갖는 String 개체를 반환합니다.|  
  
 **속성**  
  
 String 클래스에는 다음과 같은 속성이 있습니다.  
  
|멤버|설명|  
|--------|--------|  
|[String::operator\=\= 연산자](../cppcx/string-operator-equality-operator-c-cx.md)|지정된 두 String 개체의 값이 같은지 여부를 나타냅니다.|  
|[operator\+ Operator](../cppcx/string-operator-decrementoperator.md)|두 String 개체를 새 String 개체에 연결합니다.|  
|[String::operator\> 연산자](../cppcx/string-operator-greater-than-operator-c-cx.md)|String 개체 값이 두 번째 String 개체 값보다 큰지 여부를 나타냅니다.|  
|[String::operator\>\= 연산자](../cppcx/string-operator-greater-than-or-equals-c-cx.md)|String 개체 값이 두 번째 String 개체 값보다 크거나 같은지 여부를 나타냅니다.|  
|[String::operator\!\= 연산자](../cppcx/string-operator-inequality-operator-c-cx.md)|지정된 두 String 개체의 값이 다른지 여부를 나타냅니다.|  
|[String::operator\< 연산자](../cppcx/string-operator-less-than-operator-c-cx.md)|String 개체 값이 두 번째 String 개체 값보다 작은지 여부를 나타냅니다.|  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더** vccorlib.h\(기본적으로 포함\)  
  
## 참고 항목  
 [Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)