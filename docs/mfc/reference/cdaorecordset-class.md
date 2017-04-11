---
title: "CDaoRecordset 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoRecordset
- AFXDAO/CDaoRecordset
- AFXDAO/CDaoRecordset::CDaoRecordset
- AFXDAO/CDaoRecordset::AddNew
- AFXDAO/CDaoRecordset::CanAppend
- AFXDAO/CDaoRecordset::CanBookmark
- AFXDAO/CDaoRecordset::CancelUpdate
- AFXDAO/CDaoRecordset::CanRestart
- AFXDAO/CDaoRecordset::CanScroll
- AFXDAO/CDaoRecordset::CanTransact
- AFXDAO/CDaoRecordset::CanUpdate
- AFXDAO/CDaoRecordset::Close
- AFXDAO/CDaoRecordset::Delete
- AFXDAO/CDaoRecordset::DoFieldExchange
- AFXDAO/CDaoRecordset::Edit
- AFXDAO/CDaoRecordset::FillCache
- AFXDAO/CDaoRecordset::Find
- AFXDAO/CDaoRecordset::FindFirst
- AFXDAO/CDaoRecordset::FindLast
- AFXDAO/CDaoRecordset::FindNext
- AFXDAO/CDaoRecordset::FindPrev
- AFXDAO/CDaoRecordset::GetAbsolutePosition
- AFXDAO/CDaoRecordset::GetBookmark
- AFXDAO/CDaoRecordset::GetCacheSize
- AFXDAO/CDaoRecordset::GetCacheStart
- AFXDAO/CDaoRecordset::GetCurrentIndex
- AFXDAO/CDaoRecordset::GetDateCreated
- AFXDAO/CDaoRecordset::GetDateLastUpdated
- AFXDAO/CDaoRecordset::GetDefaultDBName
- AFXDAO/CDaoRecordset::GetDefaultSQL
- AFXDAO/CDaoRecordset::GetEditMode
- AFXDAO/CDaoRecordset::GetFieldCount
- AFXDAO/CDaoRecordset::GetFieldInfo
- AFXDAO/CDaoRecordset::GetFieldValue
- AFXDAO/CDaoRecordset::GetIndexCount
- AFXDAO/CDaoRecordset::GetIndexInfo
- AFXDAO/CDaoRecordset::GetLastModifiedBookmark
- AFXDAO/CDaoRecordset::GetLockingMode
- AFXDAO/CDaoRecordset::GetName
- AFXDAO/CDaoRecordset::GetParamValue
- AFXDAO/CDaoRecordset::GetPercentPosition
- AFXDAO/CDaoRecordset::GetRecordCount
- AFXDAO/CDaoRecordset::GetSQL
- AFXDAO/CDaoRecordset::GetType
- AFXDAO/CDaoRecordset::GetValidationRule
- AFXDAO/CDaoRecordset::GetValidationText
- AFXDAO/CDaoRecordset::IsBOF
- AFXDAO/CDaoRecordset::IsDeleted
- AFXDAO/CDaoRecordset::IsEOF
- AFXDAO/CDaoRecordset::IsFieldDirty
- AFXDAO/CDaoRecordset::IsFieldNull
- AFXDAO/CDaoRecordset::IsFieldNullable
- AFXDAO/CDaoRecordset::IsOpen
- AFXDAO/CDaoRecordset::Move
- AFXDAO/CDaoRecordset::MoveFirst
- AFXDAO/CDaoRecordset::MoveLast
- AFXDAO/CDaoRecordset::MoveNext
- AFXDAO/CDaoRecordset::MovePrev
- AFXDAO/CDaoRecordset::Open
- AFXDAO/CDaoRecordset::Requery
- AFXDAO/CDaoRecordset::Seek
- AFXDAO/CDaoRecordset::SetAbsolutePosition
- AFXDAO/CDaoRecordset::SetBookmark
- AFXDAO/CDaoRecordset::SetCacheSize
- AFXDAO/CDaoRecordset::SetCacheStart
- AFXDAO/CDaoRecordset::SetCurrentIndex
- AFXDAO/CDaoRecordset::SetFieldDirty
- AFXDAO/CDaoRecordset::SetFieldNull
- AFXDAO/CDaoRecordset::SetFieldValue
- AFXDAO/CDaoRecordset::SetFieldValueNull
- AFXDAO/CDaoRecordset::SetLockingMode
- AFXDAO/CDaoRecordset::SetParamValue
- AFXDAO/CDaoRecordset::SetParamValueNull
- AFXDAO/CDaoRecordset::SetPercentPosition
- AFXDAO/CDaoRecordset::Update
- AFXDAO/CDaoRecordset::m_bCheckCacheForDirtyFields
- AFXDAO/CDaoRecordset::m_nFields
- AFXDAO/CDaoRecordset::m_nParams
- AFXDAO/CDaoRecordset::m_pDAORecordset
- AFXDAO/CDaoRecordset::m_pDatabase
- AFXDAO/CDaoRecordset::m_strFilter
- AFXDAO/CDaoRecordset::m_strSort
dev_langs:
- C++
helpviewer_keywords:
- recordsets, types
- CDaoRecordset class
- records, CDaoRecordSet
ms.assetid: 2322067f-1027-4662-a5d7-aa2fc7488630
caps.latest.revision: 26
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
ms.openlocfilehash: bd211f55e2a07ef2d0c61e039df526fc2cd654f4
ms.lasthandoff: 04/01/2017

