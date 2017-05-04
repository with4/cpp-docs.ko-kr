---
title: "String::operator&gt;= 연산자(C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::operator>="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::operator>="
ms.assetid: 58cc458f-e82c-4024-b0c5-7f66941bc8aa
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::operator&gt;= 연산자(C++/CX)
String 개체 값이 두 번째 String 개체 값보다 크거나 같은지 여부를 나타냅니다.  
  
## 구문  
  
```cpp  
  
bool String::operator>=( String^ str1,  
                         String^ str2)  
  
```  
  
#### 매개 변수  
 `str1`  
 첫 번째 String 개체입니다.  
  
 `str2`  
 두 번째 String 개체입니다.  
  
## 반환 값  
 `str1`의 값이 `str2`의 값보다 크거나 같으면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** vccorlib.h  
  
## 참고 항목  
 [Platform::String 클래스](../cppcx/platform-string-class.md)