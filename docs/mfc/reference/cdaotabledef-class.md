---
title: "CDaoTableDef 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoTableDef
- AFXDAO/CDaoTableDef
- AFXDAO/CDaoTableDef::CDaoTableDef
- AFXDAO/CDaoTableDef::Append
- AFXDAO/CDaoTableDef::CanUpdate
- AFXDAO/CDaoTableDef::Close
- AFXDAO/CDaoTableDef::Create
- AFXDAO/CDaoTableDef::CreateField
- AFXDAO/CDaoTableDef::CreateIndex
- AFXDAO/CDaoTableDef::DeleteField
- AFXDAO/CDaoTableDef::DeleteIndex
- AFXDAO/CDaoTableDef::GetAttributes
- AFXDAO/CDaoTableDef::GetConnect
- AFXDAO/CDaoTableDef::GetDateCreated
- AFXDAO/CDaoTableDef::GetDateLastUpdated
- AFXDAO/CDaoTableDef::GetFieldCount
- AFXDAO/CDaoTableDef::GetFieldInfo
- AFXDAO/CDaoTableDef::GetIndexCount
- AFXDAO/CDaoTableDef::GetIndexInfo
- AFXDAO/CDaoTableDef::GetName
- AFXDAO/CDaoTableDef::GetRecordCount
- AFXDAO/CDaoTableDef::GetSourceTableName
- AFXDAO/CDaoTableDef::GetValidationRule
- AFXDAO/CDaoTableDef::GetValidationText
- AFXDAO/CDaoTableDef::IsOpen
- AFXDAO/CDaoTableDef::Open
- AFXDAO/CDaoTableDef::RefreshLink
- AFXDAO/CDaoTableDef::SetAttributes
- AFXDAO/CDaoTableDef::SetConnect
- AFXDAO/CDaoTableDef::SetName
- AFXDAO/CDaoTableDef::SetSourceTableName
- AFXDAO/CDaoTableDef::SetValidationRule
- AFXDAO/CDaoTableDef::SetValidationText
- AFXDAO/CDaoTableDef::m_pDAOTableDef
- AFXDAO/CDaoTableDef::m_pDatabase
dev_langs:
- C++
helpviewer_keywords:
- database classes [C++], DAO
- tabledefs [C++]
- CDaoTableDef class
- database tables [C++], attached table definition
- database tables [C++], base table definition
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
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
ms.openlocfilehash: 8bfd0ef3c63c243cabb0a4f841ba278fbeed4ae8
ms.lasthandoff: 02/24/2017

