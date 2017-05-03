---
title: "String::operator== 연산자(C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::operator=="
ms.assetid: c804b269-64f9-4bc0-929b-2dfa87bf46ac
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::operator== 연산자(C++/CX)
지정된 두 String 개체의 텍스트 값이 같은지 여부를 나타냅니다.  
  
## 구문  
  
```cpp  
  
bool String::operator==( String^ str1,  
                         String^ str2)  
  
```  
  
#### 매개 변수  
 `str1`  
 비교할 첫 번째 String 개체입니다.  
  
 `str2`  
 비교할 두 번째 String 개체입니다.  
  
## 반환 값  
 `true`의 내용이 `str1`와 같으면 `str2`이고, 그렇지 않으면 `false`입니다.  
  
## 설명  
 이 연산자는 [String::CompareOrdinal 메서드](../cppcx/string-compareordinal-method.md)와 동일합니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** vccorlib.h  
  
## 참고 항목  
 [Platform::String 클래스](../cppcx/platform-string-class.md)