---
title: "SafeIntException::SafeIntException | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeIntException"
  - "SafeIntException.SafeIntException"
  - "SafeIntException::SafeIntException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeIntException, 생성자"
ms.assetid: 8e5a0c24-a56b-4c80-9ee8-876604b1e7dc
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# SafeIntException::SafeIntException
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`SafeIntException` 개체를 만듭니다.  
  
## 구문  
  
```  
SafeIntException();  
  
SafeIntException(  
   SafeIntError code  
);  
```  
  
#### 매개 변수  
 \[in\] `code`  
 An enumerated data value that describes the error that occurred.  
  
## 설명  
 The possible values for `code` are defined in the file Safeint.h.  For convenience, the possible values are also listed here.  
  
-   `SafeIntNoError`  
  
-   `SafeIntArithmeticOverflow`  
  
-   `SafeIntDivideByZero`  
  
## 요구 사항  
 **Header:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## 참고 항목  
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeIntException 클래스](../windows/safeintexception-class.md)   
 [SafeInt 클래스](../windows/safeint-class.md)