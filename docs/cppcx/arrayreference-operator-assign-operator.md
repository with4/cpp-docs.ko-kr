---
title: "ArrayReference::operator= 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::ArrayReference::operator="
dev_langs: 
  - "C++"
ms.assetid: 131a4612-d66b-48e4-90af-c665ccc0cce4
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# ArrayReference::operator= 연산자
의미 체계 이동을 사용하여 지정된 개체를[Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) 개체에 할당합니다.  
  
## 구문  
  
```cpp  
  
ArrayReference& operator=(ArrayReference&& __otherArg);  
  
```  
  
#### 매개 변수  
 `__ otherArg`  
 현재 `ArrayReference` 개체로 이동되는 개체입니다.  
  
## 반환 값  
 `ArrayReference` 형식의 개체에 대한 참조입니다.  
  
## 설명  
 `Platform::ArrayReference`는 ref 클래스가 아닌 표준 C\+\+ 클래스 템플릿입니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 참고 항목  
 [Platform::ArrayReference 클래스](../cppcx/platform-arrayreference-class.md)