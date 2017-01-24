---
title: "_com_error::GUID | Microsoft Docs"
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
  - "GUID"
  - "_com_error.GUID"
  - "_com_error::GUID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GUID 메서드"
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::GUID
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 **IErrorInfo::GetGUID** 함수를 호출합니다.  
  
## 구문  
  
```  
  
GUID GUID( ) const throw( );  
  
```  
  
## 반환 값  
 `_com_error` 개체 내에 기록된 **IErrorInfo** 개체에 대한 **IErrorInfo::GetGUID**의 결과를 반환합니다.  기록되는 **IErrorInfo** 개체가 없으면 `GUID_NULL`을 반환합니다.  
  
## 설명  
 **IErrorInfo::GetGUID** 메서드를 호출하는 동안 발생하는 모든 오류는 무시됩니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_com\_error 클래스](../cpp/com-error-class.md)