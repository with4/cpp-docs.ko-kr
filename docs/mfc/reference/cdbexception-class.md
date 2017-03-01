---
title: "잠금을 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBException
dev_langs:
- C++
helpviewer_keywords:
- CDBException class
- exceptions [C++], database
- database exceptions [C++]
- ODBC classes [C++], exceptions
- errors [C++], database
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: fc3bf7be273bf509dd1ee79fb42e69050070e830
ms.lasthandoff: 02/24/2017

---
# <a name="cdbexception-class"></a>잠금을 클래스
데이터베이스 클래스에서 발생하는 예외 상태를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDBException : public CException  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDBException::m_nRetCode](#m_nretcode)|개방형 데이터베이스 연결 (ODBC) 반환 코드를 형식이 포함 **RETCODE**합니다.|  
|[CDBException::m_strError](#m_strerror)|영숫자 측면에서 오류를 설명 하는 문자열을 포함 합니다.|  
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|ODBC에서 반환 된 오류 코드를 기준으로 오류를 설명 하는 문자열을 포함 합니다.|  
  
## <a name="remarks"></a>주의  
 클래스는 예외를 설명 하는 텍스트 메시지를 표시 또는 예외의 원인을 확인 하기 위해 사용할 수 있습니다 하는 두 명의 공용 데이터 멤버를 포함 합니다. `CDBException`개체는 생성 및 데이터베이스 클래스의 멤버 함수에 의해 throw 됩니다.  
  
> [!NOTE]
>  이 클래스는 MFC의 ODBC Open Database Connectivity () 클래스 중 하나입니다. 대신 새로운 데이터 액세스 개체 (DAO) 클래스를 사용할 경우 사용 하 여 [CDaoException](../../mfc/reference/cdaoexception-class.md) 대신 합니다. DAO 클래스 이름의 접두사로 "CDao"가 있습니다. 자세한 내용은 문서를 참조 하십시오. [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)합니다.  
  
 예외는 데이터 소스와 같은 프로그램의 제어를 벗어날 조건 관련 된 비정상적인 실행의 경우 또는 네트워크 I/O 오류가 있습니다. 실행 중인 프로그램의 정상적인 과정에서 참조 되는 오류는 일반적으로 아닙니다 예외.  
  
 범위 내에서 이러한 개체를 액세스할 수는 **CATCH** 식입니다. Throw 할 수 있습니다 `CDBException` 사용 하 여 사용자 고유의 코드에서 개체는 `AfxThrowDBException` 전역 함수입니다.  
  
 일반 또는 정보에서 예외 처리에 대 한 자세한 내용은 `CDBException` 문서를 참조 하는 개체를 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md) 및 [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDBException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdb.h  
  
##  <a name="a-namemnretcodea--cdbexceptionmnretcode"></a><a name="m_nretcode"></a>CDBException::m_nRetCode  
 형식의 ODBC 오류 코드를 포함 **RETCODE** ODBC 응용 프로그래밍 인터페이스 (API) 함수에서 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 형식은 ODBC에 정의 된 SQL 맨 앞에 나오는 코드 및 데이터베이스 클래스에서 정의 하는 AFX_SQL 맨 앞에 나오는 코드를 포함 합니다. 에 대 한 한 `CDBException`,이 멤버는 다음 값 중 하나가 포함 됩니다.  
  
- **AFX_SQL_ERROR_API_CONFORMANCE** 에 대 한 드라이버는 `CDatabase::OpenEx` 또는 `CDatabase::Open` 호출 필요한 ODBC API 규칙 수준 1에 맞지 않습니다 ( **SQL_OAC_LEVEL1**).  
  
- **AFX_SQL_ERROR_CONNECT_FAIL** 데이터 원본에 연결 하지 못했습니다. 전달 하는 **NULL** `CDatabase` 레코드 집합 생성자 및 연결을 만드는 후속 시도에 대 한 포인터에 따라 `GetDefaultConnect` 실패 했습니다.  
  
- **AFX_SQL_ERROR_DATA_TRUNCATED** 에 대 한 저장소를 제공 하는 것 보다 더 많은 데이터를 요청 합니다. 제공 되는 데이터 저장소에 대 한 증가에 대 한 내용은 `CString` 또는 `CByteArray` 데이터 형식 참조는 `nMaxLength` 에 대 한 인수 [RFX_Text](http://msdn.microsoft.com/library/de3c7581-d26c-40cb-81f3-c492ef4809f6) 및 [RFX_Binary](http://msdn.microsoft.com/library/908ff945-3ad0-43a1-9932-cdcdc8b14915) "매크로 및 전역 변수입니다."  
  
- **AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED** 에 대 한 호출 `CRecordset::Open` 다이너셋은 요청 하지 못했습니다. 다이너셋은 드라이버에서 지원 되지 않습니다.  
  
- **AFX_SQL_ERROR_EMPTY_COLUMN_LIST** 테이블을 열려고 했습니다 (또는 지정한 사용자를 식별할 수 없는 프로시저 호출으로 또는 **선택** 문)의 레코드 필드 교환 (RFX) 함수 호출에서 식별 된 열이 없는 하지만 프로그램 `DoFieldExchange` 재정의 합니다.  
  
- **AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH** 의 RFX 함수 유형 프로그램 `DoFieldExchange` 재정의 레코드 집합의 열 데이터 형식과 호환 되지 않습니다.  
  
- **AFX_SQL_ERROR_ILLEGAL_MODE** 호출 하 여 `CRecordset::Update` 이전에 호출 하지 않고 `CRecordset::AddNew` 또는 `CRecordset::Edit`합니다.  
  
- **AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED** ODBC 드라이버는 잠금을 지원 하지 않으므로 업데이트에 대 한 레코드 잠금에 대 한 요청을 수행할 수 없습니다.  
  
- **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED** 호출 하 여 `CRecordset::Update` 또는 **삭제** 없는 고유 키가 있는 테이블에 대 한 여러 레코드를 변경 합니다.  
  
- **AFX_SQL_ERROR_NO_CURRENT_RECORD** 편집 하거나 이전에 삭제 된 레코드를 삭제 했습니다. 삭제 한 후에 새로운 현재 레코드로으로 스크롤해야 합니다.  
  
- **AFX_SQL_ERROR_NO_POSITIONED_UPDATES** 요청 다이너셋은 ODBC 드라이버가 지원 하지 않기 때문에 수행할 수 없습니다에 대 한 위치 지정 업데이트 합니다.  
  
- **AFX_SQL_ERROR_NO_ROWS_AFFECTED** 호출 하 여 `CRecordset::Update` 또는 **삭제**, 하지만 작업을 시작 하기 전에 레코드가 더 이상 찾을 수 없습니다.  
  
- **AFX_SQL_ERROR_ODBC_LOAD_FAILED** ODBC를 로드 하려고 합니다. DLL에 실패 했습니다. Windows를 찾을 수 없거나이 DLL을 로드할 수 없습니다. 이 오류는 치명적입니다.  
  
- **AFX_SQL_ERROR_ODBC_V2_REQUIRED** 레벨 2 호환 ODBC 드라이버가 필요 하기 때문에 다이너셋에 대 한 요청을 수행할 수 없습니다.  
  
- **AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY** 데이터 소스에서 뒤로 스크롤을 지원 하지 않으므로 스크롤해야 시도가 실패 했습니다.  
  
- **AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED** 에 대 한 호출 `CRecordset::Open` 스냅숏 요청 하지 못했습니다. 스냅숏은은 드라이버에서 지원 되지 않습니다. (만 발생 해야 때 ODBC 커서 라이브러리 â €"ODBCCURS 합니다. DLL â €"존재 하지 않습니다.)  
  
- **AFX_SQL_ERROR_SQL_CONFORMANCE** 에 대 한 드라이버는 `CDatabase::OpenEx` 또는 `CDatabase::Open` 호출 "최소" 필요한 ODBC SQL 규칙 수준에 맞지 않습니다 ( **SQL_OSC_MINIMUM**).  
  
- **AFX_SQL_ERROR_SQL_NO_TOTAL** 는 ODBC 드라이버의 총 크기를 지정 하지 못했습니다.는 `CLongBinary` 데이터 값입니다. 전역 메모리 블록 미리 할당 하지 못했습니다 아마도 작업이 실패 합니다.  
  
- **AFX_SQL_ERROR_RECORDSET_READONLY** 데이터 소스는 읽기 전용 또는 읽기 전용 레코드 집합을 업데이트 하려고 했습니다. 레코드 집합으로 없습니다 업데이트 작업을 수행할 수 또는 `CDatabase` 와 연결 된 개체입니다.  
  
- **SQL_ERROR** 함수가 실패 했습니다. ODBC 함수에서 반환 된 오류 메시지 **SQLError** 에 저장 되는 **m_strError** 데이터 멤버입니다.  
  
- **SQL_INVALID_HANDLE** 는 잘못 된 환경 핸들, 연결 핸들 또는 문 핸들 인해 함수가 실패 했습니다. 이 프로그래밍 오류를 나타냅니다. 추가 정보 없이 ODBC 함수에서 사용할 수 있는 **SQLError**합니다.  
  
 SQL 맨 앞에 나오는 코드는 ODBC에서 정의 됩니다. AFX 맨 앞에 나오는 코드는 AFXDB에서 정의 됩니다. H, MFC\INCLUDE에서 찾을 수 있습니다.  
  
##  <a name="a-namemstrerrora--cdbexceptionmstrerror"></a><a name="m_strerror"></a>CDBException::m_strError  
 예외를 발생 시킨 오류를 설명 하는 문자열을 포함 합니다.  
  
### <a name="remarks"></a>주의  
 영숫자 측면에서 오류를 설명 하는 문자열입니다. 에 대 한 자세한 내용 및 예제 참조 **m_strStateNativeOrigin**합니다.  
  
##  <a name="a-namemstrstatenativeorigina--cdbexceptionmstrstatenativeorigin"></a><a name="m_strstatenativeorigin"></a>CDBException::m_strStateNativeOrigin  
 예외를 발생 시킨 오류를 설명 하는 문자열을 포함 합니다.  
  
### <a name="remarks"></a>주의  
 문자열 서식 코드를에서 설명 하는 값으로 바뀌는 양식 "상태 %s, 네이티브 %ld, 원본 %s"의 같습니다.:::  
  
-   **SQLSTATE**에 반환 된&5; 자의 오류 코드를 포함 하는 null로 끝나는 문자열의 *szSqlState* ODBC 함수의 매개 변수가 **SQLError**합니다. **SQLSTATE** 값 부록 A에에서 나열 된 [ODBC 오류 코드](https://msdn.microsoft.com/library/ms714687.aspx)에 *ODBC 프로그래머 참조*합니다. 예: "S0022"입니다.  
  
-   반환 하는 데이터 소스에만 적용 되는 원시 오류 코드는 *pfNativeError* 의 매개 변수는 **SQLError** 함수입니다. 예: 207 합니다.  
  
-   반환 된 오류 메시지 텍스트는 *szErrorMsg* 의 매개 변수는 **SQLError** 함수입니다. 이 메시지는 여러 개의 대괄호로 묶인된 이름을 이루어져 있습니다. 오류가 사용자에 게 해당 소스에서 전달 되는 고유 이름을 각 ODBC 구성 요소 (데이터 원본, 드라이버를 드라이버 관리자)에 추가 합니다. 이 정보는 오류의 출처를 정확 하 게 찾을 수 있습니다. 예: [Microsoft] [ODBC SQL Server Driver] [SQL Server]  
  
 프레임 워크를 오류 문자열을 해석 하 고 해당 구성 요소에 배치 **m_strStateNativeOrigin**경우 **m_strStateNativeOrigin** 정보가 포함 되어 둘 이상의 오류에 대 한 오류 바꿈으로 구분 됩니다. 프레임 워크에서 영숫자 오류 텍스트를 배치 **m_strError**합니다.  
  
 이 문자열을 구성 하는 데 사용 되는 코드에 대 한 자세한 내용은 참조는 [SQLError](https://msdn.microsoft.com/library/ms716312.aspx) 함수는 *ODBC 프로그래머 참조*합니다.  
  
### <a name="example"></a>예제  
  ODBC:에서 "상태: S0022, 네이티브:&207;, 원본: [Microsoft] [ODBC SQL Server Driver] [SQL Server] 잘못 된 열 이름 'ColName'"  
  
 **m_strStateNativeOrigin**: "상태: S0022, 네이티브:&207;, 원본: [Microsoft] [ODBC SQL Server Driver] [SQL Server]"  
  
 **m_strError**: "잘못 된 열 이름 'ColName'"  
  
## <a name="see-also"></a>참고 항목  
 [CException 클래스](../../mfc/reference/cexception-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDatabase 클래스](../../mfc/reference/cdatabase-class.md)   
 [CRecordset 클래스](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange 클래스](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset::Update](../../mfc/reference/crecordset-class.md#update)   
 [CRecordset::Delete](../../mfc/reference/crecordset-class.md#delete)   
 [CException 클래스](../../mfc/reference/cexception-class.md)

