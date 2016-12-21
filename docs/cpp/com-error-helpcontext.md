---
title: "_com_error::HelpContext | Microsoft Docs"
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
  - "_com_error::HelpContext"
  - "HelpContext"
  - "_com_error.HelpContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HelpContext 메서드"
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::HelpContext
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 **IErrorInfo::GetHelpContext** 함수를 호출합니다.  
  
## 구문  
  
```  
  
DWORD HelpContext( ) const throw( );  
  
```  
  
## 반환 값  
 `_com_error` 개체 내에 기록된 **IErrorInfo** 개체에 대해 **IErrorInfo::GetDescription**의 결과가 반환됩니다.  **IErrorInfo** 개체에 대한 기록이 없으면 0을 반환합니다.  
  
## 설명  
 **IErrorInfo::GetHelpContext** 메서드를 호출하는 동안 발생하는 오류는 모두 무시됩니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_error 클래스](../cpp/com-error-class.md)