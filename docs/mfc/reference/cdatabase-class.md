---
title: "CDatabase 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDatabase
- AFXDB/CDatabase
- AFXDB/CDatabase::CDatabase
- AFXDB/CDatabase::BeginTrans
- AFXDB/CDatabase::BindParameters
- AFXDB/CDatabase::Cancel
- AFXDB/CDatabase::CanTransact
- AFXDB/CDatabase::CanUpdate
- AFXDB/CDatabase::Close
- AFXDB/CDatabase::CommitTrans
- AFXDB/CDatabase::ExecuteSQL
- AFXDB/CDatabase::GetBookmarkPersistence
- AFXDB/CDatabase::GetConnect
- AFXDB/CDatabase::GetCursorCommitBehavior
- AFXDB/CDatabase::GetCursorRollbackBehavior
- AFXDB/CDatabase::GetDatabaseName
- AFXDB/CDatabase::IsOpen
- AFXDB/CDatabase::OnSetOptions
- AFXDB/CDatabase::Open
- AFXDB/CDatabase::OpenEx
- AFXDB/CDatabase::Rollback
- AFXDB/CDatabase::SetLoginTimeout
- AFXDB/CDatabase::SetQueryTimeout
- AFXDB/CDatabase::m_hdbc
dev_langs:
- C++
helpviewer_keywords:
- database classes [C++], ODBC
- MFC [C++], ODBC
- ODBC [C++], CDatabase class
- ODBC database class
- database connections [C++], CDatabase class
- CDatabase class
ms.assetid: bd0de70a-e3c3-4441-bcaa-bbf434426ca8
caps.latest.revision: 24
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: e7b151d83f4229586ad8787a326e332abb9fc79d
ms.lasthandoff: 04/01/2017