---
# <a name="cdaorecordset-class"></a>CDaoRecordset 클래스
데이터 소스에서 선택한 레코드 집합을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDaoRecordset : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoRecordset::CDaoRecordset](#cdaorecordset)|`CDaoRecordset` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoRecordset::AddNew](#addnew)|새 레코드를 추가 하기 위한 준비 합니다. 호출 [업데이트](#update) 추가 완료 합니다.|  
|[CDaoRecordset::CanAppend](#canappend)|새 레코드를 통해 레코드 집합에 추가할 수 있으면 0이 아닌 반환는 [AddNew](#addnew) 멤버 함수입니다.|  
|[CDaoRecordset::CanBookmark](#canbookmark)|레코드 집합에서 책갈피를 지 원하는 경우 0이 아닌 값을 반환 합니다.|  
|[CDaoRecordset::CancelUpdate](#cancelupdate)|취소로 인해 모든 보류 중인 업데이트는 [편집](#edit) 또는 [AddNew](#addnew) 작업 합니다.|  
|[CDaoRecordset::CanRestart](#canrestart)|0이 아닌 경우 반환 [Requery](#requery) 레코드 집합의 쿼리를 다시 실행 하기 위해 호출할 수 있습니다.|  
|[CDaoRecordset::CanScroll](#canscroll)|레코드를 스크롤할 수 있으면 0이 아닌 값을 반환 합니다.|  
|[CDaoRecordset::CanTransact](#cantransact)|데이터 소스에서 트랜잭션을 지원 하면 0이 아닌 값을 반환 합니다.|  
|[CDaoRecordset::CanUpdate](#canupdate)|레코드 집합을 업데이트할 수 있으면 0이 아닌 반환 (있습니다 수 추가, 업데이트 또는 삭제 레코드).|  
|[CDaoRecordset::Close](#close)|레코드 집합을 닫습니다.|  
|[CDaoRecordset::Delete](#delete)|레코드 집합에서 현재 레코드를 삭제합니다. 삭제 후 명시적으로 다른 레코드로 스크롤하여 해야 합니다.|  
|[CDaoRecordset::DoFieldExchange](#dofieldexchange)|레코드 집합의 필드 데이터 멤버와 데이터 원본에 있는 해당 레코드 간에 (양방향)으로 데이터를 교환 하기 위해 호출 합니다. 구현 DAO 레코드 필드 교환 (DFX).|  
|[CDaoRecordset::Edit](#edit)|현재 레코드에 변경 내용에 대해 준비합니다. 호출 **업데이트** 편집을 완료 합니다.|  
|[CDaoRecordset::FillCache](#fillcache)|모든 채우기 또는 ODBC 데이터 원본에서 데이터를 포함 하는 레코드 집합 개체에 대 한 로컬 캐시의 일부입니다.|  
|[CDaoRecordset::Find](#find)|첫째, 다음을 찾습니다. 지정 된 조건 및 현재 레코드로 설정에 맞는 다이너셋 형식의 레코드 집합에서 특정 문자열의 이전 또는 마지막 위치입니다.|  
|[CDaoRecordset::FindFirst](#findfirst)|다이너셋 형식 또는 현재 레코드로 설정 확인 하 고 지정 된 조건을 충족 하는 스냅숏 형식 레코드 집합의 첫 번째 레코드를 찾습니다.|  
|[CDaoRecordset::FindLast](#findlast)|다이너셋 형 또는 현재 레코드로 설정 확인 하 고 지정 된 조건을 충족 하는 스냅숏 형식 레코드 집합의 마지막 레코드를 찾습니다.|  
|[CDaoRecordset::FindNext](#findnext)|다이너셋 형식 또는 현재 레코드로 설정 확인 하 고 지정 된 조건을 충족 하는 스냅숏 형식 레코드 집합의 다음 레코드를 찾습니다.|  
|[CDaoRecordset::FindPrev](#findprev)|다이너셋 형식 또는 현재 레코드로 설정 확인 하 고 지정 된 조건을 충족 하는 스냅숏 형식 레코드 집합의 이전 레코드를 찾습니다.|  
|[CDaoRecordset::GetAbsolutePosition](#getabsoluteposition)|레코드 집합 개체의 현재 레코드의 레코드 번호를 반환합니다.|  
|[CDaoRecordset::GetBookmark](#getbookmark)|레코드에서 책갈피를 나타내는 값을 반환 합니다.|  
|[CDaoRecordset::GetCacheSize](#getcachesize)|ODBC 데이터 원본에서 로컬로 캐시할 데이터를 포함 하는 다이너셋 형식의 레코드 집합에서 레코드의 수를 지정 하는 값을 반환 합니다.|  
|[CDaoRecordset::GetCacheStart](#getcachestart)|캐시할 레코드 집합의 첫 번째 레코드의 책갈피를 지정 하는 값을 반환 합니다.|  
|[CDaoRecordset::GetCurrentIndex](#getcurrentindex)|반환 된 `CString` 인덱스, 테이블 형식에 사용 되는 이름을 포함 하는 인덱스의 가장 최근에 `CDaoRecordset`합니다.|  
|[CDaoRecordset::GetDateCreated](#getdatecreated)|기본 테이블의 기본 날짜 및 시간 반환는 `CDaoRecordset` 개체가 만들어진|  
|[CDaoRecordset::GetDateLastUpdated](#getdatelastupdated)|반환 날짜 및 시간을 가장 최근의 변경 내용이 원본 기본 테이블의 디자인에 대 한 `CDaoRecordset` 개체입니다.|  
|[CDaoRecordset::GetDefaultDBName](#getdefaultdbname)|기본 데이터 원본의 이름을 반환합니다.|  
|[CDaoRecordset::GetDefaultSQL](#getdefaultsql)|기본 SQL 문자열 실행을 가져오기 위해 호출 됩니다.|  
|[CDaoRecordset::GetEditMode](#geteditmode)|현재 레코드의 편집 상태를 나타내는 값을 반환 합니다.|  
|[CDaoRecordset::GetFieldCount](#getfieldcount)|레코드 집합의 필드 수를 나타내는 값을 반환 합니다.|  
|[CDaoRecordset::GetFieldInfo](#getfieldinfo)|레코드 집합의 특정 종류의 필드에 대 한 정보를 반환합니다.|  
|[CDaoRecordset::GetFieldValue](#getfieldvalue)|레코드 집합에서 필드의 값을 반환합니다.|  
|[CDaoRecordset::GetIndexCount](#getindexcount)|레코드 집합을 기본 테이블의 인덱스 수를 검색 합니다.|  
|[CDaoRecordset::GetIndexInfo](#getindexinfo)|다양 한 종류의 인덱스에 대 한 정보를 반환합니다.|  
|[CDaoRecordset::GetLastModifiedBookmark](#getlastmodifiedbookmark)|가장 최근에 추가 되거나 레코드 업데이트를 확인 하는 데 사용 합니다.|  
|[CDaoRecordset::GetLockingMode](#getlockingmode)|편집 하는 동안 적용 되는 잠금 유형을 나타내는 값을 반환 합니다.|  
|[CDaoRecordset::GetName](#getname)|반환 된 `CString` 레코드 집합의 이름을 포함 합니다.|  
|[CDaoRecordset::GetParamValue](#getparamvalue)|기본 DAOParameter 개체에 저장 된 지정된 된 매개 변수의 현재 값을 검색 합니다.|  
|[CDaoRecordset::GetPercentPosition](#getpercentposition)|레코드의 총 수의 백분율 현재 레코드의 위치를 반환 합니다.|  
|[CDaoRecordset::GetRecordCount](#getrecordcount)|레코드 집합 개체에 액세스 하는 레코드의 수를 반환 합니다.|  
|[CDaoRecordset::GetSQL](#getsql)|레코드 집합에 대 한 레코드를 선택 하는 데 SQL 문자열을 가져옵니다.|  
|[CDaoRecordset::GetType](#gettype)|레코드 집합의 형식을 결정 하기 위해 호출 됩니다: 테이블 형식, 다이너셋 형식 또는 스냅숏 형식입니다.|  
|[CDaoRecordset::GetValidationRule](#getvalidationrule)|반환 된 `CString` 필드에 입력 데이터의 유효성을 검사 하는 값이 들어 있는입니다.|  
|[CDaoRecordset::GetValidationText](#getvalidationtext)|유효성 검사 규칙을 만족 하지 않을 때 표시 되는 텍스트를 검색 합니다.|  
|[CDaoRecordset::IsBOF](#isbof)|레코드 집합의 첫 번째 레코드 바로 앞 배치 된 경우 0이 아닌 값을 반환 합니다. 현재 기록이 없습니다.|  
|[CDaoRecordset::IsDeleted](#isdeleted)|레코드 집합 삭제 된 레코드에 배치 되는 경우 0이 아닌 값을 반환 합니다.|  
|[CDaoRecordset::IsEOF](#iseof)|레코드 집합 마지막 레코드 뒤 배치 된 경우 0이 아닌 값을 반환 합니다. 현재 기록이 없습니다.|  
|[CDaoRecordset::IsFieldDirty](#isfielddirty)|현재 레코드에 지정된 된 필드 정보가 변경 된 경우 0이 아닌 값을 반환 합니다.|  
|[CDaoRecordset::IsFieldNull](#isfieldnull)|현재 레코드에 지정된 된 필드 (예: 값 없음) Null 이면 0이 아닌 값을 반환 합니다.|  
|[CDaoRecordset::IsFieldNullable](#isfieldnullable)|현재 레코드에 지정된 된 필드 (예: 값 없음) 하는 Null로 설정할 수 있는 경우 0이 아닌 값을 반환 합니다.|  
|[CDaoRecordset::IsOpen](#isopen)|0이 아닌 경우 반환 [열려](#open) 가 이전에 호출 되었습니다.|  
|[CDaoRecordset::Move](#move)|어느 방향으로든에서 현재 레코드에서 지정된 된 수의 레코드를 레코드 집합을 배치합니다.|  
|[CDaoRecordset::MoveFirst](#movefirst)|레코드 집합의 첫 번째 레코드를 현재 레코드를 배치합니다.|  
|[CDaoRecordset::MoveLast](#movelast)|레코드 집합의 마지막 레코드를 현재 레코드를 배치합니다.|  
|[CDaoRecordset::MoveNext](#movenext)|레코드 집합의 다음 레코드를 현재 레코드를 배치합니다.|  
|[CDaoRecordset::MovePrev](#moveprev)|레코드 집합의 이전 레코드를 현재 레코드를 배치합니다.|  
|[Cdaorecordset:: Open](#open)|테이블, 다이너셋, 또는 스냅숏에서 새 레코드 집합을 만듭니다.|  
|[CDaoRecordset::Requery](#requery)|레코드 집합의 쿼리를 선택된 된 레코드를 새로 고치려면 다시 실행 합니다.|  
|[CDaoRecordset::Seek](#seek)|현재 인덱스 및 현재 레코드로 설정에 대 한 지정 된 조건을 충족 하는 인덱싱된 테이블 형식 레코드 집합 개체에 레코드를 찾습니다.|  
|[CDaoRecordset::SetAbsolutePosition](#setabsoluteposition)|레코드 집합 개체의 현재 레코드의 레코드 번호를 설정합니다.|  
|[CDaoRecordset::SetBookmark](#setbookmark)|지정된 된 책갈피를 포함 하는 레코드를 레코드 집합을 배치 합니다.|  
|[CDaoRecordset::SetCacheSize](#setcachesize)|ODBC 데이터 원본에서 로컬로 캐시할 데이터를 포함 하는 다이너셋 형식의 레코드 집합에서 레코드의 수를 지정 하는 값을 설정 합니다.|  
|[CDaoRecordset::SetCacheStart](#setcachestart)|캐시할 레코드 집합의 첫 번째 레코드의 책갈피를 지정 하는 값을 설정 합니다.|  
|[CDaoRecordset::SetCurrentIndex](#setcurrentindex)|테이블 형식 레코드 집합에 인덱스를 설정 하기 위해 호출 합니다.|  
|[CDaoRecordset::SetFieldDirty](#setfielddirty)|변경 되는 현재 레코드에 지정된 된 필드를 표시 합니다.|  
|[CDaoRecordset::SetFieldNull](#setfieldnull)|Null (예: 값 없음)로 현재 레코드에 지정된 된 필드의 값을 설정 합니다.|  
|[CDaoRecordset::SetFieldValue](#setfieldvalue)|레코드 집합에서 필드의 값을 설정합니다.|  
|[CDaoRecordset::SetFieldValueNull](#setfieldvaluenull)|Null로 레코드 집합에서 필드의 값을 설정합니다. (예: 값 없음).|  
|[CDaoRecordset::SetLockingMode](#setlockingmode)|반영 하도록 편집 하는 동안 잠금 유형을 나타내는 값을 설정 합니다.|  
|[CDaoRecordset::SetParamValue](#setparamvalue)|기본 DAOParameter 개체에 저장 된 지정된 된 매개 변수의 현재 값을 설정|  
|[CDaoRecordset::SetParamValueNull](#setparamvaluenull)|지정된 된 매개 변수의 현재 값 (예: 값 없음) Null로 설정 합니다.|  
|[CDaoRecordset::SetPercentPosition](#setpercentposition)|레코드 집합에 있는 레코드의 총 수의 백분율에 해당 하는 위치를 현재 레코드의 위치를 설정 합니다.|  
|[CDaoRecordset::Update](#update)|완료 되는 `AddNew` 또는 **편집** 데이터 원본에서 새로 만들거나 편집한 데이터를 저장 하 여 작업 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[Cdaorecordset:: M_bcheckcachefordirtyfields](#m_bcheckcachefordirtyfields)|변경 된 것으로 필드는 자동으로 표시 여부를 나타내는 플래그를 포함 합니다.|  
|[CDaoRecordset::m_nFields](#m_nfields)|레코드 집합 클래스의 필드 데이터 멤버의 수와 데이터 소스에서 레코드 집합에서 선택한 열 수가 포함 되어 있습니다.|  
|[CDaoRecordset::m_nParams](#m_nparams)|레코드 집합 클래스의 매개 변수 데이터 멤버의 개수가-레코드 집합의 쿼리와 함께 전달 되는 매개 변수 개수|  
|[CDaoRecordset::m_pDAORecordset](#m_pdaorecordset)|레코드 집합 개체를 원본 DAO 인터페이스에 대 한 포인터입니다.|  
|[CDaoRecordset::m_pDatabase](#m_pdatabase)|이 결과 집합에 대 한 원본 데이터베이스입니다. 에 대 한 포인터를 포함 한 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체입니다.|  
|[CDaoRecordset::m_strFilter](#m_strfilter)|SQL을 구성 하는 데 사용 하는 문자열이 포함 된 **여기서** 문.|  
|[CDaoRecordset::m_strSort](#m_strsort)|SQL을 구성 하는 데 사용 하는 문자열이 포함 된 **ORDER BY** 문.|  
  
## <a name="remarks"></a>설명  
 "레코드"로 알려진 `CDaoRecordset` 다음과 같은 세 가지 형태로 사용할 수 있는 개체:  
  
-   테이블 형식의 레코드를 검사, 추가, 변경 또는 단일 데이터베이스 테이블에서 레코드를 삭제 하는 데 사용할 수 있는 기본 테이블을 나타냅니다.  
  
-   다이너셋 형식의 레코드 집합은 업데이트할 수 있는 레코드를 가질 수 있는 쿼리 결과입니다. 이러한 레코드 집합은 검사, 추가, 변경 또는 원본으로 사용 하는 데이터베이스 테이블 또는 테이블에서 레코드를 삭제 하는 데 사용할 수 있는 레코드 집합이 있습니다. 다이너셋 형식 레코드는 데이터베이스에 하나 이상의 테이블에서 필드를 포함할 수 있습니다.  
  
-   스냅숏 형식 레코드 집합은 데이터를 찾거나 보고서를 생성 하는 데 사용할 수 있는 레코드 집합의 정적 복사본입니다. 이러한 레코드는 데이터베이스에 하나 이상의 테이블에서 필드를 포함할 수 있지만 업데이트할 수 없습니다.  
  
 레코드 집합의 각 형태 레코드 집합이 열릴 때 고정 레코드 집합을 나타냅니다. 테이블 형식 레코드 집합 또는 다이너셋 형식의 레코드 집합에서 레코드를 스크롤할 때 다른 사용자 또는 응용 프로그램의 다른 레코드 집합의 레코드 집합을 연 후에 레코드에 변경한 내용을 반영 합니다. (스냅숏 형식 레코드 집합을 업데이트할 수 없습니다.) 사용할 수 있습니다 `CDaoRecordset` 직접에서 응용 프로그램 관련 레코드 집합 클래스를 파생 하거나 `CDaoRecordset`합니다. 그런 다음 다음을 수행할 수 있습니다.  
  
-   레코드를 스크롤하십시오.  
  
-   인덱스를 설정 하 고 사용 하 여 레코드를 신속 하 게 찾고 [Seek](#seek) (테이블 형식 레코드 집합에만 해당).  
  
-   문자열 비교를 기반으로 레코드 찾기: "<",></",>\<=", "=" "> =", 또는 ">" (다이너셋 형식 및 스냅숏 형식 레코드 집합).  
  
-   레코드를 업데이트 하 고 스냅숏 형식 레코드 집합) (제외 잠금 모드를 지정 합니다.  
  
-   데이터 원본에서 사용 가능한 선택 레코드를 제한 하는 레코드 집합을 필터링 합니다.  
  
-   레코드 집합을 정렬 합니다.  
  
-   런타임이 될 때까지 알 수 없는 정보로 해당 선택 항목을 사용자 지정 하는 레코드 집합 매개 변수화 합니다.  
  
 클래스 `CDaoRecordset` 클래스의 것과 비슷한 인터페이스를 제공 `CRecordset`합니다. 주요 차이점은 해당 클래스 `CDaoRecordset` OLE에 따라 데이터 액세스 개체 (DAO)를 통해 데이터에 액세스 합니다. 클래스 `CRecordset` DBMS를 DBMS에 대 한 ODBC Open Database Connectivity () 및 ODBC 드라이버를 통해 액세스 합니다.  
  
> [!NOTE]
>  DAO 데이터베이스 클래스에 ODBC Open Database Connectivity ()를 기반으로 하는 MFC 데이터베이스 클래스와 다릅니다. 모든 DAO 데이터베이스 클래스 이름이 "CDao" 접두사가 있습니다. 여전히 DAO 클래스; ODBC 데이터 원본에 액세스할 수 있습니다. DAO 클래스 Microsoft Jet 데이터베이스 엔진에 특정 때문에 일반적으로 뛰어난 기능을 제공 합니다.  
  
 사용 하거나 `CDaoRecordset` 직접에서 클래스를 파생 하거나 `CDaoRecordset`합니다. 두 경우 모두 레코드 집합 클래스를 사용 하려면 데이터베이스를 열고 생성자에 대 한 포인터에 전달 하는 레코드 집합 개체를 생성 하면 `CDaoDatabase` 개체입니다. 생성할 수도 있습니다는 `CDaoRecordset` MFC 임시 개체를 `CDaoDatabase` 있습니다에 대 한 개체입니다. 레코드 집합의 다음 호출 [열려](#open) 테이블 형식의 레코드 집합, 다이너셋 형식의 레코드 집합 또는 스냅숏 형식 레코드 집합 개체 인지를 지정 하는 멤버 함수를 합니다. 호출 **열려** 데이터베이스에서 데이터를 선택 하 고 첫 번째 레코드를 검색 합니다.  
  
 개체의 멤버 함수 및 데이터 멤버를 사용 하 여 작업할 및 레코드를 스크롤합니다. 사용 가능한 작업 개체 인지 여부는 테이블 형식의 레코드 집합, 다이너셋 형식 recordset 스냅숏 형식 레코드 집합 및 업데이트 가능 하거나 읽기 전용 인지에 따라 달라 집니다-데이터베이스 연결 ODBC (Open Database) 데이터 원본 등의 기능에 따라 다릅니다. 새로 고침 레코드 변경 되거나 이후 추가 된 수에 **열려** 호출, 개체의 [Requery](#requery) 멤버 함수입니다. 개체의 **닫기** 멤버 함수를 함께 했으면 개체를 삭제 합니다.  
  
 `CDaoRecordset`DAO 레코드 필드 교환 (DFX)의 형식이 안전한 c + + 멤버를 통해 읽기 및 레코드 필드의 업데이트를 지원 하기 위해 사용 하 여 프로그램 `CDaoRecordset` 또는 `CDaoRecordset`-클래스를 파생 합니다. 사용 하 여 DFX 메커니즘을 사용 하지 않고 데이터베이스의 열 동적 바인딩을 구현할 수도 있습니다 [GetFieldValue](#getfieldvalue) 및 [SetFieldValue](#setfieldvalue)합니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "Recordset 개체" 항목을 참조 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoRecordset`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
##  <a name="addnew"></a>CDaoRecordset::AddNew  
 테이블 형식 또는 다이너셋 형식의 레코드 집합에 새 레코드를 추가 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual void AddNew();
```  
  
### <a name="remarks"></a>주의  
 레코드의 필드는 처음 Null입니다. (데이터베이스 용어에서 Null 의미 "가치가 없습니다" 아니며 동일 **NULL** c + +에서.) 작업을 완료 하려면 호출 해야 합니다는 [업데이트](#update) 멤버 함수입니다. **업데이트** 데이터 소스에 변경 내용을 저장 합니다.  
  
> [!CAUTION]
>  레코드를 편집 하 고 호출 하지 않고 다른 레코드로 스크롤한 다음 경우 **업데이트**, 변경 내용을 경고 없이 손실 됩니다.  
  
 호출 하 여 다이너셋 형식의 레코드 집합에 레코드를 추가 하는 경우 [AddNew](#addnew), 레코드를 레코드 집합에 표시 되 고의 원본으로 사용 하는 테이블에서는 전혀 인식 새로운 포함 `CDaoRecordset` 개체입니다.  
  
 새 레코드의 위치 레코드 집합의 유형에 따라 달라 집니다.  
  
-   다이너셋 형식의 레코드 집합을 새 레코드를 삽입 하는 보장 되지 않습니다. 이 동작의 성능과 동시성의 이유로 Microsoft Jet 3.0으로 변경 합니다. 이 단계의 목표는 현재 레코드 새로 추가 된 레코드를 확인 하는 것을 마지막으로 수정 된 레코드의 책갈피 가져오고 해당 책갈피로 이동 합니다.  
  
 [!code-cpp[NVC_MFCDatabase # 1](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]  
  
-   index가 지정 된 테이블 형식의 레코드 집합의 정렬 순서에서 적절 한 위치에서 레코드가 반환 됩니다. 인덱스가 없는 지정 된 경우 새 레코드가 레코드 집합의 끝에 반환 됩니다.  
  
 사용 하기 전에 현재 레코드가 `AddNew` 현재 상태로 유지 됩니다. 현재 새 레코드를 확인 하 고 레코드 집합 책갈피, 호출을 지 원하는 경우 [SetBookmark](#setbookmark) 기본 DAO 레코드 집합 개체의 LastModified 속성 설정에 의해 식별 된 책갈피를 합니다. 이렇게 하는 것은 추가 된 레코드의 카운터 (자동 증분) 필드에 대 한 값을 판별한 유용 합니다. 자세한 내용은 참조 [GetLastModifiedBookmark](#getlastmodifiedbookmark)합니다.  
  
 데이터베이스 트랜잭션을 지 원하는 경우 만들 수 있습니다 프로그램 `AddNew` 트랜잭션의 일부를 호출 합니다. 트랜잭션에 대 한 자세한 내용은 클래스를 참조 하십시오. [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)합니다. 호출 해야 하는 참고 [CDaoWorkspace::BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans) 호출 하기 전에 `AddNew`합니다.  
  
 호출할 수 없는 `AddNew` 레코드 집합에 대 한 해당 [열려](#open) 멤버 함수가 호출 되지 않았습니다. A `CDaoException` 호출 하는 경우 throw 되 `AddNew` 에 대 한 레코드 집합에 추가할 수 없습니다. 레코드 집합을 호출 하 여 업데이트할 수 있는지 여부를 확인할 수 있습니다 [CanAppend](#canappend)합니다.  
  
 프레임 워크 부호를 사용 하 여 읽기 전용 이므로 DAO 레코드 필드 교환 (DFX) 메커니즘을 통해 데이터 소스에서 레코드에 기록 될 됩니다 되도록 필드 데이터 멤버 필드의 값을 일반적으로 변경 필드 설정 더티 자동으로 되므로 호출 필요가 거의 [SetFieldDirty](#setfielddirty) 하지만, 직접 할 때도 열은 명시적으로 업데이트 되거나 삽입 될 어떤 값이 필드 데이터 멤버에 관계 없이 확인 합니다. DFX 메커니즘의 사용을 손쉽게 **의사 NULL**합니다. 자세한 내용은 참조 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)합니다.  
  
 이중 버퍼링 메커니즘을 사용 하지 않는 경우 다음 필드의 값을 변경 설정 되지 않습니다 필드 커밋되지 않은 것으로 합니다. 이 경우 커밋되지 않은 데이터 필드를 명시적으로 설정 해야 합니다. 에 포함 된 플래그 [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) 이 자동 필드 검사를 제어 합니다.  
  
> [!NOTE]
>  레코드가 이중 버퍼링 된 경우 (즉, 자동 필드 검사 사용), 호출 `CancelUpdate` 하기 전에 있던 값을 멤버 변수를 복원 합니다 `AddNew` 또는 **편집** 호출 되었습니다.  
  
 관련된 정보에 대 한 "AddNew 메서드", "CancelUpdate 메서드", "LastModified Property" 및 DAO 도움말의 "EditMode Property" 항목을 참조 합니다.  
  
##  <a name="canappend"></a>CDaoRecordset::CanAppend  
 이전에 열린된 레코드 집합 수를 호출 하 여 새 레코드를 추가할 수 있는지 여부를 확인 하려면이 멤버 함수 호출의 [AddNew](#addnew) 멤버 함수입니다.  
  
```  
BOOL CanAppend() const;  
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합; 새 레코드를 추가할 수 있습니다. 0이 아닌 그렇지 않으면 0입니다. `CanAppend`읽기 전용으로 레코드 집합을 연 경우에 0을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 관련된 정보에 대 한 DAO 도움말의 "추가 방법" 항목을 참조 합니다.  
  
##  <a name="canbookmark"></a>CDaoRecordset::CanBookmark  
 개별적으로 책갈피를 사용 하 여 레코드를 표시 하 여 이전에 열린된 레코드 집합 수 있는지 여부를 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL CanBookmark();
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합 책갈피, 그렇지 않으면 0을 지 원하는 경우에 0이 아닙니다.  
  
### <a name="remarks"></a>주의  
 Microsoft Jet 데이터베이스 엔진 테이블 전적으로 기반으로 하는 레코드 집합을 사용 하는 경우 앞 으로만 이동 가능한 스크롤 레코드 집합으로 플래그가 지정 되는 스냅숏 형식 레코드 집합에 제외 하 고 책갈피에 사용할 수 있습니다. 다른 데이터베이스 제품 (외부 ODBC 데이터 원본)에서 책갈피를 지원 하지 않습니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "책갈피를 설정할 Property" 항목을 참조 합니다.  
  
##  <a name="cancelupdate"></a>CDaoRecordset::CancelUpdate  
 `CancelUpdate` 로 인해 모든 보류 중인 업데이트를 취소 하는 멤버 함수는 [편집](#edit) 또는 [AddNew](#addnew) 작업 합니다.  
  
```  
virtual void CancelUpdate();
```  
  
### <a name="remarks"></a>주의  
 예를 들어, 응용 프로그램을 호출 하는 경우는 **편집** 또는 `AddNew` 멤버 함수 및 호출 되지 않은 [업데이트](#update), `CancelUpdate` 이후의 모든 변경 내용을 취소 **편집** 또는 `AddNew` 호출 되었습니다.  
  
> [!NOTE]
>  레코드가 이중 버퍼링 된 경우 (즉, 자동 필드 검사 사용), 호출 `CancelUpdate` 하기 전에 있던 값을 멤버 변수를 복원 합니다 `AddNew` 또는 **편집** 호출 되었습니다.  
  
 없는 경우 없는 **편집** 또는 `AddNew` 작업을 보류 `CancelUpdate` MFC 예외를 throw 하면 합니다. 호출 된 [GetEditMode](#geteditmode) 멤버 함수를 취소할 수 있는 보류 중인 작업이 있는지 확인 합니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "CancelUpdate Method" 항목을 참조 합니다.  
  
##  <a name="canrestart"></a>CDaoRecordset::CanRestart  
 레코드 집합의 쿼리 (해당 레코드를 새로 고침)를 호출 하 여 다시 시작을 허용 하는지 여부를 확인 하려면이 멤버 함수 호출의 **Requery** 멤버 함수입니다.  
  
```  
BOOL CanRestart();
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우 **Requery** 레코드 집합의 쿼리를 다시 그렇지 않으면 0을 실행 하기 위해 호출할 수 있습니다.  
  
### <a name="remarks"></a>주의  
 테이블 형식 레코드 집합을 지원 하지 않는 **Requery**합니다.  
  
 경우 **Requery** 은 호출 지원 되지 않습니다 [닫기](#close) 다음 [열려](#open) 데이터 새로 고침 합니다. 호출할 수 있습니다 **Requery** recordset 개체를 업데이트 원본으로 사용 매개 변수 쿼리 매개 변수 값 변경 된 후입니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "다시 시작 가능 Property" 항목을 참조 합니다.  
  
##  <a name="canscroll"></a>CDaoRecordset::CanScroll  
 레코드 집합 스크롤을 허용 하는지 여부를 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL CanScroll() const;  
```  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면 0 레코드를 통해 스크롤할 수 있으면 0이 아닙니다.  
  
### <a name="remarks"></a>주의  
 호출 하는 경우 [열려](#open) 와 **dbForwardOnly**, 레코드 집합 앞으로 스크롤하여만 볼 수 있습니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "DAO를 사용 하 여 현재 레코드 포인터 위치 지정" 항목을 참조 합니다.  
  
##  <a name="cantransact"></a>CDaoRecordset::CanTransact  
 레코드 집합 트랜잭션을 허용 하는지 여부를 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL CanTransact();
```  
  
### <a name="return-value"></a>반환 값  
 데이터 원본에서 트랜잭션, 그렇지 않으면 0을 지 원하는 경우에 0이 아닙니다.  
  
### <a name="remarks"></a>설명  
 관련된 정보에 대 한 DAO 도움말의 "트랜잭션 Property" 항목을 참조 합니다.  
  
##  <a name="canupdate"></a>CDaoRecordset::CanUpdate  
 레코드 집합을 업데이트할 수 있는지 여부를 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합을 업데이트할 수 있으면 0이 아닌 (추가, 업데이트 및 삭제 레코드), 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 레코드 집합 수 읽기 전용 데이터 원본에는 읽기 전용 또는 지정한 경우 **dbReadOnly** 에 대 한 `nOptions` 호출할 때 [열려](#open) 레코드 집합에 대 한 합니다.  
  
 관련된 정보에 대 한 "AddNew 메서드", "편집 메서드", "Delete 메서드", "Update 메서드" 및 "업데이트할 수 있는 속성" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="cdaorecordset"></a>CDaoRecordset::CDaoRecordset  
 `CDaoRecordset` 개체를 생성합니다.  
  
```  
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDatabase`  
 에 대 한 포인터를 포함 한 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체 또는 값 **NULL**합니다. 그렇지 않은 경우 **NULL** 및 `CDaoDatabase` 개체의 **열고** 데이터 원본에 연결 하는 데 멤버 함수가 호출 되지 않은, 레코드 집합 자체는 동안를 열려고 시도 [열](#open) 호출 합니다. 전달 하는 경우 **NULL**, `CDaoDatabase` 개체 생성 되어에서 레코드 집합 클래스를 파생 하는 경우 지정한 데이터 원본 정보를 사용 하 여 연결 된 `CDaoRecordset`합니다.  
  
### <a name="remarks"></a>설명  
 사용 하거나 `CDaoRecordset` 직접에서 응용 프로그램 관련 클래스를 파생 하거나 `CDaoRecordset`합니다. 레코드 집합 클래스를 파생 클래스 마법사를 사용할 수 있습니다.  
  
> [!NOTE]
>  파생 하는 경우는 `CDaoRecordset` 클래스를 파생 프로그램 클래스는 해당 생성자를 제공 해야 합니다. 파생된 클래스의 생성자에서 생성자를 호출 `CDaoRecordset::CDaoRecordset`을 따라 적절 한 매개 변수를 전달 합니다.  
  
 전달 **NULL** 있어야 recordset 생성자에는 `CDaoDatabase` 개체 구현 되 고 하기 위해 자동으로 연결 합니다. 이것은 생성 하 고 연결할 필요가 없는 유용한 바로 가기는 `CDaoDatabase` 레코드 집합을 생성 하기 전에 개체입니다. 경우는 `CDaoDatabase` 개체 열려 있지 않으면는 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 개체의 기본 작업 영역을 사용 하 여을 생성 됩니다. 자세한 내용은 참조 [CDaoDatabase::CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase)합니다.  
  
##  <a name="close"></a>CDaoRecordset::Close  
 닫기는 `CDaoRecordset` 개체 관련된 데이터베이스에서 열려 있는 레코드 집합이의 컬렉션에서 제거 합니다.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>주의  
 때문에 **닫기** 제거 하지 않습니다는 `CDaoRecordset` 개체를 호출 하 여 개체를 다시 사용할 수 있습니다 **열려** 동일한 데이터 원본 또는 다른 데이터 원본에 있습니다.  
  
 보류 중인 모든 [AddNew](#addnew) 또는 [편집](#edit) 문이 취소 되 고 보류 중인 모든 트랜잭션이 롤백됩니다. 보류 중인 추가 또는 편집에 유지 하려는 경우 호출 [업데이트](#update) 호출 하기 전에 **닫기** 각 레코드 집합에 대 한 합니다.  
  
 호출할 수 있습니다 **열려** 호출 후에 다시 **닫기**합니다. 이 레코드 집합 개체를 다시 사용할 수 있습니다. 호출 하는 것이 더 좋은 것 [Requery](#requery), 가능한 경우.  
  
 관련된 정보에 대 한 "Close 메서드" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="delete"></a>CDaoRecordset::Delete  
 열려 있는 다이너셋 형식 또는 테이블 형식 recordset 개체의 현재 레코드를 삭제 하려면이 함수를 호출 합니다.  
  
```  
virtual void Delete();
```  
  
### <a name="remarks"></a>주의  
 성공적으로 삭제 후에 레코드 집합의 필드 데이터 멤버는 Null 값으로 설정 되 고 레코드 집합 탐색 멤버 함수 중 하나를 명시적으로 호출 해야 합니다 ( [이동](#move), [Seek](#seek), [SetBookmark](#setbookmark)등)는 삭제 된 레코드에서 이동 하려면. 레코드 집합에서 레코드를 삭제 하면 현재 레코드에에서 있어야 레코드 집합 호출 하기 전에 **삭제**고, 그렇지 않으면, MFC 예외를 throw 합니다.  
  
 **삭제** 현재 레코드를 제거 하 고 액세스할 수 없게 합니다. 편집 하거나 삭제 된 레코드를 사용할 수 없습니다, 있지만 현재 유지 됩니다. 하지만 다른 레코드로 이동은 만들지 않습니다는 삭제 된 레코드 현재 다시.  
  
> [!CAUTION]
>  레코드 집합을 업데이트할 수 있어야 하며 있어야 유효한 레코드를 레코드 집합의 현재 호출 하는 경우 **삭제**합니다. 예를 들어 레코드를 삭제 하지만 호출 하기 전에 새 레코드로 스크롤되지 않습니다 **삭제** 다시 **삭제** throw 한 [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다.  
  
 트랜잭션을 사용 하는 경우 호출 하면 레코드를 삭제 취소할 수 있습니다는 [CDaoWorkspace::Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) 멤버 함수입니다. 기본 테이블은 기본 테이블을 계단식으로 관계를 삭제 합니다. 현재 레코드를 삭제 하면 외래 테이블의 하나 이상의 레코드도 삭제 될 수 있습니다. 자세한 내용은 DAO 도움말의 정의 "cascade를 삭제"를 참조 하십시오.  
  
 와 달리 `AddNew` 및 **편집**에 대 한 호출 **삭제** 다음에 대 한 호출에 나타나지 않으면 **업데이트**합니다.  
  
 관련된 정보에 대 한 "AddNew 메서드", "편집 메서드", "Delete 메서드", "Update 메서드" 및 "업데이트할 수 있는 속성" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="dofieldexchange"></a>CDaoRecordset::DoFieldExchange  
 프레임 워크는 자동으로 레코드 집합 개체의 필드 데이터 멤버와 데이터 소스에서 현재 레코드의 해당 열 간에 데이터를 교환 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFX`  
 에 대 한 포인터를 포함 한 `CDaoFieldExchange` 개체입니다. 프레임 워크 필드 exchange 작업에 대 한 컨텍스트를 지정 하려면이 개체를 설정 있어야 합니다.  
  
### <a name="remarks"></a>주의  
 매개 변수 자리 표시자 레코드 집합의 선택에 대 한 SQL 문의 문자열에 있는 경우 새 매개 변수 데이터 멤버를 사용 하 여 바인딩합니다. 양쪽 방향에서 작동 하는 DAO 레코드 필드 교환 (DFX) 라고 하는 필드 데이터를 교환할: 데이터 소스에서 레코드의 필드에 레코드 집합 개체의 필드 데이터 멤버와 recordset 개체에 데이터 소스에서 레코드입니다. 열을 동적으로 바인딩하는 경우 구현 하려면 않아도 됩니다 `DoFieldExchange`합니다.  
  
 구현 하기 위해 일반적으로 수행 해야 하는 작업만 `DoFieldExchange` 파생된 레코드 집합에 대 한 클래스는 클래스 마법사도 클래스를 만들고 필드 데이터 멤버의 이름 및 데이터 형식을 지정 합니다. 또한 매개 변수 데이터 멤버를 지정 하려면 클래스 마법사가 쓰기 기능 코드를 추가할 수 있습니다. 모든 필드에 동적으로 바인딩할 수 않을 경우이 함수는 비활성화 됩니다 매개 변수 데이터 멤버를 지정 하지 않는 한 합니다.  
  
 마법사의 재정의 기록 classwizard 함께 사용 된 파생된 레코드 집합 클래스를 선언 하면 `DoFieldExchange` 다음 예제와 유사한는:  
  
 [!code-cpp[NVC_MFCDatabase # 2](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]  
  
##  <a name="edit"></a>CDaoRecordset::Edit  
 현재 레코드에 대 한 변경을 허용 하려면이 함수를 호출 합니다.  
  
```  
virtual void Edit();
```  
  
### <a name="remarks"></a>주의  
 호출 하 여 **편집** 멤버 함수를 현재 레코드의 필드에 대 한 변경 내용을 복사 버퍼에 복사 됩니다. 레코드에 원하는 변경 내용을 변경한 후 호출 **업데이트** 변경 내용을 저장 합니다. **편집** 레코드 집합의 데이터 멤버의 값을 저장 합니다. 호출 하는 경우 **편집**를 변경한 다음 호출 **편집** 레코드의 값은 첫 번째 전에 있었던으로 복원 하는 다시 **편집** 호출 합니다.  
  
> [!CAUTION]
>  레코드를 편집한 다음 먼저 호출 하지 않고 다른 레코드로 이동 하는 작업을 수행 하는 경우 **업데이트**, 변경 내용을 경고 없이 손실 됩니다. 또한 레코드 집합 또는 상위 데이터베이스를 닫은 경우 사용자의 편집 된 레코드는 경고 없이 삭제 됩니다.  
  
 경우에 따라 Null (데이터 포함) 하 여 열을 업데이트 하는 것이 좋습니다. 이렇게 하려면 호출 `SetFieldNull` 의 매개 변수와 함께 **TRUE** Null; 필드를 표시 하려면이 인해 업데이트 열 합니다. 해당 값이 변경 되지 않은 경우에 데이터 원본에 쓸 수를 호출 하는 필드를 원하는 경우 `SetFieldDirty` 의 매개 변수와 함께 **TRUE**합니다. 필드에 Null 값 하는 경우에 작동 합니다.  
  
 프레임 워크 부호를 사용 하 여 읽기 전용 이므로 DAO 레코드 필드 교환 (DFX) 메커니즘을 통해 데이터 소스에서 레코드에 기록 될 됩니다 되도록 필드 데이터 멤버 필드의 값을 일반적으로 변경 필드 설정 더티 자동으로 되므로 호출 필요가 거의 [SetFieldDirty](#setfielddirty) 하지만, 직접 할 때도 열은 명시적으로 업데이트 되거나 삽입 될 어떤 값이 필드 데이터 멤버에 관계 없이 확인 합니다. DFX 메커니즘의 사용을 손쉽게 **의사 NULL**합니다. 자세한 내용은 참조 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)합니다.  
  
 이중 버퍼링 메커니즘을 사용 하지 않는 경우 다음 필드의 값을 변경 설정 되지 않습니다 필드 커밋되지 않은 것으로 합니다. 이 경우 커밋되지 않은 데이터 필드를 명시적으로 설정 해야 합니다. 에 포함 된 플래그 [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) 이 자동 필드 검사를 제어 합니다.  
  
 레코드 시간부터 잠긴 상태로 유지 pessimistically에 다중 사용자 환경에서 레코드 집합 개체를 잠그면 **편집** 업데이트가 완료 될 때까지 사용 됩니다. 레코드 집합 낙관적으로 잠겨 있으면 레코드 잠기고 데이터베이스를 업데이트 하기 바로 전에 미리 편집 된 레코드와 비교 합니다. 레코드는 호출 이후 변경 된 경우 **편집**, **업데이트** 작업이 실패 하면 MFC 예외를 throw 합니다. 사용 하 여 잠금 모드를 변경할 수 있습니다 `SetLockingMode`합니다.  
  
> [!NOTE]
>  낙관적 잠금 ODBC 및 설치 가능한 ISAM 등의 외부 데이터베이스 형식에 항상 사용 됩니다.  
  
 호출한 후에 현재 레코드가 남아 **편집**합니다. 호출할 **편집**, 현재 레코드가 있어야 합니다. 현재 기록이 없습니다. 또는 레코드 집합 개방형 테이블 형식 또는 형식 다이너셋 recordset 개체를 참조 하지 않는 경우 예외가 발생 합니다. 호출 **편집** 발생 한 `CDaoException` 다음과 같은 경우에 throw 됩니다.  
  
-   현재 기록이 없습니다.  
  
-   데이터베이스 또는 레코드 집합에는 읽기 전용입니다.  
  
-   레코드에 없는 필드를 업데이트할 수 있습니다.  
  
-   데이터베이스 또는 레코드 집합이 독점적인 사용을 위해 다른 사용자가 열렸습니다.  
  
-   레코드가 포함 된 페이지를 다른 사용자가 잠근 했습니다.  
  
 데이터 원본 트랜잭션을 지 원하는 경우 만들 수 있습니다는 **편집** 트랜잭션의 일부를 호출 합니다. 호출 해야 하는 참고 `CDaoWorkspace::BeginTrans` 호출 하기 전에 **편집** 레코드 집합 열린 후 및 합니다. 또한 호출 하는 참고 `CDaoWorkspace::CommitTrans` 호출에 대 한 대체 하지 않습니다 **업데이트** 완료 하는 **편집** 작업 합니다. 트랜잭션에 대 한 자세한 내용은 클래스를 참조 하십시오. `CDaoWorkspace`합니다.  
  
 관련된 정보에 대 한 "AddNew 메서드", "편집 메서드", "Delete 메서드", "Update 메서드" 및 "업데이트할 수 있는 속성" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="fillcache"></a>CDaoRecordset::FillCache  
 지정된 된 수의 레코드 집합의 레코드를 캐시 하려면이 함수를 호출 합니다.  
  
```  
void FillCache(
    long* pSize = NULL,  
    COleVariant* pBookmark = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSize`  
 캐시를 작성 하는 행 수를 지정 합니다. 이 매개 변수를 생략 하면 값이 기본 DAO 개체의 CacheSize 속성 설정에 따라 결정 됩니다.  
  
 `pBookmark`  
 A [COleVariant](../../mfc/reference/colevariant-class.md) 책갈피를 지정 합니다. 이 책갈피를 가리키는 레코드에서 시작 캐시가 채워집니다. 이 매개 변수를 생략 하면 기본 DAO 개체의 CacheStart 속성으로 나타내는 레코드에서 시작 캐시가 채워집니다.  
  
### <a name="remarks"></a>주의  
 캐시를 검색 하는 경우 또는 원격 서버에서 데이터를 인출 하는 응용 프로그램의 성능을 향상 됩니다. 캐시는 데이터 아마도 다시 요청 되는 응용 프로그램을 실행 하는 동안 가정에 서버에서 가장 최근에 인출 된 데이터를 보유 하는 로컬 메모리 공간이 합니다. 데이터가 요청 되 면 Microsoft Jet 데이터베이스 엔진 데이터에 대 한 캐시 먼저 확인 처리 시간을 절약 서버에서 반입 하지 않고 있습니다. 데이터를 비 ODBC 데이터 원본에 대 한 캐싱을 사용 하 여 효과가 없습니다 데이터 캐시에 저장 되지 않습니다.  
  
 인출 될 때 레코드도 채워질 캐시를 기다리는 대신 있습니다 수 명시적으로 캐시를 채우는 언제 든 지 호출 하 여는 `FillCache` 멤버 함수입니다. 이 방법은 더 빠른 때문에 캐시를 채우는 데 `FillCache` 한 번에 한 번에 하나씩 하지 않고 여러 레코드를 인출 합니다. 예를 들어 레코드의 전체 화면 표시 되 면, 응용 프로그램 호출 있을 수 `FillCache` 를 레코드의 다음 전체 화면을 가져옵니다.  
  
 레코드 집합 개체를 사용 하 여 액세스 하는 모든 ODBC 데이터베이스를 로컬 캐시를 가질 수 있습니다. 캐시를 만들려면 원격 데이터 원본에서 레코드 집합 개체를 열기 고 호출에서 `SetCacheSize` 및 `SetCacheStart` 레코드 집합의 멤버 함수입니다. 경우 `lSize` 및 *lBookmark* 부분적으로 나 완전히 지정 된 범위 밖에 있는 범위를 만들고 `SetCacheSize` 및 `SetCacheStart`,이 범위를 벗어나는 레코드 집합의 일부는 무시 되 고는 캐시에 로드 됩니다. 경우 `FillCache` 요청 원격 데이터 원본에 보다 더 많은 레코드를 유지 하 고 나머지는 레코드를 페치 예외가 throw 되지 않습니다.  
  
 캐시에서 인출 된 레코드는 다른 사용자가 원본 데이터에 동시에 변경한 내용을 반영 하지 않습니다.  
  
 `FillCache`아직 캐시 된 레코드에만 인출 합니다. 모든 캐시 된 데이터의 업데이트를 실행 하려면 호출는 `SetCacheSize` 멤버 함수를 한 `lSize` 매개 변수를 0으로 호출 `SetCacheSize` 사용 하 여 다시는 `lSize` 원래 요청 하 고 다음 호출 매개 변수 같은 캐시의 크기 `FillCache`합니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "FillCache Method" 항목을 참조 합니다.  
  
##  <a name="find"></a>CDaoRecordset::Find  
 이 비교 연산자를 사용 하 여 다이너셋 또는 스냅숏 형식 레코드 집합에서 특정 문자열을 찾을 수 함수를 호출 합니다.  
  
```  
virtual BOOL Find(
    long lFindType,  
    LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>매개 변수  
 *lFindType*  
 원하는 찾기 작업의 유형을 나타내는 값입니다. 가능한 값은 다음과 같습니다.  
  
- **AFX_DAO_NEXT** 일치 하는 문자열의 다음 위치를 확인 합니다.  
  
- **AFX_DAO_PREV** 일치 하는 문자열의 이전 위치를 확인 합니다.  
  
- **AFX_DAO_FIRST** 일치 하는 문자열의 첫 번째 위치를 확인 합니다.  
  
- **AFX_DAO_LAST** 일치 하는 문자열의 마지막 위치를 확인 합니다.  
  
 `lpszFilter`  
 문자열 식 (같은 **여기서** 단어 없이 SQL 문에 절 **여기서**) 레코드를 찾는 데 사용 합니다. 예:  
  
 [!code-cpp[NVC_MFCDatabase # 3](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]  
  
### <a name="return-value"></a>반환 값  
 일치 하는 레코드가 발견 되 면 그렇지 않은 경우 0 0이 아닌 지정 합니다.  
  
### <a name="remarks"></a>주의  
 첫째, 다음을 찾을 수 있습니다 문자열의 이전 또는 마지막 인스턴스. **찾을** 이므로 가상 함수 재정의 하 고 사용자 고유의 구현을 추가 합니다. `FindFirst`, `FindLast`, `FindNext`, 및 `FindPrev` 멤버 함수 호출의 **찾을** 멤버 함수를 사용할 수 있도록 **찾을** 모든 찾기 작업의 동작을 제어 합니다.  
  
 테이블 형식 레코드 집합에서 레코드를 찾으려고 호출는 [Seek](#seek) 멤버 함수입니다.  
  
> [!TIP]
>  레코드를 더 효과적 집합이 작을수록 **찾을** 됩니다. 일반적으로 및 ODBC 데이터와 특히 원하는 레코드만 검색 하는 새 쿼리를 작성 하는 것이 좋습니다.  
  
 관련된 정보에 대 한 항목을 DAO 도움말의 "FindFirst, FindLast, FindNext, FindPrevious 메서드" 참조 합니다.  
  
##  <a name="findfirst"></a>CDaoRecordset::FindFirst  
 이 지정 된 조건과 일치 하는 첫 번째 레코드를 찾을 수 함수를 호출 합니다.  
  
```  
BOOL FindFirst(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFilter`  
 문자열 식 (같은 **여기서** 단어 없이 SQL 문에 절 **여기서**) 레코드를 찾는 데 사용 합니다.  
  
### <a name="return-value"></a>반환 값  
 일치 하는 레코드가 발견 되 면 그렇지 않은 경우 0 0이 아닌 지정 합니다.  
  
### <a name="remarks"></a>주의  
 `FindFirst` 멤버 함수는 레코드 집합의 처음부터 검색 및 레코드 집합의 끝에 검색을 시작 합니다.  
  
 레코드 (개체만 아니라 특정 조건에 맞는)를 검색에 레코드를 이동 하려면 이동 작업 중 하나를 사용 하는 모든 포함 하려면. 테이블 형식 레코드 집합에서 레코드를 찾으려고 호출에서 `Seek` 멤버 함수입니다.  
  
 현재 레코드 포인터 아직 결정 조건과 일치 하는 레코드를 찾으면 및 `FindFirst` 0을 반환 합니다. 레코드 집합에서 조건에 맞는 레코드가 여러 개 포함 되어 있는 경우 `FindFirst` 찾습니다. 첫 번째 `FindNext` 고 다음 항목을 찾습니다.  
  
> [!CAUTION]
>  현재 레코드를 편집 하는 경우 호출 하 여 변경 내용을 저장 하 해야는 **업데이트** 다른 레코드로 이동 하기 전에 멤버 함수입니다. 업데이트 하지 않고 다른 레코드로 이동 하는 경우 변경 내용을 경고 없이 손실 됩니다.  
  
 **찾을** 멤버 함수는 위치에서 및 다음 표에 지정 된 방향으로 검색 합니다.  
  
|찾기 작업|시작|검색 방향|  
|---------------------|-----------|----------------------|  
|`FindFirst`|레코드 집합의 시작|레코드 집합의 끝|  
|`FindLast`|레코드 집합의 끝|레코드 집합의 시작|  
|`FindNext`|현재 레코드|레코드 집합의 끝|  
|**FindPrevious**|현재 레코드|레코드 집합의 시작|  
  
> [!NOTE]
>  호출 하는 경우 `FindLast`, Microsoft Jet 데이터베이스 엔진 아직 수행 하지 않은 경우 검색을 시작 하기 전에 레코드 집합에 완전히 채웁니다. 첫 번째 검색 후속 검색 보다 더 오래 걸릴 수 있습니다.  
  
 그러나 찾기 작업 중 하나를 사용 하 여 같지 않습니다 호출할 때와 **MoveFirst** 또는 `MoveNext`,는 식별 하기가 첫 번째 또는 다음 레코드로 현재 조건을 지정 하지 않고 있습니다. 이동 작업을 사용 하 여 찾기 작업을 수행할 수 있습니다.  
  
 찾기 작업을 사용 하는 경우 다음을 염두에 두십시오.  
  
-   경우 **찾을** 반환 0이 아니고, 현재 레코드가 정의 되어 있지 않습니다. 이 경우 유효한 레코드에 다시 현재 레코드 포인터를 배치 해야 합니다.  
  
-   앞 으로만 이동 가능한 스크롤 스냅숏 형식 레코드 집합으로는 찾기 작업을 사용할 수 없습니다.  
  
-   미국 날짜 형식 (월-일-연도)를 사용 해야 Microsoft Jet 데이터베이스 엔진;의 (미국) 버전을 사용 하지 않는 경우에 날짜를 포함 하는 필드를 검색할 때 그렇지 않으면 일치 하는 레코드 없을 수 있습니다.  
  
-   ODBC 데이터베이스 및 큰 다이너셋을 사용할 때 특히 큰 레코드 집합으로 작업할 경우 찾기 작업을 사용 하 여 인지 느려지고, 검색할 수 있습니다. SQL 쿼리를 사용 하 여 성능을 향상 시킬 수 있습니다 사용자 지정할 **ORDERBY** 또는 **여기서** 절, 매개 변수 쿼리 또는 **CDaoQuerydef** 인덱싱된 특정 레코드를 검색 하는 개체입니다.  
  
 관련된 정보에 대 한 항목을 DAO 도움말의 "FindFirst, FindLast, FindNext, FindPrevious 메서드" 참조 합니다.  
  
##  <a name="findlast"></a>CDaoRecordset::FindLast  
 이 지정 된 조건과 일치 하는 마지막 레코드를 찾을 수 함수를 호출 합니다.  
  
```  
BOOL FindLast(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFilter`  
 문자열 식 (같은 **여기서** 단어 없이 SQL 문에 절 **여기서**) 레코드를 찾는 데 사용 합니다.  
  
### <a name="return-value"></a>반환 값  
 일치 하는 레코드가 발견 되 면 그렇지 않은 경우 0 0이 아닌 지정 합니다.  
  
### <a name="remarks"></a>주의  
 `FindLast` 멤버 함수 시작 레코드 집합의 끝에 검색 및 레코드 집합의 시작 부분 쪽으로 뒤로 검색 합니다.  
  
 레코드 (개체만 아니라 특정 조건에 맞는)를 검색에 레코드를 이동 하려면 이동 작업 중 하나를 사용 하는 모든 포함 하려면. 테이블 형식 레코드 집합에서 레코드를 찾으려고 호출에서 `Seek` 멤버 함수입니다.  
  
 현재 레코드 포인터 아직 결정 조건과 일치 하는 레코드를 찾으면 및 `FindLast` 0을 반환 합니다. 레코드 집합에서 조건에 맞는 레코드가 여러 개 포함 되어 있는 경우 `FindFirst` 찾습니다. 첫 번째 `FindNext` 첫 번째 등에 후 다음 항목을 찾습니다.  
  
> [!CAUTION]
>  현재 레코드를 편집 하는 경우 반드시 호출 하 여 변경 내용을 저장는 **업데이트** 다른 레코드로 이동 하기 전에 멤버 함수입니다. 업데이트 하지 않고 다른 레코드로 이동 하는 경우 변경 내용을 경고 없이 손실 됩니다.  
  
 그러나 찾기 작업 중 하나를 사용 하 여 같지 않습니다 호출할 때와 **MoveFirst** 또는 `MoveNext`,는 식별 하기가 첫 번째 또는 다음 레코드로 현재 조건을 지정 하지 않고 있습니다. 이동 작업을 사용 하 여 찾기 작업을 수행할 수 있습니다.  
  
 찾기 작업을 사용 하는 경우 다음을 염두에 두십시오.  
  
-   경우 **찾을** 반환 0이 아니고, 현재 레코드가 정의 되어 있지 않습니다. 이 경우 유효한 레코드에 다시 현재 레코드 포인터를 배치 해야 합니다.  
  
-   앞 으로만 이동 가능한 스크롤 스냅숏 형식 레코드 집합으로는 찾기 작업을 사용할 수 없습니다.  
  
-   미국 날짜 형식 (월-일-연도)를 사용 해야 Microsoft Jet 데이터베이스 엔진;의 (미국) 버전을 사용 하지 않는 경우에 날짜를 포함 하는 필드를 검색할 때 그렇지 않으면 일치 하는 레코드 없을 수 있습니다.  
  
-   ODBC 데이터베이스 및 큰 다이너셋을 사용할 때 특히 큰 레코드 집합으로 작업할 경우 찾기 작업을 사용 하 여 인지 느려지고, 검색할 수 있습니다. SQL 쿼리를 사용 하 여 성능을 향상 시킬 수 있습니다 사용자 지정할 **ORDERBY** 또는 **여기서** 절, 매개 변수 쿼리 또는 **CDaoQuerydef** 인덱싱된 특정 레코드를 검색 하는 개체입니다.  
  
 관련된 정보에 대 한 항목을 DAO 도움말의 "FindFirst, FindLast, FindNext, FindPrevious 메서드" 참조 합니다.  
  
##  <a name="findnext"></a>CDaoRecordset::FindNext  
 이 지정된 된 조건과 일치 하는 다음 레코드를 찾을 수 함수를 호출 합니다.  
  
```  
BOOL FindNext(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFilter`  
 문자열 식 (같은 **여기서** 단어 없이 SQL 문에 절 **여기서**) 레코드를 찾는 데 사용 합니다.  
  
### <a name="return-value"></a>반환 값  
 일치 하는 레코드가 발견 되 면 그렇지 않은 경우 0 0이 아닌 지정 합니다.  
  
### <a name="remarks"></a>설명  
 `FindNext` 멤버 함수는 현재 레코드에서 해당 검색을 시작 하 고 레코드 집합의 끝에 검색 합니다.  
  
 레코드 (개체만 아니라 특정 조건에 맞는)를 검색에 레코드를 이동 하려면 이동 작업 중 하나를 사용 하는 모든 포함 하려면. 테이블 형식 레코드 집합에서 레코드를 찾으려고 호출에서 `Seek` 멤버 함수입니다.  
  
 현재 레코드 포인터 아직 결정 조건과 일치 하는 레코드를 찾으면 및 `FindNext` 0을 반환 합니다. 레코드 집합에서 조건에 맞는 레코드가 여러 개 포함 되어 있는 경우 `FindFirst` 찾습니다. 첫 번째 `FindNext` 고 다음 항목을 찾습니다.  
  
> [!CAUTION]
>  현재 레코드를 편집 하는 경우 반드시 호출 하 여 변경 내용을 저장는 **업데이트** 다른 레코드로 이동 하기 전에 멤버 함수입니다. 업데이트 하지 않고 다른 레코드로 이동 하는 경우 변경 내용을 경고 없이 손실 됩니다.  
  
 그러나 찾기 작업 중 하나를 사용 하 여 같지 않습니다 호출할 때와 **MoveFirst** 또는 `MoveNext`,는 식별 하기가 첫 번째 또는 다음 레코드로 현재 조건을 지정 하지 않고 있습니다. 이동 작업을 사용 하 여 찾기 작업을 수행할 수 있습니다.  
  
 찾기 작업을 사용 하는 경우 다음을 염두에 두십시오.  
  
-   경우 **찾을** 반환 0이 아니고, 현재 레코드가 정의 되어 있지 않습니다. 이 경우 유효한 레코드에 다시 현재 레코드 포인터를 배치 해야 합니다.  
  
-   앞 으로만 이동 가능한 스크롤 스냅숏 형식 레코드 집합으로는 찾기 작업을 사용할 수 없습니다.  
  
-   미국 날짜 형식 (월-일-연도)를 사용 해야 Microsoft Jet 데이터베이스 엔진;의 (미국) 버전을 사용 하지 않는 경우에 날짜를 포함 하는 필드를 검색할 때 그렇지 않으면 일치 하는 레코드 없을 수 있습니다.  
  
-   ODBC 데이터베이스 및 큰 다이너셋을 사용할 때 특히 큰 레코드 집합으로 작업할 경우 찾기 작업을 사용 하 여 인지 느려지고, 검색할 수 있습니다. SQL 쿼리를 사용 하 여 성능을 향상 시킬 수 있습니다 사용자 지정할 **ORDERBY** 또는 **여기서** 절, 매개 변수 쿼리 또는 **CDaoQuerydef** 인덱싱된 특정 레코드를 검색 하는 개체입니다.  
  
 관련된 정보에 대 한 항목을 DAO 도움말의 "FindFirst, FindLast, FindNext, FindPrevious 메서드" 참조 합니다.  
  
##  <a name="findprev"></a>CDaoRecordset::FindPrev  
 이 지정 된 조건과 일치 하는 이전 레코드를 찾을 수 함수를 호출 합니다.  
  
```  
BOOL FindPrev(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFilter`  
 문자열 식 (같은 **여기서** 단어 없이 SQL 문에 절 **여기서**) 레코드를 찾는 데 사용 합니다.  
  
### <a name="return-value"></a>반환 값  
 일치 하는 레코드가 발견 되 면 그렇지 않은 경우 0 0이 아닌 지정 합니다.  
  
### <a name="remarks"></a>주의  
 `FindPrev` 멤버 함수는 현재 레코드에서 해당 검색을 시작 하 고 레코드 집합의 시작 부분 쪽으로 뒤로 검색 합니다.  
  
 레코드 (개체만 아니라 특정 조건에 맞는)를 검색에 레코드를 이동 하려면 이동 작업 중 하나를 사용 하는 모든 포함 하려면. 테이블 형식 레코드 집합에서 레코드를 찾으려고 호출에서 `Seek` 멤버 함수입니다.  
  
 현재 레코드 포인터 아직 결정 조건과 일치 하는 레코드를 찾으면 및 `FindPrev` 0을 반환 합니다. 레코드 집합에서 조건에 맞는 레코드가 여러 개 포함 되어 있는 경우 `FindFirst` 찾습니다. 첫 번째 `FindNext` 고 다음 항목을 찾습니다.  
  
> [!CAUTION]
>  현재 레코드를 편집 하는 경우 반드시 호출 하 여 변경 내용을 저장는 **업데이트** 다른 레코드로 이동 하기 전에 멤버 함수입니다. 업데이트 하지 않고 다른 레코드로 이동 하는 경우 변경 내용을 경고 없이 손실 됩니다.  
  
 그러나 찾기 작업 중 하나를 사용 하 여 같지 않습니다 호출할 때와 **MoveFirst** 또는 `MoveNext`,는 식별 하기가 첫 번째 또는 다음 레코드로 현재 조건을 지정 하지 않고 있습니다. 이동 작업을 사용 하 여 찾기 작업을 수행할 수 있습니다.  
  
 찾기 작업을 사용 하는 경우 다음을 염두에 두십시오.  
  
-   경우 **찾을** 반환 0이 아니고, 현재 레코드가 정의 되어 있지 않습니다. 이 경우 유효한 레코드에 다시 현재 레코드 포인터를 배치 해야 합니다.  
  
-   앞 으로만 이동 가능한 스크롤 스냅숏 형식 레코드 집합으로는 찾기 작업을 사용할 수 없습니다.  
  
-   미국 날짜 형식 (월-일-연도)를 사용 해야 Microsoft Jet 데이터베이스 엔진;의 (미국) 버전을 사용 하지 않는 경우에 날짜를 포함 하는 필드를 검색할 때 그렇지 않으면 일치 하는 레코드 없을 수 있습니다.  
  
-   ODBC 데이터베이스 및 큰 다이너셋을 사용할 때 특히 큰 레코드 집합으로 작업할 경우 찾기 작업을 사용 하 여 인지 느려지고, 검색할 수 있습니다. SQL 쿼리를 사용 하 여 성능을 향상 시킬 수 있습니다 사용자 지정할 **ORDERBY** 또는 **여기서** 절, 매개 변수 쿼리 또는 **CDaoQuerydef** 인덱싱된 특정 레코드를 검색 하는 개체입니다.  
  
 관련된 정보에 대 한 항목을 DAO 도움말의 "FindFirst, FindLast, FindNext, FindPrevious 메서드" 참조 합니다.  
  
##  <a name="getabsoluteposition"></a>CDaoRecordset::GetAbsolutePosition  
 레코드 집합 개체의 현재 레코드의 레코드 번호를 반환합니다.  
  
```  
long GetAbsolutePosition();
```  
  
### <a name="return-value"></a>반환 값  
 정수 0에서 레코드 집합의 레코드 수입니다. 레코드 집합의 현재 레코드의 서 수 위치에 해당합니다.  
  
### <a name="remarks"></a>주의  
 AbsolutePosition 속성 값은 기본 DAO 개체는 0부터 시작 합니다. 0으로 설정 레코드 집합의 첫 번째 레코드를 가리킵니다. 호출 하 여 레코드 집합의 레코드의 수를 확인할 수 [GetRecordCount](#getrecordcount)합니다. 호출 `GetRecordCount` 개수를 결정 하는 모든 레코드에 액세스 해야 하기 때문에 다소 시간이 걸릴 수 있습니다.  
  
 레코드 집합의 레코드가 없습니다. 때로 현재 레코드가, 없을 경우 1이 반환 됩니다. 현재 레코드를 삭제 한 경우 AbsolutePosition 속성 값을 정의 하지 않은 하 고 MFC 참조 하는 경우 예외를 throw 합니다. 다이너셋 형식의 레코드 집합에 대 한 새 레코드 시퀀스의 끝에 추가 됩니다.  
  
> [!NOTE]
>  이 속성으로 서로게이트 레코드 번호를 사용할 수 없습니다. 책갈피는 계속 유지 하 고 지정된 된 위치를 반환 하는 권장된 방법을 이며 모든 유형의 레코드 집합 개체에서 현재 레코드의 위치 하는 유일한 방법은입니다. 특히, 지정된 된 레코드의 위치는 앞의 레코드를 삭제 한 경우 변경 합니다. 에 지정된 된 레코드 해야 같은 절대 위치로 사용 하 여 SQL 문을 생성 하지 않는 한 레코드 집합 내에서 개별 레코드의 순서가 보장 되지 않으므로 레코드 집합 다시 다시 생성 하는 경우 반드시 이기도 한 **ORDERBY** 절.  
  
> [!NOTE]
>  이 멤버 함수는 다이너셋 형식 및 스냅숏 형식 레코드 집합에 대해서만 유효 합니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "AbsolutePosition Property" 항목을 참조 합니다.  
  
##  <a name="getbookmark"></a>CDaoRecordset::GetBookmark  
 이 특정 레코드에 책갈피 값을 가져오는 함수를 호출 합니다.  
  
```  
COleVariant GetBookmark();
```  
  
### <a name="return-value"></a>반환 값  
 현재 레코드에서 책갈피를 나타내는 값을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 레코드 집합 개체를 만들거나 열 때 각 레코드에 이미 고유 책갈피를 지 원하는 경우. 호출 `CanBookmark` 레코드 집합 책갈피를 지원 하는지 확인 합니다.  
  
 책갈피의 값을 할당 하 여 현재 레코드에 대 한 책갈피를 저장할 수는 `COleVariant` 개체입니다. 다른 레코드로 이동 후 언제 든 지를 해당 레코드를 신속 하 게 반환 하려면 호출 `SetBookmark` 해당 값에 해당 하는 매개 변수와 함께 `COleVariant` 개체입니다.  
  
> [!NOTE]
>  호출 [Requery](#requery) DAO 책갈피를 변경 합니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "책갈피 Property" 항목을 참조 합니다.  
  
##  <a name="getcachesize"></a>CDaoRecordset::GetCacheSize  
 캐시 된 레코드의 수를 가져오려면이 함수를 호출 합니다.  
  
```  
long GetCacheSize();
```  
  
### <a name="return-value"></a>반환 값  
 ODBC 데이터 원본에서 로컬로 캐시할 데이터를 포함 하는 다이너셋 형식의 레코드 집합에서 레코드의 수를 지정 하는 값입니다.  
  
### <a name="remarks"></a>주의  
 데이터 캐싱 다이너셋 형식의 레코드 집합 개체를 통해 원격 서버에서 데이터를 검색 하는 응용 프로그램의 성능을 향상 시킵니다. 캐시에서 데이터 다시 요청 되는 응용 프로그램을 실행 하는 동안 서버에서 가장 최근에 검색 된 데이터를 보유 하는 로컬 메모리 공간이 합니다. 데이터가 요청 되 면 Microsoft Jet 데이터베이스 엔진 요청된 된 데이터에 대 한 캐시 먼저 확인 처리 시간을 절약 하는 서버에서 가져오는 것입니다. ODBC 데이터 원본에서 제공 되지 않는 데이터 캐시에 저장 되지 않습니다.  
  
 연결된 된 테이블 같은 ODBC 데이터 원본에는 로컬 캐시를 가질 수 있습니다.  
  
 관련된 내용은 DAO 도움말의 "CacheSize CacheStart 속성" 항목을 참조 합니다.  
  
##  <a name="getcachestart"></a>CDaoRecordset::GetCacheStart  
 캐시할 레코드 집합의 첫 번째 레코드의 책갈피 값을 얻기 위해이 함수를 호출 합니다.  
  
```  
COleVariant GetCacheStart();
```  
  
### <a name="return-value"></a>반환 값  
 A `COleVariant` 캐시할 레코드 집합의 첫 번째 레코드의 책갈피를 지정 하는 합니다.  
  
### <a name="remarks"></a>주의  
 Microsoft Jet 데이터베이스 엔진 캐시에서 캐시 범위 내에 있는 레코드를 요청 하 고 서버에서 캐시 범위 외부의 레코드를 요청 합니다.  
  
> [!NOTE]
>  캐시에서 검색 된 레코드는 다른 사용자가 원본 데이터에 동시에 변경한 내용을 반영 하지 않습니다.  
  
 관련된 내용은 DAO 도움말의 "CacheSize CacheStart 속성" 항목을 참조 합니다.  
  
##  <a name="getcurrentindex"></a>CDaoRecordset::GetCurrentIndex  
 인덱싱된 테이블 형식에서 사용 중인 현재 인덱스를 확인 하려면이 함수를 호출 `CDaoRecordset` 개체입니다.  
  
```  
CString GetCurrentIndex();
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 테이블 형식의 레코드 집합으로 사용 중인 인덱스의 이름을 포함 합니다. 설정 된 인덱스가 없는 경우 빈 문자열을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 인덱스는 테이블 형식의 레코드 집합의 레코드를 정렬 하기 위한 기반 및에서 사용 되는 [Seek](#seek) 레코드를 찾는 데 멤버 함수입니다.  
  
 A `CDaoRecordset` 개체 둘 이상의 인덱스를 가질 수 있지만 한 번에 하나의 인덱스를 사용할 수 있습니다 (하지만 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 개체에 정의 된 여러 개의 인덱스가 있을 수 있습니다).  
  
 관련된 정보 항목 "Index 개체" 및 "현재 인덱스" DAO 도움말의 정의 참조 하십시오.  
  
##  <a name="getdatecreated"></a>CDaoRecordset::GetDateCreated  
 기본 테이블을 만든 시간과 날짜를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>반환 값  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 기본 테이블을 만든 시간과 날짜를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 날짜 및 시간 설정이 기본 테이블이 생성 된 컴퓨터에서 파생 됩니다.  
  
 관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.  
  
##  <a name="getdatelastupdated"></a>CDaoRecordset::GetDateLastUpdated  
 스키마 마지막으로 업데이트 된 시간과 날짜를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>반환 값  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 날짜와 시간 (스키마) 기본 테이블 구조를 마지막으로 업데이트를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 날짜 및 시간 설정이입니다 (스키마) 기본 테이블 구조를 마지막으로 업데이트 하는 컴퓨터에서 파생 됩니다.  
  
 관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.  
  
##  <a name="getdefaultdbname"></a>CDaoRecordset::GetDefaultDBName  
 이 레코드 집합에 대 한 데이터베이스의 이름을 확인 하려면이 함수를 호출 합니다.  
  
```  
virtual CString GetDefaultDBName();
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 이 레코드 집합 파생 되는 데이터베이스의 이름과 경로 포함 합니다.  
  
### <a name="remarks"></a>주의  
 레코드 집합에 대 한 포인터 없이 만들어질 경우는 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md), 아니면이 경로 사용 하는 레코드 집합에서 기본 데이터베이스 열을 합니다. 기본적으로이 함수는 빈 문자열을 반환합니다. 클래스 마법사에서 새 레코드 집합을 파생 하는 경우 `CDaoRecordset`,이 함수를 만듭니다.  
  
 다음 예제에서는 이중 백슬래시 (\\\\) 문자열에서 요구 된 대로 문자열이 올바르게 해석 될 수 있습니다.  
  
 [!code-cpp[NVC_MFCDatabase # 4](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]  
  
##  <a name="getdefaultsql"></a>CDaoRecordset::GetDefaultSQL  
 프레임 워크 멤버 가져오려면이 함수를 레코드 집합의 기반이 되는 기본 SQL 문을 호출 합니다.  
  
```  
virtual CString GetDefaultSQL();
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 기본 SQL 문이 들어 있는입니다.  
  
### <a name="remarks"></a>주의  
 테이블 이름 또는 SQL 때문일 **선택** 문.  
  
 직접 정의한 하지 기본 SQL 문을 클래스 마법사를 사용 하 여 레코드 집합 클래스를 선언 하 여 및 classwizard 함께 사용 하면에 대 한이 작업을 수행 합니다.  
  
 Null SQL 문자열을 전달 하는 경우 [열려](#open), 레코드 집합에 대 한 테이블 이름이 나 SQL을 확인 하려면이 함수 호출 됩니다.  
  
##  <a name="geteditmode"></a>CDaoRecordset::GetEditMode  
 이 함수를 호출의 편집 상태를 확인 하는 다음 값 중 하나:  
  
```  
short GetEditMode();
```  
  
### <a name="return-value"></a>반환 값  
 현재 레코드의 편집 상태를 나타내는 값을 반환 합니다.  
  
### <a name="remarks"></a>주의  
  
|값|설명|  
|-----------|-----------------|  
|**dbEditNone**|편집 작업이 진행 중입니다.|  
|**dbEditInProgress**|**편집** 가 호출 되었습니다.|  
|**dbEditAdd**|`AddNew`가 호출 되었습니다.|  
  
 관련된 정보에 대 한 DAO 도움말의 "EditMode Property" 항목을 참조 합니다.  
  
##  <a name="getfieldcount"></a>CDaoRecordset::GetFieldCount  
 레코드 집합에 정의 된 필드 (열)의 수를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합의 필드 수를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 관련된 정보에 대 한 항목 DAO 도움말의 "Count 속성"을 참조 합니다.  
  
##  <a name="getfieldinfo"></a>CDaoRecordset::GetFieldInfo  
 레코드 집합의 필드에 대 한 정보를 얻으려면이 멤버 함수를 호출 합니다.  
  
```  
void GetFieldInfo(
    int nIndex,  
    CDaoFieldInfo& fieldinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetFieldInfo(
    LPCTSTR lpszName,  
    CDaoFieldInfo& fieldinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 인덱스에 의해 조회에 대 한 레코드 집합의 필드 컬렉션에 있는 미리 정의 된 필드의 0부터 시작 하는 인덱스입니다.  
  
 `fieldinfo`  
 에 대 한 참조는 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조입니다.  
  
 `dwInfoOptions`  
 검색할 레코드 집합에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 반환 하는 함수를 입히기 무엇 함께 나열 됩니다. 최상의 성능을 위해 필요한 정보 수준의 검색:  
  
- `AFX_DAO_PRIMARY_INFO`(기본값) 이름, 유형, 크기, 속성  
  
- `AFX_DAO_SECONDARY_INFO`기본 정보, 플러스: 서 수 위치에 필요한 길이, 데이터 정렬 순서, 외부 이름, 원본 필드, 원본 테이블 0 허용  
  
- `AFX_DAO_ALL_INFO`기본 및 보조 정보 플러스: Default Value, 유효성 검사 규칙 유효성 검사 텍스트  
  
 `lpszName`  
 @FSHO2@필드의 이름입니다.  
  
### <a name="remarks"></a>주의  
 한 버전의 함수를 사용 하면 인덱스 필드를 찾을 수 있습니다. 다른 버전 필드 이름으로 조회할 수 있습니다.  
  
 반환 되는 정보에 대 한 참조는 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조입니다. 이 구조에는 항목의 설명에 위에 나열 된 정보에 해당 하는 멤버가 `dwInfoOptions`합니다. 한 수준에서 정보를 요청할 때 모든 상위 수준의에 대 한 정보를 가져옵니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "특성 Property" 항목을 참조 합니다.  
  
##  <a name="getfieldvalue"></a>CDaoRecordset::GetFieldValue  
 레코드 집합에서 데이터를 검색 하려면이 함수를 호출 합니다.  
  
```  
virtual void GetFieldValue(
    LPCTSTR lpszName,  
    COleVariant& varValue);

 
virtual void GetFieldValue(
    int nIndex,  
    COleVariant& varValue);
 
virtual COleVariant GetFieldValue(LPCTSTR lpszName); 
virtual COleVariant GetFieldValue(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 필드의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `varValue`  
 에 대 한 참조는 `COleVariant` 필드의 값을 저장 하는 개체입니다.  
  
 `nIndex`  
 인덱스에 의해 조회에 대 한 레코드 집합의 필드 컬렉션의 필드는 0부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 두 가지 버전의 `GetFieldValue` 값을 반환 하는 반환 된 [COleVariant](../../mfc/reference/colevariant-class.md) 필드의 값이 포함 된 개체입니다.  
  
### <a name="remarks"></a>주의  
 이름이 나 서 수 위치 필드를 찾을 수 있습니다.  
  
> [!NOTE]
>  것이 더 효율적이 멤버 함수는 버전 중 하나를 호출 하는 `COleVariant` 개체 참조 매개 변수를 반환 하는 버전을 호출 하지 않고는 `COleVariant` 개체입니다. 이 함수의 두 번째 버전은 이전 버전과 호환성을 위해 유지 됩니다.  
  
 사용 하 여 `GetFieldValue` 및 [SetFieldValue](#setfieldvalue) 실행된 시간 보다는 정적으로 사용 하 여 바인딩 열 필드를 동적으로 바인딩하는 [DoFieldExchange](#dofieldexchange) 메커니즘입니다.  
  
 `GetFieldValue`및 `DoFieldExchange` 메커니즘을 조합 하 여 성능을 향상 시킬 수 있습니다. 사용 예를 들어 `GetFieldValue` , 필요할 경우에 해야 하는 값을 검색 하 호출 하는 인터페이스의 "추가 정보" 단추를 할당 합니다.  
  
 관련된 정보에 대 한 "Field 개체"과 "값 속성" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="getindexcount"></a>CDaoRecordset::GetIndexCount  
 테이블 형식 레코드 집합에서 사용할 수 있는 인덱스 번호를 확인 하려면이 함수를 호출 합니다.  
  
```  
short GetIndexCount();
```  
  
### <a name="return-value"></a>반환 값  
 테이블 형식 레코드 집합의 인덱스 수입니다.  
  
### <a name="remarks"></a>주의  
 `GetIndexCount`레코드 집합의 모든 인덱스를 통해 반복 하는 데 유용 합니다. 이 위해 사용 하 여 `GetIndexCount` 함께에서 [GetIndexInfo](#getindexinfo)합니다. 다이너셋 형식 또는 스냅숏 형식 레코드 집합에서이 함수를 호출 하는 경우 MFC 예외를 throw 합니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "특성 Property" 항목을 참조 합니다.  
  
##  <a name="getindexinfo"></a>CDaoRecordset::GetIndexInfo  
 다양 한 종류의 레코드 집합을 원본 기본 테이블에 정의 된 인덱스에 대 한 정보를 가져오려면이 함수를 호출 합니다.  
  
```  
void GetIndexInfo(
    int nIndex,  
    CDaoIndexInfo& indexinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetIndexInfo(
    LPCTSTR lpszName,  
    CDaoIndexInfo& indexinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 조회 되는 숫자 위치 하 여 테이블의 인덱스 컬렉션에 0부터 시작 하는 인덱스입니다.  
  
 `indexinfo`  
 에 대 한 참조는 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조입니다.  
  
 `dwInfoOptions`  
 인덱스를 검색 하는 방법에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 반환 하는 함수를 입히기 무엇 함께 나열 됩니다. 최상의 성능을 위해 필요한 정보 수준의 검색:  
  
- `AFX_DAO_PRIMARY_INFO`(기본값) 이름, 필드 정보 필드  
  
- `AFX_DAO_SECONDARY_INFO`기본 정보, 플러스: 주, Unique, 클러스터형, 필수, IgnoreNulls 외부  
  
- `AFX_DAO_ALL_INFO`기본 및 보조 정보 플러스: 고유 카운트  
  
 `lpszName`  
 이름별으로 조회에 대 한 인덱스 개체의 이름에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 한 버전의 함수를 사용 하면 컬렉션에서 해당 위치에 따라 인덱스를 조회할 수 있습니다. 다른 버전 이름으로 인덱스를 조회할 수 있습니다.  
  
 반환 되는 정보에 대 한 참조는 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조입니다. 이 구조에는 항목의 설명에 위에 나열 된 정보에 해당 하는 멤버가 `dwInfoOptions`합니다. 한 수준에서 정보를 요청할 때 모든 상위 수준의에 대 한 정보를 가져옵니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "특성 Property" 항목을 참조 합니다.  
  
##  <a name="getlastmodifiedbookmark"></a>CDaoRecordset::GetLastModifiedBookmark  
 가장 최근에 추가 되거나 업데이트 된 레코드의 책갈피를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
COleVariant GetLastModifiedBookmark();
```  
  
### <a name="return-value"></a>반환 값  
 A `COleVariant` 가장 최근에 나타내는 책갈피가 포함 된 추가 되거나 변경 된 레코드입니다.  
  
### <a name="remarks"></a>주의  
 레코드 집합 개체를 만들거나 열 때 각 레코드에 이미 고유 책갈피를 지 원하는 경우. 호출 [GetBookmark](#getbookmark) 를 레코드 집합에서 책갈피를 지원 하는지 확인 합니다. 레코드 집합 책갈피, 지원 하지 않는 경우는 `CDaoException` throw 됩니다.  
  
 레코드를 추가 하는 레코드 집합의 끝에 나타납니다 하 고 현재 기록이 없습니다. 새 레코드를 현재 레코드로 호출 `GetLastModifiedBookmark` 호출 `SetBookmark` 새로 추가 된 레코드 돌아갑니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "LastModified Property" 항목을 참조 합니다.  
  
##  <a name="getlockingmode"></a>CDaoRecordset::GetLockingMode  
 레코드 집합에 대 한 잠금 유형을 결정 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetLockingMode();
```  
  
### <a name="return-value"></a>반환 값  
 잠금 유형을 최악 하면 0이 아니고 그렇지 않으면 0 낙관적 레코드 잠금에 대 한 합니다.  
  
### <a name="remarks"></a>주의  
 호출 되는 즉시 잠겨 때 비관적 잠금가 적용 된 경우 편집 중인 레코드를 포함 하는 데이터 페이지는 [편집](#edit) 멤버 함수입니다. 호출 하는 경우 페이지 잠금 해제 되어는 [업데이트](#update) 또는 [닫기](#close) 멤버 함수 또는 이동 또는 찾기 작업 중 하나입니다.  
  
 레코드를 포함 하는 데이터 페이지와 레코드를 업데이트 하는 동안에 잠긴 경우 낙관적 잠금이 적용 됩니다는 **업데이트** 멤버 함수입니다.  
  
 ODBC 데이터 소스를 사용할 때는 잠금 모드 낙관적 항상입니다.  
  
 관련된 정보에 대 한 "LockEdits 속성" 및 "잠금 동작에 여러 사용자 용 응용 프로그램" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="getname"></a>CDaoRecordset::GetName  
 레코드 집합의 이름을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 레코드 집합의 이름을 포함 합니다.  
  
### <a name="remarks"></a>설명  
 레코드 집합의 이름은 문자로 시작 해야 하며 최대 40 자까지 포함할 수 있습니다. 숫자를 포함할 수 있습니다 및 밑줄 문자는 문장 부호 또는 공백을 포함할 수 없습니다.  
  
 관련된 정보에 대 한 항목 DAO 도움말의 "Name 속성"을 참조 합니다.  
  
##  <a name="getparamvalue"></a>CDaoRecordset::GetParamValue  
 기본 DAOParameter 개체에 저장 된 지정된 된 매개 변수의 현재 값을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual COleVariant GetParamValue(int nIndex);  
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 기본 DAOParameter 개체의 숫자 위치 매개 변수입니다.  
  
 `lpszName`  
 매개 변수 값을 변경할의 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 클래스의 개체 [COleVariant](../../mfc/reference/colevariant-class.md) 매개 변수의 값이 들어 있는입니다.  
  
### <a name="remarks"></a>주의  
 매개 변수 이름 또는 컬렉션의 숫자에 따라 액세스할 수 있습니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "매개 변수 개체" 항목을 참조 합니다.  
  
##  <a name="getpercentposition"></a>CDaoRecordset::GetPercentPosition  
 호출 하는 경우 다이너셋 형식 또는 스냅숏 형식 레코드 집합으로 작업할 때 `GetPercentPosition` 레코드 집합을 완벽 하 게 채우기, 전에 이동은 호출 하 여 표시 된 대로 액세스 하는 레코드의 수를 기준으로 [GetRecordCount](#getrecordcount)합니다.  
  
```  
float GetPercentPosition();
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합에 있는 레코드의 백분율을 기반으로 하는 레코드 집합 개체의 현재 레코드의 대략적인 위치를 나타내는 0에서 100 사이의 숫자입니다.  
  
### <a name="remarks"></a>주의  
 이동할 수 있습니다 마지막 레코드를 호출 하 여 [MoveLast](#movelast) 을 완료 하지만 모든 레코드 집합의 채우기 걸릴 수 있습니다 상당한 시간이 있습니다.  
  
 호출할 수 있습니다 `GetPercentPosition` recordset 개체의 모든 세 가지 종류의 인덱스가 없는 테이블을 포함 합니다. 그러나 호출할 수 없습니다 `GetPercentPosition` 앞 으로만 이동 가능한 스크롤 스냅숏, 또는 통과 쿼리는 외부 데이터베이스에 대해에서 연 레코드 집합입니다. 현재 기록이 없습니다, 또는 그 현재 레코드를 삭제 하는 경우는 `CDaoException` throw 됩니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "PercentPosition Property" 항목을 참조 합니다.  
  
##  <a name="getrecordcount"></a>CDaoRecordset::GetRecordCount  
 레코드 집합의 레코드 수가 액세스 했는지 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
long GetRecordCount();
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합 개체에 액세스 하는 레코드의 수를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 `GetRecordCount`모든 레코드 액세스 되기 전까지 다이너셋 형식 또는 스냅숏 형식 레코드 집합에 포함 된 개수 레코드를 나타내지 않습니다. 이 멤버 함수 호출을 완료 하는 데 시간이 많이 걸릴 수 있습니다.  
  
 마지막 레코드에 액세스 되 면 반환 값은 레코드 집합에서 삭제 되지 않은 레코드의 총 수를 나타냅니다. 에 액세스 하는 마지막 레코드를 강제로 표시 하려면 호출는 `MoveLast` 또는 `FindLast` 레코드 집합에 대 한 멤버 함수입니다. 또한 쿼리는 반환 된 레코드의 대략적인 수를 확인 하려면 SQL 수를 사용할 수 있습니다.  
  
 다이너셋 형식의 레코드 집합의 반환 값의 레코드를 삭제 하는 응용 프로그램으로 `GetRecordCount` 감소 합니다. 그러나 다른 사용자가 삭제 된 레코드에서 반영 되지 않습니다 `GetRecordCount` 현재 레코드는 삭제 된 레코드에 배치 될 때까지 합니다. 레코드 수에 영향을 주는 트랜잭션을 실행 하 고 트랜잭션을 롤백할 경우 `GetRecordCount` 나머지 레코드의 실제 수를 반영 되지 것입니다.  
  
 값 `GetRecordCount` 스냅숏 형식 레코드 집합에서 영향을 받지 않는 기본 테이블의 변경 내용입니다.  
  
 값 `GetRecordCount` 테이블 형식에서 레코드 집합 테이블에 있는 레코드의 대략적인 수를 반영 되어 있으며는 영향을 받는 즉시 테이블 레코드 추가 및 삭제 합니다.  
  
 레코드가 없는 레코드 집합 값이 0 반환합니다. ODBC 데이터베이스 또는 연결 된 테이블을 작업할 때 `GetRecordCount` 항상-1 반환 합니다. 호출 된 **Requery** 레코드 집합에서 멤버 함수에 값을 기본값으로 다시 설정 `GetRecordCount` 하면 쿼리가 다시 실행 된 것 처럼 합니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "RecordCount Property" 항목을 참조 합니다.  
  
##  <a name="getsql"></a>CDaoRecordset::GetSQL  
 이 멤버 함수는가 열려 있을 때 레코드 집합의 레코드를 선택 하는 데 사용 된 SQL 문이를 호출 합니다.  
  
```  
CString GetSQL() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` SQL 문이 들어 있는입니다.  
  
### <a name="remarks"></a>설명  
 일반적으로 SQL 됩니다 **선택** 문.  
  
 반환한 문자열 `GetSQL` 간에 차이가 있는 일반적으로 모든 문자열에서 레코드 집합에 전달 했습니다는 `lpszSQL` 매개 변수를는 [열려](#open) 멤버 함수입니다. 레코드 집합에 전달 하는 것에 따라 전체 SQL 문을 생성 때문에 이것이 **열려**, 클래스, 마법사를 사용 하 여 지정한 내용 및 어떻게 지정에 [m_strFilter](#m_strfilter) 및 [m_strSort](#m_strsort) 데이터 멤버입니다.  
  
> [!NOTE]
>  이 함수를 호출한 후에 호출 **열려**합니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "SQL Property" 항목을 참조 합니다.  
  
##  <a name="gettype"></a>CDaoRecordset::GetType  
 레코드 집합 개체의 형식을 확인 하는 레코드 집합을 연 후이 함수를 호출 합니다.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합의 형식을 나타내는 다음 값 중 하나입니다.  
  
- **dbOpenTable** 테이블 형식의 레코드 집합  
  
- **dbOpenDynaset** 다이너셋 형식의 레코드 집합  
  
- **dbOpenSnapshot** 스냅숏 형식 레코드 집합  
  
### <a name="remarks"></a>설명  
 관련된 정보에 대 한 항목 DAO 도움말의 "Type 속성"을 참조 합니다.  
  
##  <a name="getvalidationrule"></a>CDaoRecordset::GetValidationRule  
 데이터 유효성 검사에 사용 되는 규칙을 확인 하려면이 함수를 호출 합니다.  
  
```  
CString GetValidationRule();
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 가 변경 되거나 테이블에 추가 되는 레코드의 데이터 유효성을 검사 하는 값을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 규칙은 텍스트 기반 하 고 사용 하는 테이블이 변경 될 때마다 적용 됩니다. 데이터를 사용할 수 없는 경우 MFC는 예외가 throw 됩니다. 반환 된 오류 메시지를 지정 하는 경우 기본 필드 개체의 유효성 검사 텍스트 속성의 텍스트 또는 내부 필드 개체의 유효성 검사 규칙 속성에 지정 된 식의 텍스트입니다. 호출할 수 있습니다 [GetValidationText](#getvalidationtext) 오류 메시지의 텍스트를 가져올 수 있습니다.  
  
 예를 들어 월의 일을 필요로 하는 레코드의 필드는 규칙이 있을 수 유효성 검사와 같은 "일 BETWEEN 1에서 31입니다."  
  
 관련된 정보에 대 한 DAO 도움말의 "ValidationRule Property" 항목을 참조 합니다.  
  
##  <a name="getvalidationtext"></a>CDaoRecordset::GetValidationText  
 기본 필드 개체의 유효성 검사 텍스트 속성의 텍스트를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetValidationText();
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 필드의 값은 기본 필드 개체의 유효성 검사 규칙을 충족 하지 못하는 경우 표시 되는 메시지의 텍스트를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 관련된 정보에 대 한 DAO 도움말의 "유효성 검사 텍스트 Property" 항목을 참조 합니다.  
  
##  <a name="isbof"></a>CDaoRecordset::IsBOF  
 레코드 집합의 첫 번째 레코드 바로 앞를 벗어났는지 여부를 알아보려면 레코드로 레코드에서 스크롤하기 전에이 멤버 함수를 호출 합니다.  
  
```  
BOOL IsBOF() const;  
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 레코드; 앞 뒤로 스크롤 하는 경우 또는 레코드 집합에 레코드가 없는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 호출할 수도 있습니다 `IsBOF` 와 함께 `IsEOF` 레코드 집합에는 모든 레코드가 포함 하거나 비어 있는지 확인 하려면. 호출한 후에 즉시 **열려**레코드 집합에 레코드가 없는 경우, `IsBOF` 0이 아닌 값을 반환 합니다. 첫 번째 레코드는 현재 레코드 레코드가 하나 이상 있는 레코드 집합을 열 때 및 `IsBOF` 0을 반환 합니다.  
  
 첫 번째 레코드는 현재 레코드 경우 호출 하면 `MovePrev`, `IsBOF` 이후에 0이 아닌 반환 합니다. 경우 `IsBOF` 0이 아닌 값을 반환 하 고 호출 `MovePrev`, 예외가 throw 됩니다. 경우 `IsBOF` 반환 0이 아니고, 현재 레코드는 정의 되지 하 고 현재 레코드를 필요로 하는 모든 작업에서 예외가 발생 합니다.  
  
 특정 메서드의 효과 `IsBOF` 및 `IsEOF` 설정:  
  
-   호출 **열려** 내부적으로 사용 하면 첫 번째 레코드는 레코드 집합의 현재 레코드를 호출 하 여 **MoveFirst**합니다. 따라서 호출 **열려** 빈 집합이 레코드 원인에 `IsBOF` 및 `IsEOF` 0이 아닌 반환할 합니다. (실패 한 작업의 동작에 대 한 다음 표를 참조 **MoveFirst** 또는 `MoveLast` 호출 합니다.)  
  
-   둘 다 하는 레코드를 찾아 성공적으로 이동 작업의 모든 발생 `IsBOF` 및 `IsEOF` 0을 반환할 수 있습니다.  
  
-   `AddNew` 호출 뒤는 **업데이트** 성공적으로 새 레코드를 삽입 하는 호출 하면 `IsBOF` 0 이지만 경우에만 반환할 `IsEOF` 0이 아닌 이미 합니다. 상태 `IsEOF` 항상 변경 되지 것입니다. Microsoft Jet 데이터베이스 엔진에 정의 된 대로 빈 레코드 집합의 현재 레코드 포인터 이므로 파일의 끝에서 현재 레코드 뒤에 새 레코드 삽입 됩니다.  
  
-   모든 **삭제** 호출 하 여 레코드 집합에서 남아 있는 마지막 레코드를 제거 하는 경우에 변경 되지 것입니다 값 `IsBOF` 또는 `IsEOF`합니다.  
  
 이 테이블의 다양 한 조합과 함께 허용 하는 이동 작업을 보여 줍니다. `IsBOF` /  `IsEOF`합니다.  
  
||MoveFirst, MoveLast|MovePrev,<br /><br /> 이동< 0></ 0>|Move 0|MoveNext<br /><br /> > 0 이동|  
|------|-------------------------|-----------------------------|------------|-----------------------------|  
|`IsBOF`= 0이 아닌 경우<br /><br /> `IsEOF`=0|Allowed|예외|예외|Allowed|  
|`IsBOF`=0,<br /><br /> `IsEOF`0이 아닌 값 =|Allowed|Allowed|예외|예외|  
|둘 다 0이 아닌|예외|예외|예외|예외|  
|둘 다 0|Allowed|Allowed|Allowed|Allowed|  
  
 이동 작업이 허용을 작업 레코드를 제대로 찾는 것은 아닙니다. 단순히 지정 된 이동 작업을 수행 하려고 ï ´ ù 고 예외가 생성 되지 것입니다 나타냅니다. 값은 `IsBOF` 및 `IsEOF` 멤버 함수는 move 메서드 실행된의 결과로 변경 될 수 있습니다.  
  
 값에는 레코드를 두지 않는 이동 작업의 효과 `IsBOF` 및 `IsEOF` 설정은 다음 표에 표시 됩니다.  
  
||IsBOF|IsEOF|  
|------|-----------|-----------|  
|**MoveFirst**,`MoveLast`|0이 아닌|0이 아닌|  
|**이동** 0|변경 안 함|변경 안 함|  
|`MovePrev`, **Move**< 0></ 0>|0이 아닌|변경 안 함|  
|`MoveNext`, **Move** > 0|변경 안 함|0이 아닌|  
  
 관련된 내용은 항목을 참조 하십시오. "BOF, EOF 속성" DAO 도움말의 합니다.  
  
##  <a name="isdeleted"></a>CDaoRecordset::IsDeleted  
 현재 레코드 삭제 되었는지 여부를 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsDeleted() const;  
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합 삭제 된 레코드; 배치 되어 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 레코드를 스크롤할 경우 및 `IsDeleted` 반환 **TRUE** (0이 아님), 다음으로 스크롤해야 다른 레코드가 다른 레코드 집합 작업을 수행 하기 전에.  
  
> [!NOTE]
>  스냅숏 또는 테이블 형식의 레코드 집합의 레코드에 대 한 삭제 된 상태를 확인할 필요가 없습니다. 호출할 필요가 없습니다 없는 스냅숏에서 레코드를 삭제할 수 없으므로, `IsDeleted`합니다. 테이블 형식의 레코드 집합에 대 한 삭제 된 레코드는 레코드 집합에서 실제로 제거 됩니다. 일단 레코드가 삭제 되, 사용자, 다른 사용자 또는 다른 레코드 집합에서 해당 레코드에 다시 스크롤할 수 없습니다. 따라서를 호출 하지 않아도 됩니다 `IsDeleted`합니다.  
  
 다이너셋에서 레코드를 삭제 하는 경우 레코드 집합에서 제거 되 고 다시 해당 레코드를 스크롤할 수는 없습니다. 그러나의 레코드 다이너셋이 삭제 또는 다른 사용자가 동일한 테이블을 기반으로 하는 다른 레코드 집합의 `IsDeleted` 돌아갑니다 **TRUE** 때 나중에 스크롤할 때 해당 레코드입니다.  
  
 관련된 정보에 대 한 "Delete 메서드", "LastModified Property" 및 DAO 도움말의 "EditMode Property" 항목을 참조 합니다.  
  
##  <a name="iseof"></a>CDaoRecordset::IsEOF  
 레코드 집합의 마지막 레코드 범위를 벗어났는지 여부를 알아보려면 레코드로 레코드에서 스크롤할 때이 함수를 호출 합니다.  
  
```  
BOOL IsEOF() const;  
```  
  
### <a name="return-value"></a>반환 값  
 레코드 집합에 레코드가 없는 경우 또는 마지막 레코드; 보다 스크롤 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 호출할 수도 있습니다 `IsEOF` 레코드 집합에는 모든 레코드가 포함 하거나 비어 있는지 확인 하려면. 호출한 후에 즉시 **열려**레코드 집합에 레코드가 없는 경우, `IsEOF` 0이 아닌 값을 반환 합니다. 첫 번째 레코드는 현재 레코드 레코드가 하나 이상 있는 레코드 집합을 열 때 및 `IsEOF` 0을 반환 합니다.  
  
 호출 하는 경우 마지막 레코드가 현재 레코드 `MoveNext`, `IsEOF` 이후에 0이 아닌 반환 합니다. 경우 `IsEOF` 0이 아닌 값을 반환 하 고 호출 `MoveNext`, 예외가 throw 됩니다. 경우 `IsEOF` 반환 0이 아니고, 현재 레코드는 정의 되지 하 고 현재 레코드를 필요로 하는 모든 작업에서 예외가 발생 합니다.  
  
 특정 메서드의 효과 `IsBOF` 및 `IsEOF` 설정:  
  
-   호출 **열려** 내부적으로 사용 하면 첫 번째 레코드는 레코드 집합의 현재 레코드를 호출 하 여 **MoveFirst**합니다. 따라서 호출 **열려** 빈 집합이 레코드 원인에 `IsBOF` 및 `IsEOF` 0이 아닌 반환할 합니다. (실패 한 작업의 동작에 대 한 다음 표를 참조 **MoveFirst** 호출 합니다.)  
  
-   둘 다 하는 레코드를 찾아 성공적으로 이동 작업의 모든 발생 `IsBOF` 및 `IsEOF` 0을 반환할 수 있습니다.  
  
-   `AddNew` 호출 뒤는 **업데이트** 성공적으로 새 레코드를 삽입 하는 호출 하면 `IsBOF` 0 이지만 경우에만 반환할 `IsEOF` 0이 아닌 이미 합니다. 상태 `IsEOF` 항상 변경 되지 것입니다. Microsoft Jet 데이터베이스 엔진에 정의 된 대로 빈 레코드 집합의 현재 레코드 포인터 이므로 파일의 끝에서 현재 레코드 뒤에 새 레코드 삽입 됩니다.  
  
-   모든 **삭제** 호출 하 여 레코드 집합에서 남아 있는 마지막 레코드를 제거 하는 경우에 변경 되지 것입니다 값 `IsBOF` 또는 `IsEOF`합니다.  
  
 이 테이블의 다양 한 조합과 함께 허용 하는 이동 작업을 보여 줍니다. `IsBOF` /  `IsEOF`합니다.  
  
||MoveFirst, MoveLast|MovePrev,<br /><br /> 이동< 0></ 0>|Move 0|MoveNext<br /><br /> > 0 이동|  
|------|-------------------------|-----------------------------|------------|-----------------------------|  
|`IsBOF`= 0이 아닌 경우<br /><br /> `IsEOF`=0|Allowed|예외|예외|Allowed|  
|`IsBOF`=0,<br /><br /> `IsEOF`0이 아닌 값 =|Allowed|Allowed|예외|예외|  
|둘 다 0이 아닌|예외|예외|예외|예외|  
|둘 다 0|Allowed|Allowed|Allowed|Allowed|  
  
 이동 작업이 허용을 작업 레코드를 제대로 찾는 것은 아닙니다. 단순히 지정 된 이동 작업을 수행 하려고 ï ´ ù 고 예외가 생성 되지 것입니다 나타냅니다. 값은 `IsBOF` 및 `IsEOF` 멤버 함수는 Move 메서드 실행된의 결과로 변경 될 수 있습니다.  
  
 값에는 레코드를 두지 않는 이동 작업의 효과 `IsBOF` 및 `IsEOF` 설정은 다음 표에 표시 됩니다.  
  
||IsBOF|IsEOF|  
|------|-----------|-----------|  
|**MoveFirst**,`MoveLast`|0이 아닌|0이 아닌|  
|**이동** 0|변경 안 함|변경 안 함|  
|`MovePrev`, **Move**< 0></ 0>|0이 아닌|변경 안 함|  
|`MoveNext`, **Move** > 0|변경 안 함|0이 아닌|  
  
 관련된 내용은 항목을 참조 하십시오. "BOF, EOF 속성" DAO 도움말의 합니다.  
  
##  <a name="isfielddirty"></a>CDaoRecordset::IsFieldDirty  
 다이너셋의 지정 된 필드 데이터 멤버 "더티"으로 플래그가 지정 되었는지 여부를 확인 하려면 (변경)이 함수를 호출 합니다.  
  
```  
BOOL IsFieldDirty(void* pv);
```  
  
### <a name="parameters"></a>매개 변수  
 `pv`  
 필드 데이터 멤버의 상태를 확인 하려면에 대 한 포인터 또는 **NULL** 더티이 필드를 확인 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 필드 데이터 멤버; 커밋되지 않은 것으로 플래그가 지정 되어 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 모든 더티 필드 데이터 멤버의 데이터를 전송할 레코드를 데이터 원본에 대해를 호출 하 여 현재 레코드가 업데이트 될 때는 **업데이트** 의 멤버 함수 `CDaoRecordset` (호출한 이후 **편집** 또는 `AddNew`). 이 정보를 진행할 수 있습니다 더,와 같은 해제 필드 데이터 멤버는 데이터 소스에 쓸 수는 열을 표시 합니다.  
  
 `IsFieldDirty`이 통해 구현 `DoFieldExchange`합니다.  
  
##  <a name="isfieldnull"></a>CDaoRecordset::IsFieldNull  
 지정 된 필드 데이터 멤버는 레코드 집합의 Null로 플래그가 지정 되었는지 여부를 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsFieldNull(void* pv);
```  
  
### <a name="parameters"></a>매개 변수  
 `pv`  
 필드 데이터 멤버의 상태를 확인 하려면에 대 한 포인터 또는 **NULL** Null이 있는 필드를 확인 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 필드 데이터 멤버는 Null;로 플래그가 지정 되어 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 (데이터베이스 용어에서 Null 의미 "가치가 없습니다" 아니며 동일 **NULL** c + +에서.) 필드 데이터 멤버를 Null로 플래그가 지정 되어 값이 현재 레코드의 열으로 해석 됩니다.  
  
> [!NOTE]
>  사용 하 여 특정 상황에서는 `IsFieldNull` 비효율적일 수 있습니다, 다음 코드 예제와 같이:  
  
 [!code-cpp[NVC_MFCDatabase # 5](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]  
  
> [!NOTE]
>  파생 하지 않고도 동적 레코드 바인딩을 사용 중인 경우 `CDaoRecordset`을 사용 해야 **VT_NULL** 예제에서와 같이 합니다.  
  
##  <a name="isfieldnullable"></a>CDaoRecordset::IsFieldNullable  
 이 멤버 함수는 지정 된 필드 데이터 멤버 "null"이 허용 되는지 확인 하려면 (설정 될 수 있습니다; Null 값으로 호출 C + + **NULL** Null 이며 데이터베이스 용어에서 의미 같지는 않습니다 "가치가 없음").  
  
```  
BOOL IsFieldNullable(void* pv);
```  
  
### <a name="parameters"></a>매개 변수  
 `pv`  
 필드 데이터 멤버의 상태를 확인 하려면에 대 한 포인터 또는 **NULL** Null이 있는 필드를 확인 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 필드 데이터 멤버에 null 인 경우 만들 수 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 Null이 될 수 없는 필드 값이 있어야 합니다. 데이터 소스를 추가 또는 업데이트를 거부 이러한 필드를 추가 하거나 레코드를 업데이트할 때 Null로 설정 하려고 하면 및 **업데이트** 예외가 throw 됩니다. 호출 하면 예외가 발생 **업데이트**호출할 때가 아니라, `SetFieldNull`합니다.  
  
##  <a name="isopen"></a>CDaoRecordset::IsOpen  
 레코드 집합 열기 인지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우 recordset 개체 **열려** 또는 **Requery** 멤버 함수를 이전에 호출 하 고 레코드 집합 닫히지 않은; 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="m_bcheckcachefordirtyfields"></a>Cdaorecordset:: M_bcheckcachefordirtyfields  
 여부 캐시 된 필드는 자동으로 표시 커밋되지 않음 (변경) 나타내는 플래그를 포함 및 Null입니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 플래그 **TRUE**합니다. 전체 이중 버퍼링 메커니즘을 제어 하는이 데이터 멤버에 합니다. 플래그를 설정 하면 **TRUE**, DFX 메커니즘을 사용 하 여 필드 별로 캐싱을 해제할 수 있습니다. 플래그를 설정 하면 **FALSE**를 호출 해야 `SetFieldDirty` 및 `SetFieldNull` 직접 합니다.  
  
 이 데이터 멤버를 호출 하기 전에 설정 **열려**합니다. 이 메커니즘은 주로 사용 하기 쉬운 됩니다. 성능 변경 내용을 적용할 때 이중 버퍼링 필드의 때문에 느려질 수 있습니다.  
  
##  <a name="m_nfields"></a>CDaoRecordset::m_nFields  
 레코드 집합 클래스의 필드 데이터 멤버의 수와 데이터 소스에서 레코드 집합에서 선택한 열 수가 포함 되어 있습니다.  
  
### <a name="remarks"></a>주의  
 레코드 집합 클래스에 대 한 생성자를 초기화 해야 `m_nFields` 올바른 개수의 정적으로 바인딩된 필드입니다. 클래스 마법사 클래스를 선언할 때 레코드 집합을 사용 하는 경우이 초기화를 씁니다. 작성할 수도 있습니다 것 수동으로 합니다.  
  
 이 번호를 사용 하 여 필드 데이터 멤버와 데이터 소스에서 현재 레코드의 해당 열 간의 상호 작용을 관리 하는 프레임 워크입니다.  
  
> [!NOTE]
>  이 숫자에 등록 하는 출력 열의 수와 일치 해야 `DoFieldExchange` 를 호출한 후 `SetFieldType` 매개 변수와 함께 **CDaoFieldExchange::outputColumn**합니다.  
  
 동적으로 여 통해의 열을 바인딩할 수 `CDaoRecordset::GetFieldValue` 및 `CDaoRecordset::SetFieldValue`합니다. 이렇게 하면 불필요의 수를 증가 `m_nFields` 의 호출 DFX 함수의 수를 반영 하도록 프로그램 `DoFieldExchange` 멤버 함수입니다.  
  
##  <a name="m_nparams"></a>CDaoRecordset::m_nParams  
 레코드 집합 클래스의 매개 변수 데이터 멤버의 개수가-레코드 집합의 쿼리와 함께 전달 되는 매개 변수 수입니다.  
  
### <a name="remarks"></a>주의  
 레코드 집합 클래스에 매개 변수 데이터 멤버, 경우에 클래스에 대 한 생성자 초기화 해야 `m_nParams` 는 올바른 수를 사용 합니다. 값 `m_nParams` 기본값은 0입니다. 매개 변수 데이터 멤버를 추가 하는 경우-수동으로 수행 해야 하는-매개 변수 수를 반영 하기 위해 클래스 생성자에서 초기화를 수동으로 추가 해야 (수가 이상이 이어야 '의 자리 표시자 프로그램 **m_strFilter** 또는 `m_strSort` 문자열)입니다.  
  
 레코드 집합의 쿼리를 매개 변수화 하는 경우이 값을 사용 하는 프레임 워크입니다.  
  
> [!NOTE]
>  이 숫자는 "params"에 등록의 수와 일치 해야 `DoFieldExchange` 를 호출한 후 `SetFieldType` 매개 변수와 함께 **CFieldExchange::param**합니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "매개 변수 개체" 항목을 참조 합니다.  
  
##  <a name="m_pdaorecordset"></a>CDaoRecordset::m_pDAORecordset  
 DAO 레코드 집합 개체 내부에 대 한 OLE 인터페이스에 대 한 포인터는 `CDaoRecordset` 개체입니다.  
  
### <a name="remarks"></a>설명  
 DAO 인터페이스를 직접 액세스 해야 할 경우이 포인터를 사용 합니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "Recordset 개체" 항목을 참조 합니다.  
  
##  <a name="m_pdatabase"></a>CDaoRecordset::m_pDatabase  
 에 대 한 포인터는 `CDaoDatabase` 레코드 집합을 데이터 원본에 연결 되어 있는 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 변수는 두 가지 방법으로 설정 됩니다. 포인터에 전달 되는 일반적으로 `CDaoDatabase` 레코드 집합 개체를 생성할 때 개체입니다. 전달 하는 경우 **NULL** 대신 **CDaoRecordset** 만듭니다는 `CDaoDatabase` 개체를 엽니다. 두 경우 모두 `CDaoRecordset` 포인터를이 변수에 저장 합니다.  
  
 일반적으로 직접 않아도 됩니다에 저장 된 포인터를 사용 하도록 **m_pDatabase**합니다. 그러나 사용자 고유의 확장을 작성 하는 경우 `CDaoRecordset`, 포인터를 사용 하도록 할 수 있습니다. 예를 들어 할 수 있습니다 포인터 throw 되는 경우 사용자 고유의 `CDaoException`(s).  
  
 관련된 정보에 대 한 DAO 도움말의 "데이터베이스 개체가" 항목을 참조 합니다.  
  
##  <a name="m_strfilter"></a>CDaoRecordset::m_strFilter  
 생성 하는 데 사용 되는 문자열을 포함 된 **여기서** SQL 문의 절.  
  
### <a name="remarks"></a>주의  
 예약어는 포함 되지 않습니다 **여기서** 레코드 집합을 필터링 합니다. 이 데이터 멤버에 사용 하 여 테이블 형식 레코드 집합에 적용 되지 않습니다. 사용 **m_strFilter** 사용 하 여 레코드 집합을 열 때 아무 효과가 `CDaoQueryDef` 포인터입니다.  
  
 미국 날짜 형식 (월-일-연도)를 사용 하 여 Microsoft Jet 데이터베이스 엔진;의 (미국) 버전을 사용 하지 않는 경우에 날짜를 포함 하는 필드를 필터링 할 때 그렇지 않으면 예상 대로 데이터를 필터링 하지 않을 수 있습니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "필터 Property" 항목을 참조 합니다.  
  
##  <a name="m_strsort"></a>CDaoRecordset::m_strSort  
 포함 하는 문자열을 포함 된 **ORDERBY** 예약어 없이 SQL 문의 절 **ORDERBY**합니다.  
  
### <a name="remarks"></a>주의  
 다이너셋 및 스냅숏 형식 레코드 집합 개체에 정렬할 수 있습니다.  
  
 테이블 형식 레코드 집합 개체를 정렬할 수 없습니다. 테이블 형식 레코드 집합의 정렬 순서를 확인 하려면 호출 [SetCurrentIndex](#setcurrentindex)합니다.  
  
 사용 `m_strSort` 사용 하 여 레코드 집합을 열 때 아무 효과가 `CDaoQueryDef` 포인터입니다.  
  
 관련된 정보에 대 한 "Sort 속성" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="move"></a>CDaoRecordset::Move  
 레코드 집합을 배치 하려면이 함수를 호출 `lRows` 현재 레코드에서 레코드입니다.  
  
```  
virtual void Move(long lRows);
```  
  
### <a name="parameters"></a>매개 변수  
 `lRows`  
 앞으로 또는 뒤로 이동 하는 레코드의 수입니다. 양수 값을 레코드 집합의 끝 부분으로 앞으로 이동 합니다. 음수 값 시작 부분을 향해 뒤로 이동합니다.  
  
### <a name="remarks"></a>주의  
 앞으로 또는 뒤로 이동할 수 있습니다. `Move( 1 )`에 해당 `MoveNext`, 및 `Move( -1 )` 같습니다 `MovePrev`합니다.  
  
> [!CAUTION]
>  중 하나를 호출는 **이동** 함수 레코드 집합에 레코드가 없는 경우 예외를 throw 합니다. 일반적으로 모두 호출 `IsBOF` 및 `IsEOF` 레코드 집합에 레코드가 있는지 확인 하기 위해 이동 작업이 하기 전에. 호출한 후 **열려** 또는 **Requery**, 호출 `IsBOF` 또는 `IsEOF`합니다.  
  
> [!NOTE]
>  시작 또는 레코드 집합의 끝을 지나서 스크롤 하는 경우 ( `IsBOF` 또는 `IsEOF` 0이 아닌 반환)에 대 한 호출 **이동** throw 한 `CDaoException`합니다.  
  
> [!NOTE]
>  중 하나를 호출 하는 경우는 **이동** 함수 중에 현재 레코드는 업데이트 하거나 추가할 업데이트 경고 없이 손실 됩니다.  
  
 호출 하는 경우 **이동** 앞 으로만 이동 가능한 스크롤 스냅숏에 `lRows` 책갈피는 허용 되지 않으므로 진행 하려면만 및 매개 변수는 양의 정수 여야 합니다.  
  
 첫 번째, 마지막을 하려면 다음 또는 이전 기록 레코드 집합의 현재 레코드, 호출 된 **MoveFirst**, `MoveLast`, `MoveNext`, 또는 `MovePrev` 멤버 함수입니다.  
  
 관련된 정보에 대 한 "Move 메서드" 항목을 참조 하 고 "MoveFirst, MoveLast, MoveNext, MovePrevious 메서드" DAO 도움말의 합니다.  
  
##  <a name="movefirst"></a>CDaoRecordset::MoveFirst  
 (있는 경우) 레코드 집합의 첫 번째 레코드를 확인 하려면이 함수를 호출 하면 현재 레코드입니다.  
  
```  
void MoveFirst();
```  
  
### <a name="remarks"></a>설명  
 호출할 필요가 없습니다 **MoveFirst** 레코드 집합을 연 후에 즉시 합니다. 그 당시 (있는 경우) 첫 번째 레코드는 자동으로 현재 레코드.  
  
> [!CAUTION]
>  중 하나를 호출는 **이동** 함수 레코드 집합에 레코드가 없는 경우 예외를 throw 합니다. 일반적으로 모두 호출 `IsBOF` 및 `IsEOF` 레코드 집합에 레코드가 있는지 확인 하기 위해 이동 작업이 하기 전에. 호출한 후 **열려** 또는 **Requery**, 호출 `IsBOF` 또는 `IsEOF`합니다.  
  
> [!NOTE]
>  중 하나를 호출 하는 경우는 **이동** 함수 중에 현재 레코드는 업데이트 하거나 추가할 업데이트 경고 없이 손실 됩니다.  
  
 사용 하 여는 **이동** 조건을 적용 하지 않고 레코드 간을 이동 하는 함수입니다. 찾기 작업을 사용 하 여 다이너셋 형식 또는 특정 조건을 충족 하는 스냅숏 형식 레코드 집합 개체에서 레코드를 찾을 수 있습니다. 테이블 형식 레코드 집합 개체에서 레코드를 찾으려고 호출 `Seek`합니다.  
  
 레코드 집합은 테이블 형식의 레코드 집합을 참조 하는 경우 이동 테이블의 현재 인덱스를 따릅니다. 현재 인덱스가 기본 DAO 개체의 인덱스 속성을 사용 하 여 설정할 수 있습니다. 현재 인덱스를 설정 하지 않으면 반환 된 레코드의 순서가 정의 되지 않습니다.  
  
 호출 하는 경우 `MoveLast` SQL 쿼리 또는 쿼리 정의에 따라 recordset 개체에 쿼리가 완료 될 때까지 강제 되 고 레코드 집합 개체는 완전히 채워집니다.  
  
 호출할 수 없습니다는 **MoveFirst** 또는 `MovePrev` 앞 으로만 이동 가능한 스크롤 스냅숏 사용 하 여 멤버 함수입니다.  
  
 개의 레코드를 앞 이나 뒤로 돌립니다 특정 레코드 집합 개체에 기록의 현재 위치를 이동 하려면 호출 **이동**합니다.  
  
 관련된 정보에 대 한 "Move 메서드" 항목을 참조 하 고 "MoveFirst, MoveLast, MoveNext, MovePrevious 메서드" DAO 도움말의 합니다.  
  
##  <a name="movelast"></a>CDaoRecordset::MoveLast  
 현재 레코드가 레코드 집합의 마지막 레코드 (해당 되는 경우)를 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
void MoveLast();
```  
  
### <a name="remarks"></a>주의  
  
> [!CAUTION]
>  중 하나를 호출는 **이동** 함수 레코드 집합에 레코드가 없는 경우 예외를 throw 합니다. 일반적으로 모두 호출 `IsBOF` 및 `IsEOF` 레코드 집합에 레코드가 있는지 확인 하기 위해 이동 작업이 하기 전에. 호출한 후 **열려** 또는 **Requery**, 호출 `IsBOF` 또는 `IsEOF`합니다.  
  
> [!NOTE]
>  중 하나를 호출 하는 경우는 **이동** 함수 중에 현재 레코드는 업데이트 하거나 추가할 업데이트 경고 없이 손실 됩니다.  
  
 사용 하 여는 **이동** 조건을 적용 하지 않고 레코드 간을 이동 하는 함수입니다. 찾기 작업을 사용 하 여 다이너셋 형식 또는 특정 조건을 충족 하는 스냅숏 형식 레코드 집합 개체에서 레코드를 찾을 수 있습니다. 테이블 형식 레코드 집합 개체에서 레코드를 찾으려고 호출 `Seek`합니다.  
  
 레코드 집합은 테이블 형식의 레코드 집합을 참조 하는 경우 이동 테이블의 현재 인덱스를 따릅니다. 현재 인덱스가 기본 DAO 개체의 인덱스 속성을 사용 하 여 설정할 수 있습니다. 현재 인덱스를 설정 하지 않으면 반환 된 레코드의 순서가 정의 되지 않습니다.  
  
 호출 하는 경우 `MoveLast` SQL 쿼리 또는 쿼리 정의에 따라 recordset 개체에 쿼리가 완료 될 때까지 강제 되 고 레코드 집합 개체는 완전히 채워집니다.  
  
 개의 레코드를 앞 이나 뒤로 돌립니다 특정 레코드 집합 개체에 기록의 현재 위치를 이동 하려면 호출 **이동**합니다.  
  
 관련된 정보에 대 한 "Move 메서드" 항목을 참조 하 고 "MoveFirst, MoveLast, MoveNext, MovePrevious 메서드" DAO 도움말의 합니다.  
  
##  <a name="movenext"></a>CDaoRecordset::MoveNext  
 현재 레코드가 레코드 집합의 다음 레코드를 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
void MoveNext();
```  
  
### <a name="remarks"></a>주의  
 호출 하는 것이 좋습니다. `IsBOF` 이전 레코드로 이동 하기 전에. 에 대 한 호출 `MovePrev` throw 됩니다는 `CDaoException` 경우 `IsBOF` 0이 아니고 첫 번째 레코드 바로 앞 스크롤 이미 또는 레코드가 없는 레코드 집합으로 선택 된 나타내는 반환 합니다.  
  
> [!CAUTION]
>  중 하나를 호출는 **이동** 함수 레코드 집합에 레코드가 없는 경우 예외를 throw 합니다. 일반적으로 모두 호출 `IsBOF` 및 `IsEOF` 레코드 집합에 레코드가 있는지 확인 하기 위해 이동 작업이 하기 전에. 호출한 후 **열려** 또는 **Requery**, 호출 `IsBOF` 또는 `IsEOF`합니다.  
  
> [!NOTE]
>  중 하나를 호출 하는 경우는 **이동** 함수 중에 현재 레코드는 업데이트 하거나 추가할 업데이트 경고 없이 손실 됩니다.  
  
 사용 하 여는 **이동** 조건을 적용 하지 않고 레코드 간을 이동 하는 함수입니다. 찾기 작업을 사용 하 여 다이너셋 형식 또는 특정 조건을 충족 하는 스냅숏 형식 레코드 집합 개체에서 레코드를 찾을 수 있습니다. 테이블 형식 레코드 집합 개체에서 레코드를 찾으려고 호출 `Seek`합니다.  
  
 레코드 집합은 테이블 형식의 레코드 집합을 참조 하는 경우 이동 테이블의 현재 인덱스를 따릅니다. 현재 인덱스가 기본 DAO 개체의 인덱스 속성을 사용 하 여 설정할 수 있습니다. 현재 인덱스를 설정 하지 않으면 반환 된 레코드의 순서가 정의 되지 않습니다.  
  
 개의 레코드를 앞 이나 뒤로 돌립니다 특정 레코드 집합 개체에 기록의 현재 위치를 이동 하려면 호출 **이동**합니다.  
  
 관련된 정보에 대 한 "Move 메서드" 항목을 참조 하 고 "MoveFirst, MoveLast, MoveNext, MovePrevious 메서드" DAO 도움말의 합니다.  
  
##  <a name="moveprev"></a>CDaoRecordset::MovePrev  
 레코드 집합의 현재 레코드의 이전 레코드를 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
void MovePrev();
```  
  
### <a name="remarks"></a>주의  
 호출 하는 것이 좋습니다. `IsBOF` 이전 레코드로 이동 하기 전에. 에 대 한 호출 `MovePrev` throw 됩니다는 `CDaoException` 경우 `IsBOF` 0이 아니고 첫 번째 레코드 바로 앞 스크롤 이미 또는 레코드가 없는 레코드 집합으로 선택 된 나타내는 반환 합니다.  
  
> [!CAUTION]
>  중 하나를 호출는 **이동** 함수 레코드 집합에 레코드가 없는 경우 예외를 throw 합니다. 일반적으로 모두 호출 `IsBOF` 및 `IsEOF` 레코드 집합에 레코드가 있는지 확인 하기 위해 이동 작업이 하기 전에. 호출한 후 **열려** 또는 **Requery**, 호출 `IsBOF` 또는 `IsEOF`합니다.  
  
> [!NOTE]
>  중 하나를 호출 하는 경우는 **이동** 함수 중에 현재 레코드는 업데이트 하거나 추가할 업데이트 경고 없이 손실 됩니다.  
  
 사용 하 여는 **이동** 조건을 적용 하지 않고 레코드 간을 이동 하는 함수입니다. 찾기 작업을 사용 하 여 다이너셋 형식 또는 특정 조건을 충족 하는 스냅숏 형식 레코드 집합 개체에서 레코드를 찾을 수 있습니다. 테이블 형식 레코드 집합 개체에서 레코드를 찾으려고 호출 `Seek`합니다.  
  
 레코드 집합은 테이블 형식의 레코드 집합을 참조 하는 경우 이동 테이블의 현재 인덱스를 따릅니다. 현재 인덱스가 기본 DAO 개체의 인덱스 속성을 사용 하 여 설정할 수 있습니다. 현재 인덱스를 설정 하지 않으면 반환 된 레코드의 순서가 정의 되지 않습니다.  
  
 호출할 수 없습니다는 **MoveFirst** 또는 `MovePrev` 앞 으로만 이동 가능한 스크롤 스냅숏 사용 하 여 멤버 함수입니다.  
  
 개의 레코드를 앞 이나 뒤로 돌립니다 특정 레코드 집합 개체에 기록의 현재 위치를 이동 하려면 호출 **이동**합니다.  
  
 관련된 정보에 대 한 "Move 메서드" 항목을 참조 하 고 "MoveFirst, MoveLast, MoveNext, MovePrevious 메서드" DAO 도움말의 합니다.  
  
##  <a name="open"></a>Cdaorecordset:: Open  
 레코드 집합에 대 한 레코드를 검색 하려면이 멤버 함수를 호출 해야 합니다.  
  
```  
virtual void Open(
    int nOpenType = AFX_DAO_USE_DEFAULT_TYPE,  
    LPCTSTR lpszSQL = NULL,  
    int nOptions = 0);

 
virtual void Open(
    CDaoTableDef* pTableDef,  
    int nOpenType = dbOpenTable,  
    int nOptions = 0);

 
virtual void Open(
    CDaoQueryDef* pQueryDef,  
    int nOpenType = dbOpenDynaset,  
    int nOptions = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `nOpenType`  
 다음 값 중 하나입니다.  
  
- **dbOpenDynaset** 양방향 스크롤이 다이너셋 형식의 레코드 집합입니다. 이 값이 기본값입니다.  
  
- **dbOpenTable** 양방향 스크롤이 테이블 형식의 레코드 집합입니다.  
  
- **dbOpenSnapshot** 양방향 스크롤이 스냅숏 형식 레코드 집합입니다.  
  
 `lpszSQL`  
 다음 중 하나를 포함 하는 문자열 포인터.  
  
-   A **NULL** 포인터입니다.  
  
-   하나 이상의 테이블 정의 및/또는 쿼리 정의 (쉼표로 구분)의 이름입니다.  
  
-   SQL **선택** 문 (선택적으로는 SQL **여기서** 또는 **ORDERBY** 절).  
  
-   통과 쿼리 합니다.  
  
 `nOptions`  
 하나 이상의 아래 나열 된 옵션입니다. 기본값은 0입니다. 다음과 같은 값을 사용할 수 있습니다.  
  
- **dbAppendOnly** 새 레코드 (다이너셋 형식의 레코드 집합에만 해당)만 추가할 수 있습니다. 이 옵션은 문자 그대로 레코드 추가 될 수 있습니다. MFC ODBC 데이터베이스 클래스에는를 검색 하 고 추가 허용 하는 추가 전용 옵션이 제공 됩니다.  
  
- **dbForwardOnly** 레코드 집합은 정방향 스크롤 스냅숏입니다.  
  
- **dbSeeChanges** 다른 사용자가 편집 중인 데이터를 변경 하는 경우 예외를 생성 합니다.  
  
- **dbDenyWrite** 다른 사용자가 수정 하거나 레코드를 추가할 수 없습니다.  
  
- **dbDenyRead** 다른 사용자 (테이블 형식 레코드 집합에만 해당) 레코드를 볼 수 없습니다.  
  
- **dbReadOnly** 레코드를 볼 수 있습니다; 다른 사용자가 수정할 수 있습니다.  
  
- **dbInconsistent** 일관성 없는 업데이트 (다이너셋 형식의 레코드 집합에만 해당)는 사용할 수 있습니다.  
  
- **dbConsistent** 업데이트 일관성 (다이너셋 형식의 레코드 집합에만 해당)에 허용 됩니다.  
  
> [!NOTE]
>  상수 **dbConsistent** 및 **dbInconsistent** 함께 사용할 수 없습니다. 하나를 사용 하면 또는 다른 하나만의 지정 된 인스턴스에서 **열려**합니다.  
  
 *pTableDef*  
 에 대 한 포인터는 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 개체입니다. 이 버전은 테이블 형식의 레코드 집합에 대해서만 유효 합니다. 이 옵션을 사용 하는 경우는 `CDaoDatabase` 포인터 생성에 사용 되는 `CDaoRecordset` 사용 되지 않습니다; 테이블 정의 프로시저가 있는 데이터베이스를 사용 하는 대신, 합니다.  
  
 *pQueryDef*  
 에 대 한 포인터는 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 개체입니다. 이 버전은 다이너셋 유형 및 스냅숏 형식 레코드 집합에 대해서만 유효 합니다. 이 옵션을 사용 하는 경우는 `CDaoDatabase` 포인터 생성에 사용 되는 `CDaoRecordset` 사용 되지 않습니다; 쿼리 정의 프로시저가 있는 데이터베이스를 사용 하는 대신, 합니다.  
  
### <a name="remarks"></a>주의  
 호출 하기 전에 **열려**, 레코드 집합 개체를 생성 해야 합니다. 다음과 같은 여러 가지 방법으로 이 작업을 수행할 수 있습니다.  
  
-   레코드 집합 개체를 생성할 때 전달에 대 한 포인터는 `CDaoDatabase` 이미 열려 있는 개체입니다.  
  
-   레코드 집합 개체를 생성할 때 전달에 대 한 포인터는 `CDaoDatabase` 열려 있는 개체입니다. 레코드 집합을 연는 `CDaoDatabase` 개체 하지만 닫지 것입니다 recordset 개체를 닫을 때.  
  
-   레코드 집합 개체를 생성할 때 전달 된 **NULL** 포인터입니다. 레코드 집합 개체 호출 `GetDefaultDBName` Microsoft Access의 이름을 가져올 수 있습니다. MDB 파일을 열 수 있습니다. 레코드 집합을 연 다음는 `CDaoDatabase` 개체와 서 레코드 집합 열기를 열고 유지 합니다. 호출 하는 경우 **닫기** 레코드 집합에는 `CDaoDatabase` 개체도 닫힙니다.  
  
    > [!NOTE]
    >  레코드 집합을 연 경우는 `CDaoDatabase` 개체 데이터 소스 비독점적으로 액세스를 사용 하 여 여 합니다.  
  
 버전에 대 한 **열고** 를 사용 하는 `lpszSQL` 매개 변수를 레코드 집합이 열린 여러 방법 중 하나에 있는 레코드를 검색할 수 있습니다. DFX 함수에 사용 하도록 첫 번째 옵션은 프로그램 `DoFieldExchange`합니다. 두 번째 옵션은 호출 하 여 동적 바인딩을 사용 하 여 `GetFieldValue` 멤버 함수입니다. 개별적으로 또는 함께이 옵션을 구현할 수 있습니다. 를 결합 하는 경우 전달 SQL 문에서 직접 호출 해야 합니다 **열려**합니다.  
  
 두 번째 버전을 사용 하는 경우 **열려** 전달 하는 `CDaoTableDef` 개체, 결과 열을 통해 바인딩할 수 제공 됩니다 `DoFieldExchange` DFX 메커니즘 및 통해 동적으로 바인딩 `GetFieldValue`합니다.  
  
> [!NOTE]
>  호출할 수 있습니다. **열려** 를 사용 하 여는 `CDaoTableDef` 테이블 형식의 레코드 집합에 대 한 개체입니다.  
  
 세 번째 버전의를 사용 하는 경우 **열려** 전달 하는 `CDaoQueryDef` 개체, 쿼리 실행 및 결과 열을 통해 바인딩할 수 제공 됩니다 `DoFieldExchange` DFX 메커니즘 및 통해 동적으로 바인딩 `GetFieldValue`합니다.  
  
> [!NOTE]
>  에서만 호출할 수 있습니다 **열려** 를 사용 하는 `CDaoQueryDef` 다이너셋 형식 및 스냅숏 형식 레코드 집합에 대 한 개체입니다.  
  
 첫 번째 버전에 대 한 **열려** 를 사용 하는 `lpszSQL` 매개 변수를 레코드는 다음 표에 표시 된 기준에 따라 선택된 합니다.  
  
|`lpszSQL` 매개 변수의 값|선택한 레코드에 따라 다릅니다.|예제|  
|--------------------------------------|----------------------------------------|-------------|  
|**NULL**|반환한 문자열 `GetDefaultSQL`합니다.||  
|하나 이상의 테이블 정의 및/또는 쿼리 정의 이름을 포함 하는 쉼표로 구분 된 목록입니다.|모든 열에 표시 된 `DoFieldExchange`합니다.|`"Customer"`|  
|**선택** 열 목록 **FROM** 테이블 목록|지정 된 tabledef(s) 및/또는 querydef(s)의 지정 된 열입니다.|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|  
  
 전달 하는 일반적인 절차는 **NULL** 를 **열려**;이 경우 **열려** 호출 `GetDefaultSQL`, 만들 때 클래스 마법사에서 생성 하는 재정의 가능한 멤버 함수는 `CDaoRecordset`-클래스를 파생 합니다. 클래스 마법사에서 지정한 tabledef(s) 및/또는 querydef 이름이이 값을 제공 합니다. 대신의 기타 정보를 지정할 수 있습니다는 `lpszSQL` 매개 변수입니다.  
  
 전달 무엇이 든 **열려** 쿼리에 대 한 최종 SQL 문자열을 만듭니다 (문자열 SQL 있을 수 있습니다 **여기서** 및 **ORDERBY** 절에 추가 `lpszSQL` 전달 된 문자열) 다음 쿼리를 실행 하 고 있습니다. 호출 하 여 생성 된 문자열을 검사할 수 `GetSQL` 호출한 후 **열려**합니다.  
  
 레코드 집합 클래스의 필드 데이터 멤버는 선택한 데이터의 열에 바인딩됩니다. 레코드가 반환 되는 경우 첫 번째 레코드는 현재 레코드가 됩니다.  
  
 필터 또는 정렬 같은 레코드 집합에 대 한 옵션을 설정 하려면 설정 `m_strSort` 또는 **m_strFilter** recordset 개체를 생성 한 후 있지만 호출 하기 전에 **열려**합니다. 레코드 집합이 이미 열린 후 레코드 집합의 레코드를 새로 고칠 하려는 경우, 호출 **Requery**합니다.  
  
 호출 하는 경우 **열려** 다이너셋 형식 또는 스냅숏 형식 레코드 집합에 않거나 사용할 수 없는 데이터 소스는 SQL 문 또는 연결 된 테이블을 나타내는 테이블 정의를 나타내면 **dbOpenTable** 형식 인수가; 이렇게 하면 MFC 예외를 throw 합니다. 테이블 정의 개체를 연결된 된 테이블을 나타내는지 여부를 확인 하려면 만든는 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 개체와 호출 해당 [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) 멤버 함수입니다.  
  
 사용 하 여는 **dbSeeChanges** 트랩을 편집 하거나 동일한 레코드를 삭제 하는 경우 다른 사용자 또는 컴퓨터에 다른 응용 프로그램을 통한 변경 하려는 경우 플래그를 지정 합니다. 예를 들어 두 명의 사용자가 동일한 레코드를 호출 하는 첫 번째 사용자 편집을 시작 하는 경우는 **업데이트** 멤버 함수에 성공 합니다. 때 **업데이트** 두 번째 사용자에 의해 호출 됩니다는 `CDaoException` throw 됩니다. 마찬가지로, 두 번째 사용자가이 호출 하는 경우 **삭제** 하며 레코드를 삭제 하려면 이미 변경 된 첫 번째 사용자는 `CDaoException` 발생 합니다.  
  
 일반적으로이 얻으면 `CDaoException` , 업데이트 하는 동안 코드 필드의 내용을 새로 고 해야 새로 수정된 된 값을 검색 합니다. 삭제 중에 예외가 발생 하는 경우 코드 사용자와 데이터 최근에 변경 되었음을 나타내는 메시지 새 레코드 데이터를 표시할 수 있습니다. 이 시점에서 사용자 코드에는 레코드를 삭제 하는 사용자가 여전히 있는지 확인 하는 요청할 수 있습니다.  
  
> [!TIP]
>  앞 으로만 이동 가능한 스크롤 옵션을 사용 하 여 ( **dbForwardOnly**) 응용 프로그램에서 레코드 집합에 대 한 번 통과 때 성능을 개선 하려면 ODBC 데이터 원본에서 열.  
  
 관련된 정보에 대 한 DAO 도움말의 "OpenRecordset Method" 항목을 참조 합니다.  
  
##  <a name="requery"></a>CDaoRecordset::Requery  
 레코드 집합 (새로 고침)를 다시 작성 하려면이 함수를 호출 합니다.  
  
```  
virtual void Requery();
```  
  
### <a name="remarks"></a>주의  
 레코드가 반환 되는 경우 첫 번째 레코드는 현재 레코드가 됩니다.  
  
 추가 및 삭제 또는 다른 사용자가 데이터 원본에 수행 하는 반영 하기 위해 레코드를 다시 작성 해야 레코드 집합 호출 하 여 **Requery**합니다. 레코드 집합 다이너셋 인 경우 자동으로 해당 기존 레코드 (추가 하지 않음) 또는 다른 사용자가 되도록 하는 업데이트를 반영 합니다. 레코드 집합 스냅숏일 경우 호출 해야 **Requery** 다른 사용자가 뿐만 아니라 추가 및 삭제 하 여 편집 내용을 반영 하도록 합니다.  
  
 다이너셋 또는 스냅숏으로 대 한 호출 **Requery** 매개 변수 값을 사용 하 여 레코드 집합 다시 작성 하려면 언제 든 지 합니다. 설정 하 여 새 필터 또는 정렬 설정 [m_strFilter](#m_strfilter) 및 [m_strSort](#m_strsort) 호출 하기 전에 **Requery**합니다. 새 값을 호출 하기 전에 매개 변수 데이터 멤버에 할당 하 여 새 매개 변수를 설정 **Requery**합니다.  
  
 레코드 집합 다시 시도가 실패 하면 레코드 집합 닫혀 있습니다. 호출 하기 전에 **Requery**를 호출 하 여 레코드 집합 다시 쿼리되어 수 있는지 여부를 확인할 수 있습니다는 [CanRestart](#canrestart) 멤버 함수입니다. `CanRestart`에서는 프로시저를 **Requery** 성공 합니다.  
  
> [!CAUTION]
>  호출 **Requery** 호출한 후에 **열려**합니다.  
  
> [!NOTE]
>  호출 [Requery](#requery) DAO 책갈피를 변경 합니다.  
  
 호출할 수 없습니다 **Requery** 다이너셋 형식 또는 호출 하는 경우 스냅숏 형식 레코드 집합에 `CanRestart` 0을 반환 하거나 테이블 형식 레코드 집합에 사용할 수 있습니다.  
  
 두 `IsBOF` 및 `IsEOF` 호출한 후 0이 아닌 반환 **Requery**, 모든 레코드와 레코드 집합에는 데이터가 없는 쿼리를 반환 하지 않았습니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "Requery 메서드" 항목을 참조 합니다.  
  
##  <a name="seek"></a>CDaoRecordset::Seek  
 이 현재 지정된 된 조건을 인덱싱하고 레코드를 현재 레코드로 다음 사항을 충족 하는 인덱싱된 테이블 형식 recordset 개체에 레코드를 찾을 수 함수를 호출 합니다.  
  
```  
BOOL Seek(
    LPCTSTR lpszComparison,  
    COleVariant* pKey1,  
    COleVariant* pKey2 = NULL,  
    COleVariant* pKey3 = NULL);

 
BOOL Seek(
    LPCTSTR lpszComparison,  
    COleVariant* pKeyArray,  
    WORD nKeys);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszComparison`  
 다음 문자열 식 중 하나: "<",></",>\<=", "=" "> =", 또는 ">"입니다.  
  
 `pKey1`  
 에 대 한 포인터는 [COleVariant](../../mfc/reference/colevariant-class.md) 는 인덱스의 첫 번째 필드에 해당 하는 값입니다. 필수 요소.  
  
 *pKey2*  
 에 대 한 포인터는 `COleVariant` 값이 있는 경우는 인덱스의 두 번째 필드에 해당 합니다. 기본적으로 **NULL**합니다.  
  
 *pKey3*  
 에 대 한 포인터는 `COleVariant` 값이 있는 경우는 인덱스의 세 번째 필드에 해당 합니다. 기본적으로 **NULL**합니다.  
  
 *pKeyArray*  
 Variant의 배열에 대 한 포인터입니다. 배열 크기는 인덱스의 필드 수에 해당합니다.  
  
 *nKeys*  
 에 해당 하는 인덱스의 필드 수는 배열의 크기는 정수입니다.  
  
> [!NOTE]
>  키에는 와일드 카드를 지정 하지 마십시오. 와일드 카드 발생 `Seek` 없는 일치 하는 레코드를 반환 합니다.  
  
### <a name="return-value"></a>반환 값  
 일치 하는 레코드가 발견 되 면 그렇지 않은 경우 0 0이 아닌 지정 합니다.  
  
### <a name="remarks"></a>주의  
 두 번째 (배열) 버전을 사용 하 여 `Seek` 4 개의 필드의 인덱스 또는 더 처리할 수 있습니다.  
  
 `Seek`테이블 형식의 레코드 집합에 대 한 검색 하는 고성능 인덱스를 설정 합니다. 호출 하 여 현재 인덱스를 설정 해야 `SetCurrentIndex` 호출 하기 전에 `Seek`합니다. 인덱스가 고유 하지 않은 키 필드 또는 필드를 식별 하는 경우 `Seek` 조건을 충족 하는 첫 번째 레코드를 찾습니다. 인덱스를 설정 하지 않으면 예외가 throw 됩니다.  
  
 유니코드 레코드 집합을 만들지 않는 경우, `COleVariant` 개체 명시적으로 선언 해야 ANSI 합니다. 사용 하 여이 작업을 수행할 수 있습니다는 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** 생성자 형태의 `vtSrc` 로 설정 `VT_BSTRT` (ANSI) 또는 사용 하 여는 **COleVariant** 함수 [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** 와 `vtSrc` 로 설정 `VT_BSTRT`합니다.  
  
 호출 하는 경우 `Seek`, 하나 이상의 키 값과 비교 연산자를 전달 하면 ("<",></",>\<=", "=" "> =", 또는 ">"). `Seek`지정 된 키 필드를 통해 검색 하 고 첫 번째 레코드에 지정 된 조건에 맞는 `lpszComparison` 및 `pKey1`합니다. 한 번 발견 `Seek` 0이 아니면을 반환 하며 현재 해당 레코드를 만듭니다. 경우 `Seek` 을 일치 하는 항목을 찾지 못하는 `Seek` , 0을 반환 하 고 현재 레코드 정의 되지 않습니다. 직접 DAO를 사용 하 여, 명시적으로 NoMatch 속성이 검사 해야 합니다.  
  
 경우 `lpszComparison` 는 "=" "> =", 또는 ">", `Seek` 인덱스의 시작 부분에서 시작 합니다. 경우 `lpszComparison` 은 "<" or=""> </"> <=",> </=",> `Seek` 인덱스의 끝에서 시작 하 고 중복 인덱스 항목 끝에는 없는 경우 뒤로 검색 합니다. 이 경우 `Seek` 항목 인덱스의 끝에 중복 인덱스 항목 중에서 임의의 항목부터 시작 합니다.  
  
 있습니다 사용할 때 현재 레코드 수 하지 않아도 `Seek`합니다.  
  
 다이너셋 형식 또는 특정 조건을 충족 하는 스냅숏 형식 레코드 집합의 레코드를 찾으려고 찾기 작업을 사용 합니다. 뿐만 아니라 특정 조건을 만족 하는 모든 레코드를 포함 하려면 레코드 간을 이동 하려면 이동 작업을 사용 합니다.  
  
 호출할 수 없습니다 `Seek` 모든 연결된 된 테이블에서 연결 된 테이블 다이너셋 형식 또는 스냅숏 형식 레코드 집합으로 열어야 하기 때문에 입력 합니다. 그러나 호출 하는 경우 `CDaoDatabase::Open` 설치 가능한 ISAM 데이터베이스를 열려면 직접 호출할 수 있습니다 `Seek` 해당 데이터베이스의 테이블에 있는 하지만, 성능이 저하 됩니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "방법 검색" 항목을 참조 합니다.  
  
##  <a name="setabsoluteposition"></a>CDaoRecordset::SetAbsolutePosition  
 레코드 집합 개체의 현재 레코드의 상대적인 레코드 번호를 설정합니다.  
  
```  
void SetAbsolutePosition(long lPosition);
```  
  
### <a name="parameters"></a>매개 변수  
 *lPosition*  
 레코드 집합의 현재 레코드의 서 수 위치에 해당합니다.  
  
### <a name="remarks"></a>설명  
 호출 `SetAbsolutePosition` 다이너셋 형식 또는 스냅숏 형식 레코드 집합의 서 수 위치에 따라 특정 레코드를 현재 레코드 포인터 수 있습니다. 호출 하 여 현재 레코드 번호를 확인할 수도 있습니다 [GetAbsolutePosition](#getabsoluteposition)합니다.  
  
> [!NOTE]
>  이 멤버 함수는 다이너셋 형식 및 스냅숏 형식 레코드 집합에 대해서만 유효 합니다.  
  
 AbsolutePosition 속성 값은 기본 DAO 개체는 0부터 시작 합니다. 0으로 설정 레코드 집합의 첫 번째 레코드를 가리킵니다. 채워진된 레코드 하면 예외를 throw 하는 MFC 개수 보다 큰 값을 설정 합니다. 호출 하 여 레코드 집합의 레코드의 수를 확인할 수는 `GetRecordCount` 멤버 함수입니다.  
  
 현재 레코드를 삭제 한 경우 AbsolutePosition 속성 값을 정의 하지 않은 하 고 MFC 참조 하는 경우 예외를 throw 합니다. 새 레코드 시퀀스의 끝에 추가 됩니다.  
  
> [!NOTE]
>  이 속성으로 서로게이트 레코드 번호를 사용할 수 없습니다. 책갈피는 계속 유지 하 고 지정된 된 위치를 반환 하는 권장된 방법을 이며 모든 유형의 지 원하는 책갈피 recordset 개체에서 현재 레코드의 위치 하는 유일한 방법은입니다. 특히, 지정된 된 레코드의 위치는 앞의 레코드를 삭제 한 경우 변경 합니다. 에 지정된 된 레코드 해야 같은 절대 위치로 사용 하 여 SQL 문을 생성 하지 않는 한 레코드 집합 내에서 개별 레코드의 순서가 보장 되지 않으므로 레코드 집합 다시 다시 생성 하는 경우 반드시 이기도 한 **ORDERBY** 절.  
  
 관련된 정보에 대 한 DAO 도움말의 "AbsolutePosition Property" 항목을 참조 합니다.  
  
##  <a name="setbookmark"></a>CDaoRecordset::SetBookmark  
 지정된 된 책갈피를 포함 하는 레코드를 레코드 집합을 배치 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetBookmark(COleVariant varBookmark);
```  
  
### <a name="parameters"></a>매개 변수  
 `varBookmark`  
 A [COleVariant](../../mfc/reference/colevariant-class.md) 특정 레코드에 대 한 책갈피 값을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 레코드 집합 개체를 만들거나 열, 각 레코드에 이미 고유 책갈피가 있습니다. 호출 하 여 현재 레코드에 대 한 책갈피를 검색할 수 있습니다 `GetBookmark` 값을 저장 하는 `COleVariant` 개체입니다. 호출 하 여 해당 레코드로 나중 돌아갈 수 `SetBookmark` 저장 된 책갈피 값을 사용 합니다.  
  
> [!NOTE]
>  호출 [Requery](#requery) DAO 책갈피를 변경 합니다.  
  
 유니코드 레코드 집합을 만들지 않는 경우, `COleVariant` 개체가 명시적으로 선언 해야 ANSI 합니다. 사용 하 여이 작업을 수행할 수 있습니다는 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** 생성자 형태의 `vtSrc` 로 설정 `VT_BSTRT` (ANSI) 또는 사용 하 여는 **COleVariant** 함수 [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** 와 `vtSrc` 로 설정 `VT_BSTRT`합니다.  
  
 관련된 정보에 대 한 항목을 참조 "책갈피" 속성과 책갈피를 설정할 속성을 "DAO 도움말의 합니다.  
  
##  <a name="setcachesize"></a>CDaoRecordset::SetCacheSize  
 캐시할 레코드의 수를 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetCacheSize(long lSize);
```  
  
### <a name="parameters"></a>매개 변수  
 `lSize`  
 레코드의 수를 지정합니다. 일반적인 값은 100입니다. 캐시 해제 하는 0으로 설정 합니다. 설정은 5 개 레코드에서 1200 레코드 사이 여야 합니다. 캐시 된 작업은 매우 많은 양의 메모리를 사용할 수 있습니다.  
  
### <a name="remarks"></a>주의  
 캐시에서 데이터 다시 요청 되는 응용 프로그램을 실행 하는 동안 서버에서 가장 최근에 검색 된 데이터를 보유 하는 로컬 메모리 공간이 합니다. 데이터 캐싱 다이너셋 형식의 레코드 집합 개체를 통해 원격 서버에서 데이터를 검색 하는 응용 프로그램의 성능을 향상 시킵니다. 데이터가 요청 되 면 Microsoft Jet 데이터베이스 엔진 요청된 된 데이터에 대 한 캐시 먼저 확인 처리 시간을 절약 하는 서버에서 가져오는 것입니다. ODBC 데이터 원본에서 제공 되지 않는 데이터 캐시에 저장 되지 않습니다.  
  
 연결된 된 테이블 같은 ODBC 데이터 원본에는 로컬 캐시를 가질 수 있습니다. 캐시를 만드는 데 호출 원격 데이터 원본에서 레코드 집합 개체를 열기 고 `SetCacheSize` 및 `SetCacheStart` 멤버 함수 및 호출 합니다는 `FillCache` 멤버 함수 또는 이동 작업 중 하나를 사용 하 여 레코드를 하나씩 있습니다. `lSize` 의 매개 변수는 `SetCacheSize` 멤버 함수는 응용 프로그램이 한 번에 작업할 수 레코드의 수에 따라 될 수 있습니다. 예를 들어 화면에 표시할 데이터의 원본으로 레코드 집합을 사용 하는 경우 전달할 수 있습니다는 `SetCacheSize``lSize` 매개 변수를 한 번에 20 개의 레코드를 표시 하는 20으로 합니다.  
  
 관련된 내용은 DAO 도움말의 "CacheSize CacheStart 속성" 항목을 참조 합니다.  
  
##  <a name="setcachestart"></a>CDaoRecordset::SetCacheStart  
 캐시할 레코드 집합의 첫 번째 레코드의 책갈피를 지정 하려면이 함수를 호출 합니다.  
  
```  
void SetCacheStart(COleVariant varBookmark);
```  
  
### <a name="parameters"></a>매개 변수  
 `varBookmark`  
 A [COleVariant](../../mfc/reference/colevariant-class.md) 캐시할 레코드 집합의 첫 번째 레코드의 책갈피를 지정 하는 합니다.  
  
### <a name="remarks"></a>주의  
 에 대 한 모든 레코드의 책갈피 값을 사용할 수 있습니다는 `varBookmark` 의 매개 변수는 `SetCacheStart` 멤버 함수입니다. 현재 레코드와 캐시를 시작, 사용 하 여 해당 레코드에 대 한 책갈피를 설정 하려는 레코드 [SetBookmark](#setbookmark), 책갈피 값에 대 한 매개 변수로 전달 하 고는 `SetCacheStart` 멤버 함수입니다.  
  
 Microsoft Jet 데이터베이스 엔진 캐시에서 캐시 범위 내에 있는 레코드를 요청 하 고 서버에서 캐시 범위 외부의 레코드를 요청 합니다.  
  
 캐시에서 검색 된 레코드는 다른 사용자가 원본 데이터에 동시에 변경한 내용을 반영 하지 않습니다.  
  
 모든 캐시 된 데이터의 업데이트를 적용 하려면 전달 된 `lSize` 의 매개 변수 `SetCacheSize` 0으로 호출 `SetCacheSize` 다시 캐시의 크기를 사용할 때는 원래 요청한를 호출 합니다는 `FillCache` 멤버 함수입니다.  
  
 유니코드 레코드 집합을 만들지 않는 경우, `COleVariant` 개체가 명시적으로 선언 해야 ANSI 합니다. 사용 하 여이 작업을 수행할 수 있습니다는 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** 생성자 형태의 `vtSrc` 로 설정 `VT_BSTRT` (ANSI) 또는 사용 하 여는 **COleVariant** 함수 [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** 와 `vtSrc` 로 설정 `VT_BSTRT`합니다.  
  
 관련된 정보에 대 한 항목을 참조 CacheSize, CacheStart 속성 "DAO 도움말의 합니다.  
  
##  <a name="setcurrentindex"></a>CDaoRecordset::SetCurrentIndex  
 테이블 형식 레코드 집합에 인덱스를 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetCurrentIndex(LPCTSTR lpszIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszIndex`  
 설정할 인덱스의 이름을 포함 하는 포인터입니다.  
  
### <a name="remarks"></a>주의  
 기본 테이블의 레코드는 특정 순서로 저장 되지 않습니다. 데이터베이스에서 반환 된 레코드의 순서를 변경 하는 인덱스를 설정 하지만 레코드가 저장 되는 순서에 영향을 주지 않습니다. 지정된 된 인덱스를 이미 정의 되어 있어야 합니다. 존재 하지 않는 인덱스 개체를 사용 하려는 경우 또는 호출 하는 경우 인덱스를 설정 하지 않으면 [Seek](#seek), MFC 예외를 throw 합니다.  
  
 호출 하 여 테이블에 대 한 새 인덱스를 만들 수 있습니다 [CDaoTableDef::CreateIndex](../../mfc/reference/cdaotabledef-class.md#createindex) 호출 하 여 기본 테이블 정의의 인덱스 컬렉션에 새 인덱스를 추가 하 고 [CDaoTableDef::Append](../../mfc/reference/cdaotabledef-class.md#append), 다음 레코드 집합 다시 열어 합니다.  
  
 기본 테이블 정의 대해 정의 된 인덱스에 의해서만 테이블 형식의 레코드 집합에서 반환 된 레코드를 정렬할 수 있습니다. 다른 순서로 레코드를 정렬 하려면 다이너셋 형식 또는 SQL을 사용 하 여 스냅숏 형식 레코드 집합 열 수 있습니다 **ORDERBY** 절에 저장 된 [CDaoRecordset::m_strSort](#m_strsort)합니다.  
  
 관련된 정보 항목 "Index 개체" 및 "현재 인덱스" DAO 도움말의 정의 참조 하십시오.  
  
##  <a name="setfielddirty"></a>CDaoRecordset::SetFieldDirty  
 변경 되거나 변경 되지 않은 서 레코드 집합의 필드 데이터 멤버 플래그를 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetFieldDirty(
    void* pv,  
    BOOL bDirty = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `pv`  
 레코드 집합의 필드 데이터 멤버의 주소를 포함 또는 **NULL**합니다. 경우 **NULL**, 레코드 집합의 필드 데이터 멤버를 모든 플래그가 지정 됩니다. (C + + **NULL** 같지 않습니다 Null로 데이터베이스 용어에서 즉, "가치가 없습니다.")  
  
 `bDirty`  
 **True 이면** 필드 데이터 멤버 "더티" (변경) 것으로 플래그가 지정 되어야 하는 경우. 그렇지 않으면 **FALSE** 필드 데이터 멤버 "정리" (변경 되지 않음) 플래그 지정 하는 경우.  
  
### <a name="remarks"></a>설명  
 다음과 같이 변경 되지 않은 필드를 표시 하면 필드가 업데이트 되지 않습니다.  
  
 프레임 워크 부호를 사용 하 여 읽기 전용 이므로 DAO 레코드 필드 교환 (DFX) 메커니즘을 통해 데이터 소스에서 레코드에 기록 될 됩니다 되도록 필드 데이터 멤버 필드의 값을 일반적으로 변경 필드 설정 더티 자동으로 되므로 호출 필요가 거의 `SetFieldDirty` 하지만, 직접 할 때도 열은 명시적으로 업데이트 되거나 삽입 될 어떤 값이 필드 데이터 멤버에 관계 없이 확인 합니다. DFX 메커니즘의 사용을 손쉽게 **PSEUDONULL**합니다. 자세한 내용은 참조 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)합니다.  
  
 이중 버퍼링 메커니즘을 사용 하지 않는 경우 다음 필드의 값을 변경 설정 되지 않습니다 필드 커밋되지 않은 것으로 합니다. 이 경우 커밋되지 않은 것으로 필드를 명시적으로 설정 해야 합니다. 에 포함 된 플래그 [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) 이 자동 필드 검사를 제어 합니다.  
  
> [!NOTE]
>  이 멤버 함수를 호출한 후에 호출 [편집](#edit) 또는 [AddNew](#addnew)합니다.  
  
 사용 하 여 **NULL** 함수의 첫 번째 인수는 함수 모두에 적용에 대 한 **outputColumn** 필드 하지 **param** 필드를 `CDaoFieldExchange`합니다. 예를 들어, 호출  
  
 [!code-cpp[NVC_MFCDatabase # 6](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]  
  
 만 설정 됩니다 **outputColumn** 필드를 **NULL**; **param** 필드에 영향을 받지 않습니다.  
  
 작업에 **param**, 개별의 실제 주소를 입력 해야 **param** 와 같은 작업에 대 하 시겠습니까:  
  
 [!code-cpp[NVC_MFCDatabase # 7](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]  
  
 즉, 설정할 수 없습니다. 모든 **param** 필드를 **NULL**있습니다, **outputColumn** 필드입니다.  
  
 `SetFieldDirty`이 통해 구현 `DoFieldExchange`합니다.  
  
##  <a name="setfieldnull"></a>CDaoRecordset::SetFieldNull  
 Null (특히 값 예:) 또는 Null이 아닌 레코드 집합의 필드 데이터 멤버 플래그를 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetFieldNull(
    void* pv,  
    BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `pv`  
 레코드 집합의 필드 데이터 멤버의 주소를 포함 또는 **NULL**합니다. 경우 **NULL**, 레코드 집합의 필드 데이터 멤버를 모든 플래그가 지정 됩니다. (C + + **NULL** 같지 않습니다 Null로 데이터베이스 용어에서 즉, "가치가 없습니다.")  
  
 `bNull`  
 필드 데이터 멤버 (Null) 값이 없는 것으로 플래그가 지정 되어야 하는 경우에 0이 아닙니다. 필드 데이터 멤버는 Null이 아닌으로 플래그를 설정 하는 경우 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 `SetFieldNull`에 바인딩된 필드에 사용 되는 `DoFieldExchange` 메커니즘입니다.  
  
 레코드 집합에 새 레코드를 추가 하는 경우 모든 필드 데이터 멤버 처음 Null 값으로 설정 되며 "더티" (변경) 것으로 플래그가 지정 합니다. 데이터 원본에서 레코드를 검색 하는 경우 열이 이미 값 또는 null입니다. 하나의 필드에 Null, 해야 적합 하지 않은 경우는 [CDaoException](../../mfc/reference/cdaoexception-class.md) throw 됩니다.  
  
 현재 레코드의 필드 값, 호출 되지 않는 것으로 지정 하 고 싶을 경우 예를 들어 이중 버퍼링 메커니즘을 사용 중인 경우 `SetFieldNull` 와 `bNull` 로 설정 **TRUE** Null로 플래그를 지정 합니다. 필드는 Null 이전에 표시 된 값을 지정 하려는 경우 새 값을 설정 하기만 합니다. Null 플래그를 제거할 필요가 없습니다 `SetFieldNull`합니다. 필드는 Null이 될 수 있는지 여부를 확인 하려면 호출 [IsFieldNullable](#isfieldnullable)합니다.  
  
 이중 버퍼링 메커니즘을 사용 하지 않는 경우 다음 필드의 값을 변경 설정 되지 않습니다 필드 더티 및 Null이 아니어야 합니다. 특히 더티 및 Null이 아닌 필드를 설정 해야 합니다. 에 포함 된 플래그 [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) 이 자동 필드 검사를 제어 합니다.  
  
 DFX 메커니즘의 사용 적용 **PSEUDONULL**합니다. 자세한 내용은 참조 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)합니다.  
  
> [!NOTE]
>  이 멤버 함수를 호출한 후에 호출 [편집](#edit) 또는 [AddNew](#addnew)합니다.  
  
 사용 하 여 **NULL** 함수의 첫 번째 인수는 함수를에 적용 됩니다에 대 한 **outputColumn** 필드 하지 **param** 필드를 `CDaoFieldExchange`합니다. 예를 들어, 호출  
  
 [!code-cpp[NVC_MFCDatabase # 8](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]  
  
 만 설정 됩니다 **outputColumn** 필드를 **NULL**; **param** 필드에 영향을 받지 않습니다.  
  
##  <a name="setfieldvalue"></a>CDaoRecordset::SetFieldValue  
 서 수 위치 별로 또는 문자열의 값을 변경 하 여 필드의 값을 설정 하려면이 함수를 호출 합니다.  
  
```  
virtual void SetFieldValue(
    LPCTSTR lpszName,  
    const COleVariant& varValue);

 
virtual void SetFieldValue(
    int nIndex,  
    const COleVariant& varValue);

 
void SetFieldValue(
    LPCTSTR lpszName,  
    LPCTSTR lpszValue);

 
void SetFieldValue(
    int nIndex,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 필드의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `varValue`  
 에 대 한 참조는 [COleVariant](../../mfc/reference/colevariant-class.md) 필드의 내용 값이 들어 있는 개체입니다.  
  
 `nIndex`  
 정수 (0부터 시작) 레코드 집합의 필드 컬렉션에서 필드의 서 수 위치를 나타내는입니다.  
  
 `lpszValue`  
 필드의 내용의 값을 포함 하는 문자열에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 `SetFieldValue` 및 [GetFieldValue](#getfieldvalue) 실행된 시간 보다는 정적으로 사용 하 여 바인딩 열 필드를 동적으로 바인딩하는 [DoFieldExchange](#dofieldexchange) 메커니즘입니다.  
  
 유니코드 레코드 집합을 만들지 않는 경우 해야 하거나 사용할는 형태의 `SetFieldValue` 을 포함 하지 않는 한 `COleVariant` 매개 변수를 또는 `COleVariant` 개체가 명시적으로 선언 해야 ANSI 합니다. 사용 하 여이 작업을 수행할 수 있습니다는 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** 생성자 형태의 `vtSrc` 로 설정 `VT_BSTRT` (ANSI) 또는 사용 하 여는 **COleVariant** 함수 [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** 와 `vtSrc` 로 설정 `VT_BSTRT`합니다.  
  
 관련된 정보에 대 한 "Field 개체"과 "값 속성" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="setfieldvaluenull"></a>CDaoRecordset::SetFieldValueNull  
 필드를 Null 값을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetFieldValueNull(int nIndex);  
void SetFieldValueNull(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 인덱스 0부터 시작 하 여 조회에 대 한 레코드 집합의 필드의 인덱스입니다.  
  
 `lpszName`  
 이름별으로 조회에 대 한 레코드 집합에서 필드의 이름입니다.  
  
### <a name="remarks"></a>주의  
 C + + **NULL** Null 이며 데이터베이스 용어에서 의미 같지는 않습니다 "가치가 없습니다."  
  
 관련된 정보에 대 한 "Field 개체"과 "값 속성" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="setlockingmode"></a>CDaoRecordset::SetLockingMode  
 레코드 집합에 대 한 잠금 유형을 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetLockingMode(BOOL bPessimistic);
```  
  
### <a name="parameters"></a>매개 변수  
 *bPessimistic*  
 잠금 유형을 나타내는 플래그입니다.  
  
### <a name="remarks"></a>설명  
 호출 되는 즉시 잠긴 경우 비관적 잠금는 실제로 2k 페이지 편집 하는 레코드를 포함 하는 **편집** 멤버 함수입니다. 호출 하는 경우 페이지 잠금 해제 되어는 **업데이트** 또는 **닫기** 멤버 함수 또는 이동 또는 찾기 작업 중 하나입니다.  
  
 와 레코드를 업데이트 하는 동안에 레코드가 들어 있는 2k 페이지 잠긴 경우 낙관적 잠금이 적용 됩니다는 **업데이트** 멤버 함수입니다.  
  
 페이지 잠긴 경우 다른 사용자는 동일한 페이지에 레코드를 편집할 수 있습니다. 호출 하는 경우 `SetLockingMode` 및 0이 아닌 값을 전달 하 고 다른 사용자가 이미 잠긴 페이지, 호출 하는 경우 예외가 throw 됩니다 **편집**합니다. 다른 사용자가 잠긴된 페이지에서 데이터를 읽을 수 있습니다.  
  
 호출 하는 경우 `SetLockingMode` 이상 값이 0 인 호출 **업데이트** 페이지 다른 사용자에 의해 잠겨 동안 예외가 발생 합니다. 다른 사용자가 사용자 레코드에 수행한 변경 내용을 보려면 (및 변경 내용이 손실)를 호출 하는 `SetBookmark` 책갈피 값의 현재 레코드와 멤버 함수입니다.  
  
 ODBC 데이터 소스를 사용할 때는 잠금 모드 낙관적 항상입니다.  
  
##  <a name="setparamvalue"></a>CDaoRecordset::SetParamValue  
 레코드 집합의 실행 시 매개 변수 값을 설정 하려면이 함수를 호출 합니다.  
  
```  
virtual void SetParamValue(
    int nIndex,  
    const COleVariant& varValue);

 
virtual void SetParamValue(
    LPCTSTR lpszName,  
    const COleVariant& varValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 쿼리 정의 매개 변수 컬렉션에서 매개 변수의 숫자 위치입니다.  
  
 `var`  
 값을 설정 설명 부분을 참조 하십시오.  
  
 `lpszName`  
 매개 변수 값을 설정의 이름입니다.  
  
### <a name="remarks"></a>주의  
 매개 변수는 레코드 집합의 SQL 문자열의 일부로 설정 이미 있어야 합니다. 매개 변수 이름 또는 컬렉션에서의 인덱스 위치에 액세스할 수 있습니다.  
  
 으로 설정 하려면 값을 지정 된 `COleVariant` 개체입니다. 원하는 값과의 형식을 설정 하는 방법에 대 한 정보에 대 한 프로그램 `COleVariant` 개체 클래스를 참조 하십시오. [COleVariant](../../mfc/reference/colevariant-class.md)합니다. 유니코드 레코드 집합을 만들지 않는 경우, `COleVariant` 개체가 명시적으로 선언 해야 ANSI 합니다. 사용 하 여이 작업을 수행할 수 있습니다는 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** 생성자 형태의 `vtSrc` 로 설정 `VT_BSTRT` (ANSI) 또는 사용 하 여는 **COleVariant** 함수 [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** 와 `vtSrc` 로 설정 `VT_BSTRT`합니다.  
  
##  <a name="setparamvaluenull"></a>CDaoRecordset::SetParamValueNull  
 Null 값으로 매개 변수를 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetParamValueNull(int nIndex);  
void SetParamValueNull(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 인덱스 0부터 시작 하 여 조회에 대 한 레코드 집합의 필드의 인덱스입니다.  
  
 `lpszName`  
 이름별으로 조회에 대 한 레코드 집합에서 필드의 이름입니다.  
  
### <a name="remarks"></a>주의  
 C + + **NULL** Null 이며 데이터베이스 용어에서 의미 같지는 않습니다 "가치가 없습니다."  
  
##  <a name="setpercentposition"></a>CDaoRecordset::SetPercentPosition  
 레코드 집합에 있는 레코드의 백분율을 기반으로 하는 레코드 집합 개체의 현재 레코드의 대략적인 위치를 변경 하는 값을 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetPercentPosition(float fPosition);
```  
  
### <a name="parameters"></a>매개 변수  
 *fPosition*  
 0부터 100까지의 숫자입니다.  
  
### <a name="remarks"></a>설명  
 다이너셋 형식 또는 스냅숏 형식 레코드 집합으로 작업할 때는 먼저 recordset을 채울 호출 하기 전에 레코드가 마지막으로 이동 하 여 `SetPercentPosition`합니다. 호출 하는 경우 `SetPercentPosition` 레코드 집합을 완벽 하 게 채우기, 전에 이동 크기가의 값으로 표시 된 대로 액세스 하는 레코드의 수를 기준으로 [GetRecordCount](#getrecordcount)합니다. 이동할 수 있습니다 마지막 레코드를 호출 하 여 `MoveLast`합니다.  
  
 호출한 후 `SetPercentPosition`, 현재 값에 해당 하는 대략적인 위치에 있는 레코드 수입니다.  
  
> [!NOTE]
>  호출 `SetPercentPosition` 이동할 현재 레코드를 레코드 집합에서 특정 레코드 권장 되지 않습니다. 호출 된 [SetBookmark](#setbookmark) 멤버 함수를 대신 합니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "PercentPosition Property" 항목을 참조 합니다.  
  
##  <a name="update"></a>CDaoRecordset::Update  
 이 멤버 함수를 호출한 후 호출 된 `AddNew` 또는 **편집** 멤버 함수입니다.  
  
```  
virtual void Update();
```  
  
### <a name="remarks"></a>주의  
 이 호출은 필요 완료 하는 `AddNew` 또는 **편집** 작업 합니다.  
  
 둘 다 `AddNew` 및 **편집** 데이터 원본에 저장 하기 위한 추가 또는 편집 된 데이터가 배치 되는 편집 버퍼를 준비 합니다. **업데이트** 데이터를 저장 합니다. 표시 또는 변경 된 것으로 인식 필드만 업데이트 됩니다.  
  
 데이터 원본 트랜잭션을 지 원하는 경우 만들 수 있습니다는 **업데이트** 호출 (및 해당 `AddNew` 또는 **편집** 호출) 트랜잭션의 일부입니다.  
  
> [!CAUTION]
>  호출 하는 경우 **업데이트** 호출 하지 `AddNew` 또는 **편집**, **업데이트** throw 한 `CDaoException`합니다. 호출 하는 경우 `AddNew` 또는 **편집**를 호출 해야 **업데이트** 호출 하기 전에 [MoveNext](#movenext) 하거나 레코드 집합 또는 데이터 원본 연결을 닫습니다. 그렇지 않은 경우 변경 내용을 알림 없이 손실 됩니다.  
  
 레코드 시간부터 잠긴 상태로 유지 pessimistically에 다중 사용자 환경에서 레코드 집합 개체를 잠그면 **편집** 업데이트가 완료 될 때까지 사용 됩니다. 레코드 집합 낙관적으로 잠겨 있으면 레코드 잠기고 데이터베이스를 업데이트 하기 바로 전에 미리 편집 된 레코드와 비교 합니다. 레코드는 호출 이후 변경 된 경우 **편집**, **업데이트** 작업이 실패 하면 MFC 예외를 throw 합니다. 사용 하 여 잠금 모드를 변경할 수 있습니다 `SetLockingMode`합니다.  
  
> [!NOTE]
>  낙관적 잠금 ODBC 및 설치 가능한 ISAM 등의 외부 데이터베이스 형식에 항상 사용 됩니다.  
  
 관련된 정보에 대 한 "AddNew 메서드", "CancelUpdate 메서드", "Delete 메서드", "LastModified Property", "Update 메서드" 및 DAO 도움말의 "EditMode Property" 항목을 참조 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoWorkspace 클래스](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase 클래스](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)

