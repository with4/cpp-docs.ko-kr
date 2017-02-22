---
title: "_com_error::Source | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error.Source"
  - "_com_error::Source"
  - "source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Source 메서드"
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::Source
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 **IErrorInfo::GetSource** 함수를 호출합니다.  
  
## 구문  
  
```  
  
_bstr_t Source() const;  
  
```  
  
## 반환 값  
 `_com_error` 개체 내에 기록된 **IErrorInfo** 개체에 대해 **IErrorInfo::GetSource**의 결과를 반환합니다.  결과 BSTR은 `_bstr_t` 개체에 캡슐화됩니다.  기록되는 **IErrorInfo**가 없으면 빈 `_bstr_t`를 반환합니다.  
  
## 설명  
 **IErrorInfo::GetSource** 메서드를 호출하는 동안 발생하는 모든 오류는 무시됩니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_error 클래스](../cpp/com-error-class.md)