---
title: "_com_error::Error | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error.Error"
  - "_com_error::Error"
  - "Error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Error 메서드"
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::Error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성자에 전달된 `HRESULT`를 검색합니다.  
  
## 구문  
  
```  
  
HRESULT Error( ) const throw( );  
  
```  
  
## 반환 값  
 생성자에 전달된 원시 `HRESULT` 항목입니다.  
  
## 설명  
 `_com_error` 개체에서 캡슐화된 `HRESULT` 항목을 검색합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_error 클래스](../cpp/com-error-class.md)