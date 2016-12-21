---
title: "CSimpleException Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSimpleException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleException class"
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 MFC 예외 중요 한 리소스에 대 한 기본 클래스가입니다.  
  
## 구문  
  
```  
  
class AFX_NOVTABLE CSimpleException : public CException  
  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSimpleException::CSimpleException](../Topic/CSimpleException::CSimpleException.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSimpleException::GetErrorMessage](../Topic/CSimpleException::GetErrorMessage.md)|발생 한 오류에 대 한 텍스트를 제공 합니다.|  
  
## 설명  
 `CSimpleException`MFC 예외 중요 한 리소스에 대 한 기본 클래스 이며 소유권과 초기화 오류 메시지를 처리 합니다.  다음 클래스 사용 `CSimpleException` 해당 기본 클래스:  
  
|||  
|-|-|  
|[CMemoryException 클래스](../../mfc/reference/cmemoryexception-class.md)|메모리 부족 예외|  
|[CNotSupportedException 클래스](../../mfc/reference/cnotsupportedexception-class.md)|지원 되지 않는 작업에 대 한 요청|  
|[CResourceException 클래스](../../mfc/reference/cresourceexception-class.md)|Windows 리소스를 찾을 수 없습니다 또는 불가|  
|[CUserException 클래스](../../mfc/reference/cuserexception-class.md)|리소스를 나타내는 예외를 찾을 수 없습니다.|  
|[CInvalidArgException 클래스](../../mfc/reference/cinvalidargexception-class.md)|잘못 된 인수를 나타내는 예외|  
  
 때문에 `CSimpleException` 추상 기본 클래스를 선언할 수 없습니다 되는 `CSimpleException` 직접 개체입니다.  따라서 위의 표 에서처럼 파생된 개체를 선언 해야 합니다.  파생 된 클래스를 선언 하는 경우 이전 클래스를 모델로 사용 합니다.  
  
 자세한 내용은  [CException 클래스](../../mfc/reference/cexception-class.md) 항목 및  [예외 처리 \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [넓습니다](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## 요구 사항  
 **헤더:** afx.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [예외 처리](../../mfc/exception-handling-in-mfc.md)