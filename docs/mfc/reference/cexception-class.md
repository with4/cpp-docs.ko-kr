---
title: "CException Class | Microsoft Docs"
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
  - "CException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchiveException class, 기본 클래스"
  - "CDaoException class, 기본 클래스"
  - "CDBException class, 기본 클래스"
  - "CException class"
  - "CFileException class, 기본 클래스"
  - "CInternetException class, 기본 클래스"
  - "CMemoryException class, 기본 클래스"
  - "CNotSupportedException class, 기본 클래스"
  - "COleDispatchException class, 기본 클래스"
  - "COleException class, 기본 클래스"
  - "CResourceException class, 기본 클래스"
  - "CUserException class"
  - "예외, classes for"
  - "매크로, 예외 처리"
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
caps.latest.revision: 22
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mfc 라이브러리에서 모든 예외의 기본 클래스입니다.  
  
## 구문  
  
```  
class AFX_NOVTABLE CException : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CException::CException](../Topic/CException::CException.md)|`CException` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CException::Delete](../Topic/CException::Delete.md)|삭제는 `CException` 개체입니다.|  
|[CException::ReportError](../Topic/CException::ReportError.md)|메시지 상자에 오류 메시지가 사용자에 게 보고합니다.|  
  
## 설명  
 때문에 `CException` 되는 추상 기본 클래스를 만들 수 없습니다 `CException` 개체를 직접. 파생된 클래스의 개체를 만들어야 합니다.  직접 만들어야 할 경우 `CException`\-스타일 클래스, 위의 모델로 파생된 클래스 중 하나를 사용 합니다.  또한 파생된 클래스를 사용 하는지 확인 하십시오 `IMPLEMENT_DYNAMIC`.  
  
 파생된 클래스 및 해당 설명이 아래에 나와 있습니다.  
  
|||  
|-|-|  
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|MFC 예외 중요 한 리소스에 대 한 기본 클래스|  
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|잘못 된 인수 예외 조건|  
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|메모리 부족 예외|  
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|지원 되지 않는 작업에 대 한 요청|  
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|보관 관련 예외|  
|[CFileException](../../mfc/reference/cfileexception-class.md)|특정 파일 예외|  
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Windows 리소스를 찾을 수 없습니다 또는 불가|  
|[COleException](../../mfc/reference/coleexception-class.md)|OLE 예외|  
|[CDBException](../../mfc/reference/cdbexception-class.md)|데이터베이스 예외 \(MFC 데이터베이스 클래스 기반 개방형 데이터베이스 연결에서 발생 하는 예외 조건\)|  
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|OLE 디스패치 \(자동화\) 예외|  
|[CUserException](../../mfc/reference/cuserexception-class.md)|리소스를 찾을 수 있는지를 나타내는 예외|  
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|데이터 액세스 개체 \(DAO 클래스에 대 한 발생 하는 예외 조건\) 예외|  
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|인터넷 \(인터넷 클래스에 대 한 발생 하는 예외 조건\) 예외가 발생 했습니다.|  
  
 이러한 예외를 사용할 목적으로 만들어진는  [THROW](../Topic/THROW%20\(MFC\).md),  [THROW\_LAST](../Topic/THROW_LAST.md),  [시도](../Topic/TRY.md),  [CATCH](../Topic/CATCH.md),  [AND\_CATCH](../Topic/AND_CATCH.md), 및  [END\_CATCH](../Topic/END_CATCH.md) 매크로.  예외에 대 한 자세한 내용은  [예외 처리](../../mfc/reference/exception-processing.md), 또는 문서를 참조 하십시오.  [예외 처리 \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
 특정 예외를 catch 하려면 해당 파생된 클래스를 사용 합니다.  예외를 모두 catch 형식으로 사용할 `CException`, 다음  [CObject::IsKindOf](../Topic/CObject::IsKindOf.md) 간에 구분 하기 위해 `CException`\-클래스를 파생 합니다.  이때 `CObject::IsKindOf` 합니다. 클래스 선언에  [클래스](../Topic/IMPLEMENT_DYNAMIC.md) 동적 형식 검사를 사용 하기 위해 매크로.  모든 `CException`\-만들 파생된 클래스에서 사용 해야 하는 `IMPLEMENT_DYNAMIC` 매크로 너무.  
  
 세부 정보는 사용자에 게 예외에 대 한 호출 하 여 보고할 수  [GetErrorMessage](../Topic/CFileException::GetErrorMessage.md) 또는  [ReportError](../Topic/CException::ReportError.md), 두 개의 멤버 함수를 함께 `CException`파생 클래스의.  
  
 된 매크로 중 하나를 사용 하 여 예외를 catch 하는 경우는 `CException` 개체 자동 삭제 직접 삭제 하지 않습니다.  사용 하 여 예외를 catch 하는 경우는  **catch** 키워드를 자동으로 삭제 됩니다.  참고  [예외 처리 \(MFC\)](../../mfc/exception-handling-in-mfc.md) exeption 개체를 삭제 하는 경우에 대 한 자세한 내용은.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CException`  
  
## 요구 사항  
 **헤더:**  afx.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [예외 처리](../../mfc/reference/exception-processing.md)   
 [어떻게 i: 만들지 나만의 사용자 지정 예외 클래스?](http://go.microsoft.com/fwlink/?LinkId=128045)