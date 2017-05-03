---
title: "String::Length 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Length"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Length"
ms.assetid: 92376897-1bf2-4b7a-9298-d2d3f05d8d6b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::Length 메서드
현재 String 개체의 문자 수를 검색합니다.  
  
## 구문  
  
```cpp  
  
unsigned int Length()  
```  
  
## 반환 값  
 현재 String 개체의 문자 수입니다.  
  
## 설명  
 문자가 없는 String의 길이는 0입니다. 다음 String의 길이는 5입니다.  
  
```  
  
String^ str = "Hello";  
int len = str->Length(); //len = 5  
```  
  
 [String::Data 메서드](../cppcx/string-data-method.md)에서 반환하는 문자열 배열에 종결 NULL 또는 ‘\\0’인 추가 문자열이 하나 있습니다. 이 문자의 길이도 2바이트입니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** vccorlib.h  
  
## 참고 항목  
 [Platform::String 클래스](../cppcx/platform-string-class.md)