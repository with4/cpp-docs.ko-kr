---
title: CRecordset 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRecordset
- AFXDB/CRecordset
- AFXDB/CRecordset::CRecordset
- AFXDB/CRecordset::AddNew
- AFXDB/CRecordset::CanAppend
- AFXDB/CRecordset::CanBookmark
- AFXDB/CRecordset::Cancel
- AFXDB/CRecordset::CancelUpdate
- AFXDB/CRecordset::CanRestart
- AFXDB/CRecordset::CanScroll
- AFXDB/CRecordset::CanTransact
- AFXDB/CRecordset::CanUpdate
- AFXDB/CRecordset::CheckRowsetError
- AFXDB/CRecordset::Close
- AFXDB/CRecordset::Delete
- AFXDB/CRecordset::DoBulkFieldExchange
- AFXDB/CRecordset::DoFieldExchange
- AFXDB/CRecordset::Edit
- AFXDB/CRecordset::FlushResultSet
- AFXDB/CRecordset::GetBookmark
- AFXDB/CRecordset::GetDefaultConnect
- AFXDB/CRecordset::GetDefaultSQL
- AFXDB/CRecordset::GetFieldValue
- AFXDB/CRecordset::GetODBCFieldCount
- AFXDB/CRecordset::GetODBCFieldInfo
- AFXDB/CRecordset::GetRecordCount
- AFXDB/CRecordset::GetRowsetSize
- AFXDB/CRecordset::GetRowsFetched
- AFXDB/CRecordset::GetRowStatus
- AFXDB/CRecordset::GetSQL
- AFXDB/CRecordset::GetStatus
- AFXDB/CRecordset::GetTableName
- AFXDB/CRecordset::IsBOF
- AFXDB/CRecordset::IsDeleted
- AFXDB/CRecordset::IsEOF
- AFXDB/CRecordset::IsFieldDirty
- AFXDB/CRecordset::IsFieldNull
- AFXDB/CRecordset::IsFieldNullable
- AFXDB/CRecordset::IsOpen
- AFXDB/CRecordset::Move
- AFXDB/CRecordset::MoveFirst
- AFXDB/CRecordset::MoveLast
- AFXDB/CRecordset::MoveNext
- AFXDB/CRecordset::MovePrev
- AFXDB/CRecordset::OnSetOptions
- AFXDB/CRecordset::OnSetUpdateOptions
- AFXDB/CRecordset::Open
- AFXDB/CRecordset::RefreshRowset
- AFXDB/CRecordset::Requery
- AFXDB/CRecordset::SetAbsolutePosition
- AFXDB/CRecordset::SetBookmark
- AFXDB/CRecordset::SetFieldDirty
- AFXDB/CRecordset::SetFieldNull
- AFXDB/CRecordset::SetLockingMode
- AFXDB/CRecordset::SetParamNull
- AFXDB/CRecordset::SetRowsetCursorPosition
- AFXDB/CRecordset::SetRowsetSize
- AFXDB/CRecordset::Update
- AFXDB/CRecordset::m_hstmt
- AFXDB/CRecordset::m_nFields
- AFXDB/CRecordset::m_nParams
- AFXDB/CRecordset::m_pDatabase
- AFXDB/CRecordset::m_strFilter
- AFXDB/CRecordset::m_strSort
dev_langs:
- C++
helpviewer_keywords:
- CRecordset [MFC], CRecordset
- CRecordset [MFC], AddNew
- CRecordset [MFC], CanAppend
- CRecordset [MFC], CanBookmark
- CRecordset [MFC], Cancel
- CRecordset [MFC], CancelUpdate
- CRecordset [MFC], CanRestart
- CRecordset [MFC], CanScroll
- CRecordset [MFC], CanTransact
- CRecordset [MFC], CanUpdate
- CRecordset [MFC], CheckRowsetError
- CRecordset [MFC], Close
- CRecordset [MFC], Delete
- CRecordset [MFC], DoBulkFieldExchange
- CRecordset [MFC], DoFieldExchange
- CRecordset [MFC], Edit
- CRecordset [MFC], FlushResultSet
- CRecordset [MFC], GetBookmark
- CRecordset [MFC], GetDefaultConnect
- CRecordset [MFC], GetDefaultSQL
- CRecordset [MFC], GetFieldValue
- CRecordset [MFC], GetODBCFieldCount
- CRecordset [MFC], GetODBCFieldInfo
- CRecordset [MFC], GetRecordCount
- CRecordset [MFC], GetRowsetSize
- CRecordset [MFC], GetRowsFetched
- CRecordset [MFC], GetRowStatus
- CRecordset [MFC], GetSQL
- CRecordset [MFC], GetStatus
- CRecordset [MFC], GetTableName
- CRecordset [MFC], IsBOF
- CRecordset [MFC], IsDeleted
- CRecordset [MFC], IsEOF
- CRecordset [MFC], IsFieldDirty
- CRecordset [MFC], IsFieldNull
- CRecordset [MFC], IsFieldNullable
- CRecordset [MFC], IsOpen
- CRecordset [MFC], Move
- CRecordset [MFC], MoveFirst
- CRecordset [MFC], MoveLast
- CRecordset [MFC], MoveNext
- CRecordset [MFC], MovePrev
- CRecordset [MFC], OnSetOptions
- CRecordset [MFC], OnSetUpdateOptions
- CRecordset [MFC], Open
- CRecordset [MFC], RefreshRowset
- CRecordset [MFC], Requery
- CRecordset [MFC], SetAbsolutePosition
- CRecordset [MFC], SetBookmark
- CRecordset [MFC], SetFieldDirty
- CRecordset [MFC], SetFieldNull
- CRecordset [MFC], SetLockingMode
- CRecordset [MFC], SetParamNull
- CRecordset [MFC], SetRowsetCursorPosition
- CRecordset [MFC], SetRowsetSize
- CRecordset [MFC], Update
- CRecordset [MFC], m_hstmt
- CRecordset [MFC], m_nFields
- CRecordset [MFC], m_nParams
- CRecordset [MFC], m_pDatabase
- CRecordset [MFC], m_strFilter
- CRecordset [MFC], m_strSort
ms.assetid: dd89a21d-ef39-4aab-891b-1e373d67c855
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 683f1d612a57e4f6e2d8661af17faa73f725d3d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378737"
---
# <a name="crecordset-class"></a>CRecordset 클래스
데이터 소스에서 선택한 레코드 집합을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CRecordset : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CRecordset::CRecordset](#crecordset)|`CRecordset` 개체를 생성합니다. 파생 된 클래스는이 호출 하는 생성자를 제공 해야 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRecordset::AddNew](#addnew)|새 레코드를 추가 하기 위한 준비 합니다. 호출 `Update` 추가 완료 합니다.|  
|[CRecordset::CanAppend](#canappend)|새 레코드를 통해 레코드 집합에 추가할 수 있으면 0이 아닌 반환는 `AddNew` 멤버 함수입니다.|  
|[CRecordset::CanBookmark](#canbookmark)|레코드 집합에서 책갈피를 지 원하는 경우 0이 아닌 값을 반환 합니다.|  
|[CRecordset::Cancel](#cancel)|비동기 작업 또는 두 번째 스레드가 프로세스를 취소합니다.|  
|[CRecordset::CancelUpdate](#cancelupdate)|취소로 인해 모든 보류 중인 업데이트는 `AddNew` 또는 `Edit` 작업 합니다.|  
|[CRecordset::CanRestart](#canrestart)|0이 아닌 경우 반환 `Requery` 레코드 집합의 쿼리를 다시 실행 하기 위해 호출할 수 있습니다.|  
|[CRecordset::CanScroll](#canscroll)|레코드를 스크롤할 수 있으면 0이 아닌 값을 반환 합니다.|  
|[CRecordset::CanTransact](#cantransact)|데이터 소스에서 트랜잭션을 지원 하면 0이 아닌 값을 반환 합니다.|  
|[CRecordset::CanUpdate](#canupdate)|레코드 집합을 업데이트할 수 있으면 0이 아닌 반환 (있습니다 수 추가, 업데이트 또는 삭제 레코드).|  
|[CRecordset::CheckRowsetError](#checkrowseterror)|레코드를 인출 하는 동안 발생 한 오류를 처리 하기 위해 호출 합니다.|  
|[CRecordset::Close](#close)|레코드 집합을 ODBC 닫고 **HSTMT** 연관 됩니다.|  
|[CRecordset::Delete](#delete)|레코드 집합에서 현재 레코드를 삭제합니다. 삭제 후 명시적으로 다른 레코드로 스크롤하여 해야 합니다.|  
|[CRecordset::DoBulkFieldExchange](#dobulkfieldexchange)|대량 행의 데이터 원본에서 레코드 집합으로 데이터를 교환 하기 위해 호출 합니다. 구현 대량 레코드 필드 교환 (대량 RFX).|  
|[CRecordset::DoFieldExchange](#dofieldexchange)|레코드 집합의 필드 데이터 멤버와 데이터 원본에 있는 해당 레코드 간에 (양방향)으로 데이터를 교환 하기 위해 호출 합니다. 구현 레코드 필드 교환 (RFX).|  
|[CRecordset::Edit](#edit)|현재 레코드에 변경 내용에 대해 준비합니다. 호출 `Update` 편집을 완료 합니다.|  
|[CRecordset::FlushResultSet](#flushresultset)|미리 정의 된 쿼리를 사용 하는 경우 검색할 설정 되는 다른 결과 0이 아닌 반환 합니다.|  
|[CRecordset::GetBookmark](#getbookmark)|매개 변수 개체에 레코드의 책갈피 값을 할당합니다.|  
|[CRecordset::GetDefaultConnect](#getdefaultconnect)|기본 연결 문자열을 가져오기 위해 호출 됩니다.|  
|[CRecordset::GetDefaultSQL](#getdefaultsql)|기본 SQL 문자열 실행을 가져오기 위해 호출 됩니다.|  
|[CRecordset::GetFieldValue](#getfieldvalue)|레코드 집합에서 필드의 값을 반환합니다.|  
|[CRecordset::GetODBCFieldCount](#getodbcfieldcount)|레코드 집합의 필드 수를 반환합니다.|  
|[CRecordset::GetODBCFieldInfo](#getodbcfieldinfo)|레코드 집합에서 특정 유형의 필드에 대 한 정보를 반환합니다.|  
|[CRecordset::GetRecordCount](#getrecordcount)|레코드 집합의 레코드 수를 반환합니다.|  
|[CRecordset::GetRowsetSize](#getrowsetsize)|단일 인출 하는 동안 검색할 레코드 수를 반환 합니다.|  
|[CRecordset::GetRowsFetched](#getrowsfetched)|행을 인출 하는 동안 검색의 실제 수를 반환 합니다.|  
|[CRecordset::GetRowStatus](#getrowstatus)|인출 후 행의 상태를 반환합니다.|  
|[CRecordset::GetSQL](#getsql)|레코드 집합에 대 한 레코드를 선택 하는 데 SQL 문자열을 가져옵니다.|  
|[CRecordset::GetStatus](#getstatus)|레코드 집합의 상태를 가져옵니다: 현재 레코드와 레코드의 최종 개수에 가져온 여부의 인덱스입니다.|  
|[CRecordset::GetTableName](#gettablename)|레코드 집합의 기반이 되는 테이블의 이름을 가져옵니다.|  
|[CRecordset::IsBOF](#isbof)|레코드 집합의 첫 번째 레코드 바로 앞 배치 된 경우 0이 아닌 값을 반환 합니다. 현재 기록이 없습니다.|  
|[CRecordset::IsDeleted](#isdeleted)|레코드 집합 삭제 된 레코드에 배치 되는 경우 0이 아닌 값을 반환 합니다.|  
|[CRecordset::IsEOF](#iseof)|레코드 집합 마지막 레코드 뒤 배치 된 경우 0이 아닌 값을 반환 합니다. 현재 기록이 없습니다.|  
|[CRecordset::IsFieldDirty](#isfielddirty)|현재 레코드에 지정된 된 필드 정보가 변경 된 경우 0이 아닌 값을 반환 합니다.|  
|[CRecordset::IsFieldNull](#isfieldnull)|현재 레코드에 지정된 된 필드를 null 이면 0이 아닌 값을 반환 합니다 (값이 없는).|  
|[CRecordset::IsFieldNullable](#isfieldnullable)|현재 레코드에 지정된 된 필드 (예: 값 없음)을 null로 설정할 수 있는 경우 0이 아닌 값을 반환 합니다.|  
|[CRecordset::IsOpen](#isopen)|0이 아닌 경우 반환 `Open` 가 이전에 호출 되었습니다.|  
|[CRecordset::Move](#move)|어느 방향으로든에서 현재 레코드에서 지정된 된 수의 레코드를 레코드 집합을 배치합니다.|  
|[CRecordset::MoveFirst](#movefirst)|레코드 집합의 첫 번째 레코드를 현재 레코드를 배치합니다. 에 대 한 테스트 `IsBOF` 첫 번째입니다.|  
|[CRecordset::MoveLast](#movelast)|마지막 행 집합 또는 마지막 레코드에서 현재 레코드를 배치합니다. 에 대 한 테스트 `IsEOF` 첫 번째입니다.|  
|[CRecordset::MoveNext](#movenext)|다음 레코드에 또는 다음 행 집합에서 현재 레코드를 배치합니다. 에 대 한 테스트 `IsEOF` 첫 번째입니다.|  
|[CRecordset::MovePrev](#moveprev)|이전 레코드 또는 이전 행 집합에서 현재 레코드를 배치합니다. 에 대 한 테스트 `IsBOF` 첫 번째입니다.|  
|[CRecordset::OnSetOptions](#onsetoptions)|(선택에 사용 됨) 하는 옵션을 설정 하려면 지정한 ODBC 문에 대 한 호출 됩니다.|  
|[CRecordset::OnSetUpdateOptions](#onsetupdateoptions)|지정 된 ODBC 문에 대 한 옵션 (업데이트에 사용 됨)를 설정 하기 위해 호출 합니다.|  
|[Crecordset:: Open](#open)|테이블을 검색 하거나 레코드 집합을 나타내는 쿼리를 수행 하 여 레코드 집합을 엽니다.|  
|[CRecordset::RefreshRowset](#refreshrowset)|데이터 및 지정한 행의 상태를 새로 고칩니다.|  
|[>crecordset:: Requery](#requery)|레코드 집합의 쿼리를 선택된 된 레코드를 새로 고치려면 다시 실행 합니다.|  
|[CRecordset::SetAbsolutePosition](#setabsoluteposition)|지정 된 레코드 번호에 해당 하는 레코드를 레코드 집합을 배치 합니다.|  
|[CRecordset::SetBookmark](#setbookmark)|책갈피 지정 된 레코드를 레코드 집합을 배치 합니다.|  
|[CRecordset::SetFieldDirty](#setfielddirty)|변경 되는 현재 레코드에 지정된 된 필드를 표시 합니다.|  
|[CRecordset::SetFieldNull](#setfieldnull)|(예: 값 없음) null로 현재 레코드에 지정된 된 필드의 값을 설정 합니다.|  
|[CRecordset::SetLockingMode](#setlockingmode)|"낙관적" 잠금 (기본값) 또는 "비관적" 잠금을 잠금 모드를 설정 합니다. 업데이트에 대 한 레코드를 잠그는 방법을 결정 합니다.|  
|[CRecordset::SetParamNull](#setparamnull)|지정된 된 매개 변수 (예: 값 없음) null로 설정 합니다.|  
|[CRecordset::SetRowsetCursorPosition](#setrowsetcursorposition)|행 집합 내의 지정된 된 행에 커서를 놓습니다.|  
|[CRecordset::SetRowsetSize](#setrowsetsize)|인출 하는 동안 검색할 레코드 수를 지정 합니다.|  
|[CRecordset::Update](#update)|완료 되는 `AddNew` 또는 `Edit` 데이터 원본에서 새로 만들거나 편집한 데이터를 저장 하 여 작업 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CRecordset::m_hstmt](#m_hstmt)|레코드 집합에 대 한 ODBC 문 핸들을 포함합니다. `HSTMT`를 입력합니다.|  
|[CRecordset::m_nFields](#m_nfields)|레코드 집합의 필드 데이터 멤버의 수를 포함합니다. `UINT`를 입력합니다.|  
|[CRecordset::m_nParams](#m_nparams)|레코드 집합의 매개 변수 데이터 멤버의 수를 포함합니다. `UINT`를 입력합니다.|  
|[CRecordset::m_pDatabase](#m_pdatabase)|에 대 한 포인터는 `CDatabase` 레코드 집합을 데이터 원본에 연결 되어 있는 개체입니다.|  
|[CRecordset::m_strFilter](#m_strfilter)|포함 된 `CString` 구조적 쿼리 언어 (SQL)를 지정 하는 `WHERE` 절. 필터로 사용 특정 조건에 해당 하는 레코드를 선택 합니다.|  
|[CRecordset::m_strSort](#m_strsort)|포함 된 `CString` SQL를 지정 하는 `ORDER BY` 절. 레코드의 정렬 방식을 제어 하는 데 사용 합니다.|  
  
## <a name="remarks"></a>설명  
 "레코드 집합" 이라고 `CRecordset` 개체는 일반적으로 두 가지 형태로 사용: 다이너셋 및 스냅숏을 합니다. 다이너셋 다른 사용자가 만든 데이터 업데이트와 동기화가 유지 합니다. 스냅숏은은 데이터의 정적 보기입니다. 이후에 다른 사용자 또는 응용 프로그램의 다른 레코드 집합의 레코드에 수행한 변경 내용을 반영 다이너셋은에서 레코드를 스크롤할 때 이지만 각 폼 레코드 집합 열릴 때 고정 레코드 집합을 나타냅니다.  
  
> [!NOTE]
>  클래스를 사용 하 여 ODBC Open Database Connectivity () 클래스 아닌 개체 DAO (Data Access) 클래스와 함께 작업 하는 경우 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 대신 합니다. 자세한 내용은 문서 참조 [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)합니다.  
  
 두 종류의 레코드 집합을 사용 하려면 일반적으로에서 응용 프로그램 관련 레코드 집합 클래스가 파생 `CRecordset`합니다. 레코드 집합 데이터 원본에서 레코드를 선택 하 고 할 수 있습니다.  
  
-   레코드를 스크롤하십시오.  
  
-   레코드를 업데이트 하 고 잠금 모드를 지정 합니다.  
  
-   데이터 원본에서 사용 가능한 선택 레코드를 제한 하는 레코드 집합을 필터링 합니다.  
  
-   레코드 집합을 정렬 합니다.  
  
-   런타임이 될 때까지 알 수 없는 정보로 해당 선택 항목을 사용자 지정 하는 레코드 집합 매개 변수화 합니다.  
  
 클래스를 사용 하려면 데이터베이스를 열고 생성자에 대 한 포인터에 전달 하는 레코드 집합 개체를 생성 하면 `CDatabase` 개체입니다. 레코드 집합의 다음 호출 **열려** 멤버 함수를 다이너셋은 또는 스냅숏을 인지를 지정할 수 있습니다. 호출 **열려** 데이터 원본에서 데이터를 선택 합니다. 레코드 집합 개체를 연 후에 해당 멤버 함수 및 데이터 멤버를 사용 하 여 레코드를 스크롤할 작업할를 합니다. 업데이트 가능 또는 읽기 전용 개체 다이너셋은 또는 스냅숏을에 따라 다를 사용할 수 있는 작업 (이에 따라 달라 집니다 ODBC Open Database Connectivity () 데이터 소스의 기능), 대량 행 페치를 구현 했습니다. 새로 고침 레코드 변경 되거나 이후 추가 된 수에 **열려** 호출, 개체의 **Requery** 멤버 함수입니다. 개체의 **닫기** 멤버 함수를 함께 했으면 개체를 삭제 합니다.  
  
 파생 된 `CRecordset` 클래스, 레코드 필드 교환 (RFX) 또는 대량 레코드 필드 교환 (대량 RFX)를 읽고 레코드 필드의 업데이트를 지 원하는 데 사용 됩니다.  
  
 레코드 집합의 레코드 및 레코드 필드 교환에 대 한 자세한 내용은 문서를 참조 [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md), [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md), [레코드 집합: 레코드 페치 대량 (ODBC) ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md), 및 [레코드 필드 교환 (RFX)](../../data/odbc/record-field-exchange-rfx.md)합니다. 다이너셋 및 스냅숏을에 초점을 맞춰, 문서를 참조 하십시오. [다이너셋](../../data/odbc/dynaset.md) 및 [스냅숏](../../data/odbc/snapshot.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CRecordset`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdb.h  
  
##  <a name="addnew"></a>  CRecordset::AddNew  
 준비 테이블에 새 레코드를 추가 합니다.  
  
```  
virtual void AddNew();
```  
  
### <a name="remarks"></a>설명  
 호출 해야 합니다는 [Requery](#requery) 멤버 함수는 새로 추가 된 레코드를 표시 합니다. 레코드의 필드는 처음 Null입니다. (데이터베이스 용어에서 Null 의미 "가치가 없습니다" 아니며 동일 **NULL** c + +에서.) 작업을 완료 하려면 호출 해야 합니다는 [업데이트](#update) 멤버 함수입니다. **업데이트** 데이터 소스에 변경 내용을 저장 합니다.  
  
> [!NOTE]
>  대량 행 페치를 구현한 경우 호출할 수 없습니다 `AddNew`합니다. 이 인해 실패 한 어설션이 발생 합니다. 하지만 클래스 `CRecordset` 메커니즘을 제공 하지 않는 데이터의 대량 행을 업데이트 하기 위한 ODBC API 함수를 사용 하 여 사용자 고유의 함수를 작성할 수 있습니다 **SQLSetPos**합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
 `AddNew` 레코드 집합의 필드 데이터 멤버를 사용 하 여 새로운 빈 레코드를 준비 합니다. 호출한 후 `AddNew`, 레코드 집합의 필드 데이터 멤버에서 원하는 값을 설정 합니다. (호출할 필요가 없습니다는 [편집](#edit) 이 목적을 위해 멤버 함수는 사용. **편집** 기존 레코드에 대해서만 합니다.) 이후에 호출할 때 **업데이트**, 변경 된 필드 데이터 멤버의 값이 데이터 원본에 저장 됩니다.  
  
> [!CAUTION]
>  호출 하기 전에 새 레코드를 스크롤할 경우 **업데이트**, 새 레코드가 손실 되 고 경고가 제공 됩니다.  
  
 데이터 원본 트랜잭션을 지 원하는 경우 만들 수 있습니다 프로그램 `AddNew` 트랜잭션의 일부를 호출 합니다. 트랜잭션에 대 한 자세한 내용은 클래스를 참조 하십시오. [CDatabase](../../mfc/reference/cdatabase-class.md)합니다. 호출 해야 하는 참고 [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) 호출 하기 전에 `AddNew`합니다.  
  
> [!NOTE]
>  다이너셋에 대 한 마지막 레코드로 새 레코드는 레코드 집합에 추가 됩니다. 추가 된 레코드는 스냅숏을;에 추가 호출 해야 **Requery** 레코드 집합을 새로 고칠 수 있습니다.  
  
 호출할 수 없는 `AddNew` 레코드 집합에 대 한 해당 **열려** 멤버 함수가 호출 되지 않았습니다. A `CDBException` 호출 하는 경우 throw 되 `AddNew` 레코드 집합에 추가 될 수 없습니다. 레코드 집합을 호출 하 여 업데이트할 수 있는지 여부를 확인할 수 있습니다 [CanAppend](#canappend)합니다.  
  
 자세한 내용은 다음 문서를 참조: [레코드 집합: 레코드 집합의 레코드 업데이트 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md), [레코드 집합: 추가, 업데이트 및 삭제 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), 및 [트랜잭션 드 ( ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
### <a name="example"></a>예제  
 문서를 참조 [트랜잭션: 트랜잭션이 수행 레코드 집합 (ODBC)에서](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)합니다.  
  
##  <a name="canappend"></a>  CRecordset::CanAppend  
 이전에 열린된 레코드 집합 수 새 레코드를 추가할 수 있는지 여부를 결정 합니다.  
  
```  
BOOL CanAppend() const;  
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합; 새 레코드를 추가할 수 있습니다. 0이 아닌 그렇지 않으면 0입니다. `CanAppend` 읽기 전용으로 레코드 집합을 연 경우에 0을 반환 합니다.  
  
##  <a name="canbookmark"></a>  CRecordset::CanBookmark  
 책갈피를 사용 하 여 레코드를 표시 하 여 레코드 집합 수 있는지 여부를 결정 합니다.  
  
```  
BOOL CanBookmark() const;  
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합 책갈피;를 지원 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 독립적으로 **CRecordset::useBookmarks** 옵션에 `dwOptions` 의 매개 변수는 [열려](#open) 멤버 함수입니다. `CanBookmark` 지정 된 ODBC 드라이버와 커서 지원 책갈피 입력 있는지 여부를 나타냅니다. **CRecordset::useBookmarks** 되는지 여부를 나타냅니다 책갈피를 사용할 수 있는 지원 되는 제공 합니다.  
  
> [!NOTE]
>  책갈피 앞 으로만 이동 가능한 레코드 집합에서 지원 되지 않습니다.  
  
 책갈피와 레코드 탐색에 대 한 자세한 내용은 문서를 참조 [레코드 집합: 책갈피와 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) 및 [레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)합니다.  
  
##  <a name="cancel"></a>  CRecordset::Cancel  
 진행 중인 비동기 작업 또는 프로세스를 두 번째 스레드가 데이터 소스를 취소 하도록 요청 합니다.  
  
```  
void Cancel();
```  
  
### <a name="remarks"></a>설명  
 MFC ODBC 클래스에 더 이상 비동기 처리; 사용 note 비동기 작업을 수행 하려면 직접 ODBC API 함수를 호출 해야 **SQLSetConnectOption**합니다. 자세한 내용은 "비동기적으로 함수 실행" 항목을 참조는 *ODBC SDK Programmer's Guide*합니다.  
  
##  <a name="cancelupdate"></a>  CRecordset::CancelUpdate  
 보류 중인 업데이트를 인해을 모두 취소는 [편집](#edit) 또는 [AddNew](#addnew) 작업을 하기 전에 [업데이트](#update) 호출 됩니다.  
  
```  
void CancelUpdate();
```  
  
### <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 멤버 함수 대량 행 페치를 있으므로 호출할 수 없습니다. 이러한 레코드 집합을 사용 하는 레코드 집합에 적용 되지 않는 **편집**, `AddNew`, 또는 **업데이트**합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
 더티 필드 자동 검사를 사용 하는 경우 `CancelUpdate` 하기 전에 있던 값을 멤버 변수를 복원 합니다 **편집** 또는 `AddNew` 호출 하지 못했으면, 값 변경 사항이 유지 됩니다. 기본적으로 자동 필드 확인은 사용 가능 고 레코드 집합이 열립니다. 를 비활성화 하려면를 지정 해야는 **CRecordset::noDirtyFieldCheck** 에 `dwOptions` 의 매개 변수는 [열려](#open) 멤버 함수입니다.  
  
 데이터를 업데이트 하는 방법에 대 한 자세한 내용은 문서 참조 [레코드 집합: 추가, 업데이트 및 삭제 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)합니다.  
  
##  <a name="canrestart"></a>  CRecordset::CanRestart  
 레코드 집합의 쿼리 (해당 레코드를 새로 고침)를 호출 하 여 다시 시작을 허용 하는지 여부를 결정은 **Requery** 멤버 함수입니다.  
  
```  
BOOL CanRestart() const;  
```  
  
### <a name="return-value"></a>반환 값  
 Requery가 허용 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="canscroll"></a>  CRecordset::CanScroll  
 레코드 집합 스크롤을 허용 하는지 여부를 결정 합니다.  
  
```  
BOOL CanScroll() const;  
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합; 스크롤을 허용 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 스크롤 하는 방법에 대 한 자세한 내용은 문서 참조 [레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)합니다.  
  
##  <a name="cantransact"></a>  CRecordset::CanTransact  
 레코드 집합 트랜잭션을 허용 하는지 여부를 결정 합니다.  
  
```  
BOOL CanTransact() const;  
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합 트랜잭션을; 허용 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 문서 참조 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
##  <a name="canupdate"></a>  CRecordset::CanUpdate  
 레코드 집합을 업데이트할 수 있는지 여부를 결정 합니다.  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합을 업데이트할 수 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 레코드 집합 수 읽기 전용 데이터 원본에는 읽기 전용 또는 지정한 경우 **CRecordset::readOnly** 에 `dwOptions` 레코드 집합을 열 때 매개 변수입니다.  
  
##  <a name="checkrowseterror"></a>  CRecordset::CheckRowsetError  
 레코드를 인출 하는 동안 발생 한 오류를 처리 하기 위해 호출 합니다.  
  
```  
virtual void CheckRowsetError(RETCODE nRetCode);
```  
  
### <a name="parameters"></a>매개 변수  
 `nRetCode`  
 ODBC API 함수 코드를 반환 합니다. 자세한 내용은 설명을 참조하세요.  
  
### <a name="remarks"></a>설명  
 이 가상 멤버 함수는 레코드는 인출 되는 경우 발생 하는 오류를 처리 하 고 대량 행 페치 중에 유용 합니다. 재정의 하는 것이 좋습니다. 만들려는 경우 `CheckRowsetError` 사용자 고유의 오류 처리를 구현 하 합니다.  
  
 `CheckRowsetError` 자동으로 호출 커서 탐색 작업에서와 같은 **열려**, **Requery**, 또는 모든 **이동** 작업 합니다. ODBC API 함수의 반환 값 전달 **SQLExtendedFetch**합니다. 다음 표에서 사용할 수 있는 값의 `nRetCode` 매개 변수입니다.  
  
|nRetCode|설명|  
|--------------|-----------------|  
|**SQL_SUCCESS**|함수는 성공적으로 완료 되었습니다. 추가 정보 없음 ´ ù입니다.|  
|**SQL_SUCCESS_WITH_INFO**|성공적으로 치명적이 지 않은 오류와 함께 가능 완료 하는 함수입니다. 호출 하 여 추가 정보를 가져올 수 있습니다 **SQLError**합니다.|  
|**SQL_NO_DATA_FOUND**|결과 집합의 모든 행 인출 된 합니다.|  
|**SQL_ERROR**|함수가 실패 했습니다. 호출 하 여 추가 정보를 가져올 수 있습니다 **SQLError**합니다.|  
|**SQL_INVALID_HANDLE**|잘못 된 환경 핸들, 연결 핸들 또는 문 핸들 인해 함수가 실패 했습니다. 프로그래밍 오류를 나타냅니다. 추가 정보 없음에서 사용할 수는 **SQLError**합니다.|  
|`SQL_STILL_EXECUTING`|비동기적으로 시작 하는 함수는 계속 실행 됩니다. 기본적으로 MFC 전달 하지는 않지만이 값을 참고 `CheckRowsetError`; MFC는 계속 호출 **SQLExtendedFetch** 더 이상 반환 될 때까지 `SQL_STILL_EXECUTING`합니다.|  
  
 에 대 한 자세한 내용은 **SQLError**, Windows SDK를 참조 하십시오. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
##  <a name="close"></a>  CRecordset::Close  
 레코드 집합을 닫습니다.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>설명  
 ODBC **HSTMT** 및 모든 메모리를 레코드 집합에 할당 된 프레임 워크는 할당이 취소 됩니다. 일반적으로 호출한 후 **닫기**, 할당 된 경우 c + + recordset 개체를 삭제 하면 **새**합니다.  
  
 호출할 수 있습니다 **열려** 호출 후에 다시 **닫기**합니다. 이 레코드 집합 개체를 다시 사용할 수 있습니다. 호출 하는 대체 항목은 **Requery**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase#17](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]  
  
##  <a name="crecordset"></a>  CRecordset::CRecordset  
 `CRecordset` 개체를 생성합니다.  
  
```  
CRecordset(CDatabase* pDatabase = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDatabase`  
 에 대 한 포인터를 포함 한 `CDatabase` 개체 또는 값 **NULL**합니다. 그렇지 않은 경우 **NULL** 및 `CDatabase` 개체의 **열고** 데이터 원본에 연결 하는 데 멤버 함수가 호출 되지 않은, 레코드 집합 자체는 동안를 열려고 시도 **열**  호출 합니다. 전달 하는 경우 **NULL**, `CDatabase` 개체 생성 및 classwizard 함께 사용 된 레코드 집합 클래스를 파생 하는 경우 지정한 데이터 원본 정보를 사용 하 여 연결 합니다.  
  
### <a name="remarks"></a>설명  
 사용 하거나 `CRecordset` 직접에서 응용 프로그램 관련 클래스를 파생 하거나 `CRecordset`합니다. 레코드 집합 클래스를 파생 클래스 마법사를 사용할 수 있습니다.  
  
> [!NOTE]
>  파생된 클래스 *해야* 자체 생성자를 제공 합니다. 파생된 클래스의 생성자에서 생성자를 호출 `CRecordset::CRecordset`을 따라 적절 한 매개 변수를 전달 합니다.  
  
 전달 **NULL** 있어야 recordset 생성자에는 `CDatabase` 개체 구현 되 고 하기 위해 자동으로 연결 합니다. 이 하지 않아도 생성 하 고 연결 하는 유용한 줄임은 `CDatabase` 레코드 집합을 생성 하기 전에 개체입니다.  
  
### <a name="example"></a>예제  
 자세한 내용은 문서 참조 [레코드 집합: 한 클래스에는 테이블 (ODBC) 선언](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)합니다.  
  
##  <a name="delete"></a>  CRecordset::Delete  
 현재 레코드를 삭제합니다.  
  
```  
virtual void Delete();
```  
  
### <a name="remarks"></a>설명  
 성공적으로 삭제 후에 레코드 집합의 필드 데이터 멤버는 Null 값으로 설정 되 고 중 하나를 명시적으로 호출 해야 합니다는 **이동** 삭제 된 레코드를 이동 하기 위해 함수입니다. 삭제 된 레코드를 이동 하면 일단으로 돌아갈 수 없으면입니다. 데이터 원본 트랜잭션을 지 원하는 경우 만들 수 있습니다는 **삭제** 트랜잭션의 일부를 호출 합니다. 자세한 내용은 문서 참조 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
> [!NOTE]
>  대량 행 페치를 구현한 경우 호출할 수 없습니다 **삭제**합니다. 이 인해 실패 한 어설션이 발생 합니다. 하지만 클래스 `CRecordset` 메커니즘을 제공 하지 않는 데이터의 대량 행을 업데이트 하기 위한 ODBC API 함수를 사용 하 여 사용자 고유의 함수를 작성할 수 있습니다 **SQLSetPos**합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
> [!CAUTION]
>  레코드 집합을 업데이트할 수 있어야 하며 있어야 유효한 레코드를 레코드 집합의 현재 호출 하는 경우 **삭제**, 그렇지 않으면 오류가 발생 합니다. 예를 들어 레코드를 삭제 하지만 호출 하기 전에 새 레코드로 스크롤되지 않습니다 **삭제** 다시 **삭제** throw 한 [잠금을](../../mfc/reference/cdbexception-class.md)합니다.  
  
 와 달리 [AddNew](#addnew) 및 [편집](#edit)에 대 한 호출 **삭제** 다음에 대 한 호출에 나타나지 않으면 [업데이트](#update)합니다. 경우는 **삭제** 호출이 실패 하면 필드 데이터 멤버는 남아 변경 되지 않습니다.  
  
### <a name="example"></a>예제  
 이 예제는 함수의 프레임에 만든 레코드 집합을 보여 줍니다. 이 예제에서는 있다고 가정 `m_dbCust`, 형식의 멤버 변수 `CDatabase` 이미 데이터 원본에 연결 합니다.  
  
 [!code-cpp[NVC_MFCDatabase#18](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]  
  
##  <a name="dobulkfieldexchange"></a>  CRecordset::DoBulkFieldExchange  
 대량 행의 데이터 원본에서 레코드 집합으로 데이터를 교환 하기 위해 호출 합니다. 구현 대량 레코드 필드 교환 (대량 RFX).  
  
```  
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFX`  
 에 대 한 포인터는 [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) 개체입니다. 프레임 워크 필드 exchange 작업에 대 한 컨텍스트를 지정 하려면이 개체를 설정 있어야 합니다.  
  
### <a name="remarks"></a>설명  
 대량 행 페치 구현 되는 경우 프레임 워크 데이터 원본에서 레코드 집합 개체에 데이터를 자동으로 전송 하려면이 멤버 함수를 호출 합니다. `DoBulkFieldExchange` 매개 변수 자리 표시자 레코드 집합의 선택에 대 한 SQL 문의 문자열에 있는 경우에 매개 변수 데이터 멤버를 사용 하 여 바인딩합니다.  
  
 대량 행 페치 구현 되지 않은 경우 프레임 워크에서 호출 [DoFieldExchange](#dofieldexchange)합니다. 대량 행 페치를 구현 하려면 지정 해야 합니다는 `CRecordset::useMultiRowFetch` 옵션의는 `dwOptions` 에서 매개 변수는 [열려](#open) 멤버 함수입니다.  
  
> [!NOTE]
> `DoBulkFieldExchange` 파생 된 클래스를 사용 하는 경우에 사용할 수 `CRecordset`합니다. 레코드 집합 개체에서 직접 만든 경우 `CRecordset`를 호출 해야 합니다는 [GetFieldValue](#getfieldvalue) 멤버 함수가 데이터를 검색 합니다.  
  
 대량 레코드 필드 교환 (대량 RFX) 레코드 필드 교환 (RFX)와 비슷합니다. 데이터를 레코드 집합 개체 데이터 소스에서 자동으로 전송 됩니다. 그러나 호출할 수 없습니다 `AddNew`, **편집**, **삭제**, 또는 **업데이트** 변경 내용을 데이터 소스에 다시 전송 하도록 합니다. 클래스 `CRecordset` 현재 데이터의 대량 행을 업데이트 하기 위한 메커니즘을 제공 하지 않는 ODBC API 함수를 사용 하 여 함수를 직접 작성할 수 있습니다 **SQLSetPos**합니다.  
  
 클래스 마법사에서는 대량 레코드 필드 교환;를 지원 하지 않습니다 따라서 재정의 해야 `DoBulkFieldExchange` 대량 RFX 함수에 호출을 기록 하 여 수동으로 합니다. 이러한 함수에 대 한 자세한 내용은 항목을 참조 하십시오. [레코드 필드 교환 함수](../../mfc/reference/record-field-exchange-functions.md)합니다.  
  
 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요. 관련된 정보에 대 한 문서를 참조 [Exchange RFX (레코드 필드)](../../data/odbc/record-field-exchange-rfx.md)합니다.  
  
##  <a name="dofieldexchange"></a>  CRecordset::DoFieldExchange  
 레코드 집합의 필드 데이터 멤버와 데이터 원본에 있는 해당 레코드 간에 (양방향)으로 데이터를 교환 하기 위해 호출 합니다. 구현 레코드 필드 교환 (RFX).  
  
```  
virtual void DoFieldExchange(CFieldExchange* pFX);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFX`  
 에 대 한 포인터는 [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) 개체입니다. 프레임 워크 필드 exchange 작업에 대 한 컨텍스트를 지정 하려면이 개체를 설정 있어야 합니다.  
  
### <a name="remarks"></a>설명  
 대량 행 페치 구현 되지 않은 프레임 워크는 자동으로 레코드 집합 개체의 필드 데이터 멤버와 데이터 소스에서 현재 레코드의 해당 열 간에 데이터를 교환 하려면이 멤버 함수를 호출 합니다. `DoFieldExchange` 매개 변수 자리 표시자 레코드 집합의 선택에 대 한 SQL 문의 문자열에 있는 경우에 매개 변수 데이터 멤버를 사용 하 여 바인딩합니다.  
  
 대량 행 페치 구현 되는 경우 프레임 워크에서 호출 [DoBulkFieldExchange](#dobulkfieldexchange)합니다. 대량 행 페치를 구현 하려면 지정 해야 합니다는 `CRecordset::useMultiRowFetch` 옵션의는 `dwOptions` 에서 매개 변수는 [열려](#open) 멤버 함수입니다.  
  
> [!NOTE]
> `DoFieldExchange` 파생 된 클래스를 사용 하는 경우에 사용할 수 `CRecordset`합니다. 레코드 집합 개체에서 직접 만든 경우 `CRecordset`를 호출 해야 합니다는 [GetFieldValue](#getfieldvalue) 멤버 함수가 데이터를 검색 합니다.  
  
 양쪽 방향에서 작동 하는 레코드 필드 교환 (RFX) 라고 하는 필드 데이터를 교환할: 데이터 소스에서 레코드의 필드에 레코드 집합 개체의 필드 데이터 멤버와 recordset 개체에 데이터 소스에서 레코드입니다.  
  
 구현 하기 위해 일반적으로 수행 해야 하는 작업만 `DoFieldExchange` 파생된 레코드 집합에 대 한 클래스는 클래스 마법사도 클래스를 만들고 필드 데이터 멤버의 이름 및 데이터 형식을 지정 합니다. 또한 클래스 마법사를 매개 변수 데이터 멤버를 지정 하거나 동적으로 바인딩할 열을 다루는 데 쓰는 코드를 추가할 수 있습니다. 자세한 내용은 문서 참조 [레코드 집합: 데이터 열 동적 바인딩 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)합니다.  
  
 마법사의 재정의 기록 classwizard 함께 사용 된 파생된 레코드 집합 클래스를 선언 하면 `DoFieldExchange` 다음 예제와 유사한는:  
  
 [!code-cpp[NVC_MFCDatabase#19](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]  
  
 RFX 함수에 대 한 자세한 내용은 항목을 참조 하십시오. [레코드 필드 교환 함수](../../mfc/reference/record-field-exchange-functions.md)합니다.  
  
 자세한 예제에 대 한 정보에 대 한 `DoFieldExchange`, 문서를 참조 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)합니다. RFX에 대 한 일반 정보에 대 한 문서를 참조 [레코드 필드 교환](../../data/odbc/record-field-exchange-rfx.md)합니다.  
  
##  <a name="edit"></a>  CRecordset::Edit  
 현재 레코드에 변경 내용 수 있습니다.  
  
```  
virtual void Edit();
```  
  
### <a name="remarks"></a>설명  
 호출한 후 **편집**, 해당 값을 직접 설정 하 여 필드 데이터 멤버를 변경할 수 있습니다. 이후에 호출 하는 경우 작업이 완료 되는 [업데이트](#update) 멤버 함수를 데이터 원본에 변경 내용을 저장 합니다.  
  
> [!NOTE]
>  대량 행 페치를 구현한 경우 호출할 수 없습니다 **편집**합니다. 이 인해 실패 한 어설션이 발생 합니다. 하지만 클래스 `CRecordset` 메커니즘을 제공 하지 않는 데이터의 대량 행을 업데이트 하기 위한 ODBC API 함수를 사용 하 여 사용자 고유의 함수를 작성할 수 있습니다 **SQLSetPos**합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
 **편집** 레코드 집합의 데이터 멤버의 값을 저장 합니다. 호출 하는 경우 **편집**를 변경한 다음 호출 **편집** 레코드의 값은 첫 번째 전에 있었던으로 복원 하는 다시 **편집** 호출 합니다.  
  
 경우에 따라 Null (데이터 포함) 하 여 열을 업데이트 하는 것이 좋습니다. 이렇게 하려면 호출 [SetFieldNull](#setfieldnull) 의 매개 변수와 함께 **TRUE** Null; 필드를 표시 하려면이 인해 업데이트 열 합니다. 해당 값이 변경 되지 않은 경우에 데이터 원본에 쓸 수를 호출 하는 필드를 원하는 경우 [SetFieldDirty](#setfielddirty) 의 매개 변수와 함께 **TRUE**합니다. 필드에 Null 값 하는 경우에 작동 합니다.  
  
 데이터 원본 트랜잭션을 지 원하는 경우 만들 수 있습니다는 **편집** 트랜잭션의 일부를 호출 합니다. 호출 해야 하는 참고 [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) 호출 하기 전에 **편집** 레코드 집합 열린 후 및 합니다. 또한 호출 하는 참고 [CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) 호출에 대 한 대체 하지 않습니다 **업데이트** 완료 하는 **편집** 작업 합니다. 트랜잭션에 대 한 자세한 내용은 클래스를 참조 하십시오. [CDatabase](../../mfc/reference/cdatabase-class.md)합니다.  
  
 현재 잠금 모드에 따라 업데이트 되는 레코드에 의해 잠겨 **편집** 호출할 때까지 **업데이트** 또는 다른 레코드로 스크롤 중에 잠겨 있을 수 있습니다 또는 **편집** 호출 합니다. 사용 하 여 잠금 모드를 변경할 수 있습니다 [SetLockingMode](#setlockingmode)합니다.  
  
 현재 레코드의 이전 값이 호출 하기 전에 새 레코드를 스크롤할 경우 복원 **업데이트**합니다. A `CDBException` 호출 하는 경우 throw 되 **편집** 없는 현재 레코드 인지 또는 업데이트할 수 없는 레코드 집합에 대 한 합니다.  
  
 자세한 내용은 문서를 참조 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md) 및 [레코드 집합: 잠금 (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase#20](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]  
  
##  <a name="flushresultset"></a>  CRecordset::FlushResultSet  
 여러 개의 결과 집합이 있는 경우 미리 정의 된 쿼리 (저장된 프로시저)의 다음 결과 집합을 검색 합니다.  
  
```  
BOOL FlushResultSet();
```  
  
### <a name="return-value"></a>반환 값  
 검색할; 추가 결과 집합이 없는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 `FlushResultSet` 만 완료 되 면 완전히 현재 결과 집합에서 커서를 사용 합니다. 다음 결과 호출 하 여 집합을 검색 하는 경우 유의 `FlushResultSet`, 커서 해당 결과 집합에 대해 유효 하지 않으면 호출 해야는 [MoveNext](#movenext) 호출한 후 멤버 함수 `FlushResultSet`합니다.  
  
 미리 정의 된 쿼리에서 사용 하는 출력 매개 변수 또는 입력/출력 매개 변수를 호출 해야 합니다 `FlushResultSet` 반환 될 때까지 `FALSE` (값 0), 이러한 매개 변수 값을 얻기 위해 합니다.  
  
 `FlushResultSet` ODBC API 함수를 호출 `SQLMoreResults`합니다. 경우 `SQLMoreResults` 반환 `SQL_ERROR` 또는 `SQL_INVALID_HANDLE`, 다음 `FlushResultSet` 예외가 throw 됩니다. 에 대 한 자세한 내용은 `SQLMoreResults`, Windows SDK를 참조 하십시오.  
  
 저장된 프로시저를 호출 하려는 경우 필드 바인딩한 해야 `FlushResultSet`합니다.  
  
### <a name="example"></a>예제  
 다음 코드에 있다고 가정 `COutParamRecordset` 는 `CRecordset`-파생 된 개체는 입력된 매개 변수 및 출력 매개 변수를 사용 하 여 미리 정의 된 쿼리를 기반으로 하 고 여러 결과 집합입니다. 참고의 구조는 [DoFieldExchange](#dofieldexchange) 재정의 합니다.  
  
 [!code-cpp[NVC_MFCDatabase#21](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDatabase#22](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]  
  
##  <a name="getbookmark"></a>  CRecordset::GetBookmark  
 현재 레코드에 대 한 책갈피 값을 가져옵니다.  
  
```  
void GetBookmark(CDBVariant& varBookmark);
```  
  
### <a name="parameters"></a>매개 변수  
 `varBookmark`  
 에 대 한 참조는 [CDBVariant](../../mfc/reference/cdbvariant-class.md) 현재 레코드에서 책갈피를 나타내는 개체입니다.  
  
### <a name="remarks"></a>설명  
 책갈피 레코드 집합에서 지원 되는지 확인, 호출 [CanBookmark](#canbookmark)합니다. 지원 되는 경우 책갈피를 사용할 수 있도록 하려면 설정 해야 합니다는 **CRecordset::useBookmarks** 옵션에 `dwOptions` 의 매개 변수는 [열려](#open) 멤버 함수입니다.  
  
> [!NOTE]
>  책갈피 지원 되지 않거나 사용할 수 없는 경우 호출 `GetBookmark` 예외가 throw 됩니다. 책갈피 앞 으로만 이동 가능한 레코드 집합에서 지원 되지 않습니다.  
  
 `GetBookmark` 현재 레코드에 대 한 책갈피의 값을 할당 한 `CDBVariant` 개체입니다. 해당 레코드를 다른 레코드로 이동 후 언제 든 지 돌아가려면 호출 [SetBookmark](#setbookmark) 해당와 `CDBVariant` 개체입니다.  
  
> [!NOTE]
>  특정 레코드 집합 작업이 끝난 후 책갈피 유효할 수 더 이상 없습니다. 예를 들어, 호출 하는 경우 `GetBookmark` 이어서 **Requery**, 인 레코드를 반환할 수 `SetBookmark`합니다. 호출 [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) 안전 하 게 호출할 수 있는지 여부를 확인 하려면 `SetBookmark`합니다.  
  
 책갈피와 레코드 탐색에 대 한 자세한 내용은 문서를 참조 [레코드 집합: 책갈피와 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) 및 [레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)합니다.  
  
##  <a name="getdefaultconnect"></a>  CRecordset::GetDefaultConnect  
 기본 연결 문자열을 가져오기 위해 호출 됩니다.  
  
```  
virtual CString GetDefaultConnect();
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 기본 연결 문자열을 포함 하 합니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크를 레코드 집합의 기반이 되는 데이터 원본에 대 한 기본 연결 문자열을 가져옵니다.이 멤버 함수를 호출 합니다. Classwizard 함께 사용 하면에 대 한 동일한 데이터 원본에서에서 사용 하 여 클래스 마법사 테이블 및 열에 대 한 정보를 식별 하 여이 함수를 구현 합니다. 보면 하기 편리 하 게 응용 프로그램을 개발 하는 동안이 기본 연결에 의존 합니다. 하지만 기본 연결을 응용 프로그램의 사용자에 대 한 적절 한 수 있습니다. 해당 되는 경우, 해야 다시 구현할 있습니다이 함수를 클래스 마법사의 버전을 삭제 합니다. 연결 문자열에 대 한 자세한 내용은 문서 참조 [데이터 원본 (ODBC)](../../data/odbc/data-source-odbc.md)합니다.  
  
##  <a name="getdefaultsql"></a>  CRecordset::GetDefaultSQL  
 기본 SQL 문자열 실행을 가져오기 위해 호출 됩니다.  
  
```  
virtual CString GetDefaultSQL();
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 기본 SQL 문이 들어 있는입니다.  
  
### <a name="remarks"></a>설명  
 프레임 워크 멤버 가져오려면이 함수를 레코드 집합의 기반이 되는 기본 SQL 문을 호출 합니다. 테이블 이름 또는 SQL 때문일 **선택** 문.  
  
 직접 정의한 하지 기본 SQL 문을 클래스 마법사를 사용 하 여 레코드 집합 클래스를 선언 하 여 및 classwizard 함께 사용 하면에 대 한이 작업을 수행 합니다.  
  
 사용자는 용도 대 한 SQL 문의 문자열을 필요한 경우 문의 `GetSQL`를 반환 하는 SQL 문을 열려 있을 때 레코드 집합의 레코드를 선택 하는 데 사용 합니다. 클래스의 재정의에서 기본 SQL 문자열을 편집할 수 `GetDefaultSQL`합니다. 예를 들어 한 호출을 사용 하 여 미리 정의 된 쿼리를 지정할 수 있습니다는 **호출** 문. 그러나 (참고, 되는 경우 편집할 `GetDefaultSQL`를 수정 해야 `m_nFields` 데이터 원본에 있는 열의 수와 일치 하도록 합니다.)  
  
 자세한 내용은 문서 참조 [레코드 집합: 한 클래스에는 테이블 (ODBC) 선언](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)합니다.  
  
> [!CAUTION]
>  테이블 이름은 테이블 이름을 여러 개 제공 되는 경우 또는 경우 프레임 워크가 테이블 이름을 식별할 수 없습니다 비어 있게 됩니다는 **호출** 문을 해석할 수 없습니다. 사용할 때는 **호출** 문, 중괄호 사이 공백을 넣지 해야 및 **호출** 키워드, 중괄호 또는 하기 전에 공백 삽입 해야 하거나는  **선택** 키워드는 **선택** 문.  
  
##  <a name="getfieldvalue"></a>  CRecordset::GetFieldValue  
 현재 레코드의 필드 데이터를 검색합니다.  
  
```  
void GetFieldValue(
    LPCTSTR lpszName,  
    CDBVariant& varValue,  
    short nFieldType = DEFAULT_FIELD_TYPE);

 
void GetFieldValue(
    short nIndex,  
    CDBVariant& varValue,  
    short nFieldType = DEFAULT_FIELD_TYPE);

 
void GetFieldValue(
    short nIndex,  
    CStringA& strValue);

 
void GetFieldValue(
    short nIndex,  
    CStringW& strValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 필드의 이름입니다.  
  
 *varValu*e  
 에 대 한 참조는 [CDBVariant](../../mfc/reference/cdbvariant-class.md) 필드의 값을 저장 하는 개체입니다.  
  
 `nFieldType`  
 필드의 ODBC C 데이터 형식입니다. 기본값을 사용 하 여 **DEFAULT_FIELD_TYPE**, 강제로 `GetFieldValue` 다음 테이블을 기반으로 SQL 데이터 형식에서 C 데이터 형식을 결정 합니다. 그렇지 않으면 데이터를 직접 입력 하거나 호환 가능한 데이터 형식을; 선택을 지정할 수 있습니다. 예를 들어 임의의 데이터 형식으로 저장할 수 있습니다 **SQL_C_CHAR**합니다.  
  
|C 데이터 형식|SQL 데이터 형식|  
|-----------------|-------------------|  
|**SQL_C_BIT**|**SQL_BIT**|  
|**SQL_C_UTINYINT**|**SQL_TINYINT**|  
|**SQL_C_SSHORT**|**SQL_SMALLINT**|  
|**SQL_C_SLONG**|**SQL_INTEGER**|  
|**SQL_C_FLOAT**|**SQL_REAL**|  
|**SQL_C_DOUBLE**|**SQL_FLOATSQL_DOUBLE**|  
|**SQL_C_TIMESTAMP**|**SQL_DATESQL_TIMESQL_TIMESTAMP**|  
|**SQL_C_CHAR**|**SQL_NUMERICSQL_DECIMALSQL_BIGINTSQL_CHARSQL_VARCHARSQL_LONGVARCHAR**|  
|**SQL_C_BINARY**|**SQL_BINARYSQL_VARBINARYSQL_LONGVARBINARY**|  
  
 ODBC 데이터 형식에 대 한 자세한 내용은 "SQL 데이터 형식" 및 "C 데이터 형식" 부록 D의 Windows SDK에서 항목을 참조 합니다.  
  
 `nIndex`  
 필드의 0부터 시작 하는 인덱스입니다.  
  
 `strValue`  
 에 대 한 참조는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체 필드의 값을 저장 하는 텍스트 필드의 데이터 형식에 관계 없이으로 변환 합니다.  
  
### <a name="remarks"></a>설명  
 이름 또는 인덱스로 필드를 찾을 수 있습니다. 필드 값 중 하나에 저장할 수는 `CDBVariant` 개체 또는 `CString` 개체입니다.  
  
 대량 행 페치를 구현한 경우 현재 레코드가 항상 행 집합의 첫 번째 레코드에 배치 됩니다. 사용 하도록 `GetFieldValue` 에 주어진된 행 집합 내에서 레코드를 먼저 호출 해야는 [SetRowsetCursorPosition](#setrowsetcursorposition) 멤버 함수를 해당 행 집합 내에서 원하는 행으로 커서를 이동 합니다. 그런 다음 호출 `GetFieldValue` 해당 행에 대 한 합니다. 대량 행 페치를 구현 하려면 지정 해야 합니다는 `CRecordset::useMultiRowFetch` 옵션의는 `dwOptions` 에서 매개 변수는 [열려](#open) 멤버 함수입니다.  
  
 사용할 수 있습니다 `GetFieldValue` 를 동적으로 디자인 타임에이 정적으로 바인딩 보다는 실행된 시간 필드를 인출 합니다. 예를 들어, 레코드 집합 개체에서 직접 선언한 경우 `CRecordset`, 사용 해야 `GetFieldValue` 검색할 필드 데이터; 레코드 필드 교환 (RFX) 또는 대량 레코드 필드 교환 (대량 RFX) 구현 되지 않았습니다.  
  
> [!NOTE]
>  파생 하지 않는 레코드 집합 개체를 선언 하는 경우 `CRecordset`, ODBC 커서 라이브러리를 로드할 필요가 없습니다. 커서 라이브러리를 사용 하려면 레코드 집합에 바인딩된 열이 하나 이상 있어야 그러나 사용 하는 경우 `CRecordset` 를 직접 바인딩되는 열입니다. 멤버 함수 [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) 및 [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) 커서 라이브러리는 로드 하는지 여부를 제어 합니다.  
  
 `GetFieldValue` ODBC API 함수를 호출 **SQLGetData**합니다. 드라이버는 값을 출력 하는 경우 **SQL_NO_TOTAL** 필드 값의 실제 길이 대 한 `GetFieldValue` 예외를 throw 합니다. 에 대 한 자세한 내용은 **SQLGetData**, Windows SDK를 참조 하십시오.  
  
### <a name="example"></a>예제  
 다음 샘플 코드에 대 한 호출을 보여 줍니다. `GetFieldValue` recordset 개체에서 직접 선언에 대 한 `CRecordset`합니다.  
  
 [!code-cpp[NVC_MFCDatabase#23](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]  
  
> [!NOTE]
>  DAO 클래스와 달리 `CDaoRecordset`, `CRecordset` 없는 `SetFieldValue` 멤버 함수입니다. 직접 개체를 만들 경우 `CRecordset`를 효과적으로 읽기 전용입니다.  
  
 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
##  <a name="getodbcfieldcount"></a>  CRecordset::GetODBCFieldCount  
 레코드 집합 개체에서 필드의 총 수를 검색합니다.  
  
```  
short GetODBCFieldCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합의 필드 수를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 레코드 집합 만들기에 대 한 자세한 내용은 문서 참조 [레코드 집합: 집합 만들기 및 닫기 (ODBC) 레코드 집합](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)합니다.  
  
##  <a name="getodbcfieldinfo"></a>  CRecordset::GetODBCFieldInfo  
 레코드 집합의 필드에 대 한 정보를 가져옵니다.  
  
```  
void GetODBCFieldInfo(
    LPCTSTR lpszName,  
    CODBCFieldInfo& fieldinfo);

 
void GetODBCFieldInfo(
    short nIndex,  
    CODBCFieldInfo& fieldinfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 필드의 이름입니다.  
  
 `fieldinfo`  
 에 대 한 참조는 `CODBCFieldInfo` 구조입니다.  
  
 `nIndex`  
 필드의 0부터 시작 하는 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 한 버전의 함수를 사용 하면 필드 이름으로 조회할 수 있습니다. 다른 버전 인덱스 필드를 찾을 수 있습니다.  
  
 반환 되는 정보에 대 한 설명을 참조 하십시오.는 [CODBCFieldInfo](../../mfc/reference/codbcfieldinfo-structure.md) 구조입니다.  
  
 레코드 집합 만들기에 대 한 자세한 내용은 문서 참조 [레코드 집합: 집합 만들기 및 닫기 (ODBC) 레코드 집합](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)합니다.  
  
##  <a name="getrecordcount"></a>  CRecordset::GetRecordCount  
 레코드 집합의 크기를 결정 합니다.  
  
```  
long GetRecordCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합;의 레코드 수 레코드 집합에; 레코드가 없는 경우 0 또는 레코드 수를 확인할 수 없는 경우-1을 추가 합니다.  
  
### <a name="remarks"></a>설명  
  
> [!CAUTION]
>  Record count으로 "최고 수 위 표시," 번호가 가장 큰 레코드 유지 관리는 아직 볼 사용자 레코드를 모두 이동 됩니다. 레코드의 총 수는 사용자가 마지막 레코드를 벗어나는 이동 후에 알려져 있습니다. 성능상의 이유로 수 업데이트 되지 않습니다 호출 하는 경우 `MoveLast`합니다. 호출 하는 레코드, 사용자가 직접 계산 `MoveNext` 때까지 반복 해 서 `IsEOF` 0이 아닌 값을 반환 합니다. 레코드를 통해 추가 **CRecordset:AddNew** 및 **업데이트** 횟수가 늘어납니다; 통해 레코드 삭제 `CRecordset::Delete` 수를 줄입니다.  
  
##  <a name="getrowsetsize"></a>  CRecordset::GetRowsetSize  
 지정 된 인출 하는 동안 검색할 행 수에 대 한 현재 설정을 가져옵니다.  
  
```  
DWORD GetRowsetSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 지정 된 인출 하는 동안 검색할 행의 수입니다.  
  
### <a name="remarks"></a>설명  
 레코드 집합 열릴 때 기본 행 집합 크기는 25; 대량 행 페치를 사용 하는 경우 그렇지 않으면은 1입니다.  
  
 대량 행 페치를 구현 하려면 지정 해야 합니다는 `CRecordset::useMultiRowFetch` 옵션에 `dwOptions` 의 매개 변수는 [열려](#open) 멤버 함수입니다. 행 집합 크기에 대 한 설정을 변경 하려면 호출 [SetRowsetSize](#setrowsetsize)합니다.  
  
 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
##  <a name="getrowsfetched"></a>  CRecordset::GetRowsFetched  
 인출 후에 실제 검색 된 레코드 수를 결정 합니다.  
  
```  
DWORD GetRowsFetched() const;  
```  
  
### <a name="return-value"></a>반환 값  
 행 수가 페치 후 데이터 원본에서 검색 합니다.  
  
### <a name="remarks"></a>설명  
 대량 행 페치를 구현한 경우에 유용 합니다. 행 집합 크기는 일반적으로 행 개수를 반입;에서 검색 됩니다 나타냅니다. 그러나 레코드 집합의 행 수가 전체 행 집합에 얼마나 많은 행을 검색할도 적용 됩니다. 예를 들어 레코드 집합 4 행 집합 크기 설정 하 여 10 개의 레코드에 있는 경우 다음 반복 레코드 집합에서 호출 하 여 `MoveNext` 최종 행 집합의 두 레코드가 있는 것에 발생 합니다.  
  
 대량 행 페치를 구현 하려면 지정 해야 합니다는 `CRecordset::useMultiRowFetch` 옵션에 `dwOptions` 의 매개 변수는 [열려](#open) 멤버 함수입니다. 행 집합 크기를 지정 하려면 호출 [SetRowsetSize](#setrowsetsize)합니다.  
  
 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase#24](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]  
  
##  <a name="getrowstatus"></a>  CRecordset::GetRowStatus  
 현재 행 집합의 행에 대 한 상태를 가져옵니다.  
  
```  
WORD GetRowStatus(WORD wRow) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `wRow`  
 1부터 행의 위치는 현재 행 집합의 합니다. 이 값의 범위는 1에서 행 집합의 크기.  
  
### <a name="return-value"></a>반환 값  
 행에 대 한 상태 값입니다. 자세한 내용은 설명을 참조하세요.  
  
### <a name="remarks"></a>설명  
 `GetRowStatus` 데이터 소스에서 검색 된 이후 모든 행에 상태 변경 중 하나를 나타내는 값을 반환 하려면 해당 행 `wRow` 이 인출 된 합니다. 다음 표에서는 가능한 반환 값을 보여 줍니다.  
  
|상태 값|설명|  
|------------------|-----------------|  
|`SQL_ROW_SUCCESS`|행이 변경 되지 않습니다.|  
|`SQL_ROW_UPDATED`|행이 업데이트 되었습니다.|  
|`SQL_ROW_DELETED`|해당 행이 삭제 되었습니다.|  
|`SQL_ROW_ADDED`|행 추가 되었습니다.|  
|`SQL_ROW_ERROR`|행이 오류로 인해 가져올 수 없습니다.|  
|`SQL_ROW_NOROW`|에 해당 하는 행이 `wRow`합니다.|  
  
 자세한 내용은 ODBC API 함수를 참조 하십시오. **SQLExtendedFetch** Windows sdk에서입니다.  
  
##  <a name="getstatus"></a>  CRecordset::GetStatus  
 마지막 레코드에 표시 여부 및 레코드 집합의 현재 레코드의 인덱스를 결정 합니다.  
  
```  
void GetStatus(CRecordsetStatus& rStatus) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `rStatus`  
 에 대 한 참조는 **CRecordsetStatus** 개체입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
### <a name="remarks"></a>설명  
 `CRecordset` 인덱스를 추적 하려고 하지만 경우에 따라이 불가능할 수도 있습니다. 참조 [GetRecordCount](#getrecordcount) 설명 합니다.  
  
 **CRecordsetStatus** 구조 형식은 다음과 같습니다.  
  
 `struct CRecordsetStatus`  
  
 `{`  
  
 `long m_lCurrentRecord;`  
  
 `BOOL m_bRecordCountFinal;`  
  
 `};`  
  
 두 멤버가 **CRecordsetStatus** 의미는 다음과 같습니다.  
  
- **m_lCurrentRecord** 알 수 있는 경우에 레코드 집합의 현재 레코드의 0부터 시작 인덱스를 포함 합니다. 이 멤버를 포함 하는 인덱스를 확인할 수 없는 경우 **AFX_CURRENT_RECORD_UNDEFINED** -(2). 경우 `IsBOF` 은 **TRUE** (레코드 집합을 빈 또는 첫 번째 레코드 바로 앞 스크롤하려고) 다음 **m_lCurrentRecord** 로 설정 된 **AFX_CURRENT_RECORD_BOF** (-1). 첫 번째 레코드에 대해 다음 설정 된 경우 0으로, 두 번째 1, 기록 등에입니다.  
  
- **m_bRecordCountFinal** Nonzero 레코드 집합의 레코드의 총 수를 확인 하는 경우. 일반적으로이 수행 해야 합니다는 레코드 집합의 시작 부분에서 시작 하 고 호출 하 여 `MoveNext` 될 때까지 `IsEOF` 0이 아닌 값을 반환 합니다. 반환 된 레코드를 계산이 멤버가이 0 이면 `GetRecordCount`,-1을 반환 하지이 레코드의 "최고 수 위 표시" 수만 있습니다.  
  
##  <a name="getsql"></a>  CRecordset::GetSQL  
 이 멤버 함수는가 열려 있을 때 레코드 집합의 레코드를 선택 하는 데 사용 된 SQL 문이를 호출 합니다.  
  
```  
const CString& GetSQL() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **const** 에 대 한 참조는 `CString` SQL 문이 들어 있는입니다.  
  
### <a name="remarks"></a>설명  
 일반적으로 SQL 됩니다 **선택** 문. 반환한 문자열 `GetSQL` 읽기 전용입니다.  
  
 반환한 문자열 `GetSQL` 간에 차이가 있는 일반적으로 모든 문자열에서 레코드 집합에 전달 했습니다는 `lpszSQL` 매개 변수를는 **열려** 멤버 함수입니다. 레코드 집합에 전달 하는 것에 따라 전체 SQL 문을 생성 때문에 이것이 **열려**, 어떤 수에서 지정한 클래스 마법사를 사용 하 여 지정한 무엇는 **m_strFilter** 및 `m_strSort` 데이터 멤버 및 매개 변수를 지정 합니다. 문서를 참조 하는 레코드 집합이 SQL 문을 생성 하는 방법에 대 한 세부 정보에 대 한 [레코드 집합: 레코드 집합의 레코드 선택 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)합니다.  
  
> [!NOTE]
>  이 함수를 호출한 후에 호출 [열려](#open)합니다.  
  
##  <a name="gettablename"></a>  CRecordset::GetTableName  
 레코드 집합의 쿼리의 기반이 되는 SQL 테이블의 이름을 가져옵니다.  
  
```  
const CString& GetTableName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **const** 에 대 한 참조는 `CString` 테이블을 포함 하는 이름이 고, 그렇지 않으면 테이블에 따라 레코드 집합은 빈 문자열입니다.  
  
### <a name="remarks"></a>설명  
 `GetTableName` 레코드 집합에서 여러 테이블 또는 미리 정의 된 쿼리 (저장된 프로시저)의 조인이 아니라 테이블에 기반 하는 경우에 유효만 있습니다. 이름에는 읽기 전용입니다.  
  
> [!NOTE]
>  이 함수를 호출한 후에 호출 [열려](#open)합니다.  
  
##  <a name="isbof"></a>  CRecordset::IsBOF  
 레코드 집합의 첫 번째 레코드 바로 앞 배치 된 경우 0이 아닌 값을 반환 합니다. 현재 기록이 없습니다.  
  
```  
BOOL IsBOF() const;  
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 레코드; 앞 뒤로 스크롤 하는 경우 또는 레코드 집합에 레코드가 없는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 레코드 집합의 첫 번째 레코드 바로 앞를 벗어났는지 여부를 알아보려면 레코드로 레코드에서 스크롤하기 전에이 멤버 함수를 호출 합니다. 사용할 수도 있습니다 `IsBOF` 와 함께 `IsEOF` 레코드 집합에는 모든 레코드가 포함 하거나 비어 있는지 확인 하려면. 호출한 후에 즉시 **열려**레코드 집합에 레코드가 없는 경우, `IsBOF` 0이 아닌 값을 반환 합니다. 첫 번째 레코드는 현재 레코드 레코드가 하나 이상 있는 레코드 집합을 열 때 및 `IsBOF` 0을 반환 합니다.  
  
 첫 번째 레코드는 현재 레코드 경우 호출 하면 `MovePrev`, `IsBOF` 이후에 0이 아닌 반환 합니다. 경우 `IsBOF` 0이 아닌 값을 반환 하 고 호출 `MovePrev`, 오류가 발생 합니다. 경우 `IsBOF` 반환 0이 아니고, 현재 레코드는 정의 되지 하 고 현재 레코드를 필요로 하는 모든 작업에서 오류가 발생 합니다.  
  
### <a name="example"></a>예제  
 이 예에서는 `IsBOF` 및 `IsEOF` 코드 스크롤하면 각 방향에서 레코드 집합에서 레코드 집합의 한계를 검색 하 합니다.  
  
 [!code-cpp[NVC_MFCDatabase#25](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]  
  
##  <a name="isdeleted"></a>  CRecordset::IsDeleted  
 현재 레코드 삭제 되었는지 여부를 결정 합니다.  
  
```  
BOOL IsDeleted() const;  
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합 삭제 된 레코드; 배치 되어 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 레코드를 스크롤할 경우 및 `IsDeleted` 반환 **TRUE** (0이 아님), 다음으로 스크롤해야 다른 레코드가 다른 레코드 집합 작업을 수행 하기 전에.  
  
 결과 `IsDeleted` 지정한 여부를 레코드 집합이 업데이트할 수 있는지에 레코드 집합 형식이 같은 많은 요인에 따라는 **CRecordset::skipDeletedRecords** 옵션 여부는 레코드 집합을 열 때 사용자 드라이버 팩 레코드를 삭제 하 고 여러 사용자가 있는지 여부를 확인 합니다.  
  
 에 대 한 자세한 내용은 **CRecordset::skipDeletedRecords** 드라이버 압축을 참조 하 고는 [열려](#open) 멤버 함수입니다.  
  
> [!NOTE]
>  호출 하지 않아야 대량 행 페치를 구현한 경우 `IsDeleted`합니다. 대신, 호출 된 [GetRowStatus](#getrowstatus) 멤버 함수입니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
##  <a name="iseof"></a>  CRecordset::IsEOF  
 레코드 집합 마지막 레코드 뒤 배치 된 경우 0이 아닌 값을 반환 합니다. 현재 기록이 없습니다.  
  
```  
BOOL IsEOF() const;  
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합에 레코드가 없는 경우 또는 마지막 레코드; 보다 스크롤 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 레코드 집합의 마지막 레코드 범위를 벗어났는지 여부를 알아보려면 레코드로 레코드에서 스크롤할 때이 함수를 호출 합니다. 사용할 수도 있습니다 `IsEOF` 레코드 집합에는 모든 레코드가 포함 하거나 비어 있는지 확인 하려면. 호출한 후에 즉시 **열려**레코드 집합에 레코드가 없는 경우, `IsEOF` 0이 아닌 값을 반환 합니다. 첫 번째 레코드는 현재 레코드 레코드가 하나 이상 있는 레코드 집합을 열 때 및 `IsEOF` 0을 반환 합니다.  
  
 호출 하는 경우 마지막 레코드가 현재 레코드 `MoveNext`, `IsEOF` 이후에 0이 아닌 반환 합니다. 경우 `IsEOF` 0이 아닌 값을 반환 하 고 호출 `MoveNext`, 오류가 발생 합니다. 경우 `IsEOF` 반환 0이 아니고, 현재 레코드는 정의 되지 하 고 현재 레코드를 필요로 하는 모든 작업에서 오류가 발생 합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [IsBOF](#isbof)합니다.  
  
##  <a name="isfielddirty"></a>  CRecordset::IsFieldDirty  
 지정 된 필드 데이터 멤버 이후 변경 되었는지 여부를 결정 [편집](#edit) 또는 [AddNew](#addnew) 호출 되었습니다.  
  
```  
BOOL IsFieldDirty(void* pv);
```  
  
### <a name="parameters"></a>매개 변수  
 `pv`  
 필드 데이터 멤버의 상태를 확인 하려면에 대 한 포인터 또는 **NULL** 더티이 필드를 확인 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 필드 데이터 멤버 호출 이후 변경 된 경우 0이 아닌 `AddNew` 또는 **편집**그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 모든 더티 필드 데이터 멤버의 데이터를 전송할 레코드를 데이터 원본에 대해를 호출 하 여 현재 레코드가 업데이트 될 때는 [업데이트](#update) 의 멤버 함수 `CRecordset` (호출한 이후 **편집**또는 `AddNew`).  
  
> [!NOTE]
>  이 멤버 함수 대량 행 페치를 사용 하는 레코드 집합에 적용 되지 않습니다. 구현한 경우 대량 행 페치를 다음 `IsFieldDirty` 은 항상 반환 **FALSE** 실패 한 어설션이 발생 합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
 호출 `IsFieldDirty` 이전에 대 한 호출의 효과 다시 설정 됩니다 [SetFieldDirty](#setfielddirty) 필드의 더티 상태는 다시 계산 합니다. 에 `AddNew` 경우 의사 null 값에서 현재 필드 값과 다른 경우 필드가 설정을 변경 합니다. 에 **편집** 경우 필드 값와 다른 경우 캐시 된 값 필드의 상태를 더티 설정 됩니다.  
  
 `IsFieldDirty` 이 통해 구현 [DoFieldExchange](#dofieldexchange)합니다.  
  
 변경 플래그에 대 한 자세한 내용은 문서 참조 [레코드 집합: 레코드 집합의 레코드 선택 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)합니다.  
  
##  <a name="isfieldnull"></a>  CRecordset::IsFieldNull  
 현재 레코드에 지정된 된 필드에 Null 인 경우 0이 아닌 값을 반환 합니다 (값이 없는).  
  
```  
BOOL IsFieldNull(void* pv);
```  
  
### <a name="parameters"></a>매개 변수  
 `pv`  
 필드 데이터 멤버의 상태를 확인 하려면에 대 한 포인터 또는 **NULL** Null이 있는 필드를 확인 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 필드 데이터 멤버는 Null;로 플래그가 지정 되어 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 지정 된 필드 데이터 멤버는 레코드 집합의 Null로 플래그가 지정 되었는지 여부를 확인 하려면이 함수를 호출 합니다. (데이터베이스 용어에서 Null 의미 "가치가 없습니다" 아니며 동일 **NULL** c + +에서.) 필드 데이터 멤버를 Null로 플래그가 지정 되어 값이 현재 레코드의 열으로 해석 됩니다.  
  
> [!NOTE]
>  이 멤버 함수 대량 행 페치를 사용 하는 레코드 집합에 적용 되지 않습니다. 구현한 경우 대량 행 페치를 다음 `IsFieldNull` 은 항상 반환 **FALSE** 실패 한 어설션이 발생 합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
 `IsFieldNull` 이 통해 구현 [DoFieldExchange](#dofieldexchange)합니다.  
  
##  <a name="isfieldnullable"></a>  CRecordset::IsFieldNullable  
 현재 레코드에 지정된 된 필드 (예: 값 없음) 하는 Null로 설정할 수 있는 경우 0이 아닌 값을 반환 합니다.  
  
```  
BOOL IsFieldNullable(void* pv);
```  
  
### <a name="parameters"></a>매개 변수  
 `pv`  
 필드 데이터 멤버의 상태를 확인 하려면에 대 한 포인터 또는 **NULL** 에 Null 값으로 설정할 수는 경우 필드를 결정 합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 지정 된 필드 데이터 멤버 "null"이 허용 되는지 확인 하려면 (설정 될 수 있습니다; Null 값으로 호출 C + + **NULL** Null 이며 데이터베이스 용어에서 의미 같지는 않습니다 "가치가 없음").  
  
> [!NOTE]
>  대량 행 페치를 구현한 경우 호출할 수 없습니다 `IsFieldNullable`합니다. 대신, 호출 된 [GetODBCFieldInfo](#getodbcfieldinfo) 멤버 함수를 필드를 Null 값으로 설정할 수 있는지 여부를 결정 합니다. 항상 호출할 수 있는 참고 `GetODBCFieldInfo`대량 행 페치 구현 여부에 관계 없이 합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
 Null이 될 수 없는 필드 값이 있어야 합니다. 데이터 원본 추가 또는 업데이트를 거부 하는 이러한 필드를 추가 하거나 레코드를 업데이트할 때 Null로 설정 하려고 하면 및 [업데이트](#update) 예외가 throw 됩니다. 호출 하면 예외가 발생 **업데이트**호출할 때가 아니라, [SetFieldNull](#setfieldnull)합니다.  
  
 사용 하 여 **NULL** 함수의 첫 번째 인수는 함수를에 적용 됩니다에 대 한 **outputColumn** 필드 하지 **param** 필드입니다. 예를 들어, 호출  
  
 [!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 만 설정 됩니다 **outputColumn** 필드를 **NULL**; **param** 필드에 영향을 받지 않습니다.  
  
 작동 하도록 **param** 필드, 개별의 실제 주소를 입력 해야 **param** 와 같은 작업에 대 하 시겠습니까:  
  
 [!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 즉, 설정할 수 없습니다. 모든 **param** 필드를 **NULL**있습니다, **outputColumn** 필드입니다.  
  
 `IsFieldNullable` 이 통해 구현 [DoFieldExchange](#dofieldexchange)합니다.  
  
##  <a name="isopen"></a>  CRecordset::IsOpen  
 레코드 집합 열기 이미 인지 여부를 확인 합니다.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우 recordset 개체 [열려](#open) 또는 [Requery](#requery) 멤버 함수를 이전에 호출 하 고 레코드 집합 닫히지 않은; 그렇지 않으면 0입니다.  
  
##  <a name="m_hstmt"></a>  CRecordset::m_hstmt  
 형식의 ODBC 문 데이터 구조에 대 한 핸들을 포함 **HSTMT**, 레코드와 연결 합니다.  
  
### <a name="remarks"></a>설명  
 연결 된 ODBC 데이터 원본에 각 쿼리는 **HSTMT**합니다.  
  
> [!CAUTION]
>  사용 하지 마십시오 **m_hstmt** 하기 전에 [열려](#open) 가 호출 되었습니다.  
  
 에 액세스할 필요가 없습니다 일반적으로 **HSTMT** 를 직접 SQL 문을 직접 실행을 위해 필요할 수 있습니다. `ExecuteSQL` 클래스의 멤버 함수 `CDatabase` 예제를 사용 하 여 제공 **m_hstmt**합니다.  
  
##  <a name="m_nfields"></a>  CRecordset::m_nFields  
 레코드 집합 클래스의 필드 데이터 멤버의 수를 포함합니다. 즉, 데이터 원본에서 레코드 집합에서 선택한 열 번호입니다.  
  
### <a name="remarks"></a>설명  
 레코드 집합 클래스에 대 한 생성자를 초기화 해야 `m_nFields` 는 올바른 수를 사용 합니다. 하지 않은 경우 클래스 마법사 클래스를 선언할 때 레코드 집합을 사용 하는 경우이 초기화를 씁니다. 작성할 수도 있습니다 것 수동으로 합니다.  
  
 이 번호를 사용 하 여 필드 데이터 멤버와 데이터 소스에서 현재 레코드의 해당 열 간의 상호 작용을 관리 하는 프레임 워크입니다.  
  
> [!CAUTION]
>  이 숫자에 등록 하는 "출력 열"의 수와 일치 해야 `DoFieldExchange` 또는 `DoBulkFieldExchange` 를 호출한 후 [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) 매개 변수와 함께 **CFieldExchange::outputColumn**합니다.  
  
 동적으로 문서에 설명 된 대로 열을 바인딩할 수 있습니다 "레코드 집합: 동적으로 바인딩 데이터 열입니다." 이렇게 하면 경우의 수를 늘려야 `m_nFields` 의 호출 RFX 또는 대량 RFX 함수의 수를 반영 하도록 프로그램 `DoFieldExchange` 또는 `DoBulkFieldExchange` 동적으로 바인딩된 열에 대 한 멤버 함수입니다.  
  
 자세한 내용은 문서를 참조 [레코드 집합: 데이터 열 동적 바인딩 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) 및 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
### <a name="example"></a>예제  
 문서 참조 [레코드 필드 교환: RFX 사용](../../data/odbc/record-field-exchange-using-rfx.md)합니다.  
  
##  <a name="m_nparams"></a>  CRecordset::m_nParams  
 레코드 집합 클래스;의 매개 변수 데이터 멤버의 수를 포함합니다. 즉, 매개 변수 수가 레코드 집합의 쿼리와 함께 전달 합니다.  
  
### <a name="remarks"></a>설명  
 레코드 집합 클래스에 매개 변수 데이터 멤버, 경우에 클래스에 대 한 생성자 초기화 해야 `m_nParams` 는 올바른 수를 사용 합니다. 값 `m_nParams` 기본값은 0입니다. 초기화 매개 변수 수를 반영 하기 위해 클래스 생성자에서 수동으로 추가 해야 (있음 수동으로 수행 해야 합니다) 매개 변수 데이터 멤버를 추가 하는 경우 (수가 이상이 이어야 '의 자리 표시자 프로그램 **m_strFilter**  또는 `m_strSort` 문자열)입니다.  
  
 레코드 집합의 쿼리를 매개 변수화 하는 경우이 값을 사용 하는 프레임 워크입니다.  
  
> [!CAUTION]
>  이 숫자는 "params"에 등록의 수와 일치 해야 `DoFieldExchange` 또는 `DoBulkFieldExchange` 를 호출한 후 [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) 의 매개 변수 값으로 **CFieldExchange::inputParam**,  **CFieldExchange::param**, **CFieldExchange::outputParam**, 또는 **CFieldExchange::inoutParam**합니다.  
  
### <a name="example"></a>예제  
  문서를 참조 [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) 및 [레코드 필드 교환: RFX 사용](../../data/odbc/record-field-exchange-using-rfx.md)합니다.  
  
##  <a name="m_pdatabase"></a>  CRecordset::m_pDatabase  
 에 대 한 포인터는 `CDatabase` 레코드 집합을 데이터 원본에 연결 되어 있는 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 변수는 두 가지 방법으로 설정 됩니다. 이미 연결 된 포인터를 전달 일반적으로 `CDatabase` 레코드 집합 개체를 생성할 때 개체입니다. 전달 하는 경우 **NULL** 대신 `CRecordset` 만듭니다는 `CDatabase` 있습니다에 대 한 개체를 연결 합니다. 두 경우 모두 `CRecordset` 포인터를이 변수에 저장 합니다.  
  
 일반적으로 직접 않아도 됩니다에 저장 된 포인터를 사용 하도록 **m_pDatabase**합니다. 그러나 사용자 고유의 확장을 작성 하는 경우 `CRecordset`, 포인터를 사용 하도록 할 수 있습니다. 예를 들어 해야 포인터 throw 되는 경우 사용자 고유의 `CDBException`s입니다. 동일한를 사용 하 여 작업을 수행 해야 할 경우 할 수 있습니다 또는 `CDatabase` 실행 제한 시간 설정 트랜잭션을 또는 호출 등의 개체는 `ExecuteSQL` 클래스의 멤버 함수 `CDatabase` SQL 문을 직접 실행 하 합니다.  
  
##  <a name="m_strfilter"></a>  CRecordset::m_strFilter  
 레코드 집합 개체를 생성 하지만 호출 하기 전에 해당 **열려** 멤버 함수,이 데이터 멤버를 사용 하 여 저장할는 `CString` SQL 포함 된 **여기서** 절.  
  
### <a name="remarks"></a>설명  
 레코드 집합에서이 문자열을 사용 하 여 제한 (또는 필터링) 중에 선택 된 레코드는 **열려** 또는 **Requery** 호출 합니다. 이 "캘리포니아에 모든 영업" 같은 레코드 하위 집합을 선택 하는 데 유용 ("상태 = CA"). ODBC SQL 구문은 **여기서** 절은  
  
 `WHERE search-condition`  
  
 포함 하지 않는 참고는 **여기서** 문자열에는 키워드입니다. 프레임 워크를 제공 합니다.  
  
 또한 매개 변수화 하는 필터 문자열을 배치 하 여 ' 실행 시간에 자리 표시자, 각 자리 표시자에 대 한 클래스의 매개 변수 데이터 멤버를 선언 하 고에서 레코드 집합에 매개 변수를 전달 합니다. 이렇게 하면 런타임 시 필터를 생성할 수 있습니다. 자세한 내용은 문서를 참조 [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)합니다.  
  
 SQL에 대 한 자세한 내용은 **여기서** 절 문서를 참조 하십시오. [SQL](../../data/odbc/sql.md)합니다. 문서를 선택 하 고 레코드를 필터링 하는 방법에 대 한 자세한 내용은 참고 [레코드 집합: 레코드 필터링 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase#30](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]  
  
##  <a name="m_strsort"></a>  CRecordset::m_strSort  
 레코드 집합 개체를 생성 하지만 호출 하기 전에 해당 **열려** 멤버 함수,이 데이터 멤버를 사용 하 여 저장할는 `CString` SQL 포함 된 **ORDER BY** 절.  
  
### <a name="remarks"></a>설명  
 레코드 집합에서이 문자열을 사용 하 여 중 선택 하는 레코드를 정렬 하는 **열려** 또는 **Requery** 호출 합니다. 하나 이상의 열에서 레코드 집합을 정렬 하려면이 기능을 사용할 수 있습니다. ODBC SQL 구문에 대 한 프로그램 **ORDER BY** 절은  
  
 `ORDER BY sort-specification [, sort-specification]...`  
  
 여기서는 정렬 지정은 정수 또는 열 이름입니다. 정렬 문자열에 있는 열 목록에 "ASC" 또는 "DESC"를 추가 하 여 오름차순 또는 내림차순 순서 (순서는 기본적으로 오름차순)을 지정할 수도 있습니다. 선택 된 레코드는 첫 번째 열을 나열 하 여 다음의 두 번째 클러스터 및 등 기준 먼저 정렬 됩니다. 예를 들어 성, 이름으로 "Customers" 레코드 집합을 주문할 수 있습니다. 데이터 원본에 표시 하는 열의 수에 따라 달라 집니다. 자세한 내용은 Windows SDK를 참조 하십시오.  
  
 포함 하지 않는 참고는 **ORDER BY** 문자열에는 키워드입니다. 프레임 워크를 제공 합니다.  
  
 SQL 절에 대 한 자세한 내용은 문서 참조 [SQL](../../data/odbc/sql.md)합니다. 레코드를 정렬 하는 방법에 대 한 자세한 내용은 문서 참조 [레코드 집합: 레코드 정렬 (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase#31](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]  
  
##  <a name="move"></a>  CRecordset::Move  
 앞으로 또는 뒤로 레코드 집합 내에서 현재 레코드 포인터를 이동합니다.  
  
```  
virtual void Move(
    long nRows,  
    WORD wFetchType = SQL_FETCH_RELATIVE);
```  
  
### <a name="parameters"></a>매개 변수  
 `nRows`  
 앞으로 또는 뒤로 이동 하는 행의 수입니다. 양수 값을 레코드 집합의 끝 부분으로 앞으로 이동 합니다. 음수 값 시작 부분을 향해 뒤로 이동합니다.  
  
 `wFetchType`  
 행 집합을 결정 하는 **이동** 를 인출 합니다. 자세한 내용은 설명을 참조하세요.  
  
### <a name="remarks"></a>설명  
 0에 대 한 값을 전달 하는 경우 `nRows`, **이동** ; 현재 레코드를 새로 고칩니다. **이동** 현재 끝납니다 `AddNew` 또는 **편집** 모드 하기 전에 현재 레코드의 값을 복원 합니다 `AddNew` 또는 **편집** 호출 되었습니다.  
  
> [!NOTE]
>  레코드 집합을 이동할 때 삭제 된 레코드를 건너뛸 수 없습니다. 참조 [CRecordset::IsDeleted](#isdeleted) 자세한 정보에 대 한 합니다. 열 때는 `CRecordset` 와 **skipDeletedRecords** 옵션이 설정, **이동** 하면 어설션는 `nRows` 매개 변수는 0입니다. 이 문제는 삭제 된 행은 동일한 데이터를 사용 하 여 다른 클라이언트 응용 프로그램의 새로 고침을 방지 합니다. 참조는 `dwOption` 매개 변수에서 [열려](#open) 에 대 한 설명은 **skipDeletedRecords**합니다.  
  
 **이동** 행 집합에서 레코드 집합의 위치를 변경 합니다. 에 대 한 값을 기반으로 `nRows` 및 `wFetchType`, **이동** 적절 한 행 집합을 인출 하 고 다음 해당 행 집합에서 첫 번째 레코드를 현재 레코드 있도록 합니다. 하지 대량 행 페치를 구현한 다음 행 집합 크기는 항상 1입니다. 행 집합을 인출할 때 **이동** 직접 호출는 [CheckRowsetError](#checkrowseterror) 멤버 함수는 인출에서 발생 하는 오류를 처리 합니다.  
  
 사용자가 전달 하는 값에 따라 **이동** 가 다른 같음 `CRecordset` 멤버 함수입니다. 특히, 값 `wFetchType` 보다 직관적으로 파악 하는 멤버 함수 및 현재 레코드를 이동 하는 기본 방법은 종종 나타낼 수 있습니다.  
  
 다음 표에서 사용할 수 있는 값 `wFetchType`, 행 집합은 **이동** 인출 됩니다에 따라 `wFetchType` 및 `nRows`, 및 모든 해당 멤버 함수에 해당 하 `wFetchType`합니다.  
  
|wFetchType|인출 된 행 집합|해당 하는 멤버 함수|  
|----------------|--------------------|--------------------------------|  
|`SQL_FETCH_RELATIVE` (기본값)|행 집합 시작 `nRows` 현재 행 집합에 있는 첫 번째 행의 행입니다.||  
|`SQL_FETCH_NEXT`|다음 행 집합입니다. `nRows` 는 무시 됩니다.|[MoveNext](#movenext)|  
|`SQL_FETCH_PRIOR`|이전 행 집합 `nRows` 는 무시 됩니다.|[MovePrev](#moveprev)|  
|`SQL_FETCH_FIRST`|레코드 집합;에 있는 첫 번째 행 집합 `nRows` 는 무시 됩니다.|[MoveFirst](#movefirst)|  
|`SQL_FETCH_LAST`|레코드 집합;에 있는 마지막 전체 행 집합 `nRows` 는 무시 됩니다.|[MoveLast](#movelast)|  
|`SQL_FETCH_ABSOLUTE`|경우 `nRows` > 0, 시작 하는 행 집합 `nRows` 시작 부분에서 레코드 집합의 행입니다. 경우 `nRows` < 0, 시작 하는 행 집합 `nRows` 레코드 집합의 끝 에서부터 행입니다. 경우 `nRows` = 0, 파일 시작 부분 (BOF) 조건 반환 됩니다.|[SetAbsolutePosition](#setabsoluteposition)|  
|`SQL_FETCH_BOOKMARK`|에 해당 하는 책갈피 값을 갖는 행부터 행 집합 `nRows`합니다.|[SetBookmark](#setbookmark)|  
  
> [!NOTE]
>  앞 으로만 이동 가능한 레코드 집합에 대 한 **이동** 값만 유효 `SQL_FETCH_NEXT` 에 대 한 `wFetchType`합니다.  
  
> [!CAUTION]
>  호출 **이동** 레코드 집합에 레코드가 없는 경우 예외를 throw 합니다. 레코드 집합에 레코드가 있는지를 확인 하려면 호출 [IsBOF](#isbof) 및 [IsEOF](#iseof)합니다.  
  
> [!NOTE]
>  시작 또는 레코드 집합의 끝을 지나서 스크롤 하는 경우 ( `IsBOF` 또는 `IsEOF` 0이 아닌 반환), 호출는 **이동** 가능 throw 것으로 함수는 `CDBException`합니다. 예를 들어 경우 `IsEOF` 0이 아닌 값을 반환 하 고 `IsBOF` 다음 하지 않는 `MoveNext` 예외를 throw 합니다 하지만 `MovePrev` 되지 것입니다.  
  
> [!NOTE]
>  호출 하는 경우 **이동** 현재 레코드 되는 동안 업데이트 되거나 추가 된 업데이트 경고 없이 손실 됩니다.  
  
 레코드 집합 탐색에 대 한 자세한 내용은 문서를 참조 [레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) 및 [레코드 집합: 책갈피와 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요. 관련된 정보에 대 한 ODBC API 함수를 참조 하십시오. **SQLExtendedFetch** Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDatabase#28](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]  
  
##  <a name="movefirst"></a>  CRecordset::MoveFirst  
 현재 레코드를 첫 번째 행 집합의 첫 번째 레코드를 만듭니다.  
  
```  
void MoveFirst();
```  
  
### <a name="remarks"></a>설명  
 여부 대량 행 페치를 구현한에 관계 없이이 항상 첫 번째 레코드 집합의 레코드입니다.  
  
 호출할 필요가 없습니다 **MoveFirst** 레코드 집합을 연 후에 즉시 합니다. 그 당시 (있는 경우) 첫 번째 레코드는 자동으로 현재 레코드.  
  
> [!NOTE]
>  이 멤버 함수 앞 으로만 이동 가능한 레코드 집합에 대해 올바르지 않습니다.  
  
> [!NOTE]
>  레코드 집합을 이동할 때 삭제 된 레코드를 건너뛸 수 없습니다. 참조는 [IsDeleted](#isdeleted) 세부 정보에 대 한 멤버 함수입니다.  
  
> [!CAUTION]
>  중 하나를 호출는 **이동** 함수 레코드 집합에 레코드가 없는 경우 예외를 throw 합니다. 레코드 집합에 레코드가 있는지를 확인 하려면 호출 `IsBOF` 및 `IsEOF`합니다.  
  
> [!NOTE]
>  중 하나를 호출 하는 경우는 **이동** 함수 중에 현재 레코드는 업데이트 하거나 추가할 업데이트 경고 없이 손실 됩니다.  
  
 레코드 집합 탐색에 대 한 자세한 내용은 문서를 참조 [레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) 및 [레코드 집합: 책갈피와 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
### <a name="example"></a>예제  
  예를 참조 [IsBOF](#isbof)합니다.  
  
##  <a name="movelast"></a>  CRecordset::MoveLast  
 현재 레코드로 마지막 전체 행 집합의 첫 번째 레코드를 만듭니다.  
  
```  
void MoveLast();
```  
  
### <a name="remarks"></a>설명  
 레코드 집합의 높으므로 행 집합 크기가 1, 하지 대량 행 페치를 구현한 경우 `MoveLast` 단순히 마지막 레코드로 이동 레코드 집합의 합니다.  
  
> [!NOTE]
>  이 멤버 함수 앞 으로만 이동 가능한 레코드 집합에 대해 올바르지 않습니다.  
  
> [!NOTE]
>  레코드 집합을 이동할 때 삭제 된 레코드를 건너뛸 수 없습니다. 참조는 [IsDeleted](#isdeleted) 세부 정보에 대 한 멤버 함수입니다.  
  
> [!CAUTION]
>  중 하나를 호출는 **이동** 함수 레코드 집합에 레코드가 없는 경우 예외를 throw 합니다. 레코드 집합에 레코드가 있는지를 확인 하려면 호출 `IsBOF` 및 `IsEOF`합니다.  
  
> [!NOTE]
>  중 하나를 호출 하는 경우는 **이동** 함수 중에 현재 레코드는 업데이트 하거나 추가할 업데이트 경고 없이 손실 됩니다.  
  
 레코드 집합 탐색에 대 한 자세한 내용은 문서를 참조 [레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) 및 [레코드 집합: 책갈피와 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
### <a name="example"></a>예제  
  예를 참조 [IsBOF](#isbof)합니다.  
  
##  <a name="movenext"></a>  CRecordset::MoveNext  
 현재 레코드로 다음 행 집합의 첫 번째 레코드를 만듭니다.  
  
```  
void MoveNext();
```  
  
### <a name="remarks"></a>설명  
 레코드 집합의 높으므로 행 집합 크기가 1, 하지 대량 행 페치를 구현한 경우 `MoveNext` 단순히를 다음 레코드로 이동 합니다.  
  
> [!NOTE]
>  레코드 집합을 이동할 때 삭제 된 레코드를 건너뛸 수 없습니다. 참조는 [IsDeleted](#isdeleted) 세부 정보에 대 한 멤버 함수입니다.  
  
> [!CAUTION]
>  중 하나를 호출는 **이동** 함수 레코드 집합에 레코드가 없는 경우 예외를 throw 합니다. 레코드 집합에 레코드가 있는지를 확인 하려면 호출 `IsBOF` 및 `IsEOF`합니다.  
  
> [!NOTE]
>  호출 하는 것이 좋습니다 `IsEOF` 호출 하기 전에 `MoveNext`합니다. 예를 들어, 다음 레코드 집합의 끝을 지난 스크롤 `IsEOF` 는 0이 아닌; 반환 한 후속 호출에 `MoveNext` 예외를 throw 합니다.  
  
> [!NOTE]
>  중 하나를 호출 하는 경우는 **이동** 함수 중에 현재 레코드는 업데이트 하거나 추가할 업데이트 경고 없이 손실 됩니다.  
  
 레코드 집합 탐색에 대 한 자세한 내용은 문서를 참조 [레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) 및 [레코드 집합: 책갈피와 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
### <a name="example"></a>예제  
  예를 참조 [IsBOF](#isbof)합니다.  
  
##  <a name="moveprev"></a>  CRecordset::MovePrev  
 현재 레코드로 이전 행 집합의 첫 번째 레코드를 만듭니다.  
  
```  
void MovePrev();
```  
  
### <a name="remarks"></a>설명  
 레코드 집합의 높으므로 행 집합 크기가 1, 하지 대량 행 페치를 구현한 경우 `MovePrev` 단순히 이전 레코드로 이동 합니다.  
  
> [!NOTE]
>  이 멤버 함수 앞 으로만 이동 가능한 레코드 집합에 대해 올바르지 않습니다.  
  
> [!NOTE]
>  레코드 집합을 이동할 때 삭제 된 레코드를 건너뛸 수 없습니다. 참조는 [IsDeleted](#isdeleted) 세부 정보에 대 한 멤버 함수입니다.  
  
> [!CAUTION]
>  중 하나를 호출는 **이동** 함수 레코드 집합에 레코드가 없는 경우 예외를 throw 합니다. 레코드 집합에 레코드가 있는지를 확인 하려면 호출 `IsBOF` 및 `IsEOF`합니다.  
  
> [!NOTE]
>  호출 하는 것이 좋습니다 `IsBOF` 호출 하기 전에 `MovePrev`합니다. 예를 들어, 다음 레코드 집합의 시작 부분 앞 스크롤 `IsBOF` 는 0이 아닌; 반환 한 후속 호출에 `MovePrev` 예외를 throw 합니다.  
  
> [!NOTE]
>  중 하나를 호출 하는 경우는 **이동** 함수 중에 현재 레코드는 업데이트 하거나 추가할 업데이트 경고 없이 손실 됩니다.  
  
 레코드 집합 탐색에 대 한 자세한 내용은 문서를 참조 [레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) 및 [레코드 집합: 책갈피와 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
### <a name="example"></a>예제  
  예를 참조 [IsBOF](#isbof)합니다.  
  
##  <a name="onsetoptions"></a>  CRecordset::OnSetOptions  
 (선택에 사용 됨) 하는 옵션을 설정 하려면 지정한 ODBC 문에 대 한 호출 됩니다.  
  
```  
virtual void OnSetOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>매개 변수  
 `hstmt`  
 **HSTMT** ODBC 문의 해당 옵션을 설정 해야 합니다.  
  
### <a name="remarks"></a>설명  
 호출 `OnSetOptions` 지정된 ODBC 문에 대 한 (선택에 사용 됨) 하는 옵션을 설정할 수 있습니다. 프레임 워크는 레코드 집합에 대 한 초기 옵션을 설정 하려면이 멤버 함수를 호출 합니다. `OnSetOptions` 커서 동시성 및 스크롤 가능 커서에 대 한 데이터 원본 지원 하 고 그에 따라 레코드 집합의 옵션을 설정 합니다. (하지만 `OnSetOptions` 선택 작업에 사용 되 `OnSetUpdateOptions` 업데이트 작업에 사용 됩니다.)  
  
 재정의 `OnSetOptions` 드라이버 또는 데이터 소스 특정 옵션을 설정할 수 있습니다. 예를 들어 데이터 원본 단독 액세스를 위해 열기를 지원, 재정의 하 `OnSetOptions` 해당 기능을 활용할 수 있습니다.  
  
 커서에 대 한 자세한 내용은 문서 참조 [ODBC](../../data/odbc/odbc-basics.md)합니다.  
  
##  <a name="onsetupdateoptions"></a>  CRecordset::OnSetUpdateOptions  
 지정 된 ODBC 문에 대 한 옵션 (업데이트에 사용 됨)를 설정 하기 위해 호출 합니다.  
  
```  
virtual void OnSetUpdateOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>매개 변수  
 `hstmt`  
 **HSTMT** ODBC 문의 해당 옵션을 설정 해야 합니다.  
  
### <a name="remarks"></a>설명  
 호출 `OnSetUpdateOptions` 지정된 ODBC 문에 대 한 (업데이트에 사용 됨) 하는 옵션을 설정할 수 있습니다. 레코드 집합에서 레코드를 업데이트 HSTMT를 만든 후 프레임 워크에서이 멤버 함수를 호출 합니다. (하지만 `OnSetOptions` 선택 작업에 사용 되 `OnSetUpdateOptions` 업데이트 작업에 사용 됩니다.) `OnSetUpdateOptions` 커서 동시성 및 스크롤 가능 커서에 대 한 데이터 원본 지원 하 고 그에 따라 레코드 집합의 옵션을 설정 합니다.  
  
 재정의 `OnSetUpdateOptions` 해당 문을 사용 하는 데이터베이스에 액세스할 수 전에 ODBC 문의 옵션 설정입니다.  
  
 커서에 대 한 자세한 내용은 문서 참조 [ODBC](../../data/odbc/odbc-basics.md)합니다.  
  
##  <a name="open"></a>  Crecordset:: Open  
 테이블을 검색 하거나 레코드 집합을 나타내는 쿼리를 수행 하 여 레코드 집합을 엽니다.  
  
```  
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,  
    LPCTSTR lpszSQL = NULL,  
    DWORD dwOptions = none);
```  
  
### <a name="parameters"></a>매개 변수  
 `nOpenType`  
 기본 값 **AFX_DB_USE_DEFAULT_TYPE**, 또는 다음 값 중 하나에서 사용 된 **enum OpenType**:  
  
- **CRecordset::dynaset** 양방향 스크롤이 레코드 집합입니다. 레코드 집합 열릴 때 데이터 값을 다른 사용자가 변경한 패치 동작이 표시 됩니다. 멤버 자격 및 레코드의 순서가 결정 됩니다. 다이너셋의 키 집합 기반 레코드 집합 라고도 합니다.  
  
- **CRecordset::snapshot** 양방향 스크롤이 정적 레코드 집합입니다. 레코드 집합을 열면; 멤버 자격 및 레코드의 순서가 결정 됩니다. 데이터 값이 레코드는 인출 될 때 결정 됩니다. 레코드 집합을 닫고 다시 다음 될 때까지 다른 사용자가 변경한 내용이 표시 되지 않습니다.  
  
- **CRecordset::dynamic** 양방향 스크롤이 레코드 집합입니다. 멤버 자격, 정렬 및 데이터 값을 다른 사용자가 변경한 패치 동작이 표시 됩니다. 참고가 대부분의 ODBC 드라이버 이러한 형식의 레코드 집합을 지원 하지 않습니다.  
  
- **CRecordset::forwardOnly** 앞 으로만 스크롤이 읽기 전용 레코드 집합입니다.  
  
     에 대 한 `CRecordset`, 기본값은 **CRecordset::snapshot**합니다. 기본값 메커니즘은 모두 ODBC와 상호 작용 하는 Visual c + + 마법사 수 있도록 `CRecordset` 및 DAO `CDaoRecordset`를 충족 하는 기본값입니다.  
  
 이러한 레코드 집합 유형에 대 한 자세한 내용은 문서 참조 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)합니다. 관련된 정보에 대 한 "를 사용 하 여 블록 및 스크롤 가능 커서" Windows SDK에서 문서를 참조 합니다.  
  
> [!CAUTION]
>  요청 된 형식이 지원 되지 않는 경우 프레임 워크는 예외가 throw 됩니다.  
  
 `lpszSQL`  
 다음 중 하나를 포함 하는 문자열 포인터.  
  
-   A **NULL** 포인터입니다.  
  
-   테이블의 이름입니다.  
  
-   SQL **선택** 문 (선택적으로는 SQL **여기서** 또는 **ORDER BY** 절).  
  
-   A **호출** 미리 정의 된 쿼리 (저장된 프로시저)의 이름을 지정 하는 문이 있습니다. 중괄호 사이 공백을 넣지 마십시오 주의 해야 하며 **호출** 키워드입니다.  
  
 이 문자열에 대 한 자세한 내용은 테이블과 주의 아래의 클래스 마법사의 역할에 대해 토론을 참조 하십시오.  
  
> [!NOTE]
>  결과 집합의 열 순서는 RFX 순서와 일치 해야 하거나 대량 RFX 함수 호출 프로그램 [DoFieldExchange](#dofieldexchange) 또는 [DoBulkFieldExchange](#dobulkfieldexchange) 재정의 작동 합니다.  
  
 `dwOptions`  
 아래 나열 된 값의 조합을 지정할 수 있는 비트 마스크입니다. 이 중 일부는 함께 사용할 수 없습니다. 기본값은 **none**합니다.  
  
- **CRecordset::none** 아무 옵션도 설정 합니다. 이 매개 변수 값은 다른 모든 값을 함께 사용할 수 없습니다. 기본적으로 레코드 집합으로 업데이트할 수 있습니다 [편집](#edit) 또는 [삭제](#delete) 와 새 레코드를 추가할 수 있습니다. [AddNew](#addnew)합니다. 업데이트 허용 여부 뿐만 데이터 소스에 따라 다릅니다는 `nOpenType` 지정한 옵션. 대량 추가 대 한 최적화를 사용할 수 없는 경우 대량 행 페치 구현 되지 않습니다. 레코드 집합 탐색 하는 동안 삭제 된 레코드를 건너뛸 수 됩니다. 책갈피는 사용할 수 없습니다. 자동 더티 필드 검사 구현 됩니다.  
  
- **CRecordset::appendOnly** 하지 못하게 **편집** 또는 **삭제** 레코드 집합에 있습니다. 허용 `AddNew` 만 합니다. 이 옵션은 함께 사용할 수 없습니다 **CRecordset::readOnly**합니다.  
  
- **CRecordset::readOnly** 읽기 전용으로 레코드 집합을 엽니다. 이 옵션은 함께 사용할 수 없습니다 **CRecordset::appendOnly**합니다.  
  
- **CRecordset::optimizeBulkAdd** 레코드 수를 한 번에 추가 최적화 하기 위해 준비 된 SQL 문을 사용 합니다. ODBC API 함수를 사용 하지 않는 경우에 적용 **SQLSetPos** 를 레코드 집합을 업데이트 합니다. 첫 번째 업데이트 필드 커밋된 표시 되어 결정 합니다. 이 옵션은 함께 사용할 수 없습니다 `CRecordset::useMultiRowFetch`합니다.  
  
- `CRecordset::useMultiRowFetch` 여러 행을 단일 인출 작업에서 검색할 수 있도록 대량 행 페치를 구현 합니다. 이 고급 기능으로 성능이 향상을 위해 디자인 그러나 대량 레코드 필드 교환 classwizard 함께 사용 하 여 지원 되지 않습니다. 이 옵션은 함께 사용할 수 없습니다 **CRecordset::optimizeBulkAdd**합니다. 지정 하는 경우 유의 `CRecordset::useMultiRowFetch`, 다음 옵션 **CRecordset::noDirtyFieldCheck** 자동으로 켜 집니다 (이중 버퍼링은 사용할 수 없음); 앞 으로만 이동 가능한 레코드 집합, 옵션에  **CRecordset::useExtendedFetch** 자동으로 켜 집니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
- **CRecordset::skipDeletedRecords** 레코드 집합을 탐색할 경우 모든 삭제 된 레코드를 건너뜁니다. 특정 상대 인출에 있는 성능 속도가 느려집니다. 이 옵션은 앞 으로만 이동 가능한 레코드 집합에 유효 하지 않습니다. 호출 하는 경우 [이동](#move) 와 `nRows` 0으로 설정 하는 매개 변수 및 **CRecordset::skipDeletedRecords** 옵션이 설정, **이동** 어설션 됩니다. **CRecordset::skipDeletedRecords** 비슷합니다 *드라이버 압축*, 삭제 된 행을 의미 하는 레코드 집합에서 제거 됩니다. 그러나 경우 드라이버 팩 레코드, 다음 그 건너뜁니다 삭제; 레코드로 레코드 집합에 열려 있는 동안 다른 사용자가 삭제 된 레코드 건너뛰지 않습니다. **CRecordset::skipDeletedRecords** 다른 사용자가 삭제 된 행을 건너뜁니다.  
  
- **CRecordset::useBookmarks** 지원 되는 경우는 레코드 집합에서는 책갈피를 사용할 수 있습니다. 책갈피는 데이터 검색 속도가 느린 하지만 데이터 탐색에 대 한 성능 향상. 앞 으로만 이동 가능한 레코드 집합에는 유효 하지 않습니다. 자세한 내용은 문서 참조 [레코드 집합: 책갈피와 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)합니다.  
  
- **CRecordset::noDirtyFieldCheck** 더티 필드 자동 확인 (이중 버퍼링)를 해제 합니다. 이렇게 하면 성능이 향상 됩니다. 그러나 수동으로 표시 해야 필드 더티 같이 호출 하 여는 `SetFieldDirty` 및 `SetFieldNull` 멤버 함수입니다. 클래스에서 해당 이중 버퍼링 참고 `CRecordset` 이중 버퍼링 클래스에서 유사한 `CDaoRecordset`합니다. 그러나 `CRecordset`, 개별 필드에 이중 버퍼링을 사용할 수 없습니다; 모든 필드에 대해 사용 하도록 설정 하거나 모든 필드에 대해 사용 하지 않도록 설정 합니다. 옵션을 지정 하는 경우 `CRecordset::useMultiRowFetch`, 다음 **CRecordset::noDirtyFieldCheck** 켜 집니다 자동으로 소비량이 적어지지만 `SetFieldDirty` 및 `SetFieldNull` 대량 행 페치를 구현 하는 레코드 집합에서 사용할 수 없습니다.  
  
- **CRecordset::executeDirect** 준비 된 SQL 문을 사용 하지 마십시오. 경우 성능 향상된을 위해이 옵션을 지정 된 **Requery** 멤버 함수가 호출 되지 것입니다.  
  
- **CRecordset::useExtendedFetch** 구현 **SQLExtendedFetch** 대신 **SQLFetch**합니다. 이 앞 으로만 이동 가능한 레코드 집합에 대량 행 페치를 구현 하기 위한 설계 되었습니다. 옵션을 지정 하는 경우 `CRecordset::useMultiRowFetch` 앞 으로만 이동 가능한 레코드 집합에, 다음 **CRecordset::useExtendedFetch** 자동으로 켜 집니다.  
  
- **CRecordset::userAllocMultiRowBuffers** 사용자 데이터에 대 한 저장소 버퍼를 할당 합니다. 와 함께에서이 옵션을 사용 하 여 `CRecordset::useMultiRowFetch` ; 사용자 고유의 저장소를 할당 하려면 그렇지 않은 경우 프레임 워크는 자동으로 할당 필요한 저장소입니다. 자세한 내용은 문서 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다. 지정 **CRecordset::userAllocMultiRowBuffers** 지정 하지 않고 `CRecordset::useMultiRowFetch` 실패 한 어설션이 발생 합니다.  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우에는 `CRecordset` 개체 했으면 성공적으로 열린 경우 0 [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) (호출) 하는 경우 0을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 레코드 집합에 정의 된 쿼리를 실행 하려면이 멤버 함수를 호출 해야 합니다. 호출 하기 전에 **열려**, 레코드 집합 개체를 생성 해야 합니다.  
  
 이 레코드 집합의 데이터 원본이 연결을 호출 하기 전에 레코드 집합을 생성 하는 방법에 따라 달라 집니다 **열려**합니다. 전달 하는 경우는 [CDatabase](../../mfc/reference/cdatabase-class.md) 개체 데이터 소스에 연결 되지 않은 레코드 집합 생성자를 사용 하 여이 멤버 함수 [GetDefaultConnect](#getdefaultconnect) 데이터베이스 개체를 엽니다. 전달 하는 경우 **NULL** recordset 생성자에는 생성자를 생성 한 `CDatabase` , 개체 및 **열려** 데이터베이스 개체를 연결 하려고 합니다. 레코드 집합 및 이러한 다양 한 상황에서 연결을 닫지 대 한 세부 정보를 참조 하십시오. [닫기](#close)합니다.  
  
> [!NOTE]
>  통해 데이터 원본에 대 한 액세스는 `CRecordset` 항상 개체를 공유 합니다. 와 달리는 `CDaoRecordset` 사용할 수 없는 클래스는 `CRecordset` 개체를 단독으로 데이터 소스를 엽니다.  
  
 호출 하는 경우 **열려**, 일반적으로 SQL 쿼리를 **선택** 문은, 다음 표에 표시 된 조건에 따라 레코드를 선택 합니다.  
  
|LpszSQL 매개 변수 값|선택한 레코드에 따라 다릅니다.|예제|  
|------------------------------------|----------------------------------------|-------------|  
|**NULL**|반환한 문자열 `GetDefaultSQL`합니다.||  
|SQL 테이블 이름|테이블 목록의 모든 열 `DoFieldExchange` 또는 `DoBulkFieldExchange`합니다.|`"Customer"`|  
|미리 정의 된 쿼리 (저장된 프로시저) 이름|쿼리가 반환할 정의 된 열입니다.|`"{call OverDueAccts}"`|  
|**선택** 열 목록 **FROM** 테이블 목록|지정 된 테이블의 지정 된 열입니다.|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|  
  
> [!CAUTION]
>  SQL 문자열의 추가 공백을 넣지 마십시오 주의 해야 합니다. 예를 들어, 중괄호 사이 공백을 삽입 하는 경우 및 **호출** 키워드, MFC는 테이블 이름으로 SQL 문자열을 잘못 해석할에 통합 하는 **선택** 져 문에 예외가 throw 됩니다. 마찬가지로, 출력 매개 변수를 사용 하는 미리 정의 된 쿼리 넣지 마십시오 중괄호 사이 공백이 및 ' 기호입니다. 마지막으로, 앞에 중괄호가 공백 하지 삽입 해야는 **호출** 문 또는 그 전에 **선택** 키워드는 **선택** 문.  
  
 전달 하는 일반적인 절차는 **NULL** 를 **열려**;이 경우 **열려** 호출 [GetDefaultSQL](#getdefaultsql)합니다. 파생 된 사용 중인 경우 `CRecordset` 클래스 **GetDefaultSQL** 클래스 마법사에서 지정한 테이블 이름을 제공 합니다. 대신의 기타 정보를 지정할 수 있습니다는 `lpszSQL` 매개 변수입니다.  
  
 전달 무엇이 든 **열려** 쿼리에 대 한 최종 SQL 문자열을 만듭니다 (문자열 SQL 있을 수 **여기서** 및 **ORDER BY** 절에 추가 `lpszSQL` 문자열을 지 남) 한 다음 쿼리를 실행 합니다. 호출 하 여 생성 된 문자열을 검사할 수 [GetSQL](#getsql) 호출한 후 **열려**합니다. 문서를 참조 하는 레코드 SQL 문을 생성 하 고 레코드를 선택 하는 방법에 대 한 추가 세부 정보에 대 한 [레코드 집합: 레코드 집합의 레코드 선택 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)합니다.  
  
 레코드 집합 클래스의 필드 데이터 멤버는 선택한 데이터의 열에 바인딩됩니다. 레코드가 반환 되는 경우 첫 번째 레코드는 현재 레코드가 됩니다.  
  
 필터 또는 정렬 같은 레코드 집합에 대 한 옵션을 설정 하려는 경우는 레코드 집합 개체를 생성 한 후 있지만 호출 하기 전에 이러한 하 게 지정 **열려**합니다. 레코드 집합이 이미 열린 후 레코드 집합의 레코드를 새로 고칠 하려는 경우, 호출 [Requery](#requery)합니다.  
  
 추가 예제를 비롯 한 자세한 내용은 문서를 참조 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md), [레코드 집합: 레코드 집합의 레코드 선택 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md), 및 [레코드 집합: 집합 만들기 및 닫기 레코드 집합 (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제는 여러 가지 형태의 표시는 **열려** 호출 합니다.  
  
 [!code-cpp[NVC_MFCDatabase#16](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]  
  
##  <a name="refreshrowset"></a>  CRecordset::RefreshRowset  
 데이터 및 현재 행 집합의 행에 대 한 상태를 업데이트합니다.  
  
```  
void RefreshRowset(
    WORD wRow,  
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```  
  
### <a name="parameters"></a>매개 변수  
 `wRow`  
 1부터 행의 위치는 현재 행 집합의 합니다. 이 값은 행 집합의 크기는 0부터 범위 수 있습니다.  
  
 `wLockType`  
 새로 고쳐 후 행을 잠그는 방법을 나타내는 값입니다. 자세한 내용은 설명을 참조하세요.  
  
### <a name="remarks"></a>설명  
 값 0 전달 하는 경우 `wRow`을 다음 행 집합의 모든 행을 새로 고칩니다.  
  
 사용 하도록 `RefreshRowset`, 해야 구현한 지정 하 여 대량 행 페치는 **CRecordset::useMulitRowFetch** 옵션에 [열려](#open) 멤버 함수입니다.  
  
 `RefreshRowset` ODBC API 함수를 호출 **SQLSetPos**합니다. `wLockType` 후 행 잠금 상태를 지정 하는 매개 변수 **SQLSetPos** 실행 합니다. 다음 표에서 사용할 수 있는 값에 설명 `wLockType`합니다.  
  
|wLockType|설명|  
|---------------|-----------------|  
|`SQL_LOCK_NO_CHANGE` (기본값)|드라이버 또는 데이터 원본 되기 전의 행 동일한 잠금 또는 잠금 해제 된 상태 인지 확인 `RefreshRowset` 호출 되었습니다.|  
|`SQL_LOCK_EXCLUSIVE`|드라이버 또는 데이터 원본에서 행을 단독으로 잠깁니다. 일부 데이터 원본에는 이러한 유형의 잠금 지원합니다.|  
|`SQL_LOCK_UNLOCK`|드라이버 또는 데이터 원본에는 행 잠금을 해제합니다. 일부 데이터 원본에는 이러한 유형의 잠금 지원합니다.|  
  
 에 대 한 자세한 내용은 **SQLSetPos**, Windows SDK를 참조 하십시오. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
##  <a name="requery"></a>  >crecordset:: Requery  
 (새로 고침)를 다시 작성 한 레코드 집합입니다.  
  
```  
virtual BOOL Requery();
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합을 다시 작성 되었습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 레코드가 반환 되는 경우 첫 번째 레코드는 현재 레코드가 됩니다.  
  
 추가 및 삭제 또는 다른 사용자가 데이터 원본에 수행 하는 반영 하기 위해 레코드를 다시 작성 해야 레코드 집합 호출 하 여 **Requery**합니다. 레코드 집합 다이너셋 인 경우 자동으로 해당 기존 레코드 (추가 하지 않음) 또는 다른 사용자가 되도록 하는 업데이트를 반영 합니다. 레코드 집합 스냅숏일 경우 호출 해야 **Requery** 다른 사용자가 뿐만 아니라 추가 및 삭제 하 여 편집 내용을 반영 하도록 합니다.  
  
 다이너셋 또는 스냅숏으로 대 한 호출 **Requery** 언제 든 지 새 필터 또는 정렬 또는 새 매개 변수 값을 사용 하 여 레코드 집합 다시 작성 해야 합니다. 새 값을 할당 하 여 새 필터 또는 정렬 속성을 설정 **m_strFilter** 및 `m_strSort` 호출 하기 전에 **Requery**합니다. 새 값을 호출 하기 전에 매개 변수 데이터 멤버에 할당 하 여 새 매개 변수를 설정 **Requery**합니다. 필터 및 정렬 문자열 변경 되지 않은 경우 성능을 향상 시키는 쿼리를 다시 사용할 수 있습니다.  
  
 레코드 집합 다시 시도가 실패 하면 레코드 집합 닫혀 있습니다. 호출 하기 전에 **Requery**를 호출 하 여 레코드 집합 다시 쿼리되어 수 있는지 여부를 확인할 수 있습니다는 `CanRestart` 멤버 함수입니다. `CanRestart` 에서는 프로시저를 **Requery** 성공 합니다.  
  
> [!CAUTION]
>  호출 **Requery** 호출한 후에 [열려](#open)합니다.  
  
### <a name="example"></a>예제  
 이 예제에는 다른 정렬 순서를 적용 하는 레코드 집합 다시 작성 합니다.  
  
 [!code-cpp[NVC_MFCDatabase#29](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]  
  
##  <a name="setabsoluteposition"></a>  CRecordset::SetAbsolutePosition  
 지정 된 레코드 번호에 해당 하는 레코드를 레코드 집합을 배치 합니다.  
  
```  
void SetAbsolutePosition(long nRows);
```  
  
### <a name="parameters"></a>매개 변수  
 `nRows`  
 1부터 서 수 위치는 현재 레코드에 대 한 레코드 집합의 합니다.  
  
### <a name="remarks"></a>설명  
 `SetAbsolutePosition` 이 서 수 위치에 기반 하 여 현재 레코드 포인터를 이동 합니다.  
  
> [!NOTE]
>  이 멤버 함수 앞 으로만 이동 가능한 레코드 집합에 올바르지 않습니다.  
  
 ODBC 레코드 집합에 대 한 1의 절대 위치 설정을; 레코드 집합의 첫 번째 레코드를 참조 0으로 설정 파일의 시작 부분 (BOF) 위치를 나타냅니다.  
  
 음수 값을 전달할 수도 있습니다 `SetAbsolutePosition`합니다. 이 경우 위치 레코드 집합의 레코드 집합의 끝에서 평가 됩니다. 예를 들어 `SetAbsolutePosition( -1 )` 레코드 집합의 마지막 레코드를 현재 레코드 포인터를 이동 합니다.  
  
> [!NOTE]
>  절대 위치 서로게이트 레코드 수로 사용할 수 없습니다. 책갈피는 유지 하 고 이전 레코드를 삭제할 때 레코드의 위치 변경 내용을 이후 지정된 된 위치에 반환 된 것이 좋습니다. 또한 확인할 수 없습니다에 지정된 된 레코드 해야 같은 절대 위치는 를사용하여SQL문을사용하여생성되지않는한레코드집합내에서개별레코드의순서가보장되지않으므로레코드집합다시다시생성할경우**ORDER BY** 절.  
  
 레코드 집합 탐색 및 책갈피에 대 한 자세한 내용은 문서를 참조 [레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) 및 [레코드 집합: 책갈피와 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)합니다.  
  
##  <a name="setbookmark"></a>  CRecordset::SetBookmark  
 지정된 된 책갈피를 포함 하는 레코드를 레코드 집합을 배치 합니다.  
  
```  
void SetBookmark(const CDBVariant& varBookmark);
```  
  
### <a name="parameters"></a>매개 변수  
 `varBookmark`  
 에 대 한 참조는 [CDBVariant](../../mfc/reference/cdbvariant-class.md) 특정 레코드에 대 한 책갈피 값을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 책갈피 레코드 집합에서 지원 되는지 확인, 호출 [CanBookmark](#canbookmark)합니다. 지원 되는 경우 책갈피를 사용할 수 있도록 하려면 설정 해야 합니다는 **CRecordset::useBookmarks** 옵션에 `dwOptions` 의 매개 변수는 [열려](#open) 멤버 함수입니다.  
  
> [!NOTE]
>  책갈피 지원 되지 않거나 사용할 수 없는 경우 호출 `SetBookmark` 예외가 throw 됩니다. 책갈피 앞 으로만 이동 가능한 레코드 집합에서 지원 되지 않습니다.  
  
 현재 레코드에 대 한 책갈피를 먼저 검색 하려면 호출 [GetBookmark](#getbookmark), 책갈피 값을 저장 한 `CDBVariant` 개체입니다. 나중으로 돌아갈 수 있습니다 해당 레코드를 호출 하 여 `SetBookmark` 저장 된 책갈피 값을 사용 합니다.  
  
> [!NOTE]
>  특정 레코드 집합 작업이 끝난 후 호출 하기 전에 책갈피 지 속성을 확인 해야 `SetBookmark`합니다. 예를 들어, 사용 하 여 책갈피를 검색 하는 경우 `GetBookmark` 호출 **Requery**, 책갈피가 더 이상 유효 하지 않을 수 없습니다. 호출 [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) 안전 하 게 호출할 수 있는지 여부를 확인 하려면 `SetBookmark`합니다.  
  
 책갈피와 레코드 탐색에 대 한 자세한 내용은 문서를 참조 [레코드 집합: 책갈피와 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) 및 [레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)합니다.  
  
##  <a name="setfielddirty"></a>  CRecordset::SetFieldDirty  
 필드 데이터 멤버는 레코드 집합을 변경 또는 변경 되지 않은 것을 플래그 합니다.  
  
```  
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `pv`  
 레코드 집합의 필드 데이터 멤버의 주소를 포함 하거나 **NULL**합니다. 경우 **NULL**, 레코드 집합의 필드 데이터 멤버를 모든 플래그가 지정 됩니다. (C + + **NULL** 같지 않습니다 Null로 데이터베이스 용어에서 즉, "가치가 없습니다.")  
  
 `bDirty`  
 **True 이면** 필드 데이터 멤버 "더티" (변경) 것으로 플래그가 지정 되어야 하는 경우. 그렇지 않으면 **FALSE** 필드 데이터 멤버 "정리" (변경 되지 않음) 플래그 지정 하는 경우.  
  
### <a name="remarks"></a>설명  
 다음과 같이 변경 되지 않은 필드를 표시 하면 필드를 업데이트 하지 않으면 SQL 트래픽이 적습니다.  
  
> [!NOTE]
>  이 멤버 함수 대량 행 페치를 사용 하는 레코드 집합에 적용 되지 않습니다. 구현한 경우 대량 행 페치를 다음 `SetFieldDirty` 실패 한 어설션이 발생 합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
 프레임 워크 부호를 사용 하 여 필드 데이터 멤버 레코드 필드 교환 (RFX) 메커니즘에 의해 데이터 소스에서 레코드에 기록 될 됩니다 되도록 변경 합니다. 필드의 값을 일반적으로 변경 필드 설정 더티 자동으로 되므로 호출 필요가 거의 `SetFieldDirty` 하지만, 직접 할 때도 열을 명시적으로 업데이트 되거나 어떤 값이 필드 데이터에 관계 없이 삽입 확인 멤버입니다.  
  
> [!CAUTION]
>  이 멤버 함수를 호출한 후에 호출 [편집](#edit) 또는 [AddNew](#addnew)합니다.  
  
 사용 하 여 **NULL** 함수의 첫 번째 인수는 함수를에 적용 됩니다에 대 한 **outputColumn** 필드 하지 **param** 필드입니다. 예를 들어, 호출  
  
 [!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 만 설정 됩니다 **outputColumn** 필드를 **NULL**; **param** 필드에 영향을 받지 않습니다.  
  
 작동 하도록 **param** 필드, 개별의 실제 주소를 입력 해야 **param** 와 같은 작업에 대 하 시겠습니까:  
  
 [!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 즉, 설정할 수 없습니다. 모든 **param** 필드를 **NULL**있습니다, **outputColumn** 필드입니다.  
  
##  <a name="setfieldnull"></a>  CRecordset::SetFieldNull  
 Null (특히 값 예:) 또는 Null이 아닌 레코드 집합의 필드 데이터 멤버를 플래그 지정 합니다.  
  
```  
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `pv`  
 레코드 집합의 필드 데이터 멤버의 주소를 포함 하거나 **NULL**합니다. 경우 **NULL**, 레코드 집합의 필드 데이터 멤버를 모든 플래그가 지정 됩니다. (C + + **NULL** 같지 않습니다 Null로 데이터베이스 용어에서 즉, "가치가 없습니다.")  
  
 `bNull`  
 필드 데이터 멤버 (Null) 값이 없는 것으로 플래그가 지정 되어야 하는 경우에 0이 아닙니다. 필드 데이터 멤버는 Null이 아닌으로 플래그를 설정 하는 경우 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 레코드 집합에 새 레코드를 추가 하는 경우 모든 필드 데이터 멤버 처음 Null 값으로 설정 되며 "더티" (변경) 것으로 플래그가 지정 합니다. 데이터 원본에서 레코드를 검색 하는 경우 열이 이미 값 또는 null입니다.  
  
> [!NOTE]
>  대량 행 페치를 사용 하는 레코드 집합에는이 멤버 함수를 호출 하지 마십시오. 대량 행 페치를 구현한 경우 호출 `SetFieldNull` 실패 한 어설션의 결과. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
 특히 값, 호출 되지 않는 것으로 현재 레코드의 필드를 지정 하려는 경우 `SetFieldNull` 와 `bNull` 로 설정 **TRUE** Null로 플래그를 지정 합니다. 필드는 Null 이전에 표시 된 값을 지정 하려는 경우 새 값을 설정 하기만 합니다. Null 플래그를 제거할 필요가 없습니다 `SetFieldNull`합니다. 필드는 Null이 될 수 있는지 여부를 확인 하려면 호출 `IsFieldNullable`합니다.  
  
> [!CAUTION]
>  이 멤버 함수를 호출한 후에 호출 [편집](#edit) 또는 [AddNew](#addnew)합니다.  
  
 사용 하 여 **NULL** 함수의 첫 번째 인수는 함수를에 적용 됩니다에 대 한 **outputColumn** 필드 하지 **param** 필드입니다. 예를 들어, 호출  
  
 [!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 만 설정 됩니다 **outputColumn** 필드를 **NULL**; **param** 필드에 영향을 받지 않습니다.  
  
 작동 하도록 **param** 필드, 개별의 실제 주소를 입력 해야 **param** 와 같은 작업에 대 하 시겠습니까:  
  
 [!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 즉, 설정할 수 없습니다. 모든 **param** 필드를 **NULL**있습니다, **outputColumn** 필드입니다.  
  
> [!NOTE]
>  Null에 대 한 호출으로 매개 변수를 설정할 때 `SetFieldNull` 레코드 집합 어설션에 열려 있는 결과 크기를 합니다. 이 경우 호출 [SetParamNull](#setparamnull)합니다.  
  
 `SetFieldNull` 이 통해 구현 [DoFieldExchange](#dofieldexchange)합니다.  
  
##  <a name="setlockingmode"></a>  CRecordset::SetLockingMode  
 "낙관적" 잠금 (기본값) 또는 "비관적" 잠금을 잠금 모드를 설정 합니다. 업데이트에 대 한 레코드를 잠그는 방법을 결정 합니다.  
  
```  
void SetLockingMode(UINT nMode);
```  
  
### <a name="parameters"></a>매개 변수  
 `nMode`  
 다음 값 중 하나가 포함 된 **enum LockMode**:  
  
- **낙관적** 호출 하는 동안에 업데이트 되는 레코드를 잠그는 낙관적 잠금 **업데이트**합니다.  
  
- **비관적** 레코드를 잠그는 비관적 잠금 즉시 **편집** 호출 되 고 유지 될 때까지 잠겨는 **업데이트** 호출이 완료 하거나 새 레코드로 이동 합니다.  
  
### <a name="remarks"></a>설명  
 레코드 집합 업데이트를 사용 하는 두 레코드 잠금 전략 지정 하려는 경우이 함수를 호출 합니다. 기본적으로 레코드 집합의 잠금 모드는 **낙관적**합니다. 더욱 주의로 변경할 수 **비관적** 잠금 전략입니다. 호출 `SetLockingMode` 구성 하 고 레코드 집합 개체를 열거나 후 있지만 호출 하기 전에 **편집**합니다.  
  
##  <a name="setparamnull"></a>  CRecordset::SetParamNull  
 Null (특히 값 예:) 또는 Null이 아닌 매개 변수는 플래그입니다.  
  
```  
void SetParamNull(
    int nIndex,  
    BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 이 매개 변수의 0부터 시작하는 인덱스입니다.  
  
 `bNull`  
 경우 **TRUE** (기본값) 매개 변수는 Null로 플래그가 지정 됩니다. 그렇지 않으면 매개 변수가 Null이 아닌으로 플래그가 지정 됩니다.  
  
### <a name="remarks"></a>설명  
 와 달리 [SetFieldNull](#setfieldnull)를 호출할 수 있습니다 `SetParamNull` 레코드 집합을 연 전에 합니다.  
  
 `SetParamNull` 미리 정의 된 쿼리 (저장된 프로시저) 일반적으로 사용 됩니다.  
  
##  <a name="setrowsetcursorposition"></a>  CRecordset::SetRowsetCursorPosition  
 현재 행 집합 내의 행에는 커서를 이동합니다.  
  
```  
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```  
  
### <a name="parameters"></a>매개 변수  
 `wRow`  
 1부터 행의 위치는 현재 행 집합의 합니다. 이 값의 범위는 1에서 행 집합의 크기.  
  
 `wLockType`  
 새로 고쳐 후 행을 잠그는 방법을 나타내는 값입니다. 자세한 내용은 설명을 참조하세요.  
  
### <a name="remarks"></a>설명  
 대량 행 페치를 구현 하는 경우 레코드는 인출 된 행 집합의 첫 번째 레코드는 현재 레코드를 행 집합에서 검색 됩니다. 행 집합의 다른 레코드 현재 레코드를 있도록 호출 `SetRowsetCursorPosition`합니다. 예를 들어 결합할 수 있습니다 `SetRowsetCursorPosition` 와 [GetFieldValue](#getfieldvalue) 멤버 함수를 레코드 집합의 모든 레코드에서 데이터를 동적으로 검색 합니다.  
  
 사용 하도록 `SetRowsetCursorPosition`, 해야 구현한 지정 하 여 대량 행 페치는 `CRecordset::useMultiRowFetch` 옵션의는 `dwOptions` 에서 매개 변수는 [열려](#open) 멤버 함수입니다.  
  
 `SetRowsetCursorPosition` ODBC API 함수를 호출 **SQLSetPos**합니다. `wLockType` 후 행 잠금 상태를 지정 하는 매개 변수 **SQLSetPos** 실행 합니다. 다음 표에서 사용할 수 있는 값에 설명 `wLockType`합니다.  
  
|wLockType|설명|  
|---------------|-----------------|  
|`SQL_LOCK_NO_CHANGE` (기본값)|드라이버 또는 데이터 원본 되기 전의 행 동일한 잠금 또는 잠금 해제 된 상태 인지 확인 `SetRowsetCursorPosition` 호출 되었습니다.|  
|`SQL_LOCK_EXCLUSIVE`|드라이버 또는 데이터 원본에서 행을 단독으로 잠깁니다. 일부 데이터 원본에는 이러한 유형의 잠금 지원합니다.|  
|`SQL_LOCK_UNLOCK`|드라이버 또는 데이터 원본에는 행 잠금을 해제합니다. 일부 데이터 원본에는 이러한 유형의 잠금 지원합니다.|  
  
 에 대 한 자세한 내용은 **SQLSetPos**, Windows SDK를 참조 하십시오. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
##  <a name="setrowsetsize"></a>  CRecordset::SetRowsetSize  
 인출 하는 동안 검색할 레코드 수를 지정 합니다.  
  
```  
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwNewRowsetSize*  
 지정 된 인출 하는 동안 검색할 행의 수입니다.  
  
### <a name="remarks"></a>설명  
 이 가상 멤버 함수를 대량 행 페치를 사용 하는 경우 단일 인출 하는 동안 검색 하려는 행의 수를 지정 합니다. 대량 행 페치를 구현 하려면 설정 해야 합니다는 `CRecordset::useMultiRowFetch` 옵션에 `dwOptions` 의 매개 변수는 [열려](#open) 멤버 함수입니다.  
  
> [!NOTE]
>  호출 `SetRowsetSize` 대량을 구현 하지 않고 행을 인출 하면 실패 한 어설션이 합니다.  
  
 호출 `SetRowsetSize` 호출 하기 전에 **열려** 초기 레코드 집합에 대 한 행 집합 크기를 설정 합니다. 대량 행 페치를 구현 하는 경우 기본 행 집합 크기는 25입니다.  
  
> [!NOTE]
>  호출할 때 주의 해야 `SetRowsetSize`합니다. 데이터에 대 한 저장소를 수동으로 할당 하는 경우 (에 지정 된 대로 **CRecordset::userAllocMultiRowBuffers** dwOptions 매개 변수 옵션 **열려**), 해야 하는지 여부를 확인 해야 호출한 후 이러한 저장소 버퍼 다시 할당 `SetRowsetSize`, 모든 커서 탐색 작업을 수행 하기 전에.  
  
 행 집합 크기에 대 한 현재 설정을 가져오려면, 호출 [GetRowsetSize](#getrowsetsize)합니다.  
  
 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
##  <a name="update"></a>  CRecordset::Update  
 완료 되는 `AddNew` 또는 **편집** 데이터 원본에서 새로 만들거나 편집한 데이터를 저장 하 여 작업 합니다.  
  
```  
virtual BOOL Update();
```  
  
### <a name="return-value"></a>반환 값  
 하나의 레코드를 업데이트 했습니다. 0이 아닌 그렇지 않은 경우 변경 된 열이 없는 경우 0입니다. 업데이트 된 레코드가 한 레코드가 두 번 이상으로 업데이트 된 경우 예외가 throw 됩니다. 예외가 다른 모든 오류에 대 한 데이터 원본에 throw 됩니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수를 호출한 후 호출 된 [AddNew](#addnew) 또는 [편집](#edit) 멤버 함수입니다. 이 호출은 필요 완료 하는 `AddNew` 또는 **편집** 작업 합니다.  
  
> [!NOTE]
>  대량 행 페치를 구현한 경우 호출할 수 없습니다 **업데이트**합니다. 이 인해 실패 한 어설션이 발생 합니다. 하지만 클래스 `CRecordset` 메커니즘을 제공 하지 않는 데이터의 대량 행을 업데이트 하기 위한 ODBC API 함수를 사용 하 여 사용자 고유의 함수를 작성할 수 있습니다 **SQLSetPos**합니다. 대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치(ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)문서를 참조하세요.  
  
 둘 다 `AddNew` 및 **편집** 데이터 원본에 저장 하기 위한 추가 또는 편집 된 데이터가 배치 되는 편집 버퍼를 준비 합니다. **업데이트** 데이터를 저장 합니다. 표시 또는 변경 된 것으로 인식 필드만 업데이트 됩니다.  
  
 데이터 원본 트랜잭션을 지 원하는 경우 만들 수 있습니다는 **업데이트** 호출 (및 해당 `AddNew` 또는 **편집** 호출) 트랜잭션의 일부입니다. 트랜잭션에 대 한 자세한 내용은 문서 참조 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
> [!CAUTION]
>  호출 하는 경우 **업데이트** 호출 하지 `AddNew` 또는 **편집**, **업데이트** throw 한 `CDBException`합니다. 호출 하는 경우 `AddNew` 또는 **편집**를 호출 해야 **업데이트** 호출 하기 전에 **이동** 작업 레코드 집합 또는 데이터 원본 연결을 닫기 전에 또는 합니다. 그렇지 않은 경우 변경 내용을 알림 없이 손실 됩니다.  
  
 처리에 대 한 내용은 **업데이트** 오류 문서를 참조 하십시오. [레코드 집합: 레코드 집합의 레코드 업데이트 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)합니다.  
  
### <a name="example"></a>예제  
 문서를 참조 [트랜잭션: 트랜잭션이 수행 레코드 집합 (ODBC)에서](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDatabase 클래스](../../mfc/reference/cdatabase-class.md)   
 [CRecordView 클래스](../../mfc/reference/crecordview-class.md)
