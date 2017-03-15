---
title: "_com_error::HelpFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "HelpFile"
  - "_com_error::HelpFile"
  - "_com_error.HelpFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HelpFile 메서드"
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::HelpFile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 **IErrorInfo::GetHelpFile** 함수를 호출합니다.  
  
## 구문  
  
```  
  
_bstr_t HelpFile() const;  
  
```  
  
## 반환 값  
 `_com_error` 개체 내에 기록된 **IErrorInfo** 개체에 대한 **IErrorInfo::GetHelpFile**의 결과를 반환합니다.  결과 BSTR은 `_bstr_t` 개체에 캡슐화됩니다.  기록되는 **IErrorInfo**가 없으면 빈 `_bstr_t`를 반환합니다.  
  
## 설명  
 **IErrorInfo::GetHelpFile** 메서드를 호출하는 동안 발생하는 모든 오류는 무시됩니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_error 클래스](../cpp/com-error-class.md)