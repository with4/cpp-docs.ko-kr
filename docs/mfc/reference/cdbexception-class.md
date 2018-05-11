---
title: 잠금을 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDBException
- AFXDB/CDBException
- AFXDB/CDBException::m_nRetCode
- AFXDB/CDBException::m_strError
- AFXDB/CDBException::m_strStateNativeOrigin
dev_langs:
- C++
helpviewer_keywords:
- CDBException [MFC], m_nRetCode
- CDBException [MFC], m_strError
- CDBException [MFC], m_strStateNativeOrigin
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 824ac88326042eb55ecb9667c39331d1ab5464e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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
|[CDBException::m_nRetCode](#m_nretcode)|ODBC Open Database Connectivity () 반환 코드를 형식의 포함 **RETCODE**합니다.|  
|[CDBException::m_strError](#m_strerror)|영숫자 측면에서 오류를 설명 하는 문자열을 포함 합니다.|  
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|ODBC에서 반환 된 오류 코드를 기준으로 오류를 설명 하는 문자열을 포함 합니다.|  
  
## <a name="remarks"></a>설명  
 클래스는 예외를 설명 하는 텍스트 메시지를 표시 하려면 또는 예외의 원인을 확인 하기 위해 사용할 수 있습니다 하는 두 명의 공용 데이터 멤버를 포함 합니다. `CDBException` 개체 생성 되며 데이터베이스 클래스의 멤버 함수에 의해 throw 됩니다.  
  
> [!NOTE]
>  이 클래스는 MFC의 ODBC Open Database Connectivity () 클래스 중 하나입니다. 대신 신규 개체 DAO (Data Access) 클래스를 사용할 경우 사용 하 여 [CDaoException](../../mfc/reference/cdaoexception-class.md) 대신 합니다. 모든 DAO 클래스 이름에는 접두사로 "CDao"는 합니다. 자세한 내용은 문서 참조 [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)합니다.  
  
 예외는 데이터 소스와 같은 프로그램의 제어를 벗어나는 조건 관련 된 비정상적인 실행의 경우 또는 네트워크 I/O 오류입니다. 실행 중인 프로그램의 정상적으로 표시 될 수 있습니다 하는 오류는 일반적으로 아닙니다 예외.  
  
 범위 내에서 이러한 개체에 액세스할 수 있습니다는 **CATCH** 식입니다. Throw 할 수 있습니다 `CDBException` 사용 하 여 사용자 고유의 코드에서 개체는 `AfxThrowDBException` 전역 함수입니다.  
  
 일반적으로 또는 곧에서 예외 처리에 대 한 자세한 내용은 `CDBException` 문서를 참조 하는 개체를 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md) 및 [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDBException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdb.h  
  
##  <a name="m_nretcode"></a>  CDBException::m_nRetCode  
 형식의 ODBC 오류 코드를 포함 **RETCODE** API (인터페이스) 함수를 프로그래밍 하는 ODBC 응용 프로그램에서 반환 합니다.  
  
### <a name="remarks"></a>설명  
 이 형식은 ODBC에 정의 된 SQL 맨 앞에 나오는 코드 및 데이터베이스 클래스에서 정의 된 AFX_SQL 맨 앞에 나오는 코드를 포함 합니다. 에 대 한 한 `CDBException`를이 멤버는 다음 값 중 하나가 포함 됩니다.  
  
- **AFX_SQL_ERROR_API_CONFORMANCE** 에 대 한 드라이버는 `CDatabase::OpenEx` 또는 `CDatabase::Open` 호출 필수 ODBC API 규칙 수준 1에 맞지 않습니다 ( **SQL_OAC_LEVEL1**).  
  
- **AFX_SQL_ERROR_CONNECT_FAIL** 데이터 원본에 연결 하지 못했습니다. 전달 하는 **NULL** `CDatabase` 레코드 집합 생성자 및 연결을 만드는 후속 시도에 대 한 포인터에 따라 `GetDefaultConnect` 실패 했습니다.  
  
- **AFX_SQL_ERROR_DATA_TRUNCATED** 에 대 한 저장소를 제공 하는 것 보다 더 많은 데이터를 요청 합니다. 에 대 한 제공 된 데이터 저장소 증가에 대 한 내용은 `CString` 또는 `CByteArray` 데이터 형식을 참조는 `nMaxLength` 에 대 한 인수 [RFX_Text](record-field-exchange-functions.md#rfx_text) 및 [RFX_Binary](record-field-exchange-functions.md#rfx_binary) 아래에서 "매크로 및 전역입니다. "  
  
- **AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED** 에 대 한 호출 `CRecordset::Open` 다이너셋 요청 하지 못했습니다. 다이너셋은 드라이버에서 지원 되지 않습니다.  
  
- **AFX_SQL_ERROR_EMPTY_COLUMN_LIST** 를 테이블 열 (또는 지정한 사용자를 식별할 수 없으며 프로시저 호출으로 또는 **선택** 문) (RFX) 레코드 필드 교환에서 식별 된 열이 없는 하지만 함수에서 호출 프로그램 `DoFieldExchange` 재정의 합니다.  
  
- **AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH** 에 RFX 함수의 유형을 프로그램 `DoFieldExchange` 재정의 레코드 집합의 열 데이터 형식과 호환 되지 않습니다.  
  
- **AFX_SQL_ERROR_ILLEGAL_MODE** 호출한 경우 `CRecordset::Update` 이전에 호출 하지 않고 `CRecordset::AddNew` 또는 `CRecordset::Edit`합니다.  
  
- **AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED** 잠금 ODBC 드라이버에서 지원 하지 않으므로 잠금 레코드 업데이트에 대 한 요청을 수행할 수 없습니다.  
  
- **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED** 호출한 경우 `CRecordset::Update` 또는 **삭제** 없는 고유 키가 있는 테이블에 대 한 여러 레코드를 변경 합니다.  
  
- **AFX_SQL_ERROR_NO_CURRENT_RECORD** 편집 하거나 이전에 삭제 된 레코드를 삭제 했습니다. 삭제 후에 새로운 현재 레코드로으로 스크롤해야 합니다.  
  
- **AFX_SQL_ERROR_NO_POSITIONED_UPDATES** 요청 다이너셋은 ODBC 드라이버가 지원 하지 않으므로 수행할 수 없습니다에 대 한 위치 지정 업데이트 합니다.  
  
- **AFX_SQL_ERROR_NO_ROWS_AFFECTED** 호출한 경우 `CRecordset::Update` 또는 **삭제**, 하지만 작업을 시작 하는 경우 레코드 더 이상 찾을 수 없습니다.  
  
- **AFX_SQL_ERROR_ODBC_LOAD_FAILED** ODBC를 로드 하려고 합니다. DLL에 실패 했습니다. Windows를 찾을 수 없거나이 DLL을 로드할 수 없습니다. 이 오류는 치명적입니다.  
  
- **AFX_SQL_ERROR_ODBC_V2_REQUIRED** 레벨 2 호환 ODBC 드라이버가 필요 하기 때문에 다이너셋에 대 한 요청을 수행할 수 없습니다.  
  
- **AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY** 데이터 소스는 뒤로 스크롤할를 지원 하지 않으므로 스크롤해야 시도가 실패 했습니다.  
  
- **AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED** 에 대 한 호출 `CRecordset::Open` 스냅숏 요청 하지 못했습니다. 스냅숏은은 드라이버에서 지원 되지 않습니다. (이만 발생 때 ODBC 커서 라이브러리 ODBCCURS 합니다. DLL 존재 하지 않습니다.)  
  
- **AFX_SQL_ERROR_SQL_CONFORMANCE** 에 대 한 드라이버는 `CDatabase::OpenEx` 또는 `CDatabase::Open` 호출 "최소"의 필수 ODBC SQL 규칙 수준과 일치 하지 않습니다 ( **sql_osc_minimum이 합니다**).  
  
- **AFX_SQL_ERROR_SQL_NO_TOTAL** The ODBC 드라이버의 전체 크기를 지정할 수 없습니다. 한 `CLongBinary` 데이터 값입니다. 전역 메모리 블록에 없습니다 미리 할당 된 하지 아마도 작업이 실패 합니다.  
  
- **AFX_SQL_ERROR_RECORDSET_READONLY** 데이터 소스는 읽기 전용 또는 읽기 전용 레코드 집합을 업데이트 하려고 했습니다. Update 작업이 이루어지지 레코드 집합을 수행할 수 있습니다 또는 `CDatabase` 연결 된 개체입니다.  
  
- **SQL_ERROR** 함수가 실패 했습니다. ODBC 함수에서 반환 된 오류 메시지 **SQLError** 에 저장 되는 **m_strError** 데이터 멤버입니다.  
  
- **SQL_INVALID_HANDLE** 는 잘못 된 환경 핸들, 연결 핸들 또는 문 핸들 인해 함수가 실패 했습니다. 프로그래밍 오류를 나타냅니다. ODBC 함수는 추가 정보가 **SQLError**합니다.  
  
 SQL 맨 앞에 나오는 코드는 ODBC에서 정의 됩니다. AFX 맨 앞에 나오는 코드 AFXDB에서 정의 됩니다. H, MFC\INCLUDE에서 찾을 수 있습니다.  
  
##  <a name="m_strerror"></a>  CDBException::m_strError  
 예외를 발생 시킨 오류를 설명 하는 문자열을 포함 합니다.  
  
### <a name="remarks"></a>설명  
 영숫자 측면에서 오류를 설명 하는 문자열입니다. 자세한 내용 및 예제를 참조 하세요. **m_strStateNativeOrigin**합니다.  
  
##  <a name="m_strstatenativeorigin"></a>  CDBException::m_strStateNativeOrigin  
 예외를 발생 시킨 오류를 설명 하는 문자열을 포함 합니다.  
  
### <a name="remarks"></a>설명  
 문자열은 서식 코드를에서 설명 하는 값으로 바뀌는 양식 "상태 %s, 네이티브 %ld, 원본 %s"입니다.:::  
  
-   **SQLSTATE**에 반환 된 5 자의 오류 코드를 포함 하는 null로 끝나는 문자열의 *szSqlState* 매개 변수는 ODBC 함수의 **SQLError**합니다. **SQLSTATE** 값 부록 A에에서 나열 됩니다 [ODBC 오류 코드](https://msdn.microsoft.com/library/ms714687.aspx)에 *ODBC Programmer's Reference*합니다. 예: "S0022"입니다.  
  
-   반환 하는 특정 데이터 원본에는 원시 오류 코드는 *pfNativeError* 의 매개 변수는 **SQLError** 함수입니다. 예: 207 합니다.  
  
-   반환 된 오류 메시지 텍스트는 *szErrorMsg* 의 매개 변수는 **SQLError** 함수입니다. 이 메시지는 여러 개의 대괄호로 묶인된 이름을 이루어져 있습니다. 오류가 사용자에 게 해당 원본에서 전달 때 각 ODBC 구성 요소 (데이터 원본, 드라이버, 드라이버 관리자)는 고유 이름을 추가 합니다. 이 정보는 오류의 출처를 정확 하 게 찾을 수 있습니다. 예: [Microsoft] [ODBC SQL Server Driver] [SQL Server]  
  
 프레임 워크를 오류 문자열을 해석 하 고 해당 구성 요소에 배치 **m_strStateNativeOrigin**경우 **m_strStateNativeOrigin** 정보가 둘 이상의 오류에 대 한 오류 정보에서 서로 다른 줄 바꿈 합니다. 프레임 워크에서 영숫자 오류 텍스트를 배치 **m_strError**합니다.  
  
 이 문자열을 확인 하는 데 사용 하는 코드에 대 한 자세한 내용은 참조는 [SQLError](https://msdn.microsoft.com/library/ms716312.aspx) 함수는 *ODBC Programmer's Reference*합니다.  
  
### <a name="example"></a>예제  
  ODBC:에서 "상태: S0022, 네이티브: 207, 원본: [Microsoft] [ODBC SQL Server Driver] [SQL Server] 잘못 된 열 이름 'ColName'"  
  
 **m_strStateNativeOrigin**: "상태: S0022, 네이티브: 207, 원본: [Microsoft] [ODBC SQL Server Driver] [SQL Server]"  
  
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
