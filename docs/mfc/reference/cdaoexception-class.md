---
title: "CDaoException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoException class"
  - "컬렉션, DAO 오류"
  - "DAO(Data Access Objects), 예외"
  - "오류[C++], DAO"
  - "Errors collection, DAO"
  - "예외, in MFC DAO classes"
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDaoException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터 액세스 개체 \(DAO\)를 기반으로 MFC 데이터베이스 클래스에서 발생 하는 예외 조건을 나타냅니다.  
  
## 구문  
  
```  
class CDaoException : public CException  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDaoException::CDaoException](../Topic/CDaoException::CDaoException.md)|`CDaoException` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDaoException::GetErrorCount](../Topic/CDaoException::GetErrorCount.md)|데이터베이스 엔진의 오류 컬렉션에서 오류를 반환합니다.|  
|[CDaoException::GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md)|Errors 컬렉션에서 특정 오류 개체에 대 한 오류 정보를 반환합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDaoException::m\_nAfxDaoError](../Topic/CDaoException::m_nAfxDaoError.md)|MFC DAO 클래스에는 오류에 대 한 확장된 오류 코드를 포함 합니다.|  
|[CDaoException::m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md)|에 대 한 포인터는  [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) DAO 오류 개체에 대 한 정보를 포함 하는 개체입니다.|  
|[CDaoException::m\_scode](../Topic/CDaoException::m_scode.md)|[하지](../Topic/CDaoException::m_scode.md) 오류와 관련 된 값입니다.|  
  
## 설명  
 예외의 원인을 확인할 수 있는 공용 데이터 멤버는 클래스를 포함 합니다.  `CDaoException`개체를 생성 하 여 DAO 데이터베이스 클래스의 멤버 함수에 의해 발생 합니다.  
  
> [!NOTE]
>  DAO 데이터베이스 클래스는 개방형 데이터베이스 연결 \(ODBC\)에 따라 MFC 데이터베이스 클래스와는 별개입니다.  모든 DAO 데이터베이스 클래스 이름을 "CDao" 접두사가 있습니다.  여전히 DAO 클래스가 ODBC 데이터 소스를 액세스 할 수 있습니다.  일반적으로 mfc에서 DAO 기반 ODBC 기반 mfc 보다 더. DAO 기반 클래스를 통해 자신의 데이터베이스 엔진을 통해 ODBC 드라이버를 포함 하 여 데이터를 액세스할 수 있습니다.  DAO 기반 클래스에도 테이블은 클래스를 통해 DAO를 직접 호출 하지 않고도 추가 데이터 정의 언어 \(DDL\) 작업을 지원 합니다.  ODBC 클래스에서 throw 된 예외에 대 한 자세한 내용은  [CDBException](../../mfc/reference/cdbexception-class.md).  
  
 예외 개체의 범위 내에서 액세스할 수 있는  [CATCH](../Topic/CATCH.md) 식입니다.  Throw 할 수 있습니다 `CDaoException` 으로 코드에서 개체의  [AfxThrowDaoException](../Topic/AfxThrowDaoException.md) 전역 함수입니다.  
  
 MFC에서 DAO 오류 모든 형식의 예외로 표현 됩니다 `CDaoException`.  이 형식의 예외를 catch 하는 경우 사용할 수 있습니다 `CDaoException` 멤버 함수에서 데이터베이스 엔진의 오류 컬렉션에 저장 된 DAO error 개체 정보를 검색 합니다.  오류가 발생할 때마다 하나 이상의 오류 개체가 Errors 컬렉션에 배치 됩니다.  \(일반적으로 컬렉션의 error 개체를 하나만 포함 됩니다. ODBC 데이터 소스를 사용 하는 경우에 여러 오류 개체를 얻을 수 있습니다.\) 다른 DAO 작업에서 오류가 발생 하면 Errors 컬렉션 지워지고 새 오류 개체가 Errors 컬렉션에 배치 됩니다.  오류가 발생 하지 않는 DAO 작업은 Errors 컬렉션에 영향을 주지 않습니다.  
  
 DAO 오류 코드에 대 한 DAOERR 파일을 참조 하십시오.H.  관련된 내용은 "트래핑 가능한 데이터 액세스 오류" DAO 도움말 항목을 참조 하십시오.  
  
 예외 처리 일반, 또는 정보에 대 한 자세한 내용은 `CDaoException` 개체의 문서를 참조 하십시오  [예외 처리 \(MFC\)](../../mfc/exception-handling-in-mfc.md) 및  [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md).  두 번째 문서에서는 dao에서 예외 처리를 보여 줍니다. 예제 코드를 포함 합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [넓습니다](../../mfc/reference/cexception-class.md)  
  
 `CDaoException`  
  
## 요구 사항  
 **헤더:**  afxdao.h  
  
## 참고 항목  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)