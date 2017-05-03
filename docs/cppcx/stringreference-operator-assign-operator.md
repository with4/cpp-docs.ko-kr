---
title: "StringReference::operator= 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::StringReference::operator="
dev_langs: 
  - "C++"
ms.assetid: 03a33467-d65f-4508-bcb4-17d7cc99398f
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# StringReference::operator= 연산자
지정한 개체를 현재 `StringReference` 개체에 할당합니다.  
  
## 구문  
  
```cpp  
  
   StringReference& operator=(const StringReference& __fstrArg);  
  
StringReference& operator=(const ::default::char16* __strArg);  
  
```  
  
#### 매개 변수  
 `__fstrArg`  
 현재 `StringReference` 개체를 초기화하는 데 사용되는 `StringReference` 개체의 주소입니다.  
  
 `__strArg`  
 현재 `StringReference` 개체를 초기화하는 데 사용되는 char16 값의 배열에 대한 포인터입니다.  
  
## 반환 값  
 `StringReference` 형식의 개체에 대한 참조입니다.  
  
## 설명  
 `StringReference`는 ref 클래스가 아니라 표준 C\+\+ 클래스이기 때문에 **개체 브라우저**에 나타나지 않습니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 참고 항목  
 [Platform::StringReference 클래스](../cppcx/platform-stringreference-class.md)