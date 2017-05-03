---
title: "String::Concat 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Concat"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Concat"
ms.assetid: 68052d22-3df0-4777-828d-fc3a8e8a3ab7
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::Concat 메서드
두 String 개체의 값을 연결합니다.  
  
## 구문  
  
```cpp  
  
String^ Concat( String ^ str1,   
String ^ str2  
)  
  
```  
  
#### 매개 변수  
 `str1`  
 첫 번째 String 개체 또는 `null`입니다.  
  
 `str2`  
 두 번째 String 개체 또는 `null`입니다.  
  
## 반환 값  
 `str1` 값과 `str2` 값의 연결을 값으로 하는 새로운 String^ 개체입니다.  
  
 `str1`이 `null`이고 `str2`가 아니면 `str1` 이 반환됩니다.`str2`가 `null`이고 `str1`이l 아니면 `str2`가 반환됩니다.`str1`과 `str2`가 모두 `null`이면 빈 문자열\(L""\)이 반환됩니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** vccorlib.h  
  
## 참고 항목  
 [Platform::String 클래스](../cppcx/platform-string-class.md)