---
title: "CRecordset Class | Microsoft Docs"
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
  - "CRecordset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRecordset class"
  - "database records [C++]"
  - "ODBC 레코드 집합[C++], CRecordset 개체"
  - "sets of records [C++]"
ms.assetid: dd89a21d-ef39-4aab-891b-1e373d67c855
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRecordset Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터 소스에서 선택한 레코드의 집합을 나타냅니다.  
  
## 구문  
  
```  
class CRecordset : public CObject  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CRecordset::CRecordset](../Topic/CRecordset::CRecordset.md)|`CRecordset` 개체를 생성합니다.  파생된 클래스가이 호출 하는 생성자를 제공 해야 합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CRecordset::AddNew](../Topic/CRecordset::AddNew.md)|준비에 대 한 새 레코드를 추가 합니다.  호출 `Update` 추가 완료 합니다.|  
|[CRecordset::CanAppend](../Topic/CRecordset::CanAppend.md)|레코드 집합을 통해 새 레코드를 추가할 수 있습니다 경우 0이 아닌 반환 된 `AddNew` 멤버 함수.|  
|[CRecordset::CanBookmark](../Topic/CRecordset::CanBookmark.md)|책갈피는 레코드 집합을 지 원하는 경우 0이 아닌 값을 반환 합니다.|  
|[CRecordset::Cancel](../Topic/CRecordset::Cancel.md)|두 번째 스레드가 프로세스 또는 비동기 작업을 취소합니다.|  
|[CRecordset::CancelUpdate](../Topic/CRecordset::CancelUpdate.md)|때문에 모든 보류 중인 업데이트를 취소는 `AddNew` 또는 `Edit` 작업.|  
|[CRecordset::CanRestart](../Topic/CRecordset::CanRestart.md)|0이 아닌 경우 반환 `Requery` 호출 레코드 집합의 쿼리를 다시 실행할 수 있습니다.|  
|[CRecordset::CanScroll](../Topic/CRecordset::CanScroll.md)|레코드를 스크롤할 수 있는 경우 0이 아닌 값을 반환 합니다.|  
|[CRecordset::CanTransact](../Topic/CRecordset::CanTransact.md)|데이터 소스가 트랜잭션을 지원할 경우 0이 아닌 값을 반환 합니다.|  
|[CRecordset::CanUpdate](../Topic/CRecordset::CanUpdate.md)|레코드 집합을 업데이트할 수 있는 경우에 0이 아닌 반환 \(추가, 업데이트 하거나 레코드 삭제할 수 있습니다\).|  
|[CRecordset::CheckRowsetError](../Topic/CRecordset::CheckRowsetError.md)|레코드를 가져오는 동안 발생 한 오류를 처리 하기 위해 호출 됩니다.|  
|[CRecordset::Close](../Topic/CRecordset::Close.md)|레코드 집합을 닫고 ODBC  **HSTMT** 에 연결 합니다.|  
|[CRecordset::Delete](../Topic/CRecordset::Delete.md)|레코드 집합에서 현재 레코드를 삭제합니다.  명시적으로 삭제 한 후 다른 레코드로 스크롤해야 합니다.|  
|[CRecordset::DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md)|대량 데이터 원본에서 데이터 레코드 집합 행을 교환 하기 위해 호출 됩니다.  대량 레코드 필드 교환을 \(Bulk RFX\)를 구현 합니다.|  
|[CRecordset::DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)|\(양방향\)의 데이터를 데이터 소스에서 해당 레코드와 레코드 집합의 필드 데이터 멤버 간에 교환 하기 위해 호출 됩니다.  Implements 필드 교환 RFX \(\)를 기록합니다.|  
|[CRecordset::Edit](../Topic/CRecordset::Edit.md)|변경 내용을 현재 레코드에 대 한 준비합니다.  호출 `Update` 편집을 완료 합니다.|  
|[CRecordset::FlushResultSet](../Topic/CRecordset::FlushResultSet.md)|다른 결과 이면 0이 아닌 반환 미리 정의 된 쿼리를 사용 하는 경우 검색을 설정 합니다.|  
|[CRecordset::GetBookmark](../Topic/CRecordset::GetBookmark.md)|레코드의 책갈피 값을 매개 변수 개체에 할당합니다.|  
|[CRecordset::GetDefaultConnect](../Topic/CRecordset::GetDefaultConnect.md)|기본 연결 문자열을 가져오기 위해 호출 됩니다.|  
|[CRecordset::GetDefaultSQL](../Topic/CRecordset::GetDefaultSQL.md)|호출 실행에 기본 SQL 문자열을 가져옵니다.|  
|[CRecordset::GetFieldValue](../Topic/CRecordset::GetFieldValue.md)|레코드 집합에서 필드의 값을 반환합니다.|  
|[CRecordset::GetODBCFieldCount](../Topic/CRecordset::GetODBCFieldCount.md)|레코드 집합에 필드 수를 반환합니다.|  
|[CRecordset::GetODBCFieldInfo](../Topic/CRecordset::GetODBCFieldInfo.md)|레코드 집합에서 특정 종류의 필드에 대 한 정보를 반환합니다.|  
|[CRecordset::GetRecordCount](../Topic/CRecordset::GetRecordCount.md)|레코드 집합에서 레코드 개수를 반환합니다.|  
|[CRecordset::GetRowsetSize](../Topic/CRecordset::GetRowsetSize.md)|단일 페치 프로세스에서 검색할 레코드 수를 반환 합니다.|  
|[CRecordset::GetRowsFetched](../Topic/CRecordset::GetRowsFetched.md)|페치 중에 검색 되는 행의 실제 번호를 반환 합니다.|  
|[CRecordset::GetRowStatus](../Topic/CRecordset::GetRowStatus.md)|반입 된 행의 상태를 반환합니다.|  
|[CRecordset::GetSQL](../Topic/CRecordset::GetSQL.md)|레코드 집합의 레코드를 선택 하는 데 사용 하는 SQL 문자열을 가져옵니다.|  
|[CRecordset::GetStatus](../Topic/CRecordset::GetStatus.md)|레코드 집합의 상태를 가져옵니다: 인덱스의 현재 레코드와 마지막 레코드 개수를 얻은 여부입니다.|  
|[CRecordset::GetTableName](../Topic/CRecordset::GetTableName.md)|레코드 집합의 기반이 되는 테이블의 이름을 가져옵니다.|  
|[CRecordset::IsBOF](../Topic/CRecordset::IsBOF.md)|레코드 집합의 첫 번째 레코드 앞에 배치 된 경우 0이 아닌 값을 반환 합니다.  현재 레코드가 됩니다.|  
|[CRecordset::IsDeleted](../Topic/CRecordset::IsDeleted.md)|레코드 집합에 삭제 된 레코드에 있으면 0이 아닌 값을 반환 합니다.|  
|[CRecordset::IsEOF](../Topic/CRecordset::IsEOF.md)|레코드 집합의 마지막 레코드 뒤에 배치 된 경우 0이 아닌 값을 반환 합니다.  현재 레코드가 됩니다.|  
|[CRecordset::IsFieldDirty](../Topic/CRecordset::IsFieldDirty.md)|현재 레코드에서 지정한 필드를 변경한 경우 0이 아닌 값을 반환 합니다.|  
|[CRecordset::IsFieldNull](../Topic/CRecordset::IsFieldNull.md)|현재 레코드의 지정 된 필드가 null 이면 0이 아닌 반환 \(값이\).|  
|[CRecordset::IsFieldNullable](../Topic/CRecordset::IsFieldNullable.md)|현재 레코드에서 지정한 필드 \(값이 없는 것\)를 null로 설정할 수 있는 경우 0이 아닌 값을 반환 합니다.|  
|[CRecordset::IsOpen](../Topic/CRecordset::IsOpen.md)|0이 아닌 경우 반환 `Open` 호출 된.|  
|[CRecordset::Move](../Topic/CRecordset::Move.md)|레코드 집합에서에서 현재 레코드에서 지정한 레코드 개수를 배치합니다.|  
|[CRecordset::MoveFirst](../Topic/CRecordset::MoveFirst.md)|현재 레코드가 첫 번째 레코드는 레코드 집합에 배치 됩니다.  테스트에 대 한 `IsBOF` 첫 번째.|  
|[CRecordset::MoveLast](../Topic/CRecordset::MoveLast.md)|현재 레코드에서 마지막 레코드 또는 마지막 행에 배치합니다.  테스트에 대 한 `IsEOF` 첫 번째.|  
|[CRecordset::MoveNext](../Topic/CRecordset::MoveNext.md)|다음 레코드 또는 다음 행 집합에서 현재 레코드를 배치합니다.  테스트에 대 한 `IsEOF` 첫 번째.|  
|[CRecordset::MovePrev](../Topic/CRecordset::MovePrev.md)|현재 레코드에 이전 레코드 또는 이전 행 집합에 배치 됩니다.  테스트에 대 한 `IsBOF` 첫 번째.|  
|[CRecordset::OnSetOptions](../Topic/CRecordset::OnSetOptions.md)|\(선택한 사용\) 옵션을 설정 하려면 지정한 ODBC 문에 대해 호출 됩니다.|  
|[CRecordset::OnSetUpdateOptions](../Topic/CRecordset::OnSetUpdateOptions.md)|\(업데이트 시 사용\) 옵션에 대해 지정한 ODBC 문을 설정 하기 위해 호출 됩니다.|  
|[CRecordset::Open](../Topic/CRecordset::Open.md)|테이블을 검색 하거나 레코드 집합을 나타내는 쿼리를 수행 하 여 레코드 집합을 엽니다.|  
|[CRecordset::RefreshRowset](../Topic/CRecordset::RefreshRowset.md)|데이터 및 지정 된 행의 상태를 새로 고칩니다.|  
|[CRecordset::Requery](../Topic/CRecordset::Requery.md)|다시 선택한 레코드를 새로 고치려면 레코드 집합의 쿼리를 실행 합니다.|  
|[CRecordset::SetAbsolutePosition](../Topic/CRecordset::SetAbsolutePosition.md)|레코드 집합에 지정 된 레코드 번호를 해당 레코드를 배치 합니다.|  
|[CRecordset::SetBookmark](../Topic/CRecordset::SetBookmark.md)|레코드 집합에서 책갈피가 지정 된 레코드에 배치 합니다.|  
|[CRecordset::SetFieldDirty](../Topic/CRecordset::SetFieldDirty.md)|지정한 필드는 현재 레코드에 변경 된 것으로 표시 합니다.|  
|[CRecordset::SetFieldNull](../Topic/CRecordset::SetFieldNull.md)|현재 레코드에 null \(값이 없는 필요\)에 지정 된 필드의 값을 설정 합니다.|  
|[CRecordset::SetLockingMode](../Topic/CRecordset::SetLockingMode.md)|"최적" 잠금 \(기본값\) 또는 "비관적" 잠금 잠금 모드를 설정 합니다.  업데이트에 대 한 레코드를 잠그는 방법을 결정 합니다.|  
|[CRecordset::SetParamNull](../Topic/CRecordset::SetParamNull.md)|지정한 매개 변수가 null \(값이 없는 것\)을 설정 합니다.|  
|[CRecordset::SetRowsetCursorPosition](../Topic/CRecordset::SetRowsetCursorPosition.md)|지정한 행 집합 내의 행에 커서를 배치합니다.|  
|[CRecordset::SetRowsetSize](../Topic/CRecordset::SetRowsetSize.md)|페치 중에 검색 하려는 레코드 수를 지정 합니다.|  
|[CRecordset::Update](../Topic/CRecordset::Update.md)|완료 되는 `AddNew` 또는 `Edit` 작업을 새로 만들거나 편집한 데이터는 데이터 원본에 저장 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CRecordset::m\_hstmt](../Topic/CRecordset::m_hstmt.md)|레코드 집합에 대 한 ODBC 명령문 핸들을 포함 합니다.  `HSTMT`를 입력합니다.|  
|[CRecordset::m\_nFields](../Topic/CRecordset::m_nFields.md)|레코드 집합의 필드 데이터 멤버를 포함합니다.  `UINT`를 입력합니다.|  
|[CRecordset::m\_nParams](../Topic/CRecordset::m_nParams.md)|레코드 집합에서 매개 변수 데이터 멤버를 포함합니다.  `UINT`를 입력합니다.|  
|[CRecordset::m\_pDatabase](../Topic/CRecordset::m_pDatabase.md)|포함에 대 한 포인터는 `CDatabase` 개체를 통해 레코드 집합에 연결 된 데이터 소스에.|  
|[CRecordset::m\_strFilter](../Topic/CRecordset::m_strFilter.md)|포함 된 `CString` 구조적 쿼리 언어 \(SQL\)를 지정 하는 `WHERE` 절.  필터로 특정 조건에 맞는 레코드만 선택 하는 데 사용 합니다.|  
|[CRecordset::m\_strSort](../Topic/CRecordset::m_strSort.md)|포함 된 `CString` SQL를 지정 하는 `ORDER BY` 절.  레코드 정렬 되는 방식을 제어 하는 데 사용 합니다.|  
  
## 설명  
 "레코드"로 알려진 `CRecordset` 개체는 일반적으로 두 가지 형태로 사용: 다이너셋 및 스냅샷.  다이너셋은 다른 사용자가 변경한 데이터 업데이트와 동기화 합니다.  데이터의 정적 뷰는 스냅숏입니다.  각 폼 레코드 집합을 열 때 고정 된 레코드 집합을 나타내지만 다이너셋은 레코드로 스크롤할 때 이후에 레코드를 다른 사용자 또는 다른 응용 프로그램에서 레코드 집합으로 변경 내용을 반영 합니다.  
  
> [!NOTE]
>  개방형 데이터베이스 연결 \(ODBC\) 클래스 대신 데이터 액세스 개체 \(DAO\) 클래스를 작업 하는 경우 클래스 사용  [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 대신 합니다.  자세한 내용은  [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md).  
  
 두 가지 레코드 집합을 사용 하 여 일반적으로 응용 프로그램 특정 레코드 집합 클래스에서 파생 `CRecordset`.  레코드 집합은 데이터 소스에서 레코드를 선택 하 고 있습니다.  
  
-   레코드를 스크롤할 수 있습니다.  
  
-   레코드를 업데이트 하 고 잠금 모드를 지정 합니다.  
  
-   사용 가능한 데이터 소스를 선택 하는 레코드를 제한 하는 레코드 집합을 필터링 합니다.  
  
-   레코드 집합을 정렬 합니다.  
  
-   선택을 런타임까지 알 수 없는 정보를 사용자 지정 하는 레코드 집합을 매개 변수화 합니다.  
  
 클래스를 사용 하는 데이터베이스를 열고 생성자에 대 한 포인터를 전달 하는 recordset 개체를 만드는 사용자 `CDatabase` 개체입니다.  그런 다음 레코드 집합의 호출  **열려** 멤버 함수를 개체는 다이너셋 또는 스냅샷 인지 지정할 수 있습니다.  호출  **열려** 데이터 원본에서 데이터를 선택 합니다.  레코드 집합 개체를 연 후에 작동 하 고 레코드를 스크롤할 멤버 함수와 데이터 멤버를 사용 합니다.  업데이트할 수 있거나 읽기 전용인 지 여부 사용 가능한 작업 개체는 다이너셋 또는 스냅샷 인지에 따라 다릅니다 \(개방형 데이터베이스 연결 \(ODBC\) 데이터 소스의 기능에 따라\), 및 대량 행 페치가 구현 여부.  변경 했거나 이후 추가 된 레코드를 새로 고칠 수 있는  **열기** 호출, 호출 개체의  **Requery** 멤버 함수.  호출 개체의  **닫기** 멤버 함수와 함께 마치면 개체 파괴.  
  
 파생 된 `CRecordset` 클래스, 레코드 필드 교환 \(RFX\) 또는 대량 레코드 필드 교환 \(Bulk RFX\) 읽고 레코드 필드의 업데이트를 지원 하는 데 사용 됩니다.  
  
 레코드 집합 및 레코드 필드 교환에 대 한 자세한 내용은 문서를 참조 하십시오.  [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md),  [레코드 집합 \(ODBC\)](../../data/odbc/recordset-odbc.md),  [레코드 집합: 레코드 페치 대량 \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md), 및  [RFX \(레코드 필드 교환\)](../../data/odbc/record-field-exchange-rfx.md).  스냅샷 및 다이너셋에 초점에 대 한 문서를 참고 하십시오.  [다이너셋](../../data/odbc/dynaset.md) 및  [스냅샷](../../data/odbc/snapshot.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CRecordset`  
  
## 요구 사항  
 **헤더:**  afxdb.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CRecordView Class](../../mfc/reference/crecordview-class.md)