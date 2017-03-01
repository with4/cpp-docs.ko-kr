---
title: "CDatabase 클래스 | Microsoft 문서"
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a14025d712f09bef2b6b749d46cac1b1371fd4e3
ms.lasthandoff: 02/24/2017

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
|[CDatabase::BeginTrans](#begintrans)|로, "트랜잭션" 시작 "는 일련의 되돌릴 수 있는 호출을는 `AddNew`, **편집**, **삭제**, 및 **업데이트** 클래스의 멤버 함수 `CRecordset` 로," 연결된 된 데이터 원본에 있습니다. 데이터 원본에 대 한 트랜잭션을 지원 해야 **BeginTrans** 을 적용 합니다.|  
|[CDatabase::BindParameters](#bindparameters)|호출 하기 전에 매개 변수를 바인딩할 수 있도록 `CDatabase::ExecuteSQL`합니다.|  
|[CDatabase::Cancel](#cancel)|비동기 작업 또는 두 번째 스레드에서 프로세스를 취소합니다.|  
|[CDatabase::CanTransact](#cantransact)|데이터 소스에서 트랜잭션을 지원할 경우&0;이 아닌 값을 반환 합니다.|  
|[CDatabase::CanUpdate](#canupdate)|0이 아닌 경우 반환 된 `CDatabase` 개체를 업데이트할 수 (읽기 전용이 아닌).|  
|[CDatabase::Close](#close)|데이터 원본 연결을 닫습니다.|  
|[CDatabase::CommitTrans](#committrans)|으로 시작 된 트랜잭션을 완료 **BeginTrans**합니다. 데이터 소스를 변경 하는 트랜잭션의 명령이 수행 됩니다.|  
|[CDatabase::ExecuteSQL](#executesql)|SQL 문을 실행합니다. 데이터 레코드가 반환 됩니다.|  
|[CDatabase::GetBookmarkPersistence](#getbookmarkpersistence)|Recordset 개체에 책갈피 유지 하는 작업을 식별 합니다.|  
|[CDatabase::GetConnect](#getconnect)|연결 하는 데 ODBC 연결 문자열을 반환 된 `CDatabase` 데이터 원본에 대 한 개체입니다.|  
|[CDatabase::GetCursorCommitBehavior](#getcursorcommitbehavior)|열린 레코드 집합 개체에 대 한 트랜잭션 커밋 효과 식별 합니다.|  
|[CDatabase::GetCursorRollbackBehavior](#getcursorrollbackbehavior)|열린 레코드 집합 개체에 트랜잭션을 롤백할의 효과 식별 합니다.|  
|[CDatabase::GetDatabaseName](#getdatabasename)|현재 사용 중인 데이터베이스의 이름을 반환합니다.|  
|[CDatabase::IsOpen](#isopen)|0이 아닌 경우 반환 된 `CDatabase` 개체는 현재 데이터 원본에 연결 합니다.|  
|[CDatabase::OnSetOptions](#onsetoptions)|표준 연결 옵션을 설정 하는 프레임 워크에서 호출 됩니다. 기본 구현은 쿼리 제한 시간 값을 설정합니다. 호출 하 여 사전에 이러한 옵션을 설정할 수 있습니다 `SetQueryTimeout`합니다.|  
|[CDatabase::Open](#open)|(ODBC 드라이버)를 통해 데이터 원본에 대 한 연결을 설정합니다.|  
|[CDatabase::OpenEx](#openex)|(ODBC 드라이버)를 통해 데이터 원본에 대 한 연결을 설정합니다.|  
|[CDatabase::Rollback](#rollback)|현재 트랜잭션 중에 변경 내용을 취소 합니다. 정의를 이전 상태로 반환 되는 데이터 소스는 **BeginTrans** 도 동일 하 게 호출 합니다.|  
|[CDatabase::SetLoginTimeout](#setlogintimeout)|데이터 원본 연결 시도 시간이 초과 됩니다. 초 수를 설정 합니다.|  
|[CDatabase::SetQueryTimeout](#setquerytimeout)|집합 수 (초)는 데이터베이스 쿼리 작업 시간이 초과 됩니다. 이후의 모든 레코드 집합에 영향을 줍니다 **열려**, `AddNew`, **편집**, 및 **삭제** 호출 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDatabase::m_hdbc](#m_hdbc)|데이터 원본에 데이터베이스 연결 (ODBC) 연결 핸들을 엽니다. 형식 **HDBC**합니다.|  
  
## <a name="remarks"></a>주의  
 데이터 소스는 일부 데이터베이스 관리 시스템 (DBMS)에서 호스트 되는 데이터의 특정 인스턴스입니다. Microsoft SQL Server, Microsoft Access, Borland dBASE 및 xBASE을 예로 들 수 있습니다. 하나 이상 있을 수 있습니다 `CDatabase` 응용 프로그램에서 한 번에 활성 개체입니다.  
  
> [!NOTE]
>  클래스를 사용 하 여 연결 ODBC (Open Database) 클래스를 사용 하지 않고 데이터 액세스 개체 (DAO) 클래스와 작업 하는 경우 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 대신 합니다. 자세한 내용은 문서를 참조 하십시오. [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)합니다.  
  
 사용 하 여 `CDatabase`, 생성 한 `CDatabase` 개체와 호출의 `OpenEx` 멤버 함수입니다. 연결을 엽니다. 다음 구성할 `CRecordset` 연결 된 데이터 원본에 대해 작업 개체는 레코드 집합 생성자에 대 한 포인터를 전달 하면 `CDatabase` 개체입니다. 호출 작업을 마치면 연결을 사용 하는 **닫기** 멤버 함수를 파괴는 `CDatabase` 개체입니다. **닫기** 이전에 닫지 않은 모든 레코드 집합을 닫습니다.  
  
 에 대 한 자세한 내용은 `CDatabase`, 문서를 참조 [데이터 원본 (ODBC)](../../data/odbc/data-source-odbc.md) 및 [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDatabase`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdb.h  
  
##  <a name="a-namebegintransa--cdatabasebegintrans"></a><a name="begintrans"></a>CDatabase::BeginTrans  
 연결된 된 데이터 원본에 대 한 트랜잭션의 시작 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL BeginTrans();
```  
  
### <a name="return-value"></a>반환 값  
 성공적으로 호출 하 고 변경 내용을 커밋하는 수동으로; 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 트랜잭션이 구성에 대 한 하나 이상의 호출 된는 `AddNew`, **편집**, **삭제**, 및 **업데이트** 의 멤버 함수는 `CRecordset` 개체입니다. 트랜잭션을 시작 하기 전에 `CDatabase` 개체 해야 이미 연결한 데이터 원본에 호출 하 여 해당 `OpenEx` 또는 **열려** 멤버 함수입니다. 트랜잭션이 종료 하려면 호출 [CommitTrans](#committrans) 모든 변경 내용을 적용 하는 데이터 소스에 (을)를 호출 하거나 [롤백](#rollback) 전체 트랜잭션을 중단 하 합니다. 호출 **BeginTrans** 트랜잭션에 관련된 된 모든 레코드 집합을 열 여으로 실제 가까운 업데이트 작업 가능한 배포한 합니다.  
  
> [!CAUTION]
>  ODBC 드라이버에 따라 호출 하기 전에 레코드 집합 열기 **BeginTrans** 를 호출할 때 문제가 발생할 수 있습니다 **롤백**합니다. 사용 하는 특정 드라이버를 확인 해야 합니다. 예를 들어 Microsoft ODBC Desktop Driver Pack 3.0에 포함 된 Microsoft Access 드라이버를 사용할 때 열린 커서가 있는 모든 데이터베이스에서 트랜잭션을 시작 하지 해야 하는 Jet 데이터베이스 엔진의 요구 사항에 대해 감안해 야 합니다. MFC 데이터베이스 클래스에서 열린 커서는 열려 있는 의미 `CRecordset` 개체입니다. 자세한 내용은 참조 [기술 참고 68](../../mfc/tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver.md)합니다.  
  
 **BeginTrans** 요청한 동시성 및 데이터 원본의 기능에 따라 서버에서 데이터 레코드를 잠글 수도 있습니다. 문서를 참조 데이터 잠금에 대 한 내용은 [레코드 집합: 레코드 잠금 (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)합니다.  
  
 사용자 정의 트랜잭션이 문서에 설명 된 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
 **BeginTrans** 하는 트랜잭션 시퀀스 롤백할 수 상태 설정 (역방향). 롤백에 새로운 상태를 설정 하기 위해 모든 현재 트랜잭션이 커밋 호출 **BeginTrans** 다시 합니다.  
  
> [!CAUTION]
>  호출 **BeginTrans** 호출 하지 않고 다시 **CommitTrans** 또는 **롤백** 오류가 발생 합니다.  
  
 호출의 [CanTransact](#cantransact) 멤버 함수를 드라이버에 지정된 된 데이터베이스에 대 한 트랜잭션을 지원 하는지 확인 합니다. 도 호출 해야 [GetCursorCommitBehavior](#getcursorcommitbehavior) 및 [GetCursorRollbackBehavior](#getcursorrollbackbehavior) 커서 보존에 대 한 지원을 확인 하려면.  
  
 트랜잭션에 대 한 자세한 내용은 문서를 참조 하십시오. [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
### <a name="example"></a>예제  
  문서를 참조 하십시오 [트랜잭션: 트랜잭션이 수행 레코드 집합 (ODBC)에서](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)합니다.  
  
##  <a name="a-namebindparametersa--cdatabasebindparameters"></a><a name="bindparameters"></a>CDatabase::BindParameters  
 재정의 `BindParameters` 호출 하기 전에 매개 변수를 바인딩하고 할 때 [CDatabase::ExecuteSQL](#executesql)합니다.  
  
```  
virtual void BindParameters(HSTMT hstmt);
```  
  
### <a name="parameters"></a>매개 변수  
 `hstmt`  
 매개 변수를 바인딩하고 하려는 ODBC 문 핸들입니다.  
  
### <a name="remarks"></a>주의  
 이 방식은 유용 결과 필요 하지 않은 경우 저장된 프로시저에서 설정 합니다.  
  
 재정의 시, 호출 **SQLBindParameters** 및 관련 ODBC 함수에 매개 변수를 바인딩합니다. MFC 호출 전에 호출 하 여 재정의 `ExecuteSQL`합니다. 호출할 필요가 없습니다 **SQLPrepare**; `ExecuteSQL` 호출 **SQLExecDirect** 되 고 소멸는 **hstmt**, 한 번만 사용 됩니다.  
  
##  <a name="a-namecancela--cdatabasecancel"></a><a name="cancel"></a>CDatabase::Cancel  
 진행 중인 비동기 작업 또는 프로세스를 두 번째 스레드에서 데이터 소스를 취소 하도록 요청 하려면이 멤버 함수를 호출 합니다.  
  
```  
void Cancel();
```  
  
### <a name="remarks"></a>주의  
 Note MFC ODBC 클래스에 더 이상; 비동기 처리 사용 비동기 작업을 수행 하려면 직접 ODBC API 함수를 호출 해야 [SQLSetConnectOption](https://msdn.microsoft.com/library/ms713564.aspx)합니다. 자세한 내용은 참조 [비동기 실행](https://msdn.microsoft.com/library/ms713563.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namecantransacta--cdatabasecantransact"></a><a name="cantransact"></a>CDatabase::CanTransact  
 데이터베이스 트랜잭션을 허용 하는지 여부를 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL CanTransact() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 값이 사용 하 여 레코드 집합 `CDatabase` 개체 트랜잭션을 허용 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 트랜잭션에 대 한 정보를 문서를 참조 하십시오. [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
##  <a name="a-namecanupdatea--cdatabasecanupdate"></a><a name="canupdate"></a>CDatabase::CanUpdate  
 확인 하려면이 함수를 호출 여부는 `CDatabase` 개체 업데이트를 허용 합니다.  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 값은 `CDatabase` 개체 업데이트를 사용 하 고, 그렇지 않으면 0 어느 사용자가 나타내는 전달 **TRUE** 에서 `bReadOnly` 열 때는 `CDatabase` 개체 또는 데이터 원본 자체는 읽기 전용입니다. 데이터 소스는 ODBC API 함수를 호출 하는 경우 읽기 전용 **SQLGetInfo** 에 대 한 **SQL_DATASOURCE_READ_ONLY** "y"를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 일부 드라이버 업데이트를 지원 합니다.  
  
##  <a name="a-namecdatabasea--cdatabasecdatabase"></a><a name="cdatabase"></a>CDatabase::CDatabase  
 `CDatabase` 개체를 생성합니다.  
  
```  
CDatabase();
```  
  
### <a name="remarks"></a>주의  
 호출 해야 개체를 생성 한 후 해당 `OpenEx` 또는 **열려** 멤버 함수를 지정된 된 데이터 원본에 대 한 연결을 설정 합니다.  
  
 포함 하는 편리한 방법을 찾을 수 있습니다는 `CDatabase` 문서 클래스에는 개체입니다.  
  
### <a name="example"></a>예제  
 사용 하 여 보여 주는이 예제 `CDatabase` 에 `CDocument`-클래스를 파생 합니다.  
  
 [!code-cpp[NVC_MFCDatabase #&9;](../../mfc/codesnippet/cpp/cdatabase-class_1.h)]  
  
 [!code-cpp[NVC_MFCDatabase #&10;](../../mfc/codesnippet/cpp/cdatabase-class_2.cpp)]  
  
##  <a name="a-nameclosea--cdatabaseclose"></a><a name="close"></a>CDatabase::Close  
 데이터 소스에서 연결을 끊을 하려는 경우이 멤버 함수를 호출 합니다.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>주의  
 관련 된 모든 레코드 집합을 닫아야는 `CDatabase` 이 멤버 함수를 호출 하기 전에 개체입니다. 때문에 **닫기** 소멸 시 키 지 않는 `CDatabase` 개체를 동일한 데이터 원본 또는 다른 데이터 원본에 새 연결을 열어 개체를 다시 사용할 수 있습니다.  
  
 모든 보류 중인 `AddNew` 또는 **편집** 데이터베이스를 사용 하 여 레코드 집합의 문이 취소 되 고 보류 중인 트랜잭션이 모두 롤백됩니다. 모든 레코드 집합에 종속 된 `CDatabase` 개체는 정의 되지 않은 상태로 남아 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase #&12;](../../mfc/codesnippet/cpp/cdatabase-class_3.cpp)]  
  
##  <a name="a-namecommittransa--cdatabasecommittrans"></a><a name="committrans"></a>CDatabase::CommitTrans  
 트랜잭션이 완료 될 때이 멤버 함수를 호출 합니다.  
  
```  
BOOL CommitTrans();
```  
  
### <a name="return-value"></a>반환 값  
 업데이트가 성공적으로 커밋된; 0이 아닌 그렇지 않으면 0입니다. 경우 **CommitTrans** 실패 하면 데이터 원본의 상태 정의 되지 않습니다. 상태를 확인 하기 위해 데이터를 확인 해야 합니다.  
  
### <a name="remarks"></a>주의  
 트랜잭션이 구성 된 일련의 호출을는 `AddNew`, **편집**, **삭제**, 및 **업데이트** 의 멤버 함수는 `CRecordset` 개체에 대 한 호출으로 시작 하는 [BeginTrans](#begintrans) 멤버 함수입니다. **CommitTrans** 트랜잭션을 커밋합니다. 기본적으로 업데이트 내용이 즉시 커밋됩니다. 호출 **BeginTrans** 될 때까지 지연 될 업데이트의 기여를 사용 하면 **CommitTrans** 호출 됩니다.  
  
 호출할 때까지 **CommitTrans** 트랜잭션을 종료를 호출 하면는 [롤백](#rollback) 멤버 함수를 트랜잭션을 중단 하 고 데이터 소스는 원래 상태로 둡니다. 새 트랜잭션을 시작 하려면 호출 **BeginTrans** 다시 합니다.  
  
 트랜잭션에 대 한 자세한 내용은 문서를 참조 하십시오. [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
### <a name="example"></a>예제  
  문서를 참조 하십시오 [트랜잭션: 트랜잭션이 수행 레코드 집합 (ODBC)에서](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)합니다.  
  
##  <a name="a-nameexecutesqla--cdatabaseexecutesql"></a><a name="executesql"></a>CDatabase::ExecuteSQL  
 SQL 명령 직접 실행 해야 할 때이 멤버 함수를 호출 합니다.  
  
```  
void ExecuteSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszSQL`  
 실행 하는 유효한 SQL 명령이 포함 된 null로 끝나는 문자열에 대 한 포인터입니다. 전달할 수는 [CString](../../atl-mfc-shared/reference/cstringt-class.md)합니다.  
  
### <a name="remarks"></a>주의  
 이 명령은 null로 끝나는 문자열을 만듭니다. `ExecuteSQL`데이터 레코드를 반환 하지 않습니다. 레코드에서 작동 하려면 recordset 개체를 대신 사용 합니다.  
  
 대부분의 데이터 원본에 대 한 명령 데이터 선택, 새 레코드 삽입, 레코드 및 레코드 편집에 대 한 명령을 지 원하는 레코드 집합 개체를 통해 발급 됩니다. 그러나 일부 ODBC 기능 직접 지원 됩니다 데이터베이스 클래스에서 사용 하 여 직접 SQL 호출 때때로 필요가 `ExecuteSQL`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase #&13;](../../mfc/codesnippet/cpp/cdatabase-class_4.cpp)]  
  
##  <a name="a-namegetbookmarkpersistencea--cdatabasegetbookmarkpersistence"></a><a name="getbookmarkpersistence"></a>CDatabase::GetBookmarkPersistence  
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
|`SQL_BP_DELETE`|행에 대 한 책갈피가 유효 기간이 **삭제** 해당 행에 대해 작업 합니다.|  
|`SQL_BP_DROP`|책갈피는 유효 기간이 **닫기** 작업 합니다.|  
|`SQL_BP_SCROLL`|책갈피는 후 유효한 **이동** 작업 합니다. 따라서 `CRecordset::CanBookmark`에서 반환되는 책갈피가 레코드 집합에서 지원되는지를 쉽게 파악할 수 있습니다.|  
|`SQL_BP_TRANSACTION`|트랜잭션이 커밋되거나 롤백된 후에 책갈피가 유효합니다.|  
|`SQL_BP_UPDATE`|행에 대 한 책갈피가 유효 기간이 **업데이트** 해당 행에 대해 작업 합니다.|  
|`SQL_BP_OTHER_HSTMT`|레코드 집합 개체 하나와 연결된 책갈피가 두 번째 레코드 집합에서도 유효합니다.|  
  
 이 반환 값에 대 한 자세한 내용은 ODBC API 함수를 참조 하십시오. **SQLGetInfo** 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 책갈피에 대 한 자세한 내용은 문서를 참조 하십시오. [레코드 집합: 책갈피와 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)합니다.  
  
##  <a name="a-namegetconnecta--cdatabasegetconnect"></a><a name="getconnect"></a>CDatabase::GetConnect  
 이 멤버 함수를 호출 하는 동안 사용 되는 연결 문자열을 검색 호출 `OpenEx` 또는 `Open` 연결는 `CDatabase` 데이터 원본에 개체입니다.  
  
```  
const CString GetConnect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `const` [CString](../../atl-mfc-shared/reference/cstringt-class.md) 경우 연결 문자열에 포함 된 `OpenEx` 또는 `Open` 호출 하 고, 그렇지 않으면 되었습니다 빈 문자열입니다.  
  
### <a name="remarks"></a>주의  
 참조 [CDatabase::Open](#open) 에 대 한 설명은 패키지를 만드는 방법을 연결 문자열입니다.  
  
##  <a name="a-namegetcursorcommitbehaviora--cdatabasegetcursorcommitbehavior"></a><a name="getcursorcommitbehavior"></a>CDatabase::GetCursorCommitBehavior  
 확인 하려면이 함수를 호출 방법을 [CommitTrans](#committrans) 작업 커서 열기 recordset 개체에 영향을 줍니다.  
  
```  
int GetCursorCommitBehavior() const;  
```  
  
### <a name="return-value"></a>반환 값  
 열린 레코드 집합 개체에 대 한 트랜잭션의 효과 나타내는 값입니다. 자세한 내용은 설명을 참조하세요.  
  
### <a name="remarks"></a>주의  
 다음 표에서 가능한 반환 값에 대 한 `GetCursorCommitBehavior` 열려 레코드 집합에 해당 효과입니다.  
  
|반환 값|CRecordset 개체에 미치는 영향|  
|------------------|----------------------------------|  
|`SQL_CB_CLOSE`|호출 `CRecordset::Requery` 바로 다음에 오는 트랜잭션 커밋입니다.|  
|`SQL_CB_DELETE`|호출 `CRecordset::Close` 바로 다음에 오는 트랜잭션 커밋입니다.|  
|`SQL_CB_PRESERVE`|일반적으로 계속 `CRecordset` 작업 합니다.|  
  
 이 반환 값에 대 한 자세한 내용은 ODBC API 함수를 참조 하십시오. **SQLGetInfo** 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 트랜잭션에 대 한 자세한 내용은 문서를 참조 하십시오. [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
##  <a name="a-namegetcursorrollbackbehaviora--cdatabasegetcursorrollbackbehavior"></a><a name="getcursorrollbackbehavior"></a>CDatabase::GetCursorRollbackBehavior  
 확인 하려면이 함수를 호출 방법을 [롤백](#rollback) 작업 커서 열기 recordset 개체에 영향을 줍니다.  
  
```  
int GetCursorRollbackBehavior() const;  
```  
  
### <a name="return-value"></a>반환 값  
 열린 레코드 집합 개체에 대 한 트랜잭션의 효과 나타내는 값입니다. 자세한 내용은 설명을 참조하세요.  
  
### <a name="remarks"></a>주의  
 다음 표에서 가능한 반환 값에 대 한 `GetCursorRollbackBehavior` 열려 레코드 집합에 해당 효과입니다.  
  
|반환 값|CRecordset 개체에 미치는 영향|  
|------------------|----------------------------------|  
|`SQL_CB_CLOSE`|호출 `CRecordset::Requery` 바로 다음에 오는 트랜잭션 롤백.|  
|`SQL_CB_DELETE`|호출 `CRecordset::Close` 바로 다음에 오는 트랜잭션 롤백.|  
|`SQL_CB_PRESERVE`|일반적으로 계속 `CRecordset` 작업 합니다.|  
  
 이 반환 값에 대 한 자세한 내용은 ODBC API 함수를 참조 하십시오. **SQLGetInfo** 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 트랜잭션에 대 한 자세한 내용은 문서를 참조 하십시오. [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
##  <a name="a-namegetdatabasenamea--cdatabasegetdatabasename"></a><a name="getdatabasename"></a>CDatabase::GetDatabaseName  
 (제공 하는 데이터 원본 정의 "database" 라는 명명된 된 개체)는 현재 연결 된 데이터베이스의 이름을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetDatabaseName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 성공 하 고, 그렇지 않으면 경우 데이터베이스 이름이 포함 된, 비어 있는 `CString`합니다.  
  
### <a name="remarks"></a>주의  
 에 지정 된 데이터 원본 이름 (DSN)으로 달라도 `OpenEx` 또는 **열려** 를 호출 합니다. 어떤 `GetDatabaseName` 반환 ODBC에 따라 달라 집니다. 일반적으로 데이터베이스는 테이블의 컬렉션입니다. 이 엔터티에 이름이 면 `GetDatabaseName` 반환 합니다.  
  
 예를 들어 제목에이 이름을 표시 하려면 할 수 있습니다. ODBC에서 이름을 검색 하는 동안 오류가 발생 하는 경우 `GetDatabaseName` 빈 반환 **Cstring**합니다.  
  
##  <a name="a-nameisopena--cdatabaseisopen"></a><a name="isopen"></a>CDatabase::IsOpen  
 확인 하려면이 함수를 호출 여부는 `CDatabase` 개체는 현재 데이터 원본에 연결 합니다.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 값은 `CDatabase` 개체가 현재 연결 되어 있습니다; 그렇지 않으면 0입니다.  
  
##  <a name="a-namemhdbca--cdatabasemhdbc"></a><a name="m_hdbc"></a>CDatabase::m_hdbc  
 ODBC 데이터 원본 연결에 대 한 공용 핸들 € 포함 "는"연결 핸들입니다."  
  
### <a name="remarks"></a>주의  
 일반적으로이 멤버 변수를 직접 액세스 하지 않아도 해야 합니다. 호출 하면 프레임 워크는 핸들을 할당 하는 대신, `OpenEx` 또는 **열려**합니다. 프레임 워크를 호출 하면 핸들 할당 취소는 **삭제** 연산자에는 `CDatabase` 개체입니다. 이때는 **닫기** 멤버 함수를 핸들 할당 해제 하지 않습니다.  
  
 그러나 경우에 따라 직접 핸들을 사용 하 여 할 수 있습니다. 예를 들어, 클래스를 통해가 대신 직접 ODBC API 함수를 호출 하는 경우 `CDatabase`를 매개 변수로 전달 하 여 연결 핸들을 할 수 있습니다. 아래 코드 예제를 참조 하십시오.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase #&15;](../../mfc/codesnippet/cpp/cdatabase-class_5.cpp)]  
  
##  <a name="a-nameonsetoptionsa--cdatabaseonsetoptions"></a><a name="onsetoptions"></a>CDatabase::OnSetOptions  
 프레임 워크와 SQL 문을 직접 실행 하는 경우이 멤버 함수 호출의 `ExecuteSQL` 멤버 함수입니다.  
  
```  
virtual void OnSetOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>매개 변수  
 `hstmt`  
 옵션은 설정 되는 ODBC 문 핸들입니다.  
  
### <a name="remarks"></a>주의  
 `CRecordset::OnSetOptions`또한이 멤버 함수를 호출합니다.  
  
 `OnSetOptions`로그인 제한 시간 값을 설정합니다. 에 대 한 이전 호출 된 경우는 `SetQueryTimeout` 및 멤버 함수 `OnSetOptions` ; 현재 값을 반영 합니다. 그렇지 않은 경우 기본값을 설정 합니다.  
  
> [!NOTE]
>  MFC 4.2 이전 `OnSetOptions` 어느 snychronous 또는 비동기 처리 모드를 설정할 수도 있습니다. MFC 4.2 부터는 모든 작업은 동기입니다. 비동기 작업을 수행 하려면 ODBC API 함수를 직접 호출 해야 **SQLSetPos**합니다.  
  
 재정의할 필요가 없습니다 `OnSetOptions` 시간 제한 값을 변경 합니다. 대신, 쿼리 제한 시간 값을 사용자 지정 하려면 호출 `SetQueryTimeout` ; 레코드 집합을 만들기 전에 `OnSetOptions` 새 값이 사용 됩니다. 설정 된 모든 레코드 집합 또는 직접 SQL 호출에 대 한 후속 작업에 적용 됩니다.  
  
 재정의 `OnSetOptions` 추가 옵션을 설정 하려는 경우. 재정의 시 기본 클래스를 호출 해야 `OnSetOptions` 전에 또는 ODBC API 함수를 호출 하 고 나면 **SQLSetStmtOption**합니다. 프레임 워크의 기본 구현에서 설명 하는 메서드를 따라 `OnSetOptions`합니다.  
  
##  <a name="a-nameopena--cdatabaseopen"></a><a name="open"></a>CDatabase::Open  
 이 멤버 함수는 새로 생성 된 초기화를 호출 `CDatabase` 개체입니다.  
  
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
 데이터 원본 이름을 € 지정 "odbc ODBC 관리자 프로그램을 통해 등록 된 이름입니다. DSN 값에 지정 된 경우 `lpszConnect` (형태로 "DSN =\<데이터 소스 >")를 다시 지정 하지 해야 `lpszDSN`합니다. 이 경우 `lpszDSN` 해야 **NULL**합니다. 그렇지 않으면 전달할 수 있습니다 **NULL** 사용자는 사용자가 데이터 소스를 선택할 수 있는 데이터 원본 대화 상자를 표시 하려는 경우. 자세한 내용은 설명 부분을 참조 합니다.  
  
 `bExclusive`  
 클래스 라이브러리의이 버전에서는 지원 되지 않습니다. 이 매개 변수가 어설션이 실패 하는 현재 **TRUE**합니다. 공유 (하지 제외)에 항상 데이터 소스 열릴 수 있습니다.  
  
 `bReadOnly`  
 **True 이면** 연결을 읽기 전용 및 데이터 원본에 대 한 업데이트를 하지 못하도록 하려는 경우. 종속 된 모든 레코드는이 특성을 상속합니다. 기본값은 **FALSE**합니다.  
  
 `lpszConnect`  
 연결 문자열을 지정합니다. 연결 문자열 정보를 데이터 원본 이름, 데이터 원본, 사용자 인증 문자열 (암호, 데이터 원본 하나 필요로 하는 경우) 및 기타 정보에 유효한 사용자 ID를 포함 하 여 연결 합니다. 전체 연결 문자열 앞에 있어야 문자열 "ODBC;" (대문자 또는 소문자). "ODBC"; 문자열이 ODBC 데이터 원본에 대 한 연결 임을 나타내기 위해 사용 됩니다 이 상향 호환성에 대 한 경우 클래스 라이브러리의 이후 버전에서 비 ODBC 데이터 소스를 지원할 수 있습니다.  
  
 `bUseCursorLib`  
 **True 이면** ODBC 커서 라이브러리 DLL을 로드 하려는 경우. 커서 라이브러리 (드라이버 지원) 하는 경우 다이너셋의 사용을 효과적으로 방지할 기본 ODBC 드라이버의 일부 기능을 마스크 합니다. 커서 라이브러리가 로드 하는 경우에 지원 되는 유일한 커서는 정적 스냅숏 및 정방향 전용 커서입니다. 기본값은 **TRUE**합니다. 레코드 집합 개체를 직접 만들려는 경우 `CRecordset` 에서 파생 하지 않는 하지 커서 라이브러리를 로드 해야 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공적으로 연결 되 고, 0이 아닌 그렇지 않으면 사용자가 선택 하는 경우에 0에는 더 많은 연결 정보를 묻는 대화 상자가 나타나면 취소 합니다. 다른 모든 경우에는 프레임 워크는 예외가 throw 됩니다.  
  
### <a name="remarks"></a>주의  
 레코드 집합 개체를 생성 하는 데 사용할 수 데이터베이스 개체를 초기화 합니다.  
  
> [!NOTE]
>  호출 된 [OpenEx](#openex) 멤버 함수는 데이터 원본에 연결 하 고 데이터베이스 개체를 초기화 하는 것이 좋습니다.  
  
 경우에 매개 변수 여 **열려** 호출에 연결을 만드는 데 충분 한 정보가 없는, ODBC 드라이버는 사용자 로부터 필요한 정보를 얻으려면 대화 상자를 엽니다. 호출 하는 경우 **열려**, 연결 문자열을 `lpszConnect`, 개인적으로 저장 됩니다는 `CDatabase` 개체 및를 호출 하 여 사용할 수는 [GetConnect](#getconnect) 멤버 함수입니다.  
  
 호출 하기 전에 고유한 대화 상자를 열 수 있습니다 **엽니다** 에서 암호와 같은 사용자 정보를 가져오는 다음 해당 정보를 추가를 전달 하는 연결 문자열 **열고**합니다. 응용 프로그램이 호출의 시간을 다음 재사용할 수 있도록 전달 하는 연결 문자열을 저장 하는 것이 좋습니다 또는 **열려** 에 `CDatabase` 개체입니다.  
  
 여러 수준의 로그인 권한 부여에 대 한 연결 문자열을 사용할 수도 있습니다 (다른 작업에 대 한 각 `CDatabase` 개체) 또는 다른 데이터 소스 관련 정보를 전달 합니다. 연결 문자열에 대 한 자세한 내용은에서 5 장 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 것 같습니다 시간 제한 초과로 연결 시도 대 한 경우 예를 들어 DBMS 호스트를 사용할 수 없습니다. 연결 시도 실패 하는 경우 **열려** throw 한 `CDBException`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase #&14;](../../mfc/codesnippet/cpp/cdatabase-class_6.cpp)]  
  
##  <a name="a-nameopenexa--cdatabaseopenex"></a><a name="openex"></a>CDatabase::OpenEx  
 이 멤버 함수는 새로 생성 된 초기화를 호출 `CDatabase` 개체입니다.  
  
```  
virtual BOOL OpenEx(
    LPCTSTR lpszConnectString,  
    DWORD dwOptions = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszConnectString`  
 ODBC 연결 문자열을 지정합니다. 데이터 원본 이름 뿐만 아니라 사용자 ID와 암호 등의 다른 선택적 정보가 포함 됩니다. 예를 들어 "DSN = SQLServer_Source; UID = SA; PWD = a b c&123; "은 가능한 연결 문자열입니다. 전달 하는 경우 사용자에 게 유의 **NULL** 에 대 한 `lpszConnectString`, 데이터 원본 대화 상자에는 사용자 데이터 원본을 선택에 게 표시 됩니다.  
  
 `dwOptions`  
 다음 값의 조합을 지정 하는 비트 마스크입니다. 기본값은 0으로 데이터베이스를 열 수는 의미와 공유 쓰기 액세스 하는 ODBC 커서 라이브러리 DLL 로드 되지 것입니다, 그리고 및 ODBC 연결 대화 상자는 연결을 만드는 데 충분 한 정보가 없는 경우에 표시 됩니다.  
  
- **CDatabase::openExclusive** 클래스 라이브러리의이 버전에서 지원 되지 않습니다. 공유 (하지 제외)에 항상 데이터 소스 열릴 수 있습니다. 현재이 옵션을 지정 하는 어설션이 실패 합니다.  
  
- **CDatabase::openReadOnly** 읽기 전용으로 데이터 소스를 엽니다.  
  
- **CDatabase::useCursorLib** ODBC 커서 라이브러리 DLL를 로드 합니다. 커서 라이브러리 (드라이버 지원) 하는 경우 다이너셋의 사용을 효과적으로 방지할 기본 ODBC 드라이버의 일부 기능을 마스크 합니다. 커서 라이브러리가 로드 하는 경우에 지원 되는 유일한 커서는 정적 스냅숏 및 정방향 전용 커서입니다. 레코드 집합 개체를 직접 만들려는 경우 `CRecordset` 에서 파생 하지 않는 하지 커서 라이브러리를 로드 해야 합니다.  
  
- **CDatabase::noOdbcDialog** 충분 한 연결 정보를 제공 하는 여부에 관계 없이 ODBC 연결 대화 상자를 표시 하지 않습니다.  
  
- **CDatabase::forceOdbcDialog** 항상 ODBC 연결 대화 상자를 표시 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공적으로 연결 되 고, 0이 아닌 그렇지 않으면 사용자가 선택 하는 경우에 0에는 더 많은 연결 정보를 묻는 대화 상자가 나타나면 취소 합니다. 다른 모든 경우에는 프레임 워크는 예외가 throw 됩니다.  
  
### <a name="remarks"></a>주의  
 레코드 집합 개체를 생성 하는 데 사용할 수 데이터베이스 개체를 초기화 합니다.  
  
 하는 경우는 `lpszConnectString` 매개 변수에서 프로그램 `OpenEx` 호출에 연결을 만드는 데 충분 한 정보가 없는, ODBC 드라이버를 설정 하지 않은 경우 사용자에 게 필요한 정보를 얻으려면 대화 상자를 엽니다 **CDatabase::noOdbcDialog** 또는 **CDatabase::forceOdbcDialog** 에 `dwOptions` 매개 변수입니다. 호출 하는 경우 `OpenEx`, 연결 문자열을 `lpszConnectString`, 개인적으로 저장 됩니다는 `CDatabase` 개체 및를 호출 하 여 사용할 수는 [GetConnect](#getconnect) 멤버 함수입니다.  
  
 호출 하기 전에 고유한 대화 상자를 열 수를 `OpenEx` 암호와 같은 사용자 로부터 정보를 가져와서 다음을 전달 하면 연결 문자열에 해당 정보를 추가 하려면 `OpenEx`합니다. 응용 프로그램이 호출의 시간을 다음 재사용할 수 있도록 전달 하는 연결 문자열을 저장 하는 것이 좋습니다 또는 `OpenEx` 에 `CDatabase` 개체입니다.  
  
 여러 수준의 로그인 권한 부여에 대 한 연결 문자열을 사용할 수도 있습니다 (다른 작업에 대 한 각 `CDatabase` 개체) 또는 다른 데이터 소스 관련 정보를 전달 합니다. 연결 문자열에 대 한 자세한 내용은의 6 장 참조는 *ODBC 프로그래머 참조*합니다.  
  
 것 같습니다 시간 제한 초과로 연결 시도 대 한 경우 예를 들어 DBMS 호스트를 사용할 수 없습니다. 연결 시도 실패 하는 경우 `OpenEx` throw 한 `CDBException`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase #&11;](../../mfc/codesnippet/cpp/cdatabase-class_7.cpp)]  
  
##  <a name="a-namerollbacka--cdatabaserollback"></a><a name="rollback"></a>CDatabase::Rollback  
 트랜잭션 중의 변경 내용을 취소 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL Rollback();
```  
  
### <a name="return-value"></a>반환 값  
 트랜잭션이 성공적으로 취소; 0이 아닌 그렇지 않으면 0입니다. 하는 경우는 **롤백** 호출에 실패 하면 데이터 원본 및 트랜잭션 상태 정의 되지 않습니다. 경우 **롤백** 0을 반환 상태를 확인 하려면 데이터 소스를 확인 해야 합니다.  
  
### <a name="remarks"></a>주의  
 모든 `CRecordset``AddNew`, **편집**, **삭제**, 및 **업데이트** 마지막 이후 실행 호출 [BeginTrans](#begintrans) 해당 호출의 시간에 존재 했던 상태로 롤백됩니다.  
  
 호출한 후 **롤백**, 트랜잭션이 끝났습니다 및 호출 해야 **BeginTrans** 다른 트랜잭션에 대 한 다시 합니다. 호출 하기 전에 현재 레코드가 **BeginTrans** 후 다시 현재 레코드가 됩니다 **롤백**합니다.  
  
 롤백 후, 레코드 롤백 이전에 유지 됩니다. 롤백 후 데이터 원본 및 레코드 집합의 상태에 대 한 자세한 문서를 참조 하십시오. [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
### <a name="example"></a>예제  
  문서를 참조 하십시오 [트랜잭션: 트랜잭션이 수행 레코드 집합 (ODBC)에서](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)합니다.  
  
##  <a name="a-namesetlogintimeouta--cdatabasesetlogintimeout"></a><a name="setlogintimeout"></a>CDatabase::SetLoginTimeout  
 이 멤버 함수 â € 호출 "를 호출 하기 전에 `OpenEx` 또는 **열려** â €" 시도한 데이터 발생 하기 전에 허용 되는 시간 (초) 기본값을 재정의 하려면 원본 연결 시간이 초과 합니다.  
  
```  
void SetLoginTimeout(DWORD dwSeconds);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwSeconds`  
 연결 시도 하기 전까지 허용 시간 (초)의 시간이 초과 합니다.  
  
### <a name="remarks"></a>주의  
 DBMS를 사용할 수 없는 예를 들어 하는 경우 연결 시도가 시간 초과 수 있습니다. 호출 **SetLoginTimeout** 는 초기화 되지 않은 생성 한 후 `CDatabase` 개체 하지만 호출 하기 전에 `OpenEx` 또는 **열려**합니다.  
  
 로그인 시간 제한의 기본값은 15 초입니다. 일부 데이터 원본 로그인 제한 시간 값을 지정 하는 기능을 지원 합니다. 데이터 원본에서 시간 초과 지원 하지 않습니다, 추적 출력을 만들지만 되지 않는 예외 얻을 수 있습니다. 값이 0 이면 "무한 합니다."  
  
##  <a name="a-namesetquerytimeouta--cdatabasesetquerytimeout"></a><a name="setquerytimeout"></a>CDatabase::SetQueryTimeout  
 후속 작업에 연결 된 데이터 원본 시간 초과 하기 전까지 허용 시간 (초) 기본값을 재정의 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetQueryTimeout(DWORD dwSeconds);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwSeconds`  
 쿼리 시도 하기 전까지 허용 시간 (초)의 시간이 초과 합니다.  
  
### <a name="remarks"></a>주의  
 네트워크 액세스 문제, 과도 한 쿼리 처리 시간 및 등으로 인해 작업 시간이 초과 될 수 있습니다. 호출 `SetQueryTimeout` 레코드 집합을 열기 전에 또는 레코드 집합의을 호출 하기 전에 `AddNew`, **업데이트** 또는 **삭제** 쿼리 제한 시간 값을 변경 하려는 경우 멤버 함수입니다. 설정은 모든 후속 **열려**, `AddNew`, **업데이트**, 및 **삭제** 와 연결 된 모든 레코드 집합에 대 한 호출 `CDatabase` 개체입니다. 연 후 레코드 집합에 대 한 쿼리 제한 시간 값을 변경 해도 레코드 집합에 대 한 값이 변경 되지 않습니다. 예를 들어, 후속 **이동** 작업 새 값을 사용 하지 마십시오.  
  
 쿼리 시간 제한의 기본값은 15 초입니다. 일부 데이터 원본 쿼리 제한 시간 값을 설정 하는 기능을 지원 합니다. 쿼리 제한 시간 값이 0 설정 하는 경우 시간 제한 없이 발생 합니다. 데이터 소스와의 통신에 응답 하지 않을 수 있습니다. 이 문제는 개발 하는 동안 유용할 수 있습니다. 데이터 원본에서 시간 초과 지원 하지 않습니다, 추적 출력을 만들지만 되지 않는 예외 얻을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRecordset 클래스](../../mfc/reference/crecordset-class.md)

