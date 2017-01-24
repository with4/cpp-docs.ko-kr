---
title: "_com_error::operator = | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error::operator="
  - "_com_error.operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= 연산자, 특정 Visual C++ 개체와 사용"
  - "operator = _com_error 개체"
  - "operator= _com_error 개체"
ms.assetid: b9cc4094-d055-450c-b45a-0a95317488f8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::operator =
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 기존 `_com_error` 개체를 다른 개체에 할당합니다.  
  
## 구문  
  
```  
  
      _com_error& operator = (  
   const _com_error& that   
) throw ( );  
```  
  
#### 매개 변수  
 `that`  
 `_com_error` 개체  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_error 클래스](../cpp/com-error-class.md)