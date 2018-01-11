---
title: "예외: 데이터베이스 예외 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DAO [MFC], exceptions
- exceptions [MFC], database
- exception handling [MFC], databases
- ODBC exceptions [MFC]
- ODBC [MFC], exceptions
- database exceptions [MFC]
- databases [MFC], exception handling
- error codes [MFC], database exception handling
ms.assetid: 28daf260-f824-4be6-aecc-1f859e6dec26
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e853f2bd6f57c7ccc63e802f013661efb85d9796
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-database-exceptions"></a>예외: 데이터베이스 예외
이 문서에서는 데이터베이스 예외를 처리 하는 방법을 설명 합니다. 이 문서에서 대부분 사용 하는 mfc ODBC Open Database Connectivity () 또는 MFC 클래스에 대 한 데이터 액세스 개체 (DAO) 여부를 적용 합니다. 하나 또는 다른 모델에 특정 자료 명시적으로 표시 됩니다. 다음과 같은 내용을 다룹니다.  
  
-   [예외 처리 방법](#_core_approaches_to_exception_handling)  
  
-   [데이터베이스 예외 처리 예](#_core_a_database_exception.2d.handling_example)  
  
##  <a name="_core_approaches_to_exception_handling"></a>예외 처리 방법  
 DAO 나 ODBC를 사용 하 여 작업할 방법을 같습니다.  
  
 예외 조건을 처리 하는 예외 처리기를 항상 작성 해야 합니다.  
  
 데이터베이스 예외를 catch 하는 가장 실용적인 방법은 예외 시나리오와 응용 프로그램을 테스트 하는 것입니다. 예외를 발생 강제로 및 코드에서 작업에 대 한 발생할 수 있는 예외를 결정 합니다. 그런 다음 throw 된 예외를 확인 하려면 추적 출력을 검사 하거나 디버거의 반환 된 오류 정보를 검사 합니다. 이 코드를 사용 하는 예외 시나리오에 대 한 표시를 반환 하는 알 수 있습니다.  
  
### <a name="error-codes-used-for-odbc-exceptions"></a>ODBC 예외에 대 한 사용 되는 오류 코드  
 형식의 이름으로 충족 하는 프레임 워크에 의해 정의 된, 반환 코드 외에도 **AFX_SQL_ERROR_XXX**, 일부 [CDBExceptions](../mfc/reference/cdbexception-class.md) 기반으로 [ODBC](../data/odbc/odbc-basics.md) 코드를 반환 합니다. 이러한 예외에 대 한 반환 코드는 폼의 이름이 **SQL_ERROR_XXX**합니다.  
  
 반환 코드-프레임 워크 정의 하 고 ODBC 정의-데이터베이스 클래스는 반환할 수 있습니다는 [m_nRetCode](../mfc/reference/cdbexception-class.md#m_nretcode) 클래스의 데이터 멤버 `CDBException`합니다. ODBC에 정의 된 반환 코드에 대 한 추가 정보는 ODBC SDK에서 사용할 수 있는 *Programmer's Reference* MSDN 라이브러리에서.  
  
### <a name="error-codes-used-for-dao-exceptions"></a>DAO 예외에 대 한 사용 되는 오류 코드  
 DAO 예외에 대 한 자세한 정보를 일반적으로 사용할 수 있습니다. 검색 되었습니다의 세 가지 데이터 멤버를 통해 오류 정보에 액세스할 수 [CDaoException](../mfc/reference/cdaoexception-class.md) 개체:  
  
-   [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) 에 대 한 포인터를 포함 한 [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md) 데이터베이스에 연결 된 오류 개체의 DAO의 컬렉션에 오류 정보를 캡슐화 하는 개체입니다.  
  
-   [m_nAfxDaoError](../mfc/reference/cdaoexception-class.md#m_nafxdaoerror) MFC DAO 클래스에서 확장 된 오류 코드를 포함 합니다. 폼의 이름을 포함 하는 이러한 오류 코드 **AFX_DAO_ERROR_XXX**의 데이터 멤버 아래에서 설명 `CDaoException`합니다.  
  
-   [m_scode](../mfc/reference/cdaoexception-class.md#m_scode) OLE 포함 `SCODE` 에서 DAO, 해당 하는 경우. 그러나이 오류 코드로 작업 하려면 거의 해야 합니다. 일반적으로 자세한 정보는 다른 두 데이터 멤버에 있습니다. 자세한 내용은 데이터 멤버에 대 한 참조 `SCODE` 값입니다.  
  
 클래스에서 DAO 오류, DAO 오류 개체 유형 및 DAO Errors 컬렉션에 대 한 추가 정보는 [CDaoException](../mfc/reference/cdaoexception-class.md)합니다.  
  
##  <a name="_core_a_database_exception.2d.handling_example"></a>데이터베이스 예외 처리 예  
 다음 예제에서는 생성 하려고는 [CRecordset](../mfc/reference/crecordset-class.md)-파생 된 개체를 사용 하 여 힙에 **새** 연산자 및 다음의 레코드 집합 (ODBC 데이터 원본)를 엽니다. DAO 클래스에 대 한 유사한 예 "DAO 예외 아래 예제에서는"를 참조 합니다.  
  
### <a name="odbc-exception-example"></a>ODBC 예외 예제  
 [열려](../mfc/reference/crecordset-class.md#open) 멤버 함수는 예외를 throw 할 수 있습니다 (형식의 [잠금을](../mfc/reference/cdbexception-class.md) ODBC 클래스에 대 한), 되므로이 대괄호 코드는 **열려** 하 여 호출는 **시도**  블록입니다. 후속 **catch** 블록은 catch는 `CDBException`합니다. 예외 개체를 직접 호출을 검토할 수 있습니다 `e`,이 경우에 레코드 집합을 만들려는 시도가 실패 했음을 알고 충분 하지만 합니다. **catch** 블록 메시지 상자를 표시 하 고 레코드 집합 개체를 삭제 하 여 정리 합니다.  
  
 [!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/cpp/exceptions-database-exceptions_1.cpp)]  
  
### <a name="dao-exception-example"></a>DAO 예외 예제  
 DAO 예제는 odbc의 경우 예제와 유사 하지만 일반적으로 더 많은 종류의 정보를 검색할 수 있습니다. 다음 코드는 또한 레코드 집합을 열려고 시도 합니다. 예외가 throw 되 면 오류 정보에 대 한 예외 개체의 데이터 멤버를 검사할 수 있습니다. 와 마찬가지로 이전 ODBC 예제 아마도 충분히 레코드 집합을 만들려는 시도가 실패 했음을 알 수 있습니다.  
  
 [!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/cpp/exceptions-database-exceptions_2.cpp)]  
  
 이 코드는 오류 메시지 문자열에서 가져옵니다는 [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) 예외 개체의 멤버입니다. MFC 예외를 throw 하는 경우이 멤버를 채웁니다.  
  
 반환 된 오류 정보에 대 한 내용은 `CDaoException` 개체, 클래스 참조 [CDaoException](../mfc/reference/cdaoexception-class.md) 및 [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md)합니다.  
  
 작업할 때는 대부분의 경우에서 Microsoft Jet (.mdb) 데이터베이스와 ODBC를 사용 하는 경우, 오류 개체를 하나만 됩니다. 드물긴 하지만 ODBC 데이터 소스를 사용 하 고 오류가 여러 개 있는 경우 반복 하면 DAO의 Errors 컬렉션에서 반환 된 오류 수에 따라 [CDaoException::GetErrorCount](../mfc/reference/cdaoexception-class.md#geterrorcount)합니다. 루프를 순환할 때마다 호출 [CDaoException::GetErrorInfo](../mfc/reference/cdaoexception-class.md#geterrorinfo) 다시 채우는 데는 `m_pErrorInfo` 데이터 멤버입니다.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리](../mfc/exception-handling-in-mfc.md)

