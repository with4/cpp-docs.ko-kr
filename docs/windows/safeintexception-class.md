---
title: "SafeIntException 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeIntException Class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeIntException 클래스"
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# SafeIntException 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The `SafeInt` class uses `SafeIntException` to identify why a mathematical operation cannot be completed.  
  
## 구문  
  
```  
class SafeIntException;  
```  
  
## 멤버  
  
### Public 생성자  
 [SafeIntException::SafeIntException](../windows/safeintexception-safeintexception.md)  
 `SafeIntException` 개체를 만듭니다.  
  
## 설명  
 The [SafeInt 클래스](../windows/safeint-class.md) is the only class that uses the `SafeIntException` class.  
  
## 상속 계층  
 [SafeIntException Class](../windows/safeintexception-class.md)  
  
## 요구 사항  
 **Header:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## 참고 항목  
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeInt 클래스](../windows/safeint-class.md)