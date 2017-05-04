---
title: "String::Equals 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Equals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Equals"
ms.assetid: b0c78419-242d-4d38-93e3-ff2818412624
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::Equals 메서드
지정된 String의 값이 현재 개체와 동일한지 여부를 나타냅니다.  
  
## 구문  
  
```cpp  
  
bool String::Equals(Object^ str);  
  
bool String::Equals(String^ str);  
  
```  
  
#### 매개 변수  
 `str`  
 비교할 개체입니다.  
  
## 반환 값  
 `true`이 현재 개체와 같으면 `str`이고, 그렇지 않으면 `false`입니다.  
  
## 설명  
 이 메서드는 [String::CompareOrdinal 메서드](../cppcx/string-compareordinal-method.md)와 동일합니다. 첫 번째 오버로드에서는 `str` 매개 변수가 String^ 개체로 캐스팅될 수 있어야 합니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** vccorlib.h  
  
## 참고 항목  
 [Platform::String 클래스](../cppcx/platform-string-class.md)