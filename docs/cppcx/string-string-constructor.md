---
title: "String::String 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::String"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::String"
ms.assetid: 80b6461a-5b12-4dcb-9323-f2c5f310bbc6
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::String 생성자
입력 문자열 데이터의 복사본을 사용하여 String 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```cpp  
  
String();  
  
String(  
  char16* s  
)  
  
String(  
  char16* s,   
  unsigned int n  
)  
```  
  
## 매개 변수  
 `s`  
 문자열을 초기화하는 일련의 와이드 문자입니다. char16  
  
 `n`  
 문자열의 길이를 지정하는 숫자입니다.  
  
## 설명  
 성능이 중요하며 소스 문자열의 수명을 제어한다면 String 대신 [Platform::StringReference](../cppcx/platform-stringreference-class.md)를 사용할 수 있습니다.  
  
## 예제  
  
```  
String^ s = L”Hello!”;  
```  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** vccorlib.h  
  
## 참고 항목  
 [Platform::String 클래스](../cppcx/platform-string-class.md)