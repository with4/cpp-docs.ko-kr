---
title: "_com_error::Description | Microsoft Docs"
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
  - "_com_error.Description"
  - "_com_error::Description"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Description 메서드"
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::Description
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 **IErrorInfo::GetDescription** 함수를 호출합니다.  
  
## 구문  
  
```  
  
_bstr_t Description( ) const;  
  
```  
  
## 반환 값  
 `_com_error` 개체 안에 기록된 **IErrorInfo** 개체에 대해 **IErrorInfo::GetDescription**의 결과를 반환합니다.  결과 `BSTR`은 `_bstr_t` 개체에 캡슐화됩니다.  기록되는 **IErrorInfo**가 없으면 빈 `_bstr_t`를 반환합니다.  
  
## 설명  
 **IErrorInfo::GetDescription** 함수를 호출하고 `_com_error` 개체 안에 기록된 **IErrorInfo**를 검색합니다.  **IErrorInfo::GetDescription** 메서드를 호출하는 동안 발생한 오류는 무시됩니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_error 클래스](../cpp/com-error-class.md)