---
title: "CDaoTableDef 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
- CDaoTableDef [MFC], CDaoTableDef
- CDaoTableDef [MFC], Append
- CDaoTableDef [MFC], CanUpdate
- CDaoTableDef [MFC], Close
- CDaoTableDef [MFC], Create
- CDaoTableDef [MFC], CreateField
- CDaoTableDef [MFC], CreateIndex
- CDaoTableDef [MFC], DeleteField
- CDaoTableDef [MFC], DeleteIndex
- CDaoTableDef [MFC], GetAttributes
- CDaoTableDef [MFC], GetConnect
- CDaoTableDef [MFC], GetDateCreated
- CDaoTableDef [MFC], GetDateLastUpdated
- CDaoTableDef [MFC], GetFieldCount
- CDaoTableDef [MFC], GetFieldInfo
- CDaoTableDef [MFC], GetIndexCount
- CDaoTableDef [MFC], GetIndexInfo
- CDaoTableDef [MFC], GetName
- CDaoTableDef [MFC], GetRecordCount
- CDaoTableDef [MFC], GetSourceTableName
- CDaoTableDef [MFC], GetValidationRule
- CDaoTableDef [MFC], GetValidationText
- CDaoTableDef [MFC], IsOpen
- CDaoTableDef [MFC], Open
- CDaoTableDef [MFC], RefreshLink
- CDaoTableDef [MFC], SetAttributes
- CDaoTableDef [MFC], SetConnect
- CDaoTableDef [MFC], SetName
- CDaoTableDef [MFC], SetSourceTableName
- CDaoTableDef [MFC], SetValidationRule
- CDaoTableDef [MFC], SetValidationText
- CDaoTableDef [MFC], m_pDAOTableDef
- CDaoTableDef [MFC], m_pDatabase
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7b140d61689672f9d27b8078ad7d2eab732c1582
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
|[CDaoTableDef::CanUpdate](#canupdate)|테이블을 업데이트할 수 있으면 0이 아닌 반환 (필드 또는 테이블 속성의 정의 수정할 수 있습니다).|  
|[CDaoTableDef::Close](#close)|열린 tabledef를 닫습니다.|  
|[CDaoTableDef::Create](#create)|사용 하 여 데이터베이스에 추가할 수 있는 테이블을 만듭니다 [Append](#append)합니다.|  
|[CDaoTableDef::CreateField](#createfield)|테이블에 대 한 필드를 만들기 위해 호출 합니다.|  
|[CDaoTableDef::CreateIndex](#createindex)|테이블에 대 한 인덱스를 만들기 위해 호출 합니다.|  
|[CDaoTableDef::DeleteField](#deletefield)|테이블에서 필드를 삭제 하기 위해 호출 합니다.|  
|[CDaoTableDef::DeleteIndex](#deleteindex)|테이블에서 인덱스를 삭제 하기 위해 호출 합니다.|  
|[CDaoTableDef::GetAttributes](#getattributes)|하나 이상의 특성을 나타내는 값을 반환는 `CDaoTableDef` 개체입니다.|  
|[CDaoTableDef::GetConnect](#getconnect)|테이블의 원본에 대 한 정보를 제공 하는 값을 반환 합니다.|  
|[CDaoTableDef::GetDateCreated](#getdatecreated)|기본 테이블의 기본 날짜 및 시간 반환는 `CDaoTableDef` 개체가 만들어진 합니다.|  
|[CDaoTableDef::GetDateLastUpdated](#getdatelastupdated)|기본 테이블의 디자인에 대 한 가장 최근의 변경의 시간과 날짜를 반환 합니다.|  
|[CDaoTableDef::GetFieldCount](#getfieldcount)|테이블의 필드 수를 나타내는 값을 반환 합니다.|  
|[CDaoTableDef::GetFieldInfo](#getfieldinfo)|테이블의 특정 종류의 필드에 대 한 정보를 반환 합니다.|  
|[CDaoTableDef::GetIndexCount](#getindexcount)|테이블에 대 한 인덱스를 반환합니다.|  
|[CDaoTableDef::GetIndexInfo](#getindexinfo)|특정 종류의 테이블에 대 한 인덱스에 대 한 정보를 반환합니다.|  
|[CDaoTableDef::GetName](#getname)|테이블의 사용자 정의 이름을 반환합니다.|  
|[CDaoTableDef::GetRecordCount](#getrecordcount)|테이블의 레코드 수를 반환합니다.|  
|[CDaoTableDef::GetSourceTableName](#getsourcetablename)|원본 데이터베이스에 연결 된 테이블의 이름을 지정 하는 값을 반환 합니다.|  
|[CDaoTableDef::GetValidationRule](#getvalidationrule)|이 변경 되거나 테이블에 추가 되는 필드의 데이터 유효성을 검사 하는 값을 반환 합니다.|  
|[CDaoTableDef::GetValidationText](#getvalidationtext)|Field 개체의 값은 지정 된 유효성 검사 규칙을 충족 하지 않으면 응용 프로그램에서 표시 하는 메시지의 텍스트를 지정 하는 값을 반환 합니다.|  
|[CDaoTableDef::IsOpen](#isopen)|연 테이블이 경우 0이 아닌 반환 합니다.|  
|[CDaoTableDef::Open](#open)|열립니다는 데이터베이스에 저장 된 기존 테이블 정의 테이블 정의 컬렉션입니다.|  
|[CDaoTableDef::RefreshLink](#refreshlink)|연결된 된 테이블에 대 한 연결 정보를 업데이트합니다.|  
|[CDaoTableDef::SetAttributes](#setattributes)|하나 이상의 특성을 나타내는 값을 설정 하는 `CDaoTableDef` 개체입니다.|  
|[CDaoTableDef::SetConnect](#setconnect)|테이블의 원본에 대 한 정보를 제공 하는 값을 설정 합니다.|  
|[CDaoTableDef::SetName](#setname)|테이블의 이름을 설정합니다.|  
|[CDaoTableDef::SetSourceTableName](#setsourcetablename)|원본 데이터베이스에 연결된 된 테이블의 이름을 지정 하는 값을 설정 합니다.|  
|[CDaoTableDef::SetValidationRule](#setvalidationrule)|이 변경 되거나 테이블에 추가 되는 필드의 데이터 유효성을 검사 하는 값을 설정 합니다.|  
|[CDaoTableDef::SetValidationText](#setvalidationtext)|Field 개체의 값은 지정 된 유효성 검사 규칙을 충족 하지 않으면 응용 프로그램에서 표시 하는 메시지의 텍스트를 지정 하는 값을 설정 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoTableDef::m_pDAOTableDef](#m_pdaotabledef)|테이블 정의 개체를 원본 DAO 인터페이스에 대 한 포인터입니다.|  
|[CDaoTableDef::m_pDatabase](#m_pdatabase)|이 테이블에 대 한 원본 데이터베이스입니다.|  
  
## <a name="remarks"></a>설명  
 각 DAO 데이터베이스 개체에 저장 된 모든 DAO tabledef 개체가 포함 된 테이블 정의 호출 하는 컬렉션을 유지 관리 합니다.  
  
 사용 하 여 테이블 정의 조작 하는 `CDaoTableDef` 개체입니다. 예를 들어 다음 작업을 할 수 있습니다.  
  
-   데이터베이스의 모든 로컬, 연결 또는 외부 테이블의 필드 및 인덱스 구조를 검사 합니다.  
  
-   호출 된 `SetConnect` 및 `SetSourceTableName` 연결 된 테이블 및 사용에 대 한 멤버 함수는 `RefreshLink` 멤버 함수에 대 한 연결을 업데이트 하려면 연결 된 테이블입니다.  
  
-   호출 된 `CanUpdate` 멤버 함수를 결정 하는 경우 테이블의 필드 정의 편집할 수 있습니다.  
  
-   Get 또는 set 사용 하 여 유효성 검사 상태는 `GetValidationRule` 및 `SetValidationRule`, 및 `GetValidationText` 및 `SetValidationText` 멤버 함수입니다.  
  
-   사용 하 여는 **열려** 멤버 함수는 테이블 수준, 다이너셋 또는 스냅숏 형식 만들기를 `CDaoRecordset` 개체입니다.  
  
    > [!NOTE]
    >  DAO 데이터베이스 클래스에 ODBC Open Database Connectivity ()를 기반으로 하는 MFC 데이터베이스 클래스와 다릅니다. 모든 DAO 데이터베이스 클래스 이름이 "CDao" 접두사가 있습니다. 여전히 DAO 클래스; ODBC 데이터 원본에 액세스할 수 있습니다. DAO 클래스 Microsoft Jet 데이터베이스 엔진에 특정 때문에 일반적으로 뛰어난 기능을 제공 합니다.  
  
### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>기존 테이블을 사용 하거나 새 테이블을 만들려면 테이블 정의 개체를 사용 하려면  
  
1.  모든 경우에서 먼저 작성 한 `CDaoTableDef` 에 대 한 포인터를 제공 하는 개체는 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 테이블이 속해 있는 개체입니다.  
  
2.  대상에 따라 다음을 수행 합니다.  
  
    -   기존 테이블을 저장을 사용 하려면 테이블 정의 개체의 호출 [열려](#open) 멤버 함수, 저장 된 테이블의 이름을 제공 합니다.  
  
    -   새 테이블을 만들려면 테이블 정의 개체의 호출 [만들기](#create) 멤버 함수를 테이블의 이름을 제공 합니다. 호출 [CreateField](#createfield) 및 [CreateIndex](#createindex) 테이블에 필드와 인덱스를 추가 합니다.  
  
    -   호출 [Append](#append) 데이터베이스의 TableDefs 컬렉션에 추가 하 여 테이블을 저장 합니다. **만들기** 열린 상태에 테이블 정의 저장 하므로 호출한 후 **만들기** 호출 하지 않으면 **열**합니다.  
  
        > [!TIP]
        >  저장 된 테이블을 만드는 가장 쉬운 방법은 만들고 Microsoft Access를 사용 하 여 데이터베이스에 저장 하는 합니다. 그런 다음 수를 열고 MFC 코드에서 사용 합니다.  
  
 열거나 만든 테이블 정의 개체를 사용 하려면 만들고 엽니다는 `CDaoRecordset` 개체와 테이블 정의의 이름을 지정 하는 **dbOpenTable** 값에 `nOpenType` 매개 변수입니다.  
  
 테이블 정의 개체를 만드는 데는 `CDaoRecordset` 개체를 일반적으로 만든 또는 위에 설명 된 대로 테이블 정의 열고 다음 생성 recordset 개체를 호출 하는 경우 테이블 정의 개체에 대 한 포인터를 전달 [cdaorecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open)합니다. 전달 tabledef 열린 상태에 있어야 합니다. 자세한 내용은 클래스를 참조 하십시오. [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)합니다.  
  
 호출 작업을 마치면 tabledef 개체를 사용 하 여 해당 [닫기](../../mfc/reference/cdaorecordset-class.md#close) 멤버 함수를 테이블 정의 개체를 삭제 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoTableDef`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
##  <a name="append"></a>CDaoTableDef::Append  
 이 함수를 호출한 후 호출 [만들기](#create) 데이터베이스의 테이블 정의 저장 하려면 새 테이블 정의 개체를 만듭니다.  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>설명  
 함수는 데이터베이스의 TableDefs 컬렉션에 개체를 추가합니다. 하지 추가 하 여 정의 하는 동안 임시 개체로 테이블 정의 사용할 수 있지만 호출 해야 합니다 저장 하 고 사용 하려는 경우 **Append**합니다.  
  
> [!NOTE]
>  (Null 또는 빈 문자열로 포함)는 명명 되지 않은 테이블 정의 추가 하려는 경우 MFC는 예외가 throw 됩니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "추가 방법" 항목을 참조 합니다.  
  
##  <a name="canupdate"></a>CDaoTableDef::CanUpdate  
 확인 하려면이 함수를 호출 하는지 여부를 내부 테이블의 정의 `CDaoTableDef` 개체를 변경할 수 있습니다.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>반환 값  
 테이블 구조 (스키마)를 수정할 수 있는 경우 0이 아닌 (추가 또는 필드와 인덱스를 삭제), 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 기본 새로 만든된 테이블은 `CDaoTableDef` 개체, 업데이트 및 연결 된 테이블의 기본 프로그램는 `CDaoTableDef` 개체를 업데이트할 수 없습니다. A `CDaoTableDef` 결과 레코드 집합을 업데이트할 수 없는 경우에 개체를 업데이트할 수 있습니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "업데이트할 수 있는 Property" 항목을 참조 합니다.  
  
##  <a name="cdaotabledef"></a>CDaoTableDef::CDaoTableDef  
 생성 된 **CDaoTableDef** 개체입니다.  
  
```  
CDaoTableDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDatabase`  
 에 대 한 포인터는 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 개체를 생성 한 후의 [만들기](#create) 또는 [열려](#open) 멤버 함수입니다. 호출 해야 개체를 마치면 해당 [닫기](#close) 멤버 함수를 파괴는 `CDaoTableDef` 개체입니다.  
  
##  <a name="close"></a>CDaoTableDef::Close  
 닫고 테이블 정의 개체를 해제 하려면이 함수를 호출 합니다.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>설명  
 일반적으로 호출한 후 **닫기**, 할당 된 경우 테이블 정의 개체를 삭제 하면 **새**합니다.  
  
 호출할 수 있습니다 [열려](#open) 호출 후에 다시 **닫기**합니다. 이렇게 하면 테이블 정의 개체를 다시 사용할 수 있습니다.  
  
 관련된 정보에 대 한 "Close 메서드" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="create"></a>CDaoTableDef::Create  
 이 저장 된 새 테이블을 만드는 함수를 호출 합니다.  
  
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
 에 해당 하는 테이블 정의 개체로 표현 되는 테이블의 특성 값입니다. 다음 상수 중 하나를 결합 하는 비트 OR을 사용할 수 있습니다.  
  
|상수|설명|  
|--------------|-----------------|  
|**dbAttachExclusive**|Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스, 테이블은 배타적으로 사용에 대 한 열린 연결된 된 테이블을 나타냅니다.|  
|**dbAttachSavePWD**|Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스, 사용자 ID와 연결 된 테이블에 대 한 암호는 연결 정보가 저장 됩니다를 나타냅니다.|  
|**dbSystemObject**|테이블은 Microsoft Jet 데이터베이스 엔진에서 제공 하는 시스템 테이블을 나타냅니다.|  
|**dbHiddenObject**|테이블은 Microsoft Jet 데이터베이스 엔진에서 제공 하는 숨겨진된 테이블을 나타냅니다.|  
  
 *lpszSrcTable*  
 원본 테이블 이름을 포함 하는 문자열에 대 한 포인터입니다. 기본적으로이 값으로 초기화 됩니다 **NULL**합니다.  
  
 `lpszConnect`  
 기본 연결 문자열을 포함 하는 문자열에 대 한 포인터입니다. 기본적으로이 값으로 초기화 됩니다 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 테이블 정의 지정한 후 호출할 수 있습니다 [Append](#append) 데이터베이스의 TableDefs 컬렉션에 테이블 정의 저장 합니다. 호출한 후 **Append**열린 상태에서 테이블 정의 되며 만드는 데 사용할 수는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체입니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "CreateTableDef Method" 항목을 참조 합니다.  
  
##  <a name="createfield"></a>CDaoTableDef::CreateField  
 테이블에 필드를 추가 하려면이 함수를 호출 합니다.  
  
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
|**dbCurrency**|8|통화 ( [COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|float|  
|**dbDouble**|8|double|  
|**dbDate**|8|날짜/시간 ( [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 - 255|텍스트 ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|긴 이진 (OLE 개체), [CLongBinary](../../mfc/reference/clongbinary-class.md) 또는 [CByteArray](../../mfc/reference/cbytearray-class.md)|  
|**dbMemo**|0|메모 ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
  
 `lSize`  
 최대 크기 (바이트)의 텍스트를 포함 하는 필드 또는 텍스트 또는 숫자 값을 포함 하는 필드의 고정된 크기를 나타내는 값입니다. `lSize` 텍스트 필드를 제외한 모든 매개 변수는 무시 됩니다.  
  
 `lAttributes`  
 비트 OR를 사용 하 여 해당 하는 필드의 특성 값을 결합할 수 있습니다.  
  
|상수|설명|  
|--------------|-----------------|  
|**dbFixedField**|필드 크기 (숫자 필드에 대 한 기본값)를 고정 됩니다.|  
|**dbVariableField**|필드 크기는 변수 (텍스트 필드에만 해당).|  
|**dbAutoIncrField**|고유한 정수 (long) 변경할 수 없는 새 레코드에 대 한 필드 값 자동으로 증가 합니다. Microsoft Jet 데이터베이스 테이블에 대해서만 지원 합니다.|  
|**dbUpdatableField**|필드 값을 변경할 수 있습니다.|  
|**dbDescending**|필드는 필드를 내림차순으로 정렬 됩니다 (A-Z 또는 100-0) 순서 (Index 개체의 필드 컬렉션의 필드 개체에만 적용 됨). 이 상수를 생략 하면 필드를 오름차순으로 정렬 됩니다 (A-Z 또는 0-100) 순서 (기본값).|  
  
 `fieldinfo`  
 에 대 한 참조는 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조입니다.  
  
### <a name="remarks"></a>설명  
 A **DAOField** (OLE) 개체가 생성 되 고의 Fields 컬렉션에 추가 된 **DAOTableDef** (OLE) 개체입니다. 개체 속성을 검사 하기 위한 용도 외에도 사용할 수도 있습니다 `CDaoFieldInfo` 테이블 정의에서 새 필드를 만들기 위한 입력된 매개 변수를 생성 합니다. 첫 번째 버전 `CreateField` 를 사용 하는 더 간단 하지만 두 번째 버전의 더욱 세밀 하 게 제어 하려는 경우 사용할 수 있습니다 `CreateField`,이 `CDaoFieldInfo` 매개 변수입니다.  
  
 버전을 사용 하는 경우 `CreateField` 를 사용 하는 `CDaoFieldInfo` 매개 변수를 신중 하 게 설정 해야 각각의 다음 멤버는 `CDaoFieldInfo` 구조:  
  
- **m_strName**  
  
- `m_nType`  
  
- **m_lSize**  
  
- **m_lAttributes**  
  
- **m_bAllowZeroLength**  
  
 나머지 멤버 `CDaoFieldInfo` 로 설정 해야 **0**, **FALSE**, 또는 빈 문자열인 경우는 멤버를 적절 하 게 또는 `CDaoException` 발생할 수 있습니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "CreateField 메서드" 항목을 참조 합니다.  
  
##  <a name="createindex"></a>CDaoTableDef::CreateIndex  
 테이블에 인덱스를 추가 하려면이 함수를 호출 합니다.  
  
```  
void CreateIndex(CDaoIndexInfo& indexinfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `indexinfo`  
 에 대 한 참조는 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조입니다.  
  
### <a name="remarks"></a>설명  
 인덱스는 중복 레코드가 허용 되는지 여부 및 데이터베이스 테이블에서 액세스 하는 레코드의 순서를 지정 합니다. 또한 인덱스 데이터에 효율적으로 액세스를 제공합니다.  
  
 테이블에 대 한 인덱스를 만들 필요는 없지만 크고 인덱싱되지 않은 테이블에서 특정 레코드에 액세스 하거나 레코드 집합 만들기 오래 걸릴 수 있습니다는 합니다. 반면에 너무 많은 인덱스를 만드는 느려집니다 업데이트, 추가 및 삭제 작업 모든 인덱스를 자동으로 업데이트 합니다. 만들 인덱스를 결정할 때 이러한 요소를 고려 합니다.  
  
 다음 멤버는 `CDaoIndexInfo` 구조를 설정 해야 합니다.  
  
- **m_strName** 이름을 제공 해야 합니다.  
  
- `m_pFieldInfos`배열을 가리켜야 `CDaoIndexFieldInfo` 구조입니다.  
  
- `m_nFields`배열에 있는 필드 수를 지정 해야 `CDaoFieldInfo` 구조입니다.  
  
 멤버 남아 있는 경우 무시로 설정 됩니다 **FALSE**합니다. 또한는 **m_lDistinctCount** 멤버의 인덱스를 만드는 동안 무시 됩니다.  
  
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
 테이블의 0부터 시작 필드 컬렉션의 인덱스로 조회에 대 한 필드의 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수를 사용 하 여 데이터베이스에 추가 되지에 새 개체에 되거나 [CanUpdate](#canupdate) 0이 아닌 값을 반환 합니다.  
  
 관련된 정보에 대 한 "Delete 메서드" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="deleteindex"></a>CDaoTableDef::DeleteIndex  
 원본 테이블에 인덱스를 삭제 하려면이 함수를 호출 합니다.  
  
```  
void DeleteIndex(LPCTSTR lpszName);  
void DeleteIndex(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 기존 인덱스의 이름에 해당 하는 문자열 식에 대 한 포인터입니다.  
  
 `nIndex`  
 데이터베이스의 0부터 시작 TableDefs 컬렉션에서 인덱스에 의해 조회에 대 한 인덱스 개체의 배열 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수를 사용 하 여 데이터베이스에 아직 추가 되지 하는 새 개체에 되거나 [CanUpdate](#canupdate) 0이 아닌 값을 반환 합니다.  
  
 관련된 정보에 대 한 "Delete 메서드" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="getattributes"></a>CDaoTableDef::GetAttributes  
 에 대 한는 `CDaoTableDef` 개체를 반환 값으로 표시 된 테이블의 특성을 지정는 `CDaoTableDef` 개체와 이러한 상수 중 합계만 될 수 있습니다.  
  
```  
long GetAttributes();
```  
  
### <a name="return-value"></a>반환 값  
 하나 이상의 특성을 나타내는 값을 반환는 `CDaoTableDef` 개체입니다.  
  
### <a name="remarks"></a>설명  
  
|상수|설명|  
|--------------|-----------------|  
|**dbAttachExclusive**|Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스, 테이블은 배타적으로 사용에 대 한 열린 연결된 된 테이블을 나타냅니다.|  
|**dbAttachSavePWD**|Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스, 사용자 ID와 연결 된 테이블에 대 한 암호는 연결 정보가 저장 됩니다를 나타냅니다.|  
|**dbSystemObject**|테이블은 Microsoft Jet 데이터베이스 엔진에서 제공 하는 시스템 테이블을 나타냅니다.|  
|**dbHiddenObject**|테이블은 Microsoft Jet 데이터베이스 엔진에서 제공 하는 숨겨진된 테이블을 나타냅니다.|  
|**dbAttachedTable**|테이블은 연결된 Paradox 데이터베이스와 같은 비 ODBC 데이터베이스에서 테이블을 나타냅니다.|  
|**dbAttachedODBC**|테이블은 Microsoft SQL Server 등의 ODBC 데이터베이스에서 연결 된 테이블을 나타냅니다.|  
  
 시스템 테이블은 다양 한 내부 정보를 포함 하도록 Microsoft Jet 데이터베이스 엔진에 의해 생성 된 테이블.  
  
 숨겨진된 테이블은 처럼 임시로 사용에 대 한 Microsoft Jet 데이터베이스 엔진에 의해 생성 된 테이블.  
  
 관련된 정보에 대 한 DAO 도움말의 "특성 Property" 항목을 참조 합니다.  
  
##  <a name="getconnect"></a>CDaoTableDef::GetConnect  
 데이터 원본에 대 한 연결 문자열을 가져오려면이 함수를 호출 합니다.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 테이블에 대 한 경로 및 데이터베이스 형식을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 에 대 한는 `CDaoTableDef` 연결된 된 테이블을 나타내는 개체의 `CString` 개체 (데이터베이스 형식 지정자 및 데이터베이스에 대 한 경로) 하나 또는 두 개의 부분으로 구성 됩니다.  
  
 아래 표에 나와 있는 것 처럼 데이터베이스 파일이 있는 디렉터리에 대 한 전체 경로 이며 식별자 뒤에 야 "데이터베이스 =". 경우에 따라 (데이터베이스로 Microsoft Excel 및 Microsoft Jet) 데이터베이스 path 인수에 특정 파일 이름을 포함 됩니다.  
  
 테이블 [CDaoTableDef::SetConnect](#setconnect) 가능한 데이터베이스 형식과 데이터베이스 지정자 및 경로 보여 줍니다.  
  
 Microsoft Jet 데이터베이스 기본 테이블에 지정자는 빈 문자열 ("").  
  
 ODBC 드라이버는 테이블을 액세스 하는 로그인 대화 상자는 첫 번째 시간 표시 필요한 암호가 제공 되지 않은, 다시 연결을 닫고 다시 하는 경우. 연결 된 테이블에는 **dbAttachSavePWD** 특성에 테이블 다시 열 때 로그인 프롬프트가 표시 되지 것입니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "연결 Property" 항목을 참조 합니다.  
  
##  <a name="getdatecreated"></a>CDaoTableDef::GetDateCreated  
 내부 테이블에 날짜와 시간을 확인 하려면이 함수를 호출는 `CDaoTableDef` 개체가 생성 되었습니다.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>반환 값  
 내부 테이블 만들기의 시간과 날짜를 포함 하는 값은 `CDaoTableDef` 개체입니다.  
  
### <a name="remarks"></a>설명  
 날짜 및 시간 설정에 기본 테이블을 만들거나 마지막으로 업데이트 하는 컴퓨터에서 파생 됩니다. 다중 사용자 환경에서 사용자가 얻어야 이러한 설정을; 불일치를 방지 하기 위해 파일 서버에서 직접 즉, 모든 클라이언트 "standard" 시간 원본을 사용할지-에서 서버 하나.  
  
 관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.  
  
##  <a name="getdatelastupdated"></a>CDaoTableDef::GetDateLastUpdated  
 내부 테이블에 날짜와 시간을 확인 하려면이 함수를 호출는 **CDaoTableDef** 개체가 마지막으로 업데이트 합니다.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>반환 값  
 기본 테이블의 날짜 및 시간 포함 하는 값은 **CDaoTableDef** 개체가 마지막으로 업데이트 합니다.  
  
### <a name="remarks"></a>설명  
 날짜 및 시간 설정에 기본 테이블을 만들거나 마지막으로 업데이트 하는 컴퓨터에서 파생 됩니다. 다중 사용자 환경에서 사용자가 얻어야 이러한 설정을; 불일치를 방지 하기 위해 파일 서버에서 직접 즉, 모든 클라이언트 "standard" 시간 원본을 사용할지-에서 서버 하나.  
  
 관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.  
  
##  <a name="getfieldcount"></a>CDaoTableDef::GetFieldCount  
 테이블에 정의 된 필드 수를 검색 하려면이 함수를 호출 합니다.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>반환 값  
 테이블의 필드 개수입니다.  
  
### <a name="remarks"></a>설명  
 해당 값이 0 이면 개체가 없는 컬렉션에 있습니다.  
  
 관련된 정보에 대 한 항목 DAO 도움말의 "Count 속성"을 참조 합니다.  
  
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
 테이블의 0부터 시작 필드 컬렉션의 인덱스로 조회에 대 한 필드 개체의 인덱스입니다.  
  
 `fieldinfo`  
 에 대 한 참조는 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조입니다.  
  
 `dwInfoOptions`  
 검색할 필드에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 함께 반환 하는 함수를 입히기 무엇 여기 나열 됩니다.  
  
- `AFX_DAO_PRIMARY_INFO`(기본값) 특성 이름, 유형, 크기입니다. 이 옵션을 사용 하 여 빠른 성능을 합니다.  
  
- `AFX_DAO_SECONDARY_INFO`기본 정보, 플러스: 서 수 위치에 필요한 길이, 데이터 정렬 순서, 외부 이름, 원본 필드, 원본 테이블 0 허용  
  
- `AFX_DAO_ALL_INFO`기본 및 보조 정보 플러스: Default Value 유효성 검사 규칙을 유효성 검사 텍스트  
  
 `lpszName`  
 이름별으로 조회에 대 한 필드 개체의 이름에 대 한 포인터입니다. 이름은 최대 64 자 필드의 이름을 고유 하 게 지정 하는 문자열입니다.  
  
### <a name="remarks"></a>설명  
 한 버전의 함수를 사용 하면 인덱스 필드를 찾을 수 있습니다. 다른 버전 필드 이름으로 조회할 수 있습니다.  
  
 반환 되는 정보에 대 한 참조는 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조입니다. 이 구조에는 항목의 설명에 위에 나열 된 정보에 해당 하는 멤버가 `dwInfoOptions`합니다. 한 수준에서 정보를 요청할 때 모든 상위 수준의에 대 한 정보를 가져옵니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "특성 Property" 항목을 참조 합니다.  
  
##  <a name="getindexcount"></a>CDaoTableDef::GetIndexCount  
 이 멤버 함수는 테이블에 대 한 인덱스 번호를 가져올를 호출 합니다.  
  
```  
short GetIndexCount();
```  
  
### <a name="return-value"></a>반환 값  
 테이블에 대 한 인덱스 수입니다.  
  
### <a name="remarks"></a>설명  
 해당 값이 0 이면 이면 컬렉션에 인덱스가 없는 합니다.  
  
 관련된 정보에 대 한 항목 DAO 도움말의 "Count 속성"을 참조 합니다.  
  
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
 테이블의 0부터 시작 인덱스가 컬렉션의 컬렉션에서 해당 위치에 따라 조회에 대 한 인덱스 개체의 숫자 인덱스입니다.  
  
 `indexinfo`  
 에 대 한 참조는 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조입니다.  
  
 `dwInfoOptions`  
 인덱스를 검색 하는 방법에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 함께 반환 하는 함수를 입히기 무엇 여기 나열 됩니다.  
  
- `AFX_DAO_PRIMARY_INFO`필드 이름, 필드 정보입니다. 이 옵션을 사용 하 여 빠른 성능을 합니다.  
  
- `AFX_DAO_SECONDARY_INFO`기본 정보, 플러스: 주, Unique, 클러스터형, 무시 Null, 필수, 외부  
  
- `AFX_DAO_ALL_INFO`기본 및 보조 정보 플러스: 고유 카운트  
  
 `lpszName`  
 이름별으로 조회에 대 한 인덱스 개체의 이름에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 한 버전의 함수를 사용 하면 컬렉션에서 해당 위치에 따라 인덱스를 조회할 수 있습니다. 다른 버전 이름으로 인덱스를 조회할 수 있습니다.  
  
 반환 되는 정보에 대 한 참조는 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조입니다. 이 구조에는 항목의 설명에 위에 나열 된 정보에 해당 하는 멤버가 `dwInfoOptions`합니다. 한 수준에서 정보를 요청할 때 모든 상위 수준의에 대 한 정보를 가져옵니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "특성 Property" 항목을 참조 합니다.  
  
##  <a name="getname"></a>CDaoTableDef::GetName  
 기본 테이블의 사용자 정의 이름을 가져오려면이 함수를 호출 합니다.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>반환 값  
 테이블에 대 한 사용자 정의 이름입니다.  
  
### <a name="remarks"></a>설명  
 이 이름은 문자로 시작 하 고 최대 64 자까지 포함할 수 있습니다. 숫자를 포함할 수 있습니다 및 밑줄 문자는 문장 부호 또는 공백을 포함할 수 없습니다.  
  
 관련된 정보에 대 한 항목 DAO 도움말의 "Name 속성"을 참조 합니다.  
  
##  <a name="getrecordcount"></a>CDaoTableDef::GetRecordCount  
 호출에 있는 레코드 수를 확인 하려면이 함수는 `CDaoTableDef` 개체입니다.  
  
```  
long GetRecordCount();
```  
  
### <a name="return-value"></a>반환 값  
 테이블 정의 개체에 액세스 하는 레코드의 수입니다.  
  
### <a name="remarks"></a>설명  
 호출 `GetRecordCount` 테이블 형식에 대 한 `CDaoTableDef` 개체 테이블에 있는 레코드의 대략적인 수를 반영 되어 있으며는 영향을 받는 즉시 테이블 레코드 추가 및 삭제 합니다. 호출할 때까지 트랜잭션 레코드 수의 일부로 나타납니다 롤백 [CDaoWorkSpace::CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase)합니다. A `CDaoTableDef` 레코드가 없는 개체에는 레코드 수 속성이 0으로 설정 합니다. ODBC 데이터베이스 또는 연결 된 테이블을 작업할 때 `GetRecordCount` 항상-1을 반환 합니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "RecordCount Property" 항목을 참조 합니다.  
  
##  <a name="getsourcetablename"></a>CDaoTableDef::GetSourceTableName  
 원본 데이터베이스에 연결된 된 테이블의 이름을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetSourceTableName();
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 네이티브 데이터 테이블이 있는 경우 연결된 된 테이블 또는 빈 문자열의 소스 이름을 지정 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 연결된 된 테이블은 Microsoft Jet 데이터베이스에 연결 하는 다른 데이터베이스의 테이블입니다. 연결 된 테이블에 대 한 데이터는 다른 응용 프로그램에서 조작할 수 있는 외부 데이터베이스에 남아 있습니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "속성은" 항목을 참조 합니다.  
  
##  <a name="getvalidationrule"></a>CDaoTableDef::GetValidationRule  
 테이블 정의 대 한 유효성 검사 규칙을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetValidationRule();
```  
  
### <a name="return-value"></a>반환 값  
 A **CString** 가 변경 되거나 테이블에 추가 되는 필드의 데이터 유효성을 검사 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 업데이트 작업으로 연결 된 유효성 검사 규칙이 사용 됩니다. 유효성 검사 규칙을 포함 하는 테이블 정의 데이터를 변경 하기 전에 해당 테이블 정의에 대 한 업데이트는 미리 결정 된 조건 일치 해야 합니다. 변경 된 조건 값을 포함 하는 예외 일치 하지 않는 경우 [GetValidationText](#getvalidationtext) throw 됩니다. 에 대 한는 `CDaoTableDef` 개체를이 `CString` 연결 된 테이블과 기본 테이블에 대 한 읽기/쓰기에 대 한 읽기 전용입니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "ValidationRule Property" 항목을 참조 합니다.  
  
##  <a name="getvalidationtext"></a>CDaoTableDef::GetValidationText  
 유효성 검사 규칙을 일치 하지 않는 데이터를 입력 하는 경우 표시할 문자열을 검색 하려면이 함수를 호출 합니다.  
  
```  
CString GetValidationText();
```  
  
### <a name="return-value"></a>반환 값  
 A `CString` 유효성 검사 규칙을 일치 하지 않는 데이터를 입력할 경우 표시할 텍스트를 지정 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 에 대 한는 `CDaoTableDef` 개체를이 `CString` 연결 된 테이블과 기본 테이블에 대 한 읽기/쓰기에 대 한 읽기 전용입니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "유효성 검사 텍스트 Property" 항목을 참조 합니다.  
  
##  <a name="isopen"></a>CDaoTableDef::IsOpen  
 확인 하려면이 함수를 호출 여부는 `CDaoTableDef` 개체가 현재 열려 있습니다.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우에는 `CDaoTableDef` 개체가 열려 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="m_pdatabase"></a>CDaoTableDef::m_pDatabase  
 에 대 한 포인터는 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 이 테이블에 대 한 개체입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="m_pdaotabledef"></a>CDaoTableDef::m_pDAOTableDef  
 DAO tabledef 개체 내부에 대 한 OLE 인터페이스에 대 한 포인터는 `CDaoTableDef` 개체입니다.  
  
### <a name="remarks"></a>설명  
 DAO 인터페이스를 직접 액세스 해야 할 경우이 포인터를 사용 합니다.  
  
##  <a name="open"></a>CDaoTableDef::Open  
 데이터베이스에 이전에 저장 된 테이블 정의 열려면이 멤버 함수 호출의 테이블 정의 컬렉션입니다.  
  
```  
virtual void Open(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 테이블 이름을 지정 하는 문자열에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="refreshlink"></a>CDaoTableDef::RefreshLink  
 연결된 된 테이블에 대 한 연결 정보를 업데이트 하려면이 멤버 함수를 호출 합니다.  
  
```  
void RefreshLink();
```  
  
### <a name="remarks"></a>설명  
 호출 하 여 연결된 된 테이블에 대 한 연결 정보를 변경할 [SetConnect](#setconnect) 해당 `CDaoTableDef` 개체를 사용 하는 `RefreshLink` 멤버 함수 정보를 업데이트 합니다. 호출 하는 경우 `RefreshLink`, 연결 된 테이블의 속성은 변경 되지 않습니다.  
  
 강제로 수정 된 연결 정보를 적용 하려면 열려 있는 모든 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 이 테이블 정의에 따라 개체를 닫아야 합니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "RefreshLink Method" 항목을 참조 합니다.  
  
##  <a name="setattributes"></a>CDaoTableDef::SetAttributes  
 하나 이상의 특성을 나타내는 값을 설정 하는 `CDaoTableDef` 개체입니다.  
  
```  
void SetAttributes(long lAttributes);
```  
  
### <a name="parameters"></a>매개 변수  
 `lAttributes`  
 로 표시 된 테이블의 특성은 `CDaoTableDef` 개체와 이러한 상수 중 합계만 될 수 있습니다.  
  
|상수|설명|  
|--------------|-----------------|  
|**dbAttachExclusive**|Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스, 테이블은 배타적으로 사용에 대 한 열린 연결된 된 테이블을 나타냅니다.|  
|**dbAttachSavePWD**|Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스, 사용자 ID와 연결 된 테이블에 대 한 암호는 연결 정보가 저장 됩니다를 나타냅니다.|  
|**dbSystemObject**|테이블은 Microsoft Jet 데이터베이스 엔진에서 제공 하는 시스템 테이블을 나타냅니다.|  
|**dbHiddenObject**|테이블은 Microsoft Jet 데이터베이스 엔진에서 제공 하는 숨겨진된 테이블을 나타냅니다.|  
  
### <a name="remarks"></a>설명  
 여러 특성을 설정할 때 비트 OR 연산자를 사용 하 여 적절 한 상수를 합하여 결합할 수 있습니다. 설정 **dbAttachExclusive** 연결 되지 않은 테이블에 예외를 생성 합니다. 다음 값을 결합 하는 예외 생성을도:  
  
- **dbAttachExclusive &#124; dbAttachedODBC**  
  
- **dbAttachSavePWD &#124; dbAttachedTable**  
  
 관련된 정보에 대 한 DAO 도움말의 "특성 Property" 항목을 참조 합니다.  
  
##  <a name="setconnect"></a>CDaoTableDef::SetConnect  
 에 대 한는 `CDaoTableDef` 있는 문자열 개체가 추가 된 테이블을 나타내는 개체 (데이터베이스 형식 지정자 및 데이터베이스에 대 한 경로) 하나 또는 두 개의 부분으로 구성 됩니다.  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszConnect`  
 ODBC 또는 설치 가능한 ISAM 드라이버에 전달할 추가 매개 변수를 지정 하는 문자열 식에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 아래 표에 나와 있는 것 처럼 데이터베이스 파일이 있는 디렉터리에 대 한 전체 경로 이며 식별자 뒤에 야 "데이터베이스 =". 경우에 따라 (데이터베이스로 Microsoft Excel 및 Microsoft Jet) 데이터베이스 path 인수에 특정 파일 이름을 포함 됩니다.  
  
> [!NOTE]
>  경로 문의 폼의 등호 주위에 공백을 넣지 마십시오 "데이터베이스 = 드라이브:\\\path"입니다. 이렇게 하면 예외가 throw 되 고 연결 실패 합니다.  
  
 다음 표에서 가능한 데이터베이스 형식과 데이터베이스 지정자 및 경로 보여 줍니다.  
  
|데이터베이스 유형|지정자|Path|  
|-------------------|---------------|----------|  
|Jet 데이터베이스 엔진을 사용 하 여 데이터베이스|"[ `database`];"|" `drive`:\\\ *경로*\\\ *filename*합니다. MDB "|  
|dBASE III|"dBASE III;"|" `drive`:\\\ *경로*"|  
|dBASE IV|"dBASE IV;"|" `drive`:\\\ *경로*"|  
|dBASE 5|"dBASE 5.0;"|" `drive`:\\\ *경로*"|  
|Paradox 3.x|"Paradox 3.x;"|" `drive`:\\\ *경로*"|  
|Paradox 4.x|"Paradox 4.x;"|" `drive`:\\\ *경로*"|  
|Paradox 5.x|"Paradox 5.x;"|" `drive`:\\\ *경로*"|  
|Excel 3.0|"Excel 3.0;"|" `drive`:\\\ *경로*\\\ *filename*합니다. XLS "|  
|Excel 4.0|"Excel 4.0;"|" `drive`:\\\ *경로*\\\ *filename*합니다. XLS "|  
|5.0 Excel 또는 Excel 95|"Excel 5.0;"|" `drive`:\\\ *경로*\\\ *filename*합니다. XLS "|  
|Excel 97|"Excel 8.0;"|" `drive`:\\\ *경로*\ *filename*합니다. XLS "|  
|HTML 가져오기|"HTML 가져오기;"|" `drive`:\\\ *경로*\ *filename*"|  
|HTML 내보내기|"HTML 내보내기;"|" `drive`:\\\ *경로*"|  
|텍스트|"Text";|"드라이브:\\\path"|  
|ODBC|"ODBC; 데이터베이스 = `database`; UID = *사용자*; PWD = *암호*; DSN = *datasourcename;* LOGINTIMEOUT = *; 초여야*" (모든 서버에 대 한 전체 연결 문자열 아닐 수 있습니다;는 단지 예 이 매개 변수 사이 공백이 하에 매우 중요 합니다.)|없음|  
|Exchange|"Exchange;<br /><br /> MAPILEVEL = *folderpath*;<br /><br /> [TABLETYPE = {0 &#124; 1을 (를);]<br /><br /> [프로필 = *프로필*;]<br /><br /> [PWD = *암호*;]<br /><br /> [데이터베이스 = `database`;] "|*"드라이브*:\\\ *경로*\\\ *filename*합니다. MDB "|  
  
> [!NOTE]
>  DAO 3.5부터 더 이상 Btrieve 사용할 수 없습니다.  
  
 이중 백슬래시를 사용 해야 합니다 (\\\\) 연결 문자열에 있습니다. 사용 하 여 기존 연결의 속성을 수정한 경우 `SetConnect`, 호출 이후에 해야 [RefreshLink](#refreshlink)합니다. 사용 하 여 연결 속성을 초기화 하는 경우 `SetConnect`, 하지 호출 해야 `RefreshLink`, 하지만 테이블 정의 추가할 먼저 이렇게 하도록 선택 해야 합니다.  
  
 ODBC 드라이버는 테이블을 액세스 하는 로그인 대화 상자는 첫 번째 시간 표시 필요한 암호가 제공 되지 않은, 다시 연결을 닫고 다시 하는 경우.  
  
 에 대 한 연결 문자열을 설정할 수 있습니다는 `CDaoTableDef` 개체에 대 한 소스 인수를 제공 하는 **만들기** 멤버 함수입니다. 유형, 경로, 사용자 ID, 암호 또는 ODBC 데이터 원본 데이터베이스의 확인 하려면 설정을 확인할 수 있습니다. 자세한 내용은 특정 드라이버에 대 한 설명서를 참조 하십시오.  
  
 관련된 정보에 대 한 DAO 도움말의 "연결 Property" 항목을 참조 합니다.  
  
##  <a name="setname"></a>CDaoTableDef::SetName  
 테이블에 대 한 사용자 정의 이름을 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 테이블에 대 한 이름을 지정 하는 문자열 식에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이름은 문자로 시작 해야 하며 최대 64 자까지 포함할 수 있습니다. 숫자를 포함할 수 있습니다 및 밑줄 문자는 문장 부호 또는 공백을 포함할 수 없습니다.  
  
 관련된 정보에 대 한 항목 DAO 도움말의 "Name 속성"을 참조 합니다.  
  
##  <a name="setsourcetablename"></a>CDaoTableDef::SetSourceTableName  
 에 추가 된 테이블의 이름 또는 기본 테이블의 이름을 지정 하려면이 함수를 호출는 `CDaoTableDef` 데이터의 원본 소스에 있는 개체를 기초로 합니다.  
  
```  
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszSrcTableName*  
 외부 데이터베이스에서 테이블 이름을 지정 하는 문자열 식에 대 한 포인터입니다. 기본 테이블에 대 한 설정을 빈 문자열 ("").  
  
### <a name="remarks"></a>설명  
 다음 호출 해야 [RefreshLink](#refreshlink)합니다. 이 속성 설정은 기본 테이블 및 연결된 된 테이블 또는 컬렉션에 추가 되지 않은 개체에 대 한 읽기/쓰기에 대해 비어 있습니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "속성은" 항목을 참조 합니다.  
  
##  <a name="setvalidationrule"></a>CDaoTableDef::SetValidationRule  
 테이블 정의 대 한 유효성 검사 규칙을 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetValidationRule(LPCTSTR lpszValidationRule);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszValidationRule*  
 작업의 유효성을 검사 하는 문자열 식에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 업데이트 작업으로 연결 된 유효성 검사 규칙이 사용 됩니다. 유효성 검사 규칙을 포함 하는 테이블 정의 데이터를 변경 하기 전에 해당 테이블 정의에 대 한 업데이트는 미리 결정 된 조건 일치 해야 합니다. 변경 된 조건 텍스트를 포함 하는 예외 일치 하지 않는 경우 [GetValidationText](#getvalidationtext) 표시 됩니다.  
  
 유효성 검사는 Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스에 대해서만 지원 됩니다. 사용자 정의 함수, 도메인 집계 함수, SQL 집계 함수 또는 쿼리 식은 참조할 수 없습니다. 에 대 한 유효성 검사 규칙을 `CDaoTableDef` 개체는 해당 개체의 여러 필드를 참조할 수 있습니다.  
  
 명명 된 필드에 대 한 예를 들어 `hire_date` 및 `termination_date`, 유효성 검사 규칙을 만들 수 있습니다.  
  
 [!code-cpp[NVC_MFCDatabase#34](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]  
  
 관련된 정보에 대 한 DAO 도움말의 "ValidationRule Property" 항목을 참조 합니다.  
  
##  <a name="setvalidationtext"></a>CDaoTableDef::SetValidationText  
 에 대 한 유효성 검사 규칙의 예외 텍스트를 설정 하려면이 함수를 호출는 `CDaoTableDef` Microsoft Jet 데이터베이스 엔진에서 지 원하는 기본 테이블에 있는 개체입니다.  
  
```  
void SetValidationText(LPCTSTR lpszValidationText);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszValidationText*  
 데이터를 입력 하는 경우 표시할 텍스트를 지정 하는 문자열 식에 대 한 포인터 올바르지 않습니다.  
  
### <a name="remarks"></a>설명  
 추가 된 테이블의 유효성 검사 텍스트를 설정할 수 없습니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "유효성 검사 텍스트 Property" 항목을 참조 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase 클래스](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset 클래스](../../mfc/reference/cdaorecordset-class.md)
