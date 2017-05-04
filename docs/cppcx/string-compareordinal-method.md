---
title: "String::CompareOrdinal 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::CompareOrdinal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::CompareOrdinal"
ms.assetid: dd4a7acc-fd23-4f1e-af85-64b9086f63f8
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::CompareOrdinal 메서드
개체가 나타내는 두 문자열 값에서 해당 문자의 숫자 값을 계산하여 두 `String` 개체를 비교합니다.  
  
## 구문  
  
```cpp  
  
int CompareOrdinal(  
           String^ str1,   
           String^ str2)  
  
```  
  
#### 매개 변수  
 `str1`  
 첫 번째 String 개체입니다.  
  
 `str2`  
 두 번째 String 개체입니다.  
  
## 반환 값  
 두 비교 대상 간의 어휘 관계를 나타내는 정수입니다. 다음 표에서는 가능한 반환 값을 보여 줍니다.  
  
|값|조건|  
|-------|--------|  
|\-1|`str1`가 `str2`보다 작은 경우|  
|0|`str1`이 `str2`와 같은 경우|  
|1|`str1`가 `str2`보다 큰 경우|  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** vccorlib.h  
  
## 참고 항목  
 [Platform::String 클래스](../cppcx/platform-string-class.md)