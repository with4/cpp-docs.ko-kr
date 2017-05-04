---
title: "String::End 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::End"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::End"
ms.assetid: c02ad0db-d35d-45f4-9b2a-cfc76716358e
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::End 메서드
현재 문자열의 끝을 지나는 포인터를 반환합니다.  
  
## 구문  
  
```cpp  
  
char16* End()  
```  
  
## 반환 값  
 현재 문자열의 끝을 지나는 포인터입니다.  
  
## 설명  
 End\(\)는 Begin\(\)\+Length를 반환합니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** vccorlib.h  
  
## 참고 항목  
 [Platform::String 클래스](../cppcx/platform-string-class.md)