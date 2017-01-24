---
title: "예외: 데이터베이스 예외 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO[C++], 예외"
  - "데이터베이스 예외[C++]"
  - "데이터베이스[C++], 예외 처리"
  - "오류 코드[C++], 데이터베이스 예외 처리"
  - "예외 처리[C++], 데이터베이스"
  - "예외[C++], 데이터베이스"
  - "ODBC[C++], 예외"
  - "ODBC 예외[C++]"
ms.assetid: 28daf260-f824-4be6-aecc-1f859e6dec26
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 예외: 데이터베이스 예외
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 데이터베이스 예외를 처리하는 방법을 설명합니다.  이 문서에 나와있는 자료의 대부분은 개방형 데이터베이스 연결 \(ODBC\) 또는 데이터 액세스 개체 \(DAO\)에 대한 MFC 클래스의 MFC 클래스를 사용한 작업 여부를 적용합니다.  재료 하나 또는 다른 모델에 명시적으로 표시되어 있습니다.  다음 내용을 다룹니다.  
  
-   [예외 처리 방법](#_core_approaches_to_exception_handling)  
  
-   [데이터베이스 예외 처리 예제](#_core_a_database_exception.2d.handling_example)  
  
##  <a name="_core_approaches_to_exception_handling"></a> 예외 처리 방법  
 DAO 나 ODBC를 사용하여 작업하는 방법은 같습니다.  
  
 항상 예외 조건을 처리하는 예외 처리기를 작성해야 합니다.  
  
 데이터베이스 예외를 catch 하는데 가장 현실적인 방법은 시나리오를 사용하여 응용 프로그램을 테스트 하는 것입니다.  코드에서 작업에 대한 발생을 일으키고 강제로 예외를 발생하는 예외를 확인합니다.  Throw 된 예외를 추적 출력을 검사하거나 디버거에서 반환된 오류 정보를 검사합니다.  이것은 사용하는 예외 시나리오에 볼 수있는 리턴 코드를 알 수 있습니다.  
  
### ODBC 예외에 사용된 오류 코드  
 프레임 워크에 의해 정의된 **AFX\_SQL\_ERROR\_XXX**이라는 이름의 반환 코드 뿐만 아니라, 일부 [CDBExceptions](../mfc/reference/cdbexception-class.md)는  [ODBC](../data/odbc/odbc-basics.md) 반환 코드의 기반입니다.  이러한 예외에 대한 반환 코드는  **SQL\_ERROR\_XXX** 폼이라는 이름을 가집니다.  
  
 정의 프레임 워크와 ODBC 정의된 반환 코드\-\-\- 데이터베이스 클래스는  `CDBException`  클래스의 [m\_nRetCode](../Topic/CDBException::m_nRetCode.md)데이터 멤버 아래에서 설명되어 반환할 수 있습니다.  ODBC에서 정의된 반환 코드에 대한 자세한 내용은  MSDN Library의 ODBC SDK의 *프로그래머 참조*에서 사용가능합니다.  
  
### DAO 예외에 사용된 오류 코드  
 DAO 예외에 대한 자세한 내용은 일반적으로 사용할 수 있습니다.  캐치된 [CDaoException](../mfc/reference/cdaoexception-class.md) 개체의 세 가지 데이터 멤버를 통해 오류 정보를 액세스할 수 있습니다 :  
  
-   [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md)은  [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md) 개체에 대한 포인터를 포함합니다. 이 개체는 DAO의 컬렉션 데이터베이스에 연결된 error 개체에서 오류 정보를 캡슐화하는 개체입니다.  
  
-   [m\_nAfxDaoError](../Topic/CDaoException::m_nAfxDaoError.md) 는 MFC DAO 클래스에서 확장된 오류 코드를 포함합니다.  **AFX\_DAO\_ERROR\_XXX** 폼이라는 이름을 가진 오류 코드는  `CDaoException` 의 데이터 멤버에서 설명됩니다.  
  
-   [m\_scode](../Topic/CDaoException::m_scode.md)는 해당 하는 경우 DAO에서 OLE `SCODE`  를 포함합니다.  그러나, 거의 이 오류 코드로 작업 할 필요가 없을 것입니다.  보통 자세한 내용은 다른 두 개의 데이터 멤버에서 사용할 수 있습니다.   `SCODE`  값에 대한 더 자세한 데이터 멤버를 확인하십시오.  
  
 DAO 오류, DAO 오류 개체 유형 및 DAO Errors 컬렉션에 대한 추가 정보는  [CDaoException](../mfc/reference/cdaoexception-class.md) 클래스 아래에서 사용가능합니다.  
  
##  <a name="_core_a_database_exception.2d.handling_example"></a> 데이터베이스 예외 처리 예제  
 다음 예제에서는 [CRecordset](../mfc/reference/crecordset-class.md)를 구성합니다\-  **새** 연산자 와 힙에 파생 개체를 사용합니다 그리고 레코드 집합 \(ODBC 데이터 원본\)을 여십시오.  DAO 클래스에 대한 유사한 예제 "DAO 예외 예제" 아래를 참조하십시오.  
  
### ODBC 예외 예제  
 [열기](../Topic/CRecordset::Open.md) 멤버 함수는 예외\( ODBC 클래스에 대한 [잠금](../mfc/reference/cdbexception-class.md) 형식 \)를 throw 할 수 있습니다. 따라서 이 대괄호 코드 **열기**는 **시도** 블록을 호출합니다.  다음 **catch** 블록은  `CDBException` 을 catch 할 것입니다.   `e` 을 호출하는 예외 개체를 자체적으로 검사할 수 있습니다, 하지만이 경우에는 레코드를 만들 수있는 시도가 실패했음을 알고 충분합니다.   **catch** 블록은 메시지 상자를 표시하고 레코드 집합 개체를 삭제하여 정리합니다.  
  
 [!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/CPP/exceptions-database-exceptions_1.cpp)]  
  
### DAO 예외 예제  
 DAO 예제는 odbc 예제와 유사 하지만 일반적으로 더 많은 종류의 정보를 검색할 수 있습니다.  다음 코드는 또한 레코드 집합을 열려고 시도합니다.  예외가 throw 되면 예외 오류 정보 개체의 데이터 멤버를 검사할 수 있습니다.  앞의 ODBC 예제에서 충분히 레코드 집합을 만드는 시도가 아마도 실패 했음을 알 수 있습니다.  
  
 [!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/CPP/exceptions-database-exceptions_2.cpp)]  
  
 이 코드는 예외 개체의 [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md) 멤버로부터 오류 메시지 문자열을 가져옵니다.  MFC는 예외를 throw 하는 경우 이 멤버를 채웁니다.  
  
 `CDaoException`  개체에서 반환된 오류 정보에 대해서는  [CDaoException](../mfc/reference/cdaoexception-class.md) 및  [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md) 클래스를 참조하십시오.  
  
 당신은 Microsoft Jet의 \(. MDB\)에서 작업 할 때 ODBC를 사용하는 경우, 데이터베이스 및 대부분의 경우는 하나의 오류 개체가 존재합니다.  드물긴 하지만 ODBC 데이터 소스를 사용하고 여러 오류가 발생하는 경우 DAO의 Errors 컬렉션에서 [CDaoException::GetErrorCount](../Topic/CDaoException::GetErrorCount.md) 반환된 오류 번호에 따라 반복할 수 있습니다.  루프를 실행할 때마다  [CDaoException::GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md)를 호출하여  `m_pErrorInfo`  데이터 멤버를 리필합니다.  
  
## 참고 항목  
 [예외 처리](../mfc/exception-handling-in-mfc.md)