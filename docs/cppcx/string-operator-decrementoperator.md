---
title: "String::operator+ 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::operator+"
dev_langs: 
  - "C++"
ms.assetid: 919b5ba4-3d3b-47a4-9893-9a9ce51fb9c8
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::operator+ 연산자
지정된 두 [String](../cppcx/platform-string-class.md) 개체의 값이 같은지 여부를 나타냅니다.  
  
## 구문  
  
```cpp  
  
bool String::operator+( String^ str1,  
                         String^ str2)  
  
```  
  
#### 매개 변수  
 `str1`  
 첫 번째 `String` 개체입니다.  
  
 `str2`  
 내용이 `String`에 추가될 두 번째`str1` 개체입니다.  
  
## 반환 값  
 `true`가 `str1`와 같으면 `str2`이고, 그렇지 않으면 `false`입니다.  
  
## 설명  
 이 연산자는 두 피연산자의 데이터가 들어 있는 `String^` 개체를 만듭니다. 매우 높은 성능이 중요하지 않은 경우 편의를 위해 이를 사용합니다. 함수에서 "`+`"를 몇 번 호출하는 것은 그렇게 눈에 띄지 않지만 대행 개체나 텍스트 데이터를 연속해서 조작하는 경우 표준 C\+\+ 매커니즘과 형식을 사용하세요.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** vccorlib.h  
  
## 참고 항목  
 [Platform::String 클래스](../cppcx/platform-string-class.md)