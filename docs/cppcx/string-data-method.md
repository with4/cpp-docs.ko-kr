---
title: "String::Data 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Data"
ms.assetid: 9be4e015-dfb8-431e-a252-8498bd833f03
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::Data 메서드
개체의 데이터 버퍼 시작에 대한 포인터를 `char16`\(`wchar_t`\) 요소의 C 스타일 배열로 반환합니다.  
  
## 구문  
  
```  
const char16* Data()  
```  
  
## 반환 값  
 유니코드 문자의 `const``char16` 배열 시작에 대한 포인터입니다\(`char16`은 `wchar_t`의 typedef\).  
  
## 설명  
 이 메서드를 사용하여 `Platform::String^`에서 `wchar_t*`로 변환합니다.`String` 개체가 범위를 벗어나는 경우 데이터 포인터의 유효성이 더 이상 보장되지 않습니다. 원래 `String` 개체의 수명을 넘어서는 데이터를 저장하려면 [wcscpy\_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)를 사용하여 직접 할당한 메모리로 배열을 복사합니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** vccorlib.h  
  
## 참고 항목  
 [Platform::String 클래스](../cppcx/platform-string-class.md)   
 [String::Begin 메서드](../cppcx/string-begin-method.md)