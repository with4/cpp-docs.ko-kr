---
title: "CDBException Class | Microsoft Docs"
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
  - "CDBException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBException class"
  - "database exceptions [C++]"
  - "오류[C++], 데이터베이스"
  - "exceptions [C++], 데이터베이스"
  - "ODBC 클래스[C++], 예외"
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
caps.latest.revision: 23
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터베이스 클래스에서 발생 하는 예외 조건을 나타냅니다.  
  
## 구문  
  
```  
  
class CDBException : public CException  
  
```  
  
## Members  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDBException::m\_nRetCode](../Topic/CDBException::m_nRetCode.md)|개방형 데이터베이스 연결 \(ODBC\) 반환 코드를 형식에 포함 된  **RETCODE**.|  
|[CDBException::m\_strError](../Topic/CDBException::m_strError.md)|영숫자 용어로 오류를 설명 하는 문자열을 포함 합니다.|  
|[CDBException::m\_strStateNativeOrigin](../Topic/CDBException::m_strStateNativeOrigin.md)|ODBC에서 반환 된 오류 코드에서 오류를 설명 하는 문자열을 포함 합니다.|  
  
## 설명  
 예외의 원인을 파악 하거나 예외를 설명 하는 텍스트 메시지를 표시할 수 있습니다 두 명의 공용 데이터 멤버는 클래스를 포함 합니다.  `CDBException`개체는 생성, 데이터베이스 클래스의 멤버 함수에 의해 발생 합니다.  
  
> [!NOTE]
>  이 클래스는 MFC의 개방형 데이터베이스 연결 \(ODBC\) 클래스 중 하나입니다.  사용 하는 대신 새 데이터 액세스 개체 \(DAO\) 클래스를 사용 하는 경우  [CDaoException](../../mfc/reference/cdaoexception-class.md) 대신 합니다.  모든 DAO 클래스 이름을 "CDao" 접두사로 있습니다.  자세한 내용은  [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md).  
  
 비정상 실행 프로그램의 컨트롤을 데이터 소스와 같은 외부 조건에 관련 된 경우 또는 네트워크 I\/O 오류가 예외.  확인 프로그램 실행 과정에서 예상 되는 오류 예외 일반적으로 간주 되지 않습니다.  
  
 이러한 개체의 범위 내에서 액세스할 수 있는  **CATCH** 식.  Throw 할 수 있습니다 `CDBException` 으로 코드에서 개체의 `AfxThrowDBException` 전역 함수입니다.  
  
 예외 처리 일반, 또는 정보에 대 한 자세한 내용은 `CDBException` 개체의 문서를 참조 하십시오  [예외 처리 \(MFC\)](../../mfc/exception-handling-in-mfc.md) 및  [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [넓습니다](../../mfc/reference/cexception-class.md)  
  
 `CDBException`  
  
## 요구 사항  
 **헤더:**  afxdb.h  
  
## 참고 항목  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange Class](../../mfc/reference/cfieldexchange-class.md)   
 [AfxThrowDBException](../Topic/AfxThrowDBException.md)   
 [CRecordset::Update](../Topic/CRecordset::Update.md)   
 [CRecordset::Delete](../Topic/CRecordset::Delete.md)   
 [CException Class](../../mfc/reference/cexception-class.md)