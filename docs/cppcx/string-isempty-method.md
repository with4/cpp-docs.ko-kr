---
title: "String::IsEmpty 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::IsEmpty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::IsEmpty"
ms.assetid: 4b651706-eace-4055-a694-d9e26a03ce05
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::IsEmpty 메서드
현재 String 개체가 비어 있는지 여부를 나타냅니다.  
  
## 구문  
  
```cpp  
  
bool IsEmpty()  
```  
  
## 반환 값  
 현재 String 개체가 `true` 또는 빈 문자열\(L""\)이면 `null`이고, 그렇지 않으면 `false`입니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** vccorlib.h  
  
## 참고 항목  
 [Platform::String 클래스](../cppcx/platform-string-class.md)