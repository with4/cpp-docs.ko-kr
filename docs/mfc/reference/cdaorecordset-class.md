---
title: "CDaoRecordset Class | Microsoft Docs"
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
  - "CDaoRecordset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoRecordset 클래스"
  - "레코드, CDaoRecordSet"
  - "레코드 집합, 형식"
ms.assetid: 2322067f-1027-4662-a5d7-aa2fc7488630
caps.latest.revision: 26
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoRecordset Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터 소스에서 선택한 레코드의 집합을 나타냅니다.  
  
## 구문  
  
```  
  
class CDaoRecordset : public CObject  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDaoRecordset::CDaoRecordset](../Topic/CDaoRecordset::CDaoRecordset.md)|`CDaoRecordset` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDaoRecordset::AddNew](../Topic/CDaoRecordset::AddNew.md)|준비에 대 한 새 레코드를 추가 합니다.  호출  [업데이트](../Topic/CDaoRecordset::Update.md) 추가 완료 합니다.|  
|[CDaoRecordset::CanAppend](../Topic/CDaoRecordset::CanAppend.md)|레코드 집합을 통해 새 레코드를 추가할 수 있습니다 경우 0이 아닌 반환 된  [AddNew](../Topic/CDaoRecordset::AddNew.md) 멤버 함수.|  
|[CDaoRecordset::CanBookmark](../Topic/CDaoRecordset::CanBookmark.md)|책갈피는 레코드 집합을 지 원하는 경우 0이 아닌 값을 반환 합니다.|  
|[CDaoRecordset::CancelUpdate](../Topic/CDaoRecordset::CancelUpdate.md)|때문에 모든 보류 중인 업데이트를 취소는  [편집](../Topic/CDaoRecordset::Edit.md) 또는  [AddNew](../Topic/CDaoRecordset::AddNew.md) 작업.|  
|[CDaoRecordset::CanRestart](../Topic/CDaoRecordset::CanRestart.md)|0이 아닌 경우 반환  [Requery](../Topic/CDaoRecordset::Requery.md) 호출 레코드 집합의 쿼리를 다시 실행할 수 있습니다.|  
|[CDaoRecordset::CanScroll](../Topic/CDaoRecordset::CanScroll.md)|레코드를 스크롤할 수 있는 경우 0이 아닌 값을 반환 합니다.|  
|[CDaoRecordset::CanTransact](../Topic/CDaoRecordset::CanTransact.md)|데이터 소스가 트랜잭션을 지원할 경우 0이 아닌 값을 반환 합니다.|  
|[CDaoRecordset::CanUpdate](../Topic/CDaoRecordset::CanUpdate.md)|레코드 집합을 업데이트할 수 있는 경우에 0이 아닌 반환 \(추가, 업데이트 하거나 레코드 삭제할 수 있습니다\).|  
|[CDaoRecordset::Close](../Topic/CDaoRecordset::Close.md)|레코드 집합을 닫습니다.|  
|[CDaoRecordset::Delete](../Topic/CDaoRecordset::Delete.md)|레코드 집합에서 현재 레코드를 삭제합니다.  명시적으로 삭제 한 후 다른 레코드로 스크롤해야 합니다.|  
|[CDaoRecordset::DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md)|\(양방향\)의 데이터를 데이터 소스에서 해당 레코드와 레코드 집합의 필드 데이터 멤버 간에 교환 하기 위해 호출 됩니다.  DAO 구현 필드 교환 \(DFX\)를 기록합니다.|  
|[CDaoRecordset::Edit](../Topic/CDaoRecordset::Edit.md)|변경 내용을 현재 레코드에 대 한 준비합니다.  호출  **업데이트** 편집을 완료 합니다.|  
|[CDaoRecordset::FillCache](../Topic/CDaoRecordset::FillCache.md)|모든 채우기 또는 ODBC 데이터 원본의 데이터를 포함 하는 recordset 개체에 대 한 로컬 캐시의 일부입니다.|  
|[CDaoRecordset::Find](../Topic/CDaoRecordset::Find.md)|찾는 첫 번째, 다음, 이전 또는 마지막 위치에 지정 된 조건 및 해당 레코드를 현재 레코드로 만듭니다 만족 다이너셋 형식의 레코드 집합에서 특정 문자열의.|  
|[CDaoRecordset::FindFirst](../Topic/CDaoRecordset::FindFirst.md)|다이너셋 형식 또는 지정 된 기준 및 해당 레코드를 현재 레코드로 만듭니다 만족 스냅샷 형식 레코드 집합의 첫 번째 레코드를 찾습니다.|  
|[CDaoRecordset::FindLast](../Topic/CDaoRecordset::FindLast.md)|다이너셋 형식 또는 지정 된 기준 및 해당 레코드를 현재 레코드로 만듭니다 만족 스냅샷 형식 레코드 집합의 마지막 레코드를 찾습니다.|  
|[CDaoRecordset::FindNext](../Topic/CDaoRecordset::FindNext.md)|다이너셋 형식 또는 지정 된 기준 및 해당 레코드를 현재 레코드로 만듭니다 만족 스냅샷 형식 레코드 집합의 다음 레코드를 찾습니다.|  
|[CDaoRecordset::FindPrev](../Topic/CDaoRecordset::FindPrev.md)|다이너셋 형식 또는 지정 된 기준 및 해당 레코드를 현재 레코드로 만듭니다 만족 스냅샷 형식의 레코드 집합에서 이전 레코드를 찾습니다.|  
|[CDaoRecordset::GetAbsolutePosition](../Topic/CDaoRecordset::GetAbsolutePosition.md)|Recordset 개체에서 현재 레코드의 레코드 번호를 반환합니다.|  
|[CDaoRecordset::GetBookmark](../Topic/CDaoRecordset::GetBookmark.md)|책갈피는 레코드를 나타내는 값을 반환 합니다.|  
|[CDaoRecordset::GetCacheSize](../Topic/CDaoRecordset::GetCacheSize.md)|ODBC 데이터 원본에서 로컬로 캐시 될 데이터가 들어 있는 다이너셋 형식의 레코드 집합에서 레코드 개수를 지정 하는 값을 반환 합니다.|  
|[CDaoRecordset::GetCacheStart](../Topic/CDaoRecordset::GetCacheStart.md)|레코드 집합에서 캐시할 첫 번째 레코드의 책갈피를 지정 하는 값을 반환 합니다.|  
|[CDaoRecordset::GetCurrentIndex](../Topic/CDaoRecordset::GetCurrentIndex.md)|반환 된 `CString` 사용에 인덱스 테이블 형식 인덱스 이름이 가장 최근에 포함 된 `CDaoRecordset`.|  
|[CDaoRecordset::GetDateCreated](../Topic/CDaoRecordset::GetDateCreated.md)|기본 테이블의 기본 날짜 및 시간을 반환 된 `CDaoRecordset` 작성|  
|[CDaoRecordset::GetDateLastUpdated](../Topic/CDaoRecordset::GetDateLastUpdated.md)|날짜와 시간 원본으로 사용 된 기본 테이블의 디자인을 변경한 최신의 반환은 `CDaoRecordset` 개체입니다.|  
|[CDaoRecordset::GetDefaultDBName](../Topic/CDaoRecordset::GetDefaultDBName.md)|기본 데이터 원본의 이름을 반환합니다.|  
|[CDaoRecordset::GetDefaultSQL](../Topic/CDaoRecordset::GetDefaultSQL.md)|호출 실행에 기본 SQL 문자열을 가져옵니다.|  
|[CDaoRecordset::GetEditMode](../Topic/CDaoRecordset::GetEditMode.md)|현재 레코드의 편집 상태를 나타내는 값을 반환 합니다.|  
|[CDaoRecordset::GetFieldCount](../Topic/CDaoRecordset::GetFieldCount.md)|레코드 집합의 필드 수를 나타내는 값을 반환 합니다.|  
|[CDaoRecordset::GetFieldInfo](../Topic/CDaoRecordset::GetFieldInfo.md)|레코드 집합에서 특정 종류의 필드에 대 한 정보를 반환합니다.|  
|[CDaoRecordset::GetFieldValue](../Topic/CDaoRecordset::GetFieldValue.md)|레코드 집합에서 필드의 값을 반환합니다.|  
|[CDaoRecordset::GetIndexCount](../Topic/CDaoRecordset::GetIndexCount.md)|레코드 원본으로 사용 하는 테이블에서 인덱스를 검색 합니다.|  
|[CDaoRecordset::GetIndexInfo](../Topic/CDaoRecordset::GetIndexInfo.md)|다양 한 종류의 인덱스에 대 한 정보를 반환합니다.|  
|[CDaoRecordset::GetLastModifiedBookmark](../Topic/CDaoRecordset::GetLastModifiedBookmark.md)|가장 최근에 추가 되거나 업데이트 레코드를 확인 하는 데 사용 합니다.|  
|[CDaoRecordset::GetLockingMode](../Topic/CDaoRecordset::GetLockingMode.md)|편집 하는 동안 적용 되는 잠금 유형을 나타내는 값을 반환 합니다.|  
|[CDaoRecordset::GetName](../Topic/CDaoRecordset::GetName.md)|반환은 `CString` 레코드 집합의 이름이 들어 있습니다.|  
|[CDaoRecordset::GetParamValue](../Topic/CDaoRecordset::GetParamValue.md)|지정 된 기본 DAOParameter 개체에 저장 된 매개 변수의 현재 값을 검색 합니다.|  
|[CDaoRecordset::GetPercentPosition](../Topic/CDaoRecordset::GetPercentPosition.md)|총 레코드 수의 백분율로 현재 레코드의 위치를 반환합니다.|  
|[CDaoRecordset::GetRecordCount](../Topic/CDaoRecordset::GetRecordCount.md)|레코드 집합 개체에 액세스 하는 레코드의 수를 반환 합니다.|  
|[CDaoRecordset::GetSQL](../Topic/CDaoRecordset::GetSQL.md)|레코드 집합의 레코드를 선택 하는 데 사용 하는 SQL 문자열을 가져옵니다.|  
|[CDaoRecordset::GetType](../Topic/CDaoRecordset::GetType.md)|레코드 집합의 종류를 확인 하기 위해 호출 됩니다: 테이블 형식, 다이너셋 형식 또는 스냅숏 형식.|  
|[CDaoRecordset::GetValidationRule](../Topic/CDaoRecordset::GetValidationRule.md)|반환 된 `CString` 필드에 입력할 때 데이터의 유효성을 검사 하는 값을 포함 합니다.|  
|[CDaoRecordset::GetValidationText](../Topic/CDaoRecordset::GetValidationText.md)|유효성 검사 규칙을 만족 하지 않을 때 표시 되는 텍스트를 검색 합니다.|  
|[CDaoRecordset::IsBOF](../Topic/CDaoRecordset::IsBOF.md)|레코드 집합의 첫 번째 레코드 앞에 배치 된 경우 0이 아닌 값을 반환 합니다.  현재 레코드가 됩니다.|  
|[CDaoRecordset::IsDeleted](../Topic/CDaoRecordset::IsDeleted.md)|레코드 집합에 삭제 된 레코드에 있으면 0이 아닌 값을 반환 합니다.|  
|[CDaoRecordset::IsEOF](../Topic/CDaoRecordset::IsEOF.md)|레코드 집합의 마지막 레코드 뒤에 배치 된 경우 0이 아닌 값을 반환 합니다.  현재 레코드가 됩니다.|  
|[CDaoRecordset::IsFieldDirty](../Topic/CDaoRecordset::IsFieldDirty.md)|현재 레코드에서 지정한 필드를 변경한 경우 0이 아닌 값을 반환 합니다.|  
|[CDaoRecordset::IsFieldNull](../Topic/CDaoRecordset::IsFieldNull.md)|현재 레코드에서 지정한 필드에 Null \(값이 없는 필요\) 이면 0이 아닌 값을 반환 합니다.|  
|[CDaoRecordset::IsFieldNullable](../Topic/CDaoRecordset::IsFieldNullable.md)|현재 레코드에서 지정한 필드 \(값이 없는 것\)는 Null로 설정할 수 있는 경우 0이 아닌 값을 반환 합니다.|  
|[CDaoRecordset::IsOpen](../Topic/CDaoRecordset::IsOpen.md)|0이 아닌 경우 반환  [열려](../Topic/CDaoRecordset::Open.md) 호출 된.|  
|[CDaoRecordset::Move](../Topic/CDaoRecordset::Move.md)|레코드 집합에서에서 현재 레코드에서 지정한 레코드 개수를 배치합니다.|  
|[CDaoRecordset::MoveFirst](../Topic/CDaoRecordset::MoveFirst.md)|현재 레코드가 첫 번째 레코드는 레코드 집합에 배치 됩니다.|  
|[CDaoRecordset::MoveLast](../Topic/CDaoRecordset::MoveLast.md)|현재 레코드가 recordset의 마지막 레코드에 배치합니다.|  
|[CDaoRecordset::MoveNext](../Topic/CDaoRecordset::MoveNext.md)|다음 레코드 레코드 집합에서에서 현재 레코드를 배치합니다.|  
|[CDaoRecordset::MovePrev](../Topic/CDaoRecordset::MovePrev.md)|현재 레코드가 레코드 집합의 이전 레코드로 배치 됩니다.|  
|[CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md)|새 레코드 집합 테이블, 다이너셋, 또는 스냅샷을 만듭니다.|  
|[CDaoRecordset::Requery](../Topic/CDaoRecordset::Requery.md)|다시 선택한 레코드를 새로 고치려면 레코드 집합의 쿼리를 실행 합니다.|  
|[CDaoRecordset::Seek](../Topic/CDaoRecordset::Seek.md)|현재 인덱스 및 해당 레코드를 현재 레코드로 만듭니다 지정한 조건에 맞는 인덱싱된 테이블 형식 recordset 개체에서 레코드를 찾습니다.|  
|[CDaoRecordset::SetAbsolutePosition](../Topic/CDaoRecordset::SetAbsolutePosition.md)|Recordset 개체에서 현재 레코드의 레코드 번호를 설정합니다.|  
|[CDaoRecordset::SetBookmark](../Topic/CDaoRecordset::SetBookmark.md)|지정한 책갈피가 포함 된 레코드에 레코드 집합을 배치 합니다.|  
|[CDaoRecordset::SetCacheSize](../Topic/CDaoRecordset::SetCacheSize.md)|ODBC 데이터 원본에서 로컬로 캐시 될 데이터가 들어 있는 다이너셋 형식의 레코드 집합에서 레코드 개수를 지정 하는 값을 설정 합니다.|  
|[CDaoRecordset::SetCacheStart](../Topic/CDaoRecordset::SetCacheStart.md)|레코드 집합에서 캐시할 첫 번째 레코드의 책갈피를 지정 하는 값을 설정 합니다.|  
|[CDaoRecordset::SetCurrentIndex](../Topic/CDaoRecordset::SetCurrentIndex.md)|테이블 형식 레코드 집합에 인덱스를 설정 하기 위해 호출 됩니다.|  
|[CDaoRecordset::SetFieldDirty](../Topic/CDaoRecordset::SetFieldDirty.md)|지정한 필드는 현재 레코드에 변경 된 것으로 표시 합니다.|  
|[CDaoRecordset::SetFieldNull](../Topic/CDaoRecordset::SetFieldNull.md)|현재 레코드에 Null \(값이 없는 필요\)에 지정 된 필드의 값을 설정 합니다.|  
|[CDaoRecordset::SetFieldValue](../Topic/CDaoRecordset::SetFieldValue.md)|레코드 집합에서 필드의 값을 설정합니다.|  
|[CDaoRecordset::SetFieldValueNull](../Topic/CDaoRecordset::SetFieldValueNull.md)|Null 레코드 집합에서 필드의 값을 설정합니다.  \(값이 없는 것\).|  
|[CDaoRecordset::SetLockingMode](../Topic/CDaoRecordset::SetLockingMode.md)|편집 중에 효과 적용 하는 잠금 유형을 나타내는 값을 설정 합니다.|  
|[CDaoRecordset::SetParamValue](../Topic/CDaoRecordset::SetParamValue.md)|기본 DAOParameter 개체에 저장 된 지정 된 매개 변수의 현재 값을 설정 합니다.|  
|[CDaoRecordset::SetParamValueNull](../Topic/CDaoRecordset::SetParamValueNull.md)|Null \(값이 없는 필요\)에 지정 된 매개 변수의 현재 값을 설정 합니다.|  
|[CDaoRecordset::SetPercentPosition](../Topic/CDaoRecordset::SetPercentPosition.md)|총 레코드 집합의 백분율에 해당 하는 위치는 현재 레코드 위치를 설정 합니다.|  
|[CDaoRecordset::Update](../Topic/CDaoRecordset::Update.md)|완료 되는 `AddNew` 또는  **편집** 작업을 새로 만들거나 편집한 데이터는 데이터 원본에 저장 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDaoRecordset::m\_bCheckCacheForDirtyFields](../Topic/CDaoRecordset::m_bCheckCacheForDirtyFields.md)|필드 변경에 따라 자동으로 표시 되는지 여부를 나타내는 플래그를 포함 합니다.|  
|[CDaoRecordset::m\_nFields](../Topic/CDaoRecordset::m_nFields.md)|레코드 집합 클래스의 필드 데이터 멤버와 데이터 소스에서 레코드 집합에서 선택한 열 개수를 포함 합니다.|  
|[CDaoRecordset::m\_nParams](../Topic/CDaoRecordset::m_nParams.md)|레코드 집합 클래스에서 매개 변수 데이터 멤버의 개수, 매개 변수 개수와 레코드 집합의 쿼리를 전달|  
|[CDaoRecordset::m\_pDAORecordset](../Topic/CDaoRecordset::m_pDAORecordset.md)|레코드 집합 개체를 원본으로 사용 하는 DAO 인터페이스 포인터입니다.|  
|[CDaoRecordset::m\_pDatabase](../Topic/CDaoRecordset::m_pDatabase.md)|이 결과 집합에 대 한 원본 데이터베이스입니다.  포인터를 포함 한  [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체입니다.|  
|[CDaoRecordset::m\_strFilter](../Topic/CDaoRecordset::m_strFilter.md)|SQL를 생성 하는 데 사용 되는 문자열을 포함  **는** 문.|  
|[CDaoRecordset::m\_strSort](../Topic/CDaoRecordset::m_strSort.md)|SQL를 생성 하는 데 사용 되는 문자열을 포함  **ORDER BY** 문.|  
  
## 설명  
 "레코드"로 알려진 `CDaoRecordset` 개체는 다음과 같은 세 가지 형태로 사용할 수 있습니다.  
  
-   검토, 추가, 변경 또는 단일 데이터베이스 테이블에서 레코드를 삭제 하는 데 사용할 수 있는 기본 테이블을 테이블 형식 레코드 집합을 나타냅니다.  
  
-   다이너셋 형식의 레코드 집합은 업데이트할 수 있는 레코드는 쿼리 결과입니다.  이러한 레코드를 검사, 추가, 변경 또는 원본으로 사용 하는 하나 이상의 테이블에서 레코드를 삭제 하는 데 사용할 수 있는 레코드 집합입니다.  다이너셋 형식의 레코드 집합 필드는 데이터베이스에서 하나 이상의 테이블에에서 포함 될 수 있습니다.  
  
-   스냅샷 형식의 레코드 집합 데이터를 찾거나 보고서를 생성 하는 데 사용할 수 있는 레코드 집합의 정적 복사본입니다.  이러한 레코드 집합 필드는 데이터베이스에서 하나 이상의 테이블에에서 포함할 수 있지만 업데이트할 수 없습니다.  
  
 각 폼의 레코드 집합을 레코드 집합이 열릴 때 고정 된 레코드 집합을을 나타냅니다.  테이블 형식 레코드 집합 또는 다이너셋 형식 recordset의 레코드를 스크롤하면 다른 사용자 또는 다른 응용 프로그램에서 레코드 집합 레코드 집합을 연 후 레코드를 변경 내용을 반영 합니다.  \(스냅샷 형식 레코드 집합을 업데이트할 수 없습니다.\) 사용할 수 있는 `CDaoRecordset` 직접 나는 응용 프로그램 특정 레코드 집합 클래스에서 파생 `CDaoRecordset`.  그런 다음 아래의 작업을 수행할 수 있습니다.  
  
-   레코드를 스크롤할 수 있습니다.  
  
-   인덱스를 설정 하 고 사용 하 여 레코드를 빠르게 찾을  [검색](../Topic/CDaoRecordset::Seek.md) \(테이블 형식 레코드 집합에만 해당\).  
  
-   문자열 비교에 따라 레코드 찾기. "\<", "\< \=", "\=" "\> \=", 또는 "\>" \(다이너셋 형식 및 스냅숏 형식 레코드 집합\).  
  
-   레코드를 업데이트 하 고 스냅샷 형식의 레코드 집합\) \(예외는 잠금 모드를 지정 합니다.  
  
-   사용 가능한 데이터 소스를 선택 하는 레코드를 제한 하는 레코드 집합을 필터링 합니다.  
  
-   레코드 집합을 정렬 합니다.  
  
-   선택을 런타임까지 알 수 없는 정보를 사용자 지정 하는 레코드 집합을 매개 변수화 합니다.  
  
 클래스 `CDaoRecordset` 클래스와 비슷한 인터페이스를 제공 합니다. `CRecordset`.  해당 클래스의 주요 차이점입니다 `CDaoRecordset` 통해는 DAO \(데이터 액세스 개체에 OLE를 기반으로\) 데이터 액세스.  클래스 `CRecordset` 해당 DBMS에 대 한 개방형 데이터베이스 연결 \(ODBC\) 및 ODBC 드라이버를 통해 DBMS에 액세스 합니다.  
  
> [!NOTE]
>  DAO 데이터베이스 클래스는 개방형 데이터베이스 연결 \(ODBC\)에 따라 MFC 데이터베이스 클래스와는 별개입니다.  모든 DAO 데이터베이스 클래스 이름을 "CDao" 접두사가 있습니다.  여전히 DAO 클래스가 ODBC 데이터 소스를 액세스 할 수 있습니다. DAO 클래스 이므로 Microsoft Jet 데이터베이스 엔진에 특정 일반적으로 탁월한 능력을 제공 합니다.  
  
 사용 수 `CDaoRecordset` 직접 또는 파생 클래스에서 `CDaoRecordset`.  어느 경우 든 레코드 집합 클래스를 사용 하는 데이터베이스를 열고 생성자에 대 한 포인터를 전달 하는 recordset 개체를 만드는 사용자 `CDaoDatabase` 개체입니다.  또한 생성할 수 있습니다는 `CDaoRecordset` 개체 및 임시 만들 MFC가 `CDaoDatabase` 개체를.  다음 레코드 집합의 호출  [열려](../Topic/CDaoRecordset::Open.md) 멤버 함수를 테이블 형식 레코드 집합, 다이너셋 형식 레코드 집합 또는 스냅숏 형식 recordset 개체의 여부를 지정 합니다.  호출  **열려** 데이터베이스에서 데이터를 선택 하 고 첫 번째 레코드를 검색 합니다.  
  
 레코드를 스크롤할 및 작동에 개체의 멤버 함수와 데이터 멤버를 사용 합니다.  테이블 형식 레코드 집합, 다이너셋 형식 레코드 집합 또는 스냅샷 형식의 레코드 집합 개체 인지 업데이트할 수 있거나 읽기 전용 여부에 사용 가능한 작업 다릅니다\-이 개방형 데이터베이스 연결 \(ODBC\) 데이터 원본 또는 데이터베이스의 기능에 따라 달라 집니다.  변경 했거나 이후 추가 된 레코드를 새로 고칠 수 있는  **열기** 호출, 호출 개체의  [Requery](../Topic/CDaoRecordset::Requery.md) 멤버 함수.  호출 개체의  **닫기** 멤버 함수와 함께 마치면 개체 파괴.  
  
 `CDaoRecordset`DAO 레코드 필드 교환 \(DFX\)의 형식 안전 C\+\+ 멤버를 통해 읽고 레코드 필드의 업데이트를 지원 하기 위해 사용을 `CDaoRecordset` 또는 `CDaoRecordset`\-클래스를 파생 합니다.  동적 바인딩 열 데이터베이스를 사용 하 여 DFX 메커니즘을 사용 하지 않고 구현할 수도 있습니다  [GetFieldValue](../Topic/CDaoRecordset::GetFieldValue.md) 및  [SetFieldValue](../Topic/CDaoRecordset::SetFieldValue.md).  
  
 관련된 정보를 보려면 DAO 도움말의 "Recordset 개체" 항목을 참조 하십시오.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoRecordset`  
  
## 요구 사항  
 **헤더:**  afxdao.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)