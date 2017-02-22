---
title: "CArchiveException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CArchiveException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "archive exceptions [C++]"
  - "CArchiveException class"
  - "exceptions [C++], archive"
  - "exceptions [C++], serialization"
  - "serialization[C++], 예외"
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CArchiveException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

직렬화 하는 예외 조건을 나타냅니다.  
  
## 구문  
  
```  
class CArchiveException : public CException  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CArchiveException::CArchiveException](../Topic/CArchiveException::CArchiveException.md)|`CArchiveException` 개체를 생성합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CArchiveException::m\_cause](../Topic/CArchiveException::m_cause.md)|예외 원인을 나타냅니다.|  
|[CArchiveException::m\_strFileName](../Topic/CArchiveException::m_strFileName.md)|이 예외 조건에 대 한 파일 이름을 지정합니다.|  
  
## 설명  
 `CArchiveException` 클래스 예외 원인을 나타내는 공용 데이터 멤버를 포함 합니다.  
  
 `CArchiveException`개체를 생성 하 고 내부 발생  [CArchive](../../mfc/reference/carchive-class.md) 멤버 함수입니다.  이러한 개체의 범위 내에서 액세스할 수 있는  **CATCH** 식.  원인 코드는 운영 체제에 독립적입니다.  예외 처리에 대 한 자세한 내용은  [예외 처리 \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [넓습니다](../../mfc/reference/cexception-class.md)  
  
 `CArchiveException`  
  
## 요구 사항  
 **헤더:**  afx.h  
  
## 참고 항목  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CArchive Class](../../mfc/reference/carchive-class.md)   
 [AfxThrowArchiveException](../Topic/AfxThrowArchiveException.md)   
 [예외 처리](../../mfc/reference/exception-processing.md)