---
# <a name="cdatabase-class"></a>CDatabase 클래스
데이터 소스 작업을 할 수 있는 통로인 데이터 소스에 대한 연결을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDatabase : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDatabase::CDatabase](#cdatabase)|`CDatabase` 개체를 생성합니다. 호출 하 여 개체를 초기화 해야 `OpenEx` 또는 **열려**합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDatabase::BeginTrans](#begintrans)|"트랜잭션" 시작-일련의 가역 호출을는 `AddNew`, **편집**, **삭제**, 및 **업데이트** 클래스의 멤버 함수 `CRecordset` -연결 된 데이터 원본에 있습니다. 데이터 원본에 대 한 트랜잭션을 지원 해야 **BeginTrans** 을 적용 합니다.|  
|[CDatabase::BindParameters](#bindparameters)|호출 하기 전에 매개 변수를 바인딩할 수 있도록 `CDatabase::ExecuteSQL`합니다.|  
|[CDatabase::Cancel](#cancel)|비동기 작업 또는 두 번째 스레드가 프로세스를 취소합니다.|  
|[CDatabase::CanTransact](#cantransact)|데이터 소스에서 트랜잭션을 지원 하면 0이 아닌 값을 반환 합니다.|  
|[CDatabase::CanUpdate](#canupdate)|0이 아닌 경우 반환 된 `CDatabase` 개체를 업데이트할 수 (읽기 전용이 아닌).|  
|[CDatabase::Close](#close)|데이터 원본 연결을 닫습니다.|  
|[CDatabase::CommitTrans](#committrans)|으로 시작 된 트랜잭션을 완료 **BeginTrans**합니다. 데이터 소스를 변경 하는 트랜잭션의 명령이 수행 됩니다.|  
|[CDatabase::ExecuteSQL](#executesql)|SQL 문을 실행합니다. 데이터 레코드가 반환 됩니다.|  
|[CDatabase::GetBookmarkPersistence](#getbookmarkpersistence)|책갈피 recordset 개체에 유지 하는 작업을 식별 합니다.|  
|[CDatabase::GetConnect](#getconnect)|연결 하는 데 사용 되는 ODBC 연결 문자열을 반환 된 `CDatabase` 데이터 원본에는 개체입니다.|  
|[CDatabase::GetCursorCommitBehavior](#getcursorcommitbehavior)|열린 레코드 집합 개체에는 트랜잭션 커밋 효과 식별 합니다.|  
|[CDatabase::GetCursorRollbackBehavior](#getcursorrollbackbehavior)|열린 recordset 개체에는 트랜잭션 롤백의 효과 식별 합니다.|  
|[CDatabase::GetDatabaseName](#getdatabasename)|현재 사용 중인 데이터베이스의 이름을 반환 합니다.|  
|[CDatabase::IsOpen](#isopen)|0이 아닌 경우 반환 된 `CDatabase` 개체가 현재 데이터 원본에 연결 되어 있습니다.|  
|[CDatabase::OnSetOptions](#onsetoptions)|표준 연결 옵션을 설정 하기 위해 프레임 워크에서 호출 됩니다. 기본 구현은 쿼리 제한 시간 값을 설정합니다. 호출 하 여 사전에 이러한 옵션을 설정할 수 있습니다 `SetQueryTimeout`합니다.|  
|[CDatabase::Open](#open)|(ODBC 드라이버)를 통해 데이터 원본에 대 한 연결을 설정합니다.|  
|[CDatabase::OpenEx](#openex)|(ODBC 드라이버)를 통해 데이터 원본에 대 한 연결을 설정합니다.|  
|[CDatabase::Rollback](#rollback)|현재 트랜잭션이 동안 변경 내용을 취소 합니다. 에 정의 된 대로 데이터 소스를 이전 상태로 반환 된 **BeginTrans** 변경 되지 않고 호출 합니다.|  
|[CDatabase::SetLoginTimeout](#setlogintimeout)|데이터 원본 연결 시도가 되기까지의 제한 시간 (초)을 설정 합니다.|  
|[CDatabase::SetQueryTimeout](#setquerytimeout)|설정 (초) 후 데이터베이스 쿼리 작업 시간이 초과 됩니다. 모든 후속 레코드 집합에 영향을 줍니다 **열려**, `AddNew`, **편집**, 및 **삭제** 호출 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDatabase::m_hdbc](#m_hdbc)|데이터 원본에 대 한 데이터베이스 연결 (ODBC) 연결 핸들을 엽니다. 형식 **HDBC**합니다.|  
  
## <a name="remarks"></a>설명  
 데이터 소스는 일부 데이터베이스 관리 시스템 (DBMS)에서 호스트 되는 데이터의 특정 인스턴스입니다. Microsoft SQL Server, Microsoft Access, Borland dBASE 및 xBASE을 예로 들 수 있습니다. 하나 이상 포함할 수도 있습니다 `CDatabase` 응용 프로그램에서 한 번에 활성 개체입니다.  
  
> [!NOTE]
>  클래스를 사용 하 여 ODBC Open Database Connectivity () 클래스 아닌 개체 DAO (Data Access) 클래스와 함께 작업 하는 경우 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 대신 합니다. 자세한 내용은 문서 참조 [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)합니다.  
  
 사용 하도록 `CDatabase`, 생성 한 `CDatabase` 개체와 호출 해당 `OpenEx` 멤버 함수입니다. 연결을 엽니다. 다음 작성 `CRecordset` 연결 된 데이터 원본에 대해 작업 개체는 레코드 집합 생성자에 대 한 포인터를 전달 하면 `CDatabase` 개체입니다. 호출 작업을 마치면 연결을 사용 하는 **닫기** 멤버 함수를 파괴는 `CDatabase` 개체입니다. **닫기** 이전에 닫지 않은 모든 레코드 집합을 닫습니다.  
  
 에 대 한 자세한 내용은 `CDatabase`, 문서를 참조 [데이터 원본 (ODBC)](../../data/odbc/data-source-odbc.md) 및 [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDatabase`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdb.h  
  
##  <a name="begintrans"></a>CDatabase::BeginTrans  
 연결된 된 데이터 원본에 대 한 트랜잭션의 시작 하려면이 함수를 호출 합니다.  
  
```  
BOOL BeginTrans();
```  
  
### <a name="return-value"></a>반환 값  
 호출이 성공 했으며 변경 내용을 커밋하는 수동으로; 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 트랜잭션은 구성에 대 한 하나 이상의 호출 됩니다는 `AddNew`, **편집**, **삭제**, 및 **업데이트** 의 멤버 함수는 `CRecordset` 개체입니다. 트랜잭션을 시작 하기 전에 `CDatabase` 개체 해야 이미 되었습니다에 연결한 데이터 소스를 호출 하 여 해당 `OpenEx` 또는 **열려** 멤버 함수입니다. 트랜잭션을 완료 하려면 호출 [CommitTrans](#committrans) 모든 변경 내용을 적용 하는 데이터 소스에 (을)를 호출 하거나 [롤백](#rollback) 전체 트랜잭션을 중단 하 합니다. 호출 **BeginTrans** after 트랜잭션에 관련된 된 모든 레코드 집합을 열 및 실제 가까운 업데이트에 따라 작업 최대한.  
  
> [!CAUTION]
>  ODBC 드라이버에 따라 호출 하기 전에 레코드 집합 열기 **BeginTrans** 를 호출할 때 문제가 발생할 수 있습니다 **롤백**합니다. 사용 하는 특정 드라이버를 확인 해야 합니다. 예를 들어 Microsoft ODBC Desktop Driver Pack 3.0에 포함 된 Microsoft Access 드라이버를 사용할 때 열린 커서가 있는 모든 데이터베이스에서 트랜잭션을 시작 하지 해야 하는 Jet 데이터베이스 엔진의 요구 사항에 대해 고려해 야 합니다. MFC 데이터베이스 클래스에서 열린 커서는 열려 있는 의미 `CRecordset` 개체입니다. 자세한 내용은 참조 [기술 참고 68](../../mfc/tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver.md)합니다.  
  
 **BeginTrans** 요청한 동시성 및 데이터 원본의 기능에 따라 서버에서 데이터 레코드를 잠글 수도 있습니다. 문서를 참조 데이터 잠금에 대 한 내용은 [레코드 집합: 레코드 잠금 (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)합니다.  
  
 사용자 정의 트랜잭션 문서에서 설명 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
 **BeginTrans** 에 트랜잭션 시퀀스 롤백할 수 있습니다 상태 설정 (역방향). 롤백에 대 한 새로운 상태를 설정 하려면 모든 현재 트랜잭션이 커밋 호출 **BeginTrans** 다시 합니다.  
  
> [!CAUTION]
>  호출 **BeginTrans** 호출 하지 않고 다시 **CommitTrans** 또는 **롤백** 오류가 발생 합니다.  
  
 호출 된 [CanTransact](#cantransact) 드라이버에 지정된 된 데이터베이스에 대 한 트랜잭션을 지원 하는지 확인 하려면 멤버 함수입니다. 또한를 호출 해야 [GetCursorCommitBehavior](#getcursorcommitbehavior) 및 [GetCursorRollbackBehavior](#getcursorrollbackbehavior) 커서 보존에 대 한 지원을 확인 하려면.  
  
 트랜잭션에 대 한 자세한 내용은 문서 참조 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
### <a name="example"></a>예제  
  문서를 참조 [트랜잭션: 트랜잭션이 수행 레코드 집합 (ODBC)에서](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)합니다.  
  
##  <a name="bindparameters"></a>CDatabase::BindParameters  
 재정의 `BindParameters` 호출 하기 전에 매개 변수를 바인딩하고 할 때 [CDatabase::ExecuteSQL](#executesql)합니다.  
  
```  
virtual void BindParameters(HSTMT hstmt);
```  
  
### <a name="parameters"></a>매개 변수  
 `hstmt`  
 매개 변수를 바인딩하고 하려는 ODBC 문 핸들입니다.  
  
### <a name="remarks"></a>주의  
 이 접근 방식은 결과 필요 하지 않은 경우에 유용 저장된 프로시저에서 설정 합니다.  
  
 재정의 시, 호출 **SQLBindParameters** 및 관련 ODBC 함수를 매개 변수를 바인딩합니다. 호출 하 여 하기 전에 재정의 호출 하는 MFC `ExecuteSQL`합니다. 호출할 필요가 없습니다 **SQLPrepare**; `ExecuteSQL` 호출 **SQLExecDirect** 되 고 소멸는 **hstmt**, 한 번만 사용 되는 합니다.  
  
##  <a name="cancel"></a>CDatabase::Cancel  
 진행 중인 비동기 작업 또는 프로세스를 두 번째 스레드가 데이터 소스를 취소 하도록 요청 하려면이 함수를 호출 합니다.  
  
```  
void Cancel();
```  
  
### <a name="remarks"></a>주의  
 MFC ODBC 클래스에 더 이상 비동기 처리; 사용 note 비동기 작업을 수행 하려면 직접 ODBC API 함수를 호출 해야 [SQLSetConnectOption](https://msdn.microsoft.com/library/ms713564.aspx)합니다. 자세한 내용은 참조 [비동기 실행](https://msdn.microsoft.com/library/ms713563.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="cantransact"></a>CDatabase::CanTransact  
 데이터베이스 트랜잭션을 허용 하는지 여부를 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL CanTransact() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 값이 사용 하 여 레코드 집합 `CDatabase` 개체 트랜잭션을 허용 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 트랜잭션에 대 한 정보에 대 한 문서를 참조 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
##  <a name="canupdate"></a>CDatabase::CanUpdate  
 확인 하려면이 함수를 호출 여부는 `CDatabase` 개체 업데이트를 허용 합니다.  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우에는 `CDatabase` 업데이트를 허용 하는 개체, 그렇지 않으면 0 전달 하거나 사용자가 나타내는 **TRUE** 에 `bReadOnly` 열릴 때는 `CDatabase` 개체 또는 데이터 원본 자체는 읽기 전용입니다. 데이터 소스는 ODBC API 함수를 호출 하는 경우 읽기 전용 **SQLGetInfo** 에 대 한 **SQL_DATASOURCE_READ_ONLY** "y"를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 일부 드라이버는 업데이트를 지원 합니다.  
  
##  <a name="cdatabase"></a>CDatabase::CDatabase  
 `CDatabase` 개체를 생성합니다.  
  
```  
CDatabase();
```  
  
### <a name="remarks"></a>주의  
 호출 해야 개체를 생성 한 후 해당 `OpenEx` 또는 **열려** 멤버 함수를 지정된 된 데이터 원본에 대 한 연결을 설정 합니다.  
  
 포함을 편리 하 게 찾을 수 있습니다 있습니다는 `CDatabase` 문서 클래스의 개체입니다.  
  
### <a name="example"></a>예제  
 이 예제에서는 사용 하 여 `CDatabase` 에 `CDocument`-클래스를 파생 합니다.  
  
 [!code-cpp[NVC_MFCDatabase # 9](../../mfc/codesnippet/cpp/cdatabase-class_1.h)]  
  
 [!code-cpp[NVC_MFCDatabase # 10](../../mfc/codesnippet/cpp/cdatabase-class_2.cpp)]  
  
##  <a name="close"></a>CDatabase::Close  
 데이터 원본에서 연결을 끊을 하려는 경우이 함수를 호출 합니다.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>설명  
 관련 된 모든 레코드 집합을 닫아야는 `CDatabase` 이 멤버 함수를 호출 하기 전에 개체입니다. 때문에 **닫기** 제거 하지 않습니다는 `CDatabase` 개체를 동일한 데이터 원본이 나 다른 데이터 원본에 대 한 새 연결을 여는 개체를 다시 사용할 수 있습니다.  
  
 보류 중인 모든 `AddNew` 또는 **편집** 의 모든 레코드는 데이터베이스를 사용 하 여 문 취소 되 고 보류 중인 모든 트랜잭션이 롤백됩니다. 모든 레코드 집합에 종속 된 `CDatabase` 개체가 정의 되지 않은 상태로 유지 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase # 12](../../mfc/codesnippet/cpp/cdatabase-class_3.cpp)]  
  
##  <a name="committrans"></a>CDatabase::CommitTrans  
 트랜잭션이 완료 될 때이 함수를 호출 합니다.  
  
```  
BOOL CommitTrans();
```  
  
### <a name="return-value"></a>반환 값  
 업데이트가 성공적으로 커밋된; 0이 아닌 그렇지 않으면 0입니다. 경우 **CommitTrans** 실패 하면 데이터 원본의 상태가 정의 되지 않습니다. 상태를 확인 하기 위해 데이터를 확인 해야 합니다.  
  
### <a name="remarks"></a>주의  
 트랜잭션이 구성 된 일련의 호출을는 `AddNew`, **편집**, **삭제**, 및 **업데이트** 의 멤버 함수는 `CRecordset` 개체에 대 한 호출으로 시작 하는 [BeginTrans](#begintrans) 멤버 함수입니다. **CommitTrans** 트랜잭션을 커밋합니다. 기본적으로 업데이트는 커밋될 즉시; 호출 **BeginTrans** 될 때까지 지연 될 업데이트의 기여를 사용 하면 **CommitTrans** 호출 됩니다.  
  
 호출할 때까지 **CommitTrans** 트랜잭션을 종료를 호출 하면는 [롤백](#rollback) 멤버 함수는 원래 상태로 데이터 소스를 트랜잭션을 중단 하 고 있습니다. 새 트랜잭션을 시작 하려면 호출 **BeginTrans** 다시 합니다.  
  
 트랜잭션에 대 한 자세한 내용은 문서 참조 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
### <a name="example"></a>예제  
  문서를 참조 [트랜잭션: 트랜잭션이 수행 레코드 집합 (ODBC)에서](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)합니다.  
  
##  <a name="executesql"></a>CDatabase::ExecuteSQL  
 SQL 명령 직접 실행 해야 할 경우이 함수를 호출 합니다.  
  
```  
void ExecuteSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszSQL`  
 실행 하는 유효한 SQL 명령이 포함 된 null로 끝나는 문자열에 대 한 포인터입니다. 전달할 수는 [CString](../../atl-mfc-shared/reference/cstringt-class.md)합니다.  
  
### <a name="remarks"></a>주의  
 null로 끝나는 문자열로 명령을 만듭니다. `ExecuteSQL`데이터 레코드를 반환 하지 않습니다. 레코드에 작동 하려면 recordset 개체를 대신 사용 합니다.  
  
 대부분의 데이터 원본에 대 한 명령 데이터 선택, 새 레코드 삽입, 레코드 및 레코드 편집에 대 한 명령을 지 원하는 레코드 집합 개체를 통해 발급 됩니다. 그러나 일부 ODBC 기능은 직접 지원 데이터베이스 클래스에서 사용 하 여 직접 SQL 호출 때때로 해야 하므로 `ExecuteSQL`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase # 13](../../mfc/codesnippet/cpp/cdatabase-class_4.cpp)]  
  
##  <a name="getbookmarkpersistence"></a>CDatabase::GetBookmarkPersistence  
 특정 작업 후 레코드 집합 개체에 책갈피가 유지되는지 확인하려면 이 멤버 함수를 호출합니다.  
  
```  
DWORD GetBookmarkPersistence() const;  
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합 개체에 책갈피를 유지하는 작업을 식별하는 비트 마스크입니다. 자세한 내용은 설명을 참조하세요.  
  
### <a name="remarks"></a>주의  
 예를 들어 `CRecordset::GetBookmark`와 `CRecordset::Requery`를 차례로 호출하면 `GetBookmark`에서 가져온 책갈피가 더 이상 유효하지 않게 될 수 있습니다. `GetBookmarkPersistence`를 호출하기 전에 `CRecordset::SetBookmark`를 호출해야 합니다.  
  
 다음 테이블에는 `GetBookmarkPersistence`의 반환 값에 대해 결합할 수 있는 비트 마스크 값이 나와 있습니다.  
  
|비트 마스크 값|책갈피 유지|  
|-------------------|--------------------------|  
|`SQL_BP_CLOSE`|책갈피는 유효 기간이 **Requery** 작업 합니다.|  
|`SQL_BP_DELETE`|행에 대 한 책갈피는 유효 기간이 **삭제** 해당 행에 대 한 작업이 있습니다.|  
|`SQL_BP_DROP`|책갈피는 유효 기간이 **닫기** 작업 합니다.|  
|`SQL_BP_SCROLL`|책갈피는 된 후 유효한 **이동** 작업 합니다. 따라서 `CRecordset::CanBookmark`에서 반환되는 책갈피가 레코드 집합에서 지원되는지를 쉽게 파악할 수 있습니다.|  
|`SQL_BP_TRANSACTION`|트랜잭션이 커밋되거나 롤백된 후에 책갈피가 유효합니다.|  
|`SQL_BP_UPDATE`|행에 대 한 책갈피는 유효 기간이 **업데이트** 해당 행에 대 한 작업이 있습니다.|  
|`SQL_BP_OTHER_HSTMT`|레코드 집합 개체 하나와 연결된 책갈피가 두 번째 레코드 집합에서도 유효합니다.|  
  
 이 반환 값에 대 한 자세한 내용은 ODBC API 함수를 참조 하십시오. **SQLGetInfo** 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 책갈피에 대 한 자세한 내용은 문서 참조 [레코드 집합: 책갈피와 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)합니다.  
  
##  <a name="getconnect"></a>CDatabase::GetConnect  
 이 멤버 함수를 호출 하는 동안 사용 된 연결 문자열을 검색 호출 `OpenEx` 또는 `Open` 연결는 `CDatabase` 데이터 원본에 개체입니다.  
  
```  
const CString GetConnect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `const` [CString](../../atl-mfc-shared/reference/cstringt-class.md) 경우 연결 문자열에 포함 된 `OpenEx` 또는 `Open` 호출 않았으면 빈 문자열입니다.  
  
### <a name="remarks"></a>주의  
 참조 [CDatabase::Open](#open) 에 대 한 설명은 어떻게 연결 문자열이 생성 됩니다.  
  
##  <a name="getcursorcommitbehavior"></a>CDatabase::GetCursorCommitBehavior  
 확인 하려면이 함수를 호출 방법을 [CommitTrans](#committrans) 작업 커서 열기 recordset 개체에 영향을 줍니다.  
  
```  
int GetCursorCommitBehavior() const;  
```  
  
### <a name="return-value"></a>반환 값  
 열린 레코드 집합 개체에는 트랜잭션 효과 나타내는 값입니다. 자세한 내용은 설명을 참조하세요.  
  
### <a name="remarks"></a>주의  
 다음 표에서 가능한 반환 값에 대 한 `GetCursorCommitBehavior` 및 열려 레코드 집합에 대 한 해당 영향입니다.  
  
|반환 값|CRecordset 개체에 미치는 영향|  
|------------------|----------------------------------|  
|`SQL_CB_CLOSE`|호출 `CRecordset::Requery` 바로 다음에 트랜잭션 커밋입니다.|  
|`SQL_CB_DELETE`|호출 `CRecordset::Close` 바로 다음에 트랜잭션 커밋입니다.|  
|`SQL_CB_PRESERVE`|일반적으로 계속 `CRecordset` 작업 합니다.|  
  
 이 반환 값에 대 한 자세한 내용은 ODBC API 함수를 참조 하십시오. **SQLGetInfo** 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 트랜잭션에 대 한 자세한 내용은 문서 참조 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
##  <a name="getcursorrollbackbehavior"></a>CDatabase::GetCursorRollbackBehavior  
 확인 하려면이 함수를 호출 방법을 [롤백](#rollback) 작업 커서 열기 recordset 개체에 영향을 줍니다.  
  
```  
int GetCursorRollbackBehavior() const;  
```  
  
### <a name="return-value"></a>반환 값  
 열린 레코드 집합 개체에는 트랜잭션 효과 나타내는 값입니다. 자세한 내용은 설명을 참조하세요.  
  
### <a name="remarks"></a>설명  
 다음 표에서 가능한 반환 값에 대 한 `GetCursorRollbackBehavior` 및 열려 레코드 집합에 대 한 해당 영향입니다.  
  
|반환 값|CRecordset 개체에 미치는 영향|  
|------------------|----------------------------------|  
|`SQL_CB_CLOSE`|호출 `CRecordset::Requery` 트랜잭션 롤백 바로 뒤에 따라오는 합니다.|  
|`SQL_CB_DELETE`|호출 `CRecordset::Close` 트랜잭션 롤백 바로 뒤에 따라오는 합니다.|  
|`SQL_CB_PRESERVE`|일반적으로 계속 `CRecordset` 작업 합니다.|  
  
 이 반환 값에 대 한 자세한 내용은 ODBC API 함수를 참조 하십시오. **SQLGetInfo** 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 트랜잭션에 대 한 자세한 내용은 문서 참조 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
##  <a name="getdatabasename"></a>CDatabase::GetDatabaseName  
 (제공 하는 "데이터베이스" 라는 명명 된 개체를 정의 하는 데이터 원본) 현재 연결 된 데이터베이스의 이름을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetDatabaseName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 고, 그렇지 않으면 성공 하는 경우 데이터베이스 이름이 포함 된, 비어 있는 `CString`합니다.  
  
### <a name="remarks"></a>주의  
 이것이에 지정 된 데이터 원본 이름 (DSN)와 동일 하지는 `OpenEx` 또는 **열려** 호출 합니다. 어떤 `GetDatabaseName` 반환 ODBC에 따라 달라 집니다. 일반적으로 데이터베이스는 테이블의 컬렉션입니다. 이 엔터티는 이름이 경우 `GetDatabaseName` 반환 합니다.  
  
 예를 들어 제목에는이 이름이 표시 하려면 될 수 있습니다. ODBC에서 이름을 검색 하는 동안 오류가 발생 한 경우 `GetDatabaseName` 빈 반환 **Cstring**합니다.  
  
##  <a name="isopen"></a>CDatabase::IsOpen  
 확인 하려면이 함수를 호출 여부는 `CDatabase` 개체가 현재 데이터 원본에 연결 되어 있습니다.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우에는 `CDatabase` 개체가 현재 연결 되어 있습니다; 그렇지 않으면 0입니다.  
  
##  <a name="m_hdbc"></a>CDatabase::m_hdbc  
 ODBC 데이터 원본 연결에 대 한 공용 핸들 포함-"연결 핸들"입니다.  
  
### <a name="remarks"></a>주의  
 일반적으로이 멤버 변수를 직접 액세스할 필요가 없는 해야 합니다. 호출 하는 경우 프레임 워크는 핸들을 할당 하는 대신, `OpenEx` 또는 **열려**합니다. 프레임 워크를 호출 하는 경우 핸들 할당 취소는 **삭제** 연산자에는 `CDatabase` 개체입니다. **닫기** 멤버 함수에 핸들 할당 해제 하지 않습니다.  
  
 그러나 상황에 따라 직접 핸들을 사용 하도록 할 수 있습니다. 예를 들어, 클래스를 통해가 대신 직접 ODBC API 함수를 호출 하는 경우 `CDatabase`를 매개 변수로 전달 하 여 연결 핸들을 할 수 있습니다. 아래 코드 예제를 참조 하십시오.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase # 15](../../mfc/codesnippet/cpp/cdatabase-class_5.cpp)]  
  
##  <a name="onsetoptions"></a>CDatabase::OnSetOptions  
 프레임 워크 함께 SQL 문을 직접 실행 하는 경우이 멤버 함수 호출의 `ExecuteSQL` 멤버 함수입니다.  
  
```  
virtual void OnSetOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>매개 변수  
 `hstmt`  
 옵션은 설정 되는 ODBC 문 핸들입니다.  
  
### <a name="remarks"></a>주의  
 `CRecordset::OnSetOptions`또한이 멤버 함수를 호출합니다.  
  
 `OnSetOptions`로그인 제한 시간 값을 설정합니다. 에 대 한 이전 호출 된 경우에 `SetQueryTimeout` 와 멤버 함수를 `OnSetOptions` ; 현재 값을 반영 합니다. 그렇지 않은 경우 기본값을 설정 합니다.  
  
> [!NOTE]
>  MFC 4.2 이전 `OnSetOptions` 어느 snychronous / 비동기 처리 모드를 설정할 수도 있습니다. MFC 4.2 부터는 모든 작업은 동기입니다. 비동기 작업을 수행 하려면 ODBC API 함수를 직접 호출 해야 **SQLSetPos**합니다.  
  
 재정의할 필요가 없습니다 `OnSetOptions` 제한 시간 값을 변경 합니다. 대신, 쿼리 제한 시간 값을 사용자 지정 하려면 호출 `SetQueryTimeout` ; 레코드 집합을 만들기 전에 `OnSetOptions` 새 값이 사용 됩니다. 설정 된 모든 레코드 집합 또는 직접 SQL 호출에 대 한 후속 작업에 적용 됩니다.  
  
 재정의 `OnSetOptions` 추가 옵션을 설정 하려는 경우. 재정의 기본 클래스를 호출 해야 `OnSetOptions` 이전 또는 ODBC API 함수를 호출한 후 **SQLSetStmtOption**합니다. 프레임 워크의 기본 구현에 설명 된 방법을 따릅니다 `OnSetOptions`합니다.  
  
##  <a name="open"></a>CDatabase::Open  
 이를 새로 생성 된 초기화 함수를 호출 `CDatabase` 개체입니다.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszDSN,  
    BOOL bExclusive = FALSE,  
    BOOL bReadOnly = FALSE,  
    LPCTSTR lpszConnect = _T("ODBC;"),  
    BOOL bUseCursorLib = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszDSN`  
 데이터 원본 이름을 지정-이름이 ODBC 관리자 프로그램을 통해 ODBC로 등록 합니다. DSN 값에 지정 된 경우 `lpszConnect` (형태로 "DSN =\<데이터 소스 >")를 다시 지정 하지 해야 `lpszDSN`합니다. 이 경우 `lpszDSN` 해야 **NULL**합니다. 그렇지 않으면 전달할 수 있습니다 **NULL** 사용자는 사용자가 데이터 소스를 선택할 수 있는 데이터 원본 대화 상자를 표시 하려는 경우. 자세한 내용은 설명 부분을 참조 합니다.  
  
 `bExclusive`  
 클래스 라이브러리의이 버전에서 지원 되지 않습니다. 이 매개 변수가 어설션이 실패 하는 현재 **TRUE**합니다. (제외 하지) 공유 데이터 원본이 항상 열립니다.  
  
 `bReadOnly`  
 **True 이면** 연결을 읽기 전용 및 데이터 원본에 대 한 업데이트를 하지 못하도록 하려는 경우. 종속 된 모든 레코드는이 특성을 상속합니다. 기본값은 **FALSE**합니다.  
  
 `lpszConnect`  
 연결 문자열을 지정합니다. 연결 문자열 정보를 데이터 원본 이름, 데이터 원본, 사용자 인증 문자열 (데이터 원본 하나 필요로 하는 경우 암호) 및 기타 정보에 올바른 사용자 ID를 포함 하 여 연결 합니다. 연결 문자열 전체가 "ODBC"; 문자열에 의해 앞 (대문자 또는 소문자). "ODBC"; ODBC 데이터 원본에 연결 되어 있음을 나타내려면 문자열이 사용 됩니다 이 있으면 위쪽의 호환성을 위해 클래스 라이브러리의 이후 버전 비 ODBC 데이터 소스를 지원할 수 있습니다.  
  
 `bUseCursorLib`  
 **True 이면** ODBC 커서 라이브러리 DLL을 로드 하려는 경우. 커서 라이브러리 (드라이버가 지 원하는) 경우에 효과적으로 다이너셋 사용 하지 못하게 기본 ODBC 드라이버의 일부 기능을 마스크 합니다. 커서 라이브러리가 로드 하는 경우 지원 전용 커서는 정적 스냅숏 및 정방향 전용 커서입니다. 기본값은 **TRUE**합니다. 레코드 집합 개체를 직접 만들려는 경우 `CRecordset` 없이 파생 되지 커서 라이브러리를 로드 해야 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공적으로 연결 됩니다. 0이 아닌 그렇지 않으면 0는 사용자가 선택 하는 경우 더 많은 연결 정보를 묻는 대화 상자가 나타나면 취소 합니다. 다른 모든 경우에는 프레임 워크는 예외가 throw 됩니다.  
  
### <a name="remarks"></a>설명  
 레코드 집합 개체를 생성 하는 사용 하기 전에 데이터베이스 개체를 초기화 합니다.  
  
> [!NOTE]
>  호출 된 [OpenEx](#openex) 멤버 함수는 데이터 원본에 연결 하 여 데이터베이스 개체를 초기화 하는 것이 좋습니다.  
  
 경우에 매개 변수 여 **열려** 호출 연결을 만드는 데 충분 한 정보를 포함 하지 않습니다, ODBC 드라이버는 사용자 로부터 필요한 정보를 얻기 위해 대화 상자를 엽니다. 호출 하는 경우 **열려**, 연결 문자열을 `lpszConnect`, 개인적으로 저장 되는 `CDatabase` 개체를 호출 하 여 ´ ï ´는 [GetConnect](#getconnect) 멤버 함수입니다.  
  
 호출 하기 전에 고유한 대화 상자를 열 수 있습니다 **열고** 에서 암호와 같은 사용자 정보를 가져오는 다음 해당 정보를 추가 연결 문자열에 전달할 **열고**합니다. 응용 프로그램이 호출 시간 전달 다음 재사용할 수 있도록 연결 문자열을 저장 하려는 경우 또는 **열려** 에 `CDatabase` 개체입니다.  
  
 여러 수준의 로그인 권한 부여에 대 한 연결 문자열을 사용할 수도 있습니다 (각각에 대 한 다른 `CDatabase` 개체) 또는 다른 데이터 소스 관련 정보를 전달 합니다. 연결 문자열에 대 한 자세한 내용은에서 5 장 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 있기 연결 시도가 시간 초과 대 한 경우 예를 들어 DBMS 호스트를 사용할 수 없습니다. 연결 시도가 실패 하면 **열려** throw 한 `CDBException`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase # 14](../../mfc/codesnippet/cpp/cdatabase-class_6.cpp)]  
  
##  <a name="openex"></a>CDatabase::OpenEx  
 이를 새로 생성 된 초기화 함수를 호출 `CDatabase` 개체입니다.  
  
```  
virtual BOOL OpenEx(
    LPCTSTR lpszConnectString,  
    DWORD dwOptions = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszConnectString`  
 ODBC 연결 문자열을 지정합니다. 사용자 ID 및 암호와 같은 기타 선택적 정보 뿐만 아니라 데이터 원본 이름이 포함 되어 있습니다. 예를 들어 "DSN SQLServer_Source; = UID = SA; PWD = abc123 "은 가능한 연결 문자열입니다. 전달 하는 경우 유의 **NULL** 에 대 한 `lpszConnectString`, 데이터 원본 대화 상자에서 데이터 원본을 선택 하 라는 됩니다.  
  
 `dwOptions`  
 다음 값의 조합을 지정 하는 비트 마스크입니다. 기본값은 0으로 데이터베이스를 열 수는 의미 쓰기 권한으로 공유 하는 ODBC 커서 라이브러리 DLL 로드 되지 것입니다, 그리고 및 ODBC 연결 대화 상자는 연결을 만드는 데 필요한 정보가 충분 한 경우에 표시 됩니다.  
  
- **CDatabase::openExclusive** 클래스 라이브러리의이 버전에서 지원 되지 않습니다. (제외 하지) 공유 데이터 원본은 항상 열립니다. 현재이 옵션을 지정 하는 경우는 어설션이 실패 합니다.  
  
- **CDatabase::openReadOnly** 읽기 전용으로 데이터 원본을 엽니다.  
  
- **CDatabase::useCursorLib** ODBC 커서 라이브러리 DLL를 로드 합니다. 커서 라이브러리 (드라이버가 지 원하는) 경우에 효과적으로 다이너셋 사용 하지 못하게 기본 ODBC 드라이버의 일부 기능을 마스크 합니다. 커서 라이브러리가 로드 하는 경우 지원 전용 커서는 정적 스냅숏 및 정방향 전용 커서입니다. 레코드 집합 개체를 직접 만들려는 경우 `CRecordset` 없이 파생 되지 커서 라이브러리를 로드 해야 합니다.  
  
- **CDatabase::noOdbcDialog** 충분 한 연결 정보를 제공 하는 여부에 관계 없이 ODBC 연결 대화 상자를 표시 하지 않습니다.  
  
- **CDatabase::forceOdbcDialog** 항상 ODBC 연결 대화 상자를 표시 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공적으로 연결 됩니다. 0이 아닌 그렇지 않으면 0는 사용자가 선택 하는 경우 더 많은 연결 정보를 묻는 대화 상자가 나타나면 취소 합니다. 다른 모든 경우에는 프레임 워크는 예외가 throw 됩니다.  
  
### <a name="remarks"></a>주의  
 레코드 집합 개체를 생성 하는 사용 하기 전에 데이터베이스 개체를 초기화 합니다.  
  
 경우는 `lpszConnectString` 에서 매개 변수 여 `OpenEx` 호출에 포함 된 연결에 정보가 부족, 설정 하지 않은 경우 ODBC 드라이버는 사용자 로부터 필요한 정보를 얻기 위해 대화 상자를 엽니다 **CDatabase::noOdbcDialog** 또는 **CDatabase::forceOdbcDialog** 에 `dwOptions` 매개 변수입니다. 호출 하는 경우 `OpenEx`, 연결 문자열을 `lpszConnectString`, 개인적으로 저장 됩니다는 `CDatabase` 개체를 호출 하 여 사용할 수는 [GetConnect](#getconnect) 멤버 함수입니다.  
  
 호출 하기 전에 고유한 대화 상자를 열 수를 `OpenEx` 암호와 같은 사용자 로부터 정보를 가져올 한 후에 전달할 연결 문자열에 해당 정보를 추가 `OpenEx`합니다. 응용 프로그램이 호출 시간 전달 다음 재사용할 수 있도록 연결 문자열을 저장 하려는 경우 또는 `OpenEx` 에 `CDatabase` 개체입니다.  
  
 여러 수준의 로그인 권한 부여에 대 한 연결 문자열을 사용할 수도 있습니다 (각각에 대 한 다른 `CDatabase` 개체) 또는 다른 데이터 소스 관련 정보를 전달 합니다. 연결 문자열에 대 한 자세한 내용은에서 6 장 참조는 *ODBC Programmer's Reference*합니다.  
  
 있기 연결 시도가 시간 초과 대 한 경우 예를 들어 DBMS 호스트를 사용할 수 없습니다. 연결 시도가 실패 하면 `OpenEx` throw 한 `CDBException`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase # 11](../../mfc/codesnippet/cpp/cdatabase-class_7.cpp)]  
  
##  <a name="rollback"></a>CDatabase::Rollback  
 트랜잭션 중에 수행 된 변경 내용이 되돌리는 것이 멤버 함수를 호출 합니다.  
  
```  
BOOL Rollback();
```  
  
### <a name="return-value"></a>반환 값  
 트랜잭션이 성공적으로 취소; 0이 아닌 그렇지 않으면 0입니다. 경우는 **롤백** 호출이 실패 하는 데이터 원본 및 트랜잭션 상태 정의 되지 않습니다. 경우 **롤백** 0을 반환 해당 상태를 확인 하려면 데이터 소스를 확인 해야 합니다.  
  
### <a name="remarks"></a>주의  
 모든 `CRecordset``AddNew`, **편집**, **삭제**, 및 **업데이트** 마지막 이후 실행 호출 [BeginTrans](#begintrans) 호출 하는 시간에 존재 했던 상태로으로 롤백됩니다.  
  
 호출한 후 **롤백**, 트랜잭션이 스타일러스가 및 호출 해야 **BeginTrans** 다른 트랜잭션에 대 한 다시 합니다. 호출 하기 전에 현재 레코드가 **BeginTrans** 후 다시 현재 레코드가 됩니다 **롤백**합니다.  
  
 롤백 후, 레코드 롤백 이전에 유지 됩니다. 상태 레코드 집합과 롤백 후 데이터 원본에 대 한 자세한 문서를 참조 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
### <a name="example"></a>예제  
  문서를 참조 [트랜잭션: 트랜잭션이 수행 레코드 집합 (ODBC)에서](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)합니다.  
  
##  <a name="setlogintimeout"></a>CDatabase::SetLoginTimeout  
 이 함수를 호출-호출 하기 전에 `OpenEx` 또는 **열려** -시도한 데이터 되기 전에 허용 되는 시간 (초) 기본값을 재정의 하려면 원본 연결 시간이 초과 합니다.  
  
```  
void SetLoginTimeout(DWORD dwSeconds);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwSeconds`  
 연결 시도 하기 전까지 허용 시간 (초)의 수 제한 시간이 초과 합니다.  
  
### <a name="remarks"></a>주의  
 예를 들어 DBMS 사용할 수 없으면 연결 시도가 시간 초과 수 있습니다. 호출 **SetLoginTimeout** 는 초기화 되지 않은 생성 한 후 `CDatabase` 개체 하지만 호출 하기 전에 `OpenEx` 또는 **열려**합니다.  
  
 로그인 시간 제한의 기본값은 15 초입니다. 일부 데이터 원본은 로그인 제한 시간 값을 지정 하는 기능을 지원 합니다. 데이터 원본의 제한 시간을 지원 하지 않으면 추적 출력을 만들지만 되지 않는 예외 가져옵니다. 값이 0 이면 "무제한".  
  
##  <a name="setquerytimeout"></a>CDatabase::SetQueryTimeout  
 후속 작업에 연결 된 데이터 원본 시간 초과 하기 전까지 허용 시간 (초) 기본값을 재정의 하려면이 함수를 호출 합니다.  
  
```  
void SetQueryTimeout(DWORD dwSeconds);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwSeconds`  
 쿼리 시도 하기 전까지 허용 시간 (초)의 수 제한 시간이 초과 합니다.  
  
### <a name="remarks"></a>주의  
 네트워크 액세스 문제, 과도 한 쿼리 처리 시간 및 등으로 인해 작업 시간이 초과 될 수 있습니다. 호출 `SetQueryTimeout` 레코드 집합을 열기 전에 또는 레코드 집합의이 호출 되기 전에 `AddNew`, **업데이트** 또는 **삭제** 쿼리 제한 시간 값을 변경 하려는 경우 멤버 함수입니다. 설정은 모든 후속 **열려**, `AddNew`, **업데이트**, 및 **삭제** 와 연결 된 모든 레코드 집합에 대 한 호출 `CDatabase` 개체입니다. 연 후 레코드 집합에 대 한 쿼리 제한 시간 값을 변경 하는 경우에 레코드 집합에 대 한 값을 변경 되지 않습니다. 예를 들어, 후속 **이동** 작업 새 값을 사용 하지 않습니다.  
  
 쿼리 시간 제한의 기본값은 15 초입니다. 일부 데이터 원본은 쿼리 제한 시간 값을 설정 하는 기능을 지원 합니다. 쿼리 제한 시간 값이 0 설정 하는 경우 시간 제한 없이 발생 합니다. 데이터 소스와의 통신 응답 하지 않을 수 있습니다. 개발 하는 동안이 동작이 유용할 수 있습니다. 데이터 원본의 제한 시간을 지원 하지 않으면 추적 출력을 만들지만 되지 않는 예외 가져옵니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRecordset 클래스](../../mfc/reference/crecordset-class.md)

