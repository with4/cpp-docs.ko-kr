---
title: "CMemoryException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMemoryException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ 예외 처리, 메모리"
  - "CMemoryException class"
  - "예외, memory type"
  - "memory exceptions"
  - "메모리, 예외 처리"
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMemoryException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

메모리 부족 예외 조건을 나타냅니다.  
  
## 구문  
  
```  
class CMemoryException : public CSimpleException  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMemoryException::CMemoryException](../Topic/CMemoryException::CMemoryException.md)|`CMemoryException` 개체를 생성합니다.|  
  
## 설명  
 없음 추가 검증 필요입니다.  메모리 예외 throw 자동으로  **새**.  메모리 함수를 직접 작성 하는 경우 사용 하 여 `malloc`, 예를 들어, 다음 메모리 예외를 throw 하는.  
  
 에 대 한 자세한 내용은 `CMemoryException`, 문서를 참조 하십시오.  [예외 처리 \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [넓습니다](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CMemoryException`  
  
## 요구 사항  
 **헤더:**  afx.h  
  
## 참고 항목  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)