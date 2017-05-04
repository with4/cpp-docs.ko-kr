---
title: "StringReference::StringReference 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::StringReference::StringReference"
dev_langs: 
  - "C++"
ms.assetid: 87dd9201-e638-4913-b37c-7091ae3f91ea
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# StringReference::StringReference 생성자
`StringReference` 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```cpp  
  
    StringReference();  
  
   StringReference(const StringReference& __fstrArg)  
  
StringReference(const ::default::char16* __strArg)  
  
StringReference(const ::default::char16* __strArg, size_t __lenArg)  
```  
  
#### 매개 변수  
 `__fstrArg`  
 새 인스턴스를 초기화하는 데 해당 데이터가 사용되는 `StringReference`입니다.  
  
 `__strArg`  
 새 인스턴스를 초기화하는 데 사용되는 char16 값의 배열에 대한 포인터입니다.  
  
 `__lenArg`  
 `__strArg`의 요소 수입니다.  
  
## 설명  
 이 생성자의 첫 번째 버전은 기본 생성자입니다. 두 번째 버전은 `StringReference` 매개 변수로 지정된 개체에서 새 `__fstrArg` 인스턴스 클래스를 초기화합니다. 세 번째 및 네 번째 오버로드는 char16 값의 배열에서 새 `StringReference` 인스턴스를 초기화합니다. char16은 16비트 유니코드 텍스트 문자를 나타냅니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 참고 항목  
 [Platform::StringReference 클래스](../cppcx/platform-stringreference-class.md)