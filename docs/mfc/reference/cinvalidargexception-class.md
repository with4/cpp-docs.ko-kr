---
title: "CInvalidArgException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CInvalidArgException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInvalidArgException class"
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CInvalidArgException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 잘못 된 인수 예외 조건을 나타냅니다.  
  
## 구문  
  
```  
  
class CInvalidArgException : public CSimpleException  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CInvalidArgException::CInvalidArgException](../Topic/CInvalidArgException::CInvalidArgException.md)|생성자입니다.|  
  
## 설명  
 A `CInvalidArgException` 개체에 잘못 된 인수 예외 조건을 나타냅니다.  
  
 예외 처리에 대 한 자세한 내용은  [CException 클래스](../../mfc/reference/cexception-class.md) 항목 및  [예외 처리 \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [넓습니다](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CInvalidArgException`  
  
## 요구 사항  
 **헤더:** afx.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CSimpleException Class](../../mfc/reference/csimpleexception-class.md)