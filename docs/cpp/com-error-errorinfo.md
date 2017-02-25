---
title: "_com_error::ErrorInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error::ErrorInfo"
  - "ErrorInfo"
  - "_com_error.ErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ErrorInfo 메서드"
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::ErrorInfo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성자에 전달된 **IErrorInfo** 개체를 검색합니다.  
  
## 구문  
  
```  
  
IErrorInfo * ErrorInfo( ) const throw( );  
  
```  
  
## 반환 값  
 생성자에 전달된 원시 **IErrorInfo** 항목입니다.  
  
## 설명  
 `_com_error` 개체에서 캡슐화된 **IErrorInfo** 항목을 검색하거나 기록된 **IErrorInfo** 항목이 없으면 **NULL**을 검색합니다.  호출자는 반환된 개체 사용이 끝나면 해당 개체에 대한 **릴리스**를 호출해야 합니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_error 클래스](../cpp/com-error-class.md)