---
# <a name="cdaotabledef-class"></a>CDaoTableDef 클래스
기본 테이블 또는 연결된 테이블의 저장된 정의를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDaoTableDef : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoTableDef::CDaoTableDef](#cdaotabledef)|생성 된 **CDaoTableDef** 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoTableDef::Append](#append)|데이터베이스에 새 테이블을 추가합니다.|  
|[CDaoTableDef::CanUpdate](#canupdate)|테이블을 업데이트할 수 있는 경우&0;이 아닌 (필드 또는 테이블 속성의 정의 수정할 수 있습니다).|  
|[CDaoTableDef::Close](#close)|열고 테이블 정의 닫습니다.|  
|[CDaoTableDef::Create](#create)|사용 하 여 데이터베이스에 추가할 수 있는 테이블을 만듭니다 [추가](#append)합니다.|  
|[CDaoTableDef::CreateField](#createfield)|테이블에 대 한 필드를 만들기 위해 호출 합니다.|  
|[CDaoTableDef::CreateIndex](#createindex)|테이블에 대 한 인덱스를 만들기 위해 호출 합니다.|  
|[CDaoTableDef::DeleteField](#deletefield)|테이블에서 필드를 삭제 하려면 호출 됩니다.|  
|[CDaoTableDef::DeleteIndex](#deleteindex)|테이블에서 인덱스를 삭제 하 라고 합니다.|  
|[CDaoTableDef::GetAttributes](#getattributes)|하나 이상의 특성을 나타내는 값을 반환 된 `CDaoTableDef` 개체입니다.|  
|[CDaoTableDef::GetConnect](#getconnect)|테이블의 원본에 대 한 정보를 제공 하는 값을 반환 합니다.|  
|[CDaoTableDef::GetDateCreated](#getdatecreated)|날짜와 시간을 반환 기본 테이블 내부를 `CDaoTableDef` 개체가 생성 되었습니다.|  
|[CDaoTableDef::GetDateLastUpdated](#getdatelastupdated)|기본 테이블의 디자인에서 가장 최근의 변경의 시간과 날짜를 반환 합니다.|  
|[CDaoTableDef::GetFieldCount](#getfieldcount)|테이블의 필드 수를 나타내는 값을 반환 합니다.|  
|[CDaoTableDef::GetFieldInfo](#getfieldinfo)|테이블의 특정 종류의 필드에 대 한 정보를 반환합니다.|  
|[CDaoTableDef::GetIndexCount](#getindexcount)|테이블에 대 한 인덱스의 수를 반환합니다.|  
|[CDaoTableDef::GetIndexInfo](#getindexinfo)|특정 종류의 테이블에 대 한 인덱스에 대 한 정보를 반환합니다.|  
|[CDaoTableDef::GetName](#getname)|테이블의 사용자 정의 이름을 반환합니다.|  
|[CDaoTableDef::GetRecordCount](#getrecordcount)|테이블의 레코드 수를 반환합니다.|  
|[CDaoTableDef::GetSourceTableName](#getsourcetablename)|원본 데이터베이스에 연결 된 테이블의 이름을 지정 하는 값을 반환 합니다.|  
|[CDaoTableDef::GetValidationRule](#getvalidationrule)|이 변경 되거나 테이블에 추가 되는 필드의 데이터 유효성을 검사 하는 값을 반환 합니다.|  
|[CDaoTableDef::GetValidationText](#getvalidationtext)|Field 개체의 값은 지정 된 유효성 검사 규칙을 만족 하지 않는 경우 응용 프로그램에서 표시 하는 메시지의 텍스트를 지정 하는 값을 반환 합니다.|  
|[CDaoTableDef::IsOpen](#isopen)|연 테이블이 있으면&0;이 아닌 반환 합니다.|  
|[CDaoTableDef::Open](#open)|기존 테이블 정의 데이터베이스에 저장 엽니다의 테이블 정의 컬렉션입니다.|  
|[CDaoTableDef::RefreshLink](#refreshlink)|연결된 된 테이블에 대 한 연결 정보를 업데이트합니다.|  
|[CDaoTableDef::SetAttributes](#setattributes)|하나 이상의 특성을 나타내는 값을 설정 하는 `CDaoTableDef` 개체입니다.|  
|[CDaoTableDef::SetConnect](#setconnect)|테이블의 원본에 대 한 정보를 제공 하는 값을 설정 합니다.|  
|[CDaoTableDef::SetName](#setname)|테이블의 이름을 설정합니다.|  
|[CDaoTableDef::SetSourceTableName](#setsourcetablename)|원본 데이터베이스에 연결된 된 테이블의 이름을 지정 하는 값을 설정 합니다.|  
|[CDaoTableDef::SetValidationRule](#setvalidationrule)|이 변경 되거나 테이블에 추가 되는 필드의 데이터 유효성을 검사 하는 값을 설정 합니다.|  
|[CDaoTableDef::SetValidationText](#setvalidationtext)|Field 개체의 값은 지정 된 유효성 검사 규칙을 만족 하지 않는 경우 응용 프로그램에서 표시 하는 메시지의 텍스트를 지정 하는 값을 설정 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoTableDef::m_pDAOTableDef](#m_pdaotabledef)|테이블 정의 개체를 원본 DAO 인터페이스에 대 한 포인터입니다.|  
|[CDaoTableDef::m_pDatabase](#m_pdatabase)|이 테이블에 대 한 원본 데이터베이스입니다.|  
  
## <a name="remarks"></a>주의  
 각 DAO 데이터베이스 개체에 저장 된 모든 DAO tabledef 개체가 포함 된 테이블 정의 호출 하는 컬렉션을 유지 관리 합니다.  
  
 사용 하 여 테이블 정의 조작 하는 `CDaoTableDef` 개체입니다. 예를 들어 다음 작업을 할 수 있습니다.  
  
-   데이터베이스의 모든 로컬 연결, 또는 외부 테이블의 필드 및 인덱스 구조를 검사 합니다.  
  
-   호출 된 `SetConnect` 및 `SetSourceTableName` 연결 된 테이블 및 사용에 대 한 멤버 함수는 `RefreshLink` 연결 된 테이블에 대 한 연결을 업데이트 하는 멤버 함수입니다.  
  
-   호출 된 `CanUpdate` 멤버 함수를 결정 하는 경우 테이블의 필드 정의 편집할 수 있습니다.  
  
-   가져오거나 설정할 사용 하 여 유효성 검사 조건을 `GetValidationRule` 및 `SetValidationRule`, 및 `GetValidationText` 및 `SetValidationText` 멤버 함수입니다.  
  
-   사용 된 **열려** 멤버 함수는 테이블, 다이너셋 또는 스냅숏 형식 만들기를 `CDaoRecordset` 개체입니다.  
  
    > [!NOTE]
    >  DAO 데이터베이스 클래스에 연결 ODBC (Open Database)을 기반으로 하는 MFC 데이터베이스 클래스와 구별 됩니다. 모든 DAO 데이터베이스 클래스 이름이 "CDao" 접두사가 있습니다. 여전히 DAO 클래스; ODBC 데이터 원본에 액세스할 수 있습니다. DAO 클래스 다르므로 Microsoft Jet 데이터베이스 엔진에 일반적으로 뛰어난 기능을 제공 합니다.  
  
### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>기존 테이블을 사용 하거나 새 테이블을 만들려면 테이블 정의 개체를 사용 하 여  
  
1.  모든 경우에 생성 되어 먼저는 `CDaoTableDef` 에 대 한 포인터를 제공 하는 개체를 한 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 테이블이 속해 있는 개체입니다.  
  
2.  원하는 작업에 따라 다음을 수행 합니다.  
  
    -   테이블에 저장 된 기존를 사용 하려면 테이블 정의 개체의 호출 [열려](#open) 멤버 함수를 저장된 하는 테이블의 이름을 제공 합니다.  
  
    -   새 테이블을 만들려면 테이블 정의 개체의 호출 [만들기](#create) 멤버 함수를 테이블의 이름을 제공 합니다. 호출 [CreateField](#createfield) 및 [CreateIndex](#createindex) 테이블에 필드 및 인덱스를 추가 합니다.  
  
    -   호출 [추가](#append) 데이터베이스의 TableDefs 컬렉션에 추가 하 여 테이블을 저장 합니다. **만들기** 테이블 정의 열린 상태로 설정 하므로 호출한 후 **만들기** 호출 하지 않으면 **열고**합니다.  
  
        > [!TIP]
        >  저장 된 테이블을 만드는 가장 쉬운 방법은를 만들고 Microsoft Access를 사용 하 여 데이터베이스에 저장 됩니다. 그런 다음 열고 하 고 MFC 코드에서 사용할 수 있습니다.  
  
 열거나 만든 테이블 정의 개체를 사용 하려면 만들고 엽니다는 `CDaoRecordset` 개체와 테이블 정의의 이름을 지정 하는 **dbOpenTable** 값은 `nOpenType` 매개 변수입니다.  
  
 테이블 정의 개체를 만드는 데는 `CDaoRecordset` 개체를 일반적으로 만든 또는 위에 설명 된 대로 테이블 정의 열고 다음 생성 recordset 개체를 호출할 때 테이블 정의 개체에 대 한 포인터를 전달 [cdaorecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open)합니다. 전달 하면 테이블 정의 열린 상태에 있어야 합니다. 자세한 내용은 클래스를 참조 하십시오. [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)합니다.  
  
 호출 작업을 마치면 tabledef 개체를 사용 하 여 해당 [닫기](../../mfc/reference/cdaorecordset-class.md#close) 멤버 함수, 다음 테이블 정의 개체를 삭제 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoTableDef`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
##  <a name="append"></a>CDaoTableDef::Append  
 이 멤버 함수를 호출한 후에 호출 [만들기](#create) 데이터베이스의 테이블 정의 저장 하는 새 테이블 정의 개체를 만듭니다.  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>주의  
 함수는 데이터베이스의 TableDefs 컬렉션에 개체를 추가합니다. 하지 추가 하 여 정의 하는 동안 임시 개체로 테이블 정의 사용할 수 있지만 호출 해야 저장 하 고 사용 하려는 경우 **추가**합니다.  
  
> [!NOTE]
>  (Null 또는 빈 문자열을 포함)는 명명 되지 않은 테이블 정의 추가 하려고 하면 MFC 예외를 throw 합니다.  
  
 관련된 내용은 DAO 도움말의 "추가 방법" 항목을 참조 합니다.  
  
##  <a name="canupdate"></a>CDaoTableDef::CanUpdate  
 확인 하려면이 함수를 호출 하는지 여부를 기본 테이블의 정의 `CDaoTableDef` 개체를 변경할 수 있습니다.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>반환 값  
 테이블 구조 (스키마)을 수정할 수 있는 경우 0이 아닌 (추가 또는 필드와 인덱스를 삭제), 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로 새로 만든된 테이블 내부를 `CDaoTableDef` 개체를 업데이트할 수 및 연결 된 테이블의 기본 프로그램는 `CDaoTableDef` 개체를 업데이트할 수 없습니다. A `CDaoTableDef` 결과 레코드 집합을 업데이트할 수 없는 경우에 개체를 업데이트할 수 있습니다.  
  
 관련된 내용은 DAO 도움말의 "업데이트할 수 있는 속성" 항목을 참조 합니다.  
  
##  <a name="cdaotabledef"></a>CDaoTableDef::CDaoTableDef  
 생성 된 **CDaoTableDef** 개체입니다.  
  
```  
CDaoTableDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDatabase`  
 에 대 한 포인터는 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 호출 해야 개체를 생성 한 후의 [만들기](#create) 또는 [열려](#open) 멤버 함수입니다. 호출 해야 개체를 마치면 해당 [닫기](#close) 멤버 함수를 파괴는 `CDaoTableDef` 개체입니다.  
  
##  <a name="close"></a>CDaoTableDef::Close  
 닫고 테이블 정의 개체를 해제 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>주의  
 일반적으로 호출한 후 **닫기**, 할당 된 경우 테이블 정의 개체를 삭제 하면 **새**합니다.  
  
 호출할 수 있습니다 [열려](#open) 호출 후에 다시 **닫기**합니다. 이 테이블 정의 개체를 다시 사용할 수 있습니다.  
  
 관련된 정보에 대 한 "Close 메서드" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="create"></a>CDaoTableDef::Create  
 이 새 저장 된 테이블을 만드는 함수를 호출 합니다.  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    long lAttributes = 0,  
    LPCTSTR lpszSrcTable = NULL,  
    LPCTSTR lpszConnect = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 테이블의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `lAttributes`  
 테이블 정의 개체를 나타내는 테이블의 특성에 해당 하는 값입니다. 다음 상수 중 하나를 결합 하는 비트 OR를 사용할 수 있습니다.  
  
|상수|설명|  
|--------------|-----------------|  
|**dbAttachExclusive**|Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스, 테이블은 단독 사용을 위해 열린 연결 된 테이블을 나타냅니다.|  
|**dbAttachSavePWD**|Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스, 사용자 ID와 연결 된 테이블에 대 한 암호는 연결 정보로 저장을 나타냅니다.|  
|**dbSystemObject**|Microsoft Jet 데이터베이스 엔진에서 제공 하는 시스템 테이블에서 테이블을 나타냅니다.|  
|**dbHiddenObject**|Microsoft Jet 데이터베이스 엔진에서 제공 하는 숨겨진된 테이블 테이블을 나타냅니다.|  
  
 *lpszSrcTable*  
 소스 테이블 이름을 포함 하는 문자열에 대 한 포인터입니다. 기본적으로이 값으로 초기화 됩니다 **NULL**합니다.  
  
 `lpszConnect`  
 기본 연결 문자열을 포함 하는 문자열에 대 한 포인터입니다. 기본적으로이 값으로 초기화 됩니다 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 테이블 정의 지정한 후 호출할 수 있습니다 [추가](#append) 데이터베이스의 TableDefs 컬렉션에 테이블 정의 저장 합니다. 호출한 후 **추가**열린 상태에서 테이블 정의 되며 만드는 데 사용할 수는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체입니다.  
  
 관련된 내용은 DAO 도움말의 "CreateTableDef 메서드" 항목을 참조 합니다.  
  
##  <a name="createfield"></a>CDaoTableDef::CreateField  
 테이블에 필드를 추가 하려면이 멤버 함수를 호출 합니다.  
  
```  
void CreateField(
    LPCTSTR lpszName,  
    short nType,  
    long lSize,  
    long lAttributes = 0);  
  
void CreateField(CDaoFieldInfo& fieldinfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 이 필드의 이름을 지정 하는 문자열 식에 대 한 포인터입니다.  
  
 `nType`  
 필드의 데이터 형식을 나타내는 값입니다. 설정은 다음이 값 중 하나일 수 있습니다.  
  
|형식|크기(바이트)|설명|  
|----------|--------------------|-----------------|  
|**dbBoolean**|1바이트|BOOL|  
|**dbByte**|1|BYTE|  
|**dbInteger**|2|int|  
|**dbLong**|4|long|  
|**dbCurrency**|9|통화 ( [COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|float|  
|**dbDouble**|9|double|  
|**dbDate**|9|날짜/시간 ( [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 – 255|텍스트 ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|긴 이진 (OLE 개체)를 [CLongBinary](../../mfc/reference/clongbinary-class.md) 또는 [CByteArray](../../mfc/reference/cbytearray-class.md)|  
|**dbMemo**|0|메모 ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
  
 `lSize`  
 텍스트를 포함 하는 필드의 최대 크기 또는 텍스트 또는 숫자 값을 포함 하는 필드의 고정된 크기를 나타내는 값입니다. `lSize` 텍스트 필드를 제외한 모든 매개 변수가 무시 됩니다.  
  
 `lAttributes`  
 비트 OR를 사용 하 여 해당 필드의 특징과 하는 값을 결합할 수 있습니다.  
  
|상수|설명|  
|--------------|-----------------|  
|**dbFixedField**|필드 크기 (숫자 필드에 대 한 기본값) 고정 되어 있습니다.|  
|**dbVariableField**|필드 크기는 변수 (텍스트 필드에만 해당)입니다.|  
|**dbAutoIncrField**|새 레코드에 대 한 필드 값을 고유한 정수 (long) 변경할 수 없는 자동으로 증가 합니다. Microsoft Jet 데이터베이스 테이블에 대해서만 지원 합니다.|  
|**dbUpdatableField**|필드 값을 변경할 수 있습니다.|  
|**dbDescending**|필드가 내림차순으로 정렬 됩니다 (A – Z 또는 100-0) 순서 (Index 개체의 필드 컬렉션에 있는 필드 개체에만 적용). 이 상수를 생략 하면 필드 오름차순으로 정렬 됩니다 (A-Z 또는 0-100) 순서 (기본값).|  
  
 `fieldinfo`  
 에 대 한 참조는 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조입니다.  
  
### <a name="remarks"></a>주의  
 A **DAOField** (OLE) 개체가 생성 되 고의 필드 컬렉션에 추가 된 **DAOTableDef** (OLE) 개체입니다. 개체 속성을 검사 하는 데 사용 외에도 사용할 수도 있습니다 `CDaoFieldInfo` 테이블 정의에 새 필드를 만들기 위한 입력된 매개 변수를 만들려고 합니다. 첫 번째 버전 `CreateField` 를 사용 하는 더 간단 하지만 보다 세부적으로 제어를 원하는 경우의 두 번째 버전을 사용할 수 있습니다 `CreateField`를 가져와서는 `CDaoFieldInfo` 매개 변수입니다.  
  
 버전을 사용 하는 경우 `CreateField` 사용 하는 `CDaoFieldInfo` 매개 변수를 신중 하 게 설정 해야 각각의 다음 멤버는 `CDaoFieldInfo` 구조:  
  
- **m_strName**  
  
- `m_nType`  
  
- **m_lSize**  
  
- **m_lAttributes**  
  
- **m_bAllowZeroLength**  
  
 나머지 멤버 `CDaoFieldInfo` 로 설정 해야 **0**, **FALSE**, 또는 멤버에 대 한 적절 하 게 빈 문자열인 경우 또는 `CDaoException` 발생할 수 있습니다.  
  
 관련된 내용은 DAO 도움말의 "CreateField 메서드" 항목을 참조 합니다.  
  
##  <a name="createindex"></a>CDaoTableDef::CreateIndex  
 테이블에 인덱스를 추가 하려면이 함수를 호출 합니다.  
  
```  
void CreateIndex(CDaoIndexInfo& indexinfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `indexinfo`  
 에 대 한 참조는 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조입니다.  
  
### <a name="remarks"></a>주의  
 인덱스는 중복 레코드가 허용 되는지 여부 및 데이터베이스 테이블에서 액세스 하는 레코드의 순서를 지정 합니다. 또한 인덱스 데이터에 대 한 효율적인 액세스를 제공합니다.  
  
 테이블에 대 한 인덱스를 만들 필요는 없지만 크고 인덱싱되지 않은 테이블에서 레코드 집합을 만들거나 특정 레코드에 액세스 하는 시간이 오래 걸릴 수 있습니다. 반면에 너무 많은 인덱스를 만드는 속도 늦춥니다 업데이트, 추가 및 삭제 작업으로 모든 인덱스는 자동으로 업데이트 됩니다. 만들 인덱스를 결정 하는 대로 이러한 요소를 고려 합니다.  
  
 다음 멤버는 `CDaoIndexInfo` 구조를 설정 해야 합니다.  
  
- **m_strName** 이름을 제공 해야 합니다.  
  
- `m_pFieldInfos`배열에 가리켜야 `CDaoIndexFieldInfo` 구조입니다.  
  
- `m_nFields`배열의 필드 수를 지정 해야 `CDaoFieldInfo` 구조입니다.  
  
 멤버 남아 있는 경우 무시로 설정 됩니다 **FALSE**합니다. 또한는 **m_lDistinctCount** 인덱스를 만드는 동안 멤버가 무시 됩니다.  
  
##  <a name="deletefield"></a>CDaoTableDef::DeleteField  
 필드를 제거 하 고 액세스할 수 없도록 하려면이 멤버 함수를 호출 합니다.  
  
```  
void DeleteField(LPCTSTR lpszName);  
void DeleteField(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 기존 필드의 이름에 해당 하는 문자열 식에 대 한 포인터입니다.  
  
 `nIndex`  
 테이블의&0;부터 시작 필드 컬렉션의 인덱스로 조회에 대 한 필드의 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수를 사용 하 여 데이터베이스에 추가 된이 새 개체에 사용할 경우 또는 [CanUpdate](#canupdate)&0;이 아닌 값을 반환 합니다.  
  
 관련된 정보에 대 한 "Delete 메서드" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="deleteindex"></a>CDaoTableDef::DeleteIndex  
 원본 테이블에 인덱스를 삭제 하려면이 멤버 함수를 호출 합니다.  
  
```  
void DeleteIndex(LPCTSTR lpszName);  
void DeleteIndex(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 기존 인덱스의 이름에 해당 하는 문자열 식에 대 한 포인터입니다.  
  
 `nIndex`  
 데이터베이스의&0;부터 시작 TableDefs 컬렉션의 인덱스로 조회에 대 한 인덱스 개체의 배열 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수를 사용 하 여 데이터베이스에 아직 추가 되지 하는 새 개체에 사용할 경우 또는 [CanUpdate](#canupdate)&0;이 아닌 값을 반환 합니다.  
  
 관련된 정보에 대 한 "Delete 메서드" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="getattributes"></a>CDaoTableDef::GetAttributes  
 에 대 한 한 `CDaoTableDef` 개체를 반환 값은로 표시 된 테이블의 특성을 지정는 `CDaoTableDef` 개체와 이러한 상수 중 합 수 있습니다.  
  
```  
long GetAttributes();
```  
  
### <a name="return-value"></a>반환 값  
 하나 이상의 특성을 나타내는 값을 반환 된 `CDaoTableDef` 개체입니다.  
  
### <a name="remarks"></a>주의  
  
|상수|설명|  
|--------------|-----------------|  
|**dbAttachExclusive**|Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스, 테이블은 단독 사용을 위해 열린 연결 된 테이블을 나타냅니다.|  
|**dbAttachSavePWD**|Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스, 사용자 ID와 연결 된 테이블에 대 한 암호는 연결 정보로 저장을 나타냅니다.|  
|**dbSystemObject**|Microsoft Jet 데이터베이스 엔진에서 제공 하는 시스템 테이블에서 테이블을 나타냅니다.|  
|**dbHiddenObject**|Microsoft Jet 데이터베이스 엔진에서 제공 하는 숨겨진된 테이블 테이블을 나타냅니다.|  
|**dbAttachedTable**|연결된 된 테이블의 모순 데이터베이스와 같은 비 ODBC 데이터베이스에서 테이블을 나타냅니다.|  
|**dbAttachedODBC**|테이블은 Microsoft SQL Server 등의 ODBC 데이터베이스에서 연결 된 테이블을 나타냅니다.|  
  
 시스템 테이블은 다양 한 내부 정보를 포함 하도록 Microsoft Jet 데이터베이스 엔진에 의해 생성 된 테이블.  
  
 숨겨진된 테이블은 임시 사용 하기 위해 Microsoft Jet 데이터베이스 엔진에 의해 생성 된 테이블.  
  
 관련된 내용은 DAO 도움말에서 "특성 속성" 항목을 참조 합니다.  
  
##  <a name="getconnect"></a>CDaoTableDef::GetConnect  
 데이터 원본에 대 한 연결 문자열을 가져오려면이 함수를 호출 합니다.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 테이블에 대 한 경로 및 데이터베이스 형식을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 에 대 한 한 `CDaoTableDef` 추가 된 테이블을 나타내는 개체는 `CString` 개체 (데이터베이스 형식 지정자와 데이터베이스에 대 한 경로) 하나 또는 두 부분으로 구성 됩니다.  
  
 다음 표에서 같이 경로 데이터베이스 파일이 있는 디렉터리에 대 한 전체 경로 및 식별자 뒤에 야 "데이터베이스 ="입니다. 경우에 따라 (Microsoft Excel 및 Microsoft Jet 데이터베이스) 대로 특정 파일 이름을 데이터베이스 path 인수에 포함 됩니다.  
  
 테이블에서 [CDaoTableDef::SetConnect](#setconnect) 가능한 데이터베이스 형식 및 해당 데이터베이스 지정자 및 경로 보여 줍니다.  
  
 Microsoft Jet 데이터베이스 기본 테이블에 지정자는 빈 문자열 ("").  
  
 ODBC 드라이버는 테이블을 액세스 하는 로그인 대화 상자는 첫 번째 시간 표시 필요한 암호가 제공 되지 않은, 다시 연결을 닫고 다시 하는 경우. 연결된 된 테이블에는 **dbAttachSavePWD** 특성 테이블을 다시 열 때 로그인 프롬프트가 표시 되지 것입니다.  
  
 관련된 내용은 DAO 도움말에서 "연결 속성" 항목을 참조 합니다.  
  
##  <a name="getdatecreated"></a>CDaoTableDef::GetDateCreated  
 기본 테이블에 날짜와 시간을 확인 하려면이 함수를 호출의 `CDaoTableDef` 개체가 생성 되었습니다.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>반환 값  
 내부 테이블 만들기 작업의 시간과 날짜를 포함 하는 값은 `CDaoTableDef` 개체입니다.  
  
### <a name="remarks"></a>주의  
 날짜 및 시간 설정이 있는 기본 테이블을 만들거나 마지막으로 업데이트 하는 컴퓨터에서 파생 됩니다. 다중 사용자 환경에서 사용자가 해야 이러한 설정을 가져올; 불일치를 방지 하려면 파일 서버에서 직접 즉, 모든 클라이언트는 "standard" 시간 원본을 사용 해야-서버 간에 일 것입니다.  
  
 관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.  
  
##  <a name="getdatelastupdated"></a>CDaoTableDef::GetDateLastUpdated  
 기본 테이블에 날짜와 시간을 확인 하려면이 함수를 호출의 **CDaoTableDef** 개체가 마지막으로 업데이트 합니다.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>반환 값  
 기본 테이블의 날짜 및 시간 포함 하는 값은 **CDaoTableDef** 개체가 마지막으로 업데이트 합니다.  
  
### <a name="remarks"></a>주의  
 날짜 및 시간 설정이 있는 기본 테이블을 만들거나 마지막으로 업데이트 하는 컴퓨터에서 파생 됩니다. 다중 사용자 환경에서 사용자가 해야 이러한 설정을 가져올; 불일치를 방지 하려면 파일 서버에서 직접 즉, 모든 클라이언트는 "standard" 시간 원본을 사용 해야-서버 간에 일 것입니다.  
  
 관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.  
  
##  <a name="getfieldcount"></a>CDaoTableDef::GetFieldCount  
 테이블에 정의 된 필드 수를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>반환 값  
 테이블의 필드 개수입니다.  
  
### <a name="remarks"></a>주의  
 해당 값이 0 이면 개체가 없는 컬렉션에 있습니다.  
  
 관련된 내용은 DAO 도움말의 "Count 속성" 항목을 참조 합니다.  
  
##  <a name="getfieldinfo"></a>CDaoTableDef::GetFieldInfo  
 다양 한 종류의 테이블 정의에 정의 된 필드에 대 한 정보를 가져오려면이 함수를 호출 합니다.  
  
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
 테이블의&0;부터 시작 필드 컬렉션의 인덱스로 조회에 대 한 필드 개체의 인덱스입니다.  
  
 `fieldinfo`  
 에 대 한 참조는 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조입니다.  
  
 `dwInfoOptions`  
 검색할 필드에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 한 원인을 반환 하는 함수를 함께 여기에 나열 됩니다.  
  
- `AFX_DAO_PRIMARY_INFO`(기본값) 특성 이름, 유형, 크기입니다. 이 옵션을 사용 하 여 빠른 성능을 합니다.  
  
- `AFX_DAO_SECONDARY_INFO`기본 정보, plus: 서 수 위치에 필요한 길이, 데이터 정렬 순서, 외부 이름, 원본 필드를 원본 테이블&0; 허용  
  
- `AFX_DAO_ALL_INFO`기본 및 보조 정보를 더한: 유효성 검사 규칙을 유효성 검사 텍스트 기본값  
  
 `lpszName`  
 Field 개체의 이름으로 조회에 대 한 이름에 대 한 포인터입니다. 이름은 최대 64 자 고유 필드의 이름을 지정 하는 문자열입니다.  
  
### <a name="remarks"></a>주의  
 한 버전의 함수를 사용 하면 인덱스 하 여 필드를 찾을 수 있습니다. 다른 버전에는 필드 이름으로 조회할 수 있습니다.  
  
 반환 되는 정보에 대 한 참조는 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조입니다. 이 구조에는 항목의 설명에서 위에 나열 된 정보에 해당 하는 멤버가 `dwInfoOptions`합니다. 한 수준에서 정보를 요청도 모든 이전 수준에 대 한 정보를 얻을 수 있습니다.  
  
 관련된 내용은 DAO 도움말에서 "특성 속성" 항목을 참조 합니다.  
  
##  <a name="getindexcount"></a>CDaoTableDef::GetIndexCount  
 테이블에 대 한 인덱스 번호를 가져오려면이 함수를 호출 합니다.  
  
```  
short GetIndexCount();
```  
  
### <a name="return-value"></a>반환 값  
 테이블에 대 한 인덱스의 수입니다.  
  
### <a name="remarks"></a>주의  
 해당 값이 0 이면 인덱스가 없는 컬렉션에 있는 있습니다.  
  
 관련된 내용은 DAO 도움말의 "Count 속성" 항목을 참조 합니다.  
  
##  <a name="getindexinfo"></a>CDaoTableDef::GetIndexInfo  
 다양 한 종류의 테이블 정의에 정의 된 인덱스에 대 한 정보를 가져오려면이 함수를 호출 합니다.  
  
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
 컬렉션에 있는 테이블의&0;부터 시작 인덱스를 조회 컬렉션에서 해당 위치에 대 한 인덱스 개체의 숫자 인덱스입니다.  
  
 `indexinfo`  
 에 대 한 참조는 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조입니다.  
  
 `dwInfoOptions`  
 인덱스를 검색 하는 방법에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 한 원인을 반환 하는 함수를 함께 여기에 나열 됩니다.  
  
- `AFX_DAO_PRIMARY_INFO`이름, 필드 정보 필드입니다. 이 옵션을 사용 하 여 빠른 성능을 합니다.  
  
- `AFX_DAO_SECONDARY_INFO`기본 정보, plus: 주, Unique, Clustered, Null 무시, 필수, 외부  
  
- `AFX_DAO_ALL_INFO`기본 및 보조 정보를 더한: 고유 카운트  
  
 `lpszName`  
 이름별으로 조회에 대 한 인덱스 개체의 이름에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 한 버전의 함수를 사용 하면 컬렉션에서 해당 위치는 인덱스를 조회할 수 있습니다. 다른 버전 이름으로 인덱스를 조회할 수 있습니다.  
  
 반환 되는 정보에 대 한 참조는 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조입니다. 이 구조에는 항목의 설명에서 위에 나열 된 정보에 해당 하는 멤버가 `dwInfoOptions`합니다. 한 수준에서 정보를 요청도 모든 이전 수준에 대 한 정보를 얻을 수 있습니다.  
  
 관련된 내용은 DAO 도움말에서 "특성 속성" 항목을 참조 합니다.  
  
##  <a name="getname"></a>CDaoTableDef::GetName  
 기본 테이블의 사용자 정의 이름을 가져오려면이 함수를 호출 합니다.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>반환 값  
 테이블에 대 한 사용자 정의 이름입니다.  
  
### <a name="remarks"></a>주의  
 이 이름은 문자로 시작 하 고 최대 64 자까지 포함할 수 있습니다. 숫자를 포함할 수 및 밑줄 문자는 문장 부호 또는 공백을 포함할 수 없습니다.  
  
 관련된 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.  
  
##  <a name="getrecordcount"></a>CDaoTableDef::GetRecordCount  
 레코드 수를 확인 하려면이 멤버 함수를 호출 하는 `CDaoTableDef` 개체입니다.  
  
```  
long GetRecordCount();
```  
  
### <a name="return-value"></a>반환 값  
 테이블 정의 개체에 액세스 하는 레코드 수입니다.  
  
### <a name="remarks"></a>주의  
 호출 `GetRecordCount` 테이블 형식에 대 한 `CDaoTableDef` 개체는 테이블의 레코드의 대략적인 수를 반영 하 고는 영향을 즉시 테이블 레코드를 추가 하 고 삭제 합니다. 호출할 때까지 트랜잭션 레코드 수의 일부로 나타납니다 롤백 [CDaoWorkSpace::CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase)합니다. A `CDaoTableDef` 레코드가 없는 개체에는 레코드 수 속성이 0으로 설정 합니다. ODBC 데이터베이스 또는 연결 된 테이블을 작업할 때 `GetRecordCount` 항상-1을 반환 합니다.  
  
 관련된 내용은 DAO 도움말에서 "RecordCount 속성" 항목을 참조 합니다.  
  
##  <a name="getsourcetablename"></a>CDaoTableDef::GetSourceTableName  
 원본 데이터베이스에 연결된 된 테이블의 이름을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetSourceTableName();
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 네이티브 데이터 테이블이 있는 경우 연결된 된 테이블 또는 빈 문자열의 소스 이름을 지정 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 연결된 된 테이블에는 Microsoft Jet 데이터베이스에 연결 하는 다른 데이터베이스의 테이블이입니다. 연결 된 테이블에 대 한 데이터는 다른 응용 프로그램에서 조작할 수 있는 외부 데이터베이스에 남아 있습니다.  
  
 관련된 내용은 DAO 도움말의 "속성은" 항목을 참조 합니다.  
  
##  <a name="getvalidationrule"></a>CDaoTableDef::GetValidationRule  
 테이블 정의 대 한 유효성 검사 규칙을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetValidationRule();
```  
  
### <a name="return-value"></a>반환 값  
 A **CString** 변경 이나 테이블에 추가 되는 필드의 데이터 유효성을 검사 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 유효성 검사 규칙을 사용 하 여 업데이트 작업에 연결 합니다. 유효성 검사 규칙을 포함 하는 테이블 정의 데이터를 변경 하기 전에 해당 테이블 정의에 대 한 업데이트는 미리 결정 된 조건 일치 해야 합니다. 변경 된 조건 값을 포함 하는 예외 일치 하지 않는 경우 [GetValidationText](#getvalidationtext) throw 됩니다. 에 대 한 한 `CDaoTableDef` 개체를이 `CString` 는 연결 된 테이블과 기본 테이블에 대 한 읽기/쓰기에 대 한 읽기 전용입니다.  
  
 관련된 내용은 DAO 도움말에서 "ValidationRule 속성" 항목을 참조 합니다.  
  
##  <a name="getvalidationtext"></a>CDaoTableDef::GetValidationText  
 유효성 검사 규칙을 일치 하지 않는 데이터를 입력 하는 경우 표시할 문자열을 검색 하려면이 함수를 호출 합니다.  
  
```  
CString GetValidationText();
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 유효성 검사 규칙을 일치 하지 않는 데이터를 입력할 경우 표시할 텍스트를 지정 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 에 대 한 한 `CDaoTableDef` 개체를이 `CString` 는 연결 된 테이블과 기본 테이블에 대 한 읽기/쓰기에 대 한 읽기 전용입니다.  
  
 관련된 내용은 DAO 도움말의 "유효성 검사 텍스트 속성" 항목을 참조 합니다.  
  
##  <a name="isopen"></a>CDaoTableDef::IsOpen  
 확인 하려면이 함수를 호출 여부는 `CDaoTableDef` 개체가 현재 열려 있습니다.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 값은 `CDaoTableDef` 개체가 열려 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="m_pdatabase"></a>CDaoTableDef::m_pDatabase  
 에 대 한 포인터는 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 이 테이블에 대 한 개체입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="m_pdaotabledef"></a>CDaoTableDef::m_pDAOTableDef  
 DAO tabledef 개체 내부에 대 한 OLE 인터페이스에 대 한 포인터는 `CDaoTableDef` 개체입니다.  
  
### <a name="remarks"></a>주의  
 DAO 인터페이스에 직접 액세스 하는 경우이 포인터를 사용 합니다.  
  
##  <a name="open"></a>CDaoTableDef::Open  
 데이터베이스에 이전에 저장 된 테이블 정의 열려면이 멤버 함수 호출의 테이블 정의 컬렉션입니다.  
  
```  
virtual void Open(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 테이블 이름을 지정 하는 문자열에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="refreshlink"></a>CDaoTableDef::RefreshLink  
 연결된 된 테이블에 대 한 연결 정보를 업데이트 하려면이 멤버 함수를 호출 합니다.  
  
```  
void RefreshLink();
```  
  
### <a name="remarks"></a>주의  
 호출 하 여 연결된 된 테이블에 대 한 연결 정보를 변경 하면 [SetConnect](#setconnect) 해당 `CDaoTableDef` 개체를 사용 하는 `RefreshLink` 멤버 함수 정보를 업데이트 합니다. 호출 하는 경우 `RefreshLink`, 연결 된 테이블의 속성은 변경 되지 않습니다.  
  
 강제로 수정 된 연결 정보를 적용 하려면 열려 있는 모든 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 이 테이블 정의 기반으로 개체를 닫아야 합니다.  
  
 관련된 내용은 DAO 도움말의 "RefreshLink 메서드" 항목을 참조 합니다.  
  
##  <a name="setattributes"></a>CDaoTableDef::SetAttributes  
 하나 이상의 특성을 나타내는 값을 설정 하는 `CDaoTableDef` 개체입니다.  
  
```  
void SetAttributes(long lAttributes);
```  
  
### <a name="parameters"></a>매개 변수  
 `lAttributes`  
 로 표시 된 테이블의 특성은 `CDaoTableDef` 개체와 이러한 상수 중 합 수 있습니다.  
  
|상수|설명|  
|--------------|-----------------|  
|**dbAttachExclusive**|Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스, 테이블은 단독 사용을 위해 열린 연결 된 테이블을 나타냅니다.|  
|**dbAttachSavePWD**|Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스, 사용자 ID와 연결 된 테이블에 대 한 암호는 연결 정보로 저장을 나타냅니다.|  
|**dbSystemObject**|Microsoft Jet 데이터베이스 엔진에서 제공 하는 시스템 테이블에서 테이블을 나타냅니다.|  
|**dbHiddenObject**|Microsoft Jet 데이터베이스 엔진에서 제공 하는 숨겨진된 테이블 테이블을 나타냅니다.|  
  
### <a name="remarks"></a>주의  
 여러 특성을 설정할 때 비트 OR 연산자를 사용 하 여 적절 한 상수를 합하여 결합할 수 있습니다. 설정 **dbAttachExclusive** 연결 되지 않은 테이블에서 예외를 생성 합니다. 다음 값을 결합 하는 예외를 생성을도:  
  
- **dbAttachExclusive | dbAttachedODBC**  
  
- **dbAttachSavePWD | dbAttachedTable**  
  
 관련된 내용은 DAO 도움말에서 "특성 속성" 항목을 참조 합니다.  
  
##  <a name="setconnect"></a>CDaoTableDef::SetConnect  
 에 대 한는 `CDaoTableDef` 문자열 개체가 추가 된 테이블을 나타내는 개체 (데이터베이스 형식 지정자와 데이터베이스에 대 한 경로) 하나 또는 두 부분으로 구성 됩니다.  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszConnect`  
 ODBC 또는 설치 가능한 ISAM 드라이버에 전달 하는 추가 매개 변수를 지정 하는 문자열 식에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 다음 표에서 같이 경로 데이터베이스 파일이 있는 디렉터리에 대 한 전체 경로 및 식별자 뒤에 야 "데이터베이스 ="입니다. 경우에 따라 (Microsoft Excel 및 Microsoft Jet 데이터베이스) 대로 특정 파일 이름을 데이터베이스 path 인수에 포함 됩니다.  
  
> [!NOTE]
>  폼의 경로 문에서 등호 주위에 공백을 넣지 마십시오 "데이터베이스 = 드라이브:\\\path"입니다. 이렇게 하면 예외가 throw 되 고 연결이 실패 합니다.  
  
 다음 표에서 가능한 데이터베이스 형식 및 해당 데이터베이스 지정자 및 경로 보여 줍니다.  
  
|데이터베이스 유형|지정자|Path|  
|-------------------|---------------|----------|  
|Jet 데이터베이스 엔진을 사용 하 여 데이터베이스|"[ `database`];"|" `drive`:\\\ *path*\\\ *filename*. MDB "|  
|dBASE III|"dBASE III;"|" `drive`:\\\ *path*"|  
|dBASE IV|"dBASE IV;"|" `drive`:\\\ *path*"|  
|dBASE 5|"dBASE 5.0;"|" `drive`:\\\ *path*"|  
|Paradox 3.x|"Paradox 3.x;"|" `drive`:\\\ *path*"|  
|Paradox 4.x|"Paradox 4.x;"|" `drive`:\\\ *path*"|  
|Paradox 5.x|"Paradox 5.x;"|" `drive`:\\\ *path*"|  
|Excel 3.0|"Excel 3.0;"|" `drive`:\\\ *path*\\\ *filename*. XLS "|  
|Excel 4.0|"Excel 4.0;"|" `drive`:\\\ *path*\\\ *filename*. XLS "|  
|5.0 Excel 또는 Excel 95|"Excel 5.0;"|" `drive`:\\\ *path*\\\ *filename*. XLS "|  
|Excel 97|"Excel 8.0";|" `drive`:\\\ *path*\ *filename*. XLS "|  
|HTML 가져오기|"HTML 가져오기;"|" `drive`:\\\ *path*\ *filename*"|  
|HTML 내보내기|"HTML 내보내기;"|" `drive`:\\\ *path*"|  
|텍스트|"Text";|"드라이브:\\\path"|  
|ODBC|"ODBC; 데이터베이스 = `database`; UID= *user*; PWD = *암호*; DSN = *datasourcename;* LOGINTIMEOUT = *; 초*" (수립이 모든 서버에 대 한 완전 한 연결 문자열에는 예로 든 것일 뿐입니다. 반드시을 갖는 매개 변수 사이 공백이 있습니다.)|없음|  
|Exchange|"Exchange;<br /><br /> MAPILEVEL = *folderpath*;<br /><br /> [TABLETYPE = {0 | 1};]<br /><br /> [프로필 = *프로필*;]<br /><br /> [PWD = *암호*;]<br /><br /> [데이터베이스 = `database`;] "|*"drive*:\\\ *path*\\\ *filename*. MDB "|  
  
> [!NOTE]
>  DAO 3.5부터 더 이상 Btrieve 사용할 수 없습니다.  
  
 이중 백슬래시를 사용 해야 합니다 (\\\\)의 연결 문자열에 있습니다. 사용 하 여 기존 연결의 속성을 수정한 경우 `SetConnect`, 이후에 호출 해야 [RefreshLink](#refreshlink)합니다. 사용 하 여 연결 속성을 초기화 하는 경우 `SetConnect`를 호출 하지 해야 `RefreshLink`을 선택한 경우 이렇게 하려면 먼저 테이블 정의 추가 하지만 합니다.  
  
 ODBC 드라이버는 테이블을 액세스 하는 로그인 대화 상자는 첫 번째 시간 표시 필요한 암호가 제공 되지 않은, 다시 연결을 닫고 다시 하는 경우.  
  
 에 대 한 연결 문자열을 설정할 수는 `CDaoTableDef` 소스 인수를 제공 하 여 개체는 **만들기** 멤버 함수입니다. 유형, 경로, 사용자 ID, 암호 또는 데이터베이스의 ODBC 데이터 원본을 확인 하려면 설정을 확인할 수 있습니다. 자세한 내용은 특정 드라이버에 대 한 설명서를 참조 하십시오.  
  
 관련된 내용은 DAO 도움말에서 "연결 속성" 항목을 참조 합니다.  
  
##  <a name="setname"></a>CDaoTableDef::SetName  
 테이블에 대 한 사용자 정의 이름을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 테이블의 이름을 지정 하는 문자열 식에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이름은 문자로 시작 해야 하며 최대 64 자까지 포함할 수 있습니다. 숫자를 포함할 수 및 밑줄 문자는 문장 부호 또는 공백을 포함할 수 없습니다.  
  
 관련된 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.  
  
##  <a name="setsourcetablename"></a>CDaoTableDef::SetSourceTableName  
 에 추가 된 테이블의 이름 또는 기본 테이블의 이름을 지정 하려면이 함수를 호출는 `CDaoTableDef` 데이터 원본에 있는 개체를 기초로 합니다.  
  
```  
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszSrcTableName*  
 외부 데이터베이스에서 테이블 이름을 지정 하는 문자열 식에 대 한 포인터입니다. 기본 테이블에 대 한 설정을 빈 문자열 ("").  
  
### <a name="remarks"></a>주의  
 그런 다음 호출 해야 [RefreshLink](#refreshlink)합니다. 이 속성 설정은 기본 테이블과 연결된 된 테이블 또는 컬렉션에 추가 되지 않은 개체에 대 한 읽기/쓰기에 대 한 비어 있습니다.  
  
 관련된 내용은 DAO 도움말의 "속성은" 항목을 참조 합니다.  
  
##  <a name="setvalidationrule"></a>CDaoTableDef::SetValidationRule  
 테이블 정의 대 한 유효성 검사 규칙을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetValidationRule(LPCTSTR lpszValidationRule);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszValidationRule*  
 작업의 유효성을 검사 하는 문자열 식에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 유효성 검사 규칙을 사용 하 여 업데이트 작업에 연결 합니다. 유효성 검사 규칙을 포함 하는 테이블 정의 데이터를 변경 하기 전에 해당 테이블 정의에 대 한 업데이트는 미리 결정 된 조건 일치 해야 합니다. 변경, 조건을의 텍스트를 포함 하는 예외 일치 하지 않는 경우 [GetValidationText](#getvalidationtext) 표시 됩니다.  
  
 유효성 검사는 Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스에 대해서만 지원 됩니다. 사용자 정의 함수, 도메인 집계 함수, SQL 집계 함수 또는 쿼리 식을 참조할 수 없습니다. 에 대 한 유효성 검사 규칙을 `CDaoTableDef` 개체는 해당 개체의 여러 필드를 참조할 수 있습니다.  
  
 명명 된 필드에 대 한 예를 들어 `hire_date` 및 `termination_date`, 유효성 검사 규칙을 만들 수 있습니다.  
  
 [!code-cpp[NVC_MFCDatabase #&34;](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]  
  
 관련된 내용은 DAO 도움말에서 "ValidationRule 속성" 항목을 참조 합니다.  
  
##  <a name="setvalidationtext"></a>CDaoTableDef::SetValidationText  
 에 대 한 유효성 검사 규칙의 예외 텍스트를 설정 하려면이 멤버 함수를 호출 하는 `CDaoTableDef` Microsoft Jet 데이터베이스 엔진에서 지 원하는 기본 테이블에 있는 개체입니다.  
  
```  
void SetValidationText(LPCTSTR lpszValidationText);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszValidationText*  
 데이터를 입력 하는 경우 표시할 텍스트를 지정 하는 문자열 식에 대 한 포인터가 잘못 되었습니다.  
  
### <a name="remarks"></a>주의  
 추가 된 테이블의 유효성 검사 텍스트를 설정할 수 없습니다.  
  
 관련된 내용은 DAO 도움말의 "유효성 검사 텍스트 속성" 항목을 참조 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase 클래스](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset 클래스](../../mfc/reference/cdaorecordset-class.md)

