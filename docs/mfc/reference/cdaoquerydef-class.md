---
title: "CDaoQueryDef 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoQueryDef
- AFXDAO/CDaoQueryDef
- AFXDAO/CDaoQueryDef::CDaoQueryDef
- AFXDAO/CDaoQueryDef::Append
- AFXDAO/CDaoQueryDef::CanUpdate
- AFXDAO/CDaoQueryDef::Close
- AFXDAO/CDaoQueryDef::Create
- AFXDAO/CDaoQueryDef::Execute
- AFXDAO/CDaoQueryDef::GetConnect
- AFXDAO/CDaoQueryDef::GetDateCreated
- AFXDAO/CDaoQueryDef::GetDateLastUpdated
- AFXDAO/CDaoQueryDef::GetFieldCount
- AFXDAO/CDaoQueryDef::GetFieldInfo
- AFXDAO/CDaoQueryDef::GetName
- AFXDAO/CDaoQueryDef::GetODBCTimeout
- AFXDAO/CDaoQueryDef::GetParameterCount
- AFXDAO/CDaoQueryDef::GetParameterInfo
- AFXDAO/CDaoQueryDef::GetParamValue
- AFXDAO/CDaoQueryDef::GetRecordsAffected
- AFXDAO/CDaoQueryDef::GetReturnsRecords
- AFXDAO/CDaoQueryDef::GetSQL
- AFXDAO/CDaoQueryDef::GetType
- AFXDAO/CDaoQueryDef::IsOpen
- AFXDAO/CDaoQueryDef::Open
- AFXDAO/CDaoQueryDef::SetConnect
- AFXDAO/CDaoQueryDef::SetName
- AFXDAO/CDaoQueryDef::SetODBCTimeout
- AFXDAO/CDaoQueryDef::SetParamValue
- AFXDAO/CDaoQueryDef::SetReturnsRecords
- AFXDAO/CDaoQueryDef::SetSQL
- AFXDAO/CDaoQueryDef::m_pDAOQueryDef
- AFXDAO/CDaoQueryDef::m_pDatabase
dev_langs: C++
helpviewer_keywords:
- CDaoQueryDef [MFC], CDaoQueryDef
- CDaoQueryDef [MFC], Append
- CDaoQueryDef [MFC], CanUpdate
- CDaoQueryDef [MFC], Close
- CDaoQueryDef [MFC], Create
- CDaoQueryDef [MFC], Execute
- CDaoQueryDef [MFC], GetConnect
- CDaoQueryDef [MFC], GetDateCreated
- CDaoQueryDef [MFC], GetDateLastUpdated
- CDaoQueryDef [MFC], GetFieldCount
- CDaoQueryDef [MFC], GetFieldInfo
- CDaoQueryDef [MFC], GetName
- CDaoQueryDef [MFC], GetODBCTimeout
- CDaoQueryDef [MFC], GetParameterCount
- CDaoQueryDef [MFC], GetParameterInfo
- CDaoQueryDef [MFC], GetParamValue
- CDaoQueryDef [MFC], GetRecordsAffected
- CDaoQueryDef [MFC], GetReturnsRecords
- CDaoQueryDef [MFC], GetSQL
- CDaoQueryDef [MFC], GetType
- CDaoQueryDef [MFC], IsOpen
- CDaoQueryDef [MFC], Open
- CDaoQueryDef [MFC], SetConnect
- CDaoQueryDef [MFC], SetName
- CDaoQueryDef [MFC], SetODBCTimeout
- CDaoQueryDef [MFC], SetParamValue
- CDaoQueryDef [MFC], SetReturnsRecords
- CDaoQueryDef [MFC], SetSQL
- CDaoQueryDef [MFC], m_pDAOQueryDef
- CDaoQueryDef [MFC], m_pDatabase
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e619cbc049e64c25325ab8327ec6dd9d16e071be
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="cdaoquerydef-class"></a>CDaoQueryDef 클래스
일반적으로 데이터베이스에 저장되는 쿼리 정의 또는 "querydef"를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDaoQueryDef : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoQueryDef::CDaoQueryDef](#cdaoquerydef)|생성 된 **CDaoQueryDef** 개체입니다. 다음 호출 **열려** 또는 **만들기**필요에 따라 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoQueryDef::Append](#append)|에 저장 된 쿼리라고 QueryDefs 컬렉션 데이터베이스의 쿼리 정의 추가합니다.|  
|[CDaoQueryDef::CanUpdate](#canupdate)|쿼리는 데이터베이스를 업데이트할 수 있는 경우 0이 아닌 값을 반환 합니다.|  
|[CDaoQueryDef::Close](#close)|쿼리 정의 개체를 닫습니다. 완료 하면 c + + 개체를 제거 합니다.|  
|[CDaoQueryDef::Create](#create)|기본 DAO querydef 개체를 만듭니다. 쿼리 정의 사용 하 여 임시 쿼리 또는 호출 **Append** 데이터베이스에 저장 합니다.|  
|[CDaoQueryDef::Execute](#execute)|쿼리 정의 개체에 의해 정의 된 쿼리를 실행 합니다.|  
|[CDaoQueryDef::GetConnect](#getconnect)|쿼리 정의와 관련 된 연결 문자열을 반환 합니다. 연결 문자열에는 데이터 원본을 식별 합니다. (SQL에 대 한 통과 쿼리의 고, 그렇지 않으면 빈 문자열입니다.)|  
|[CDaoQueryDef::GetDateCreated](#getdatecreated)|저장된 된 쿼리를 만든 날짜를 반환 합니다.|  
|[CDaoQueryDef::GetDateLastUpdated](#getdatelastupdated)|저장된 된 쿼리를 마지막으로 수정한 날짜를 반환 합니다.|  
|[CDaoQueryDef::GetFieldCount](#getfieldcount)|쿼리 정의에 정의 된 필드 수를 반환 합니다.|  
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|쿼리에 정의 된 지정된 된 필드에 대 한 정보를 반환 합니다.|  
|[CDaoQueryDef::GetName](#getname)|쿼리 정의의 이름을 반환합니다.|  
|[CDaoQueryDef::GetODBCTimeout](#getodbctimeout)|(ODBC 쿼리)에 대 한 ODBC에서 사용 되는 시간 제한 값을 반환 합니다. 쿼리 정의 실행 하면 됩니다. 이 기간을 결정 허용 하기 위해 쿼리 작업을 수행 합니다.|  
|[CDaoQueryDef::GetParameterCount](#getparametercount)|쿼리에 정의 된 매개 변수 개수를 반환 합니다.|  
|[CDaoQueryDef::GetParameterInfo](#getparameterinfo)|쿼리에 지정 된 매개 변수에 대 한 정보를 반환합니다.|  
|[CDaoQueryDef::GetParamValue](#getparamvalue)|쿼리에 지정된 된 매개 변수의 값을 반환합니다.|  
|[CDaoQueryDef::GetRecordsAffected](#getrecordsaffected)|쿼리가 실행의 영향을 받는 레코드 수를 반환 합니다.|  
|[CDaoQueryDef::GetReturnsRecords](#getreturnsrecords)|쿼리 정의에 정의 된 쿼리 레코드를 반환 하는 경우 0이 아닌 값을 반환 합니다.|  
|[CDaoQueryDef::GetSQL](#getsql)|쿼리 정의에 정의 된 쿼리를 지정 하는 SQL 문자열을 반환 합니다.|  
|[CDaoQueryDef::GetType](#gettype)|쿼리 형식을 반환: 삭제, 업데이트, 추가, 테이블 만들기 및 등입니다.|  
|[CDaoQueryDef::IsOpen](#isopen)|쿼리 정의가 열려 있고 실행 될 경우 0이 아닌 값을 반환 합니다.|  
|[CDaoQueryDef::Open](#open)|데이터베이스의 QueryDefs 컬렉션에 저장 된 쿼리는 기존 정의 엽니다.|  
|[CDaoQueryDef::SetConnect](#setconnect)|ODBC 데이터 원본에는 SQL 통과 쿼리의 대 한 연결 문자열을 설정합니다.|  
|[CDaoQueryDef::SetName](#setname)|쿼리 정의 만들 때 사용 중인 이름 바꾸기 저장 된 쿼리의 이름을 설정 합니다.|  
|[CDaoQueryDef::SetODBCTimeout](#setodbctimeout)|사용 되는 ODBC에서 (ODBC 쿼리) 제한 시간 값 설정 쿼리 정의 실행 하면 됩니다.|  
|[CDaoQueryDef::SetParamValue](#setparamvalue)|쿼리에 지정된 된 매개 변수의 값을 설정합니다.|  
|[CDaoQueryDef::SetReturnsRecords](#setreturnsrecords)|쿼리 정의 레코드를 반환 하는지 여부를 지정 합니다. 이 특성을 설정 **TRUE** 는 통과 쿼리를 SQL에만 유효 합니다.|  
|[CDaoQueryDef::SetSQL](#setsql)|쿼리 정의에 정의 된 쿼리를 지정 하는 SQL 문자열을 설정 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoQueryDef::m_pDAOQueryDef](#m_pdaoquerydef)|OLE 인터페이스 기본 DAO querydef 개체에 대 한 포인터입니다.|  
|[CDaoQueryDef::m_pDatabase](#m_pdatabase)|에 대 한 포인터는 `CDaoDatabase` 쿼리 정의 연결 된 개체입니다. 쿼리 정의 또는 데이터베이스에 저장 되어 있습니다.|  
  
## <a name="remarks"></a>설명  
 쿼리 정의 쿼리와 "만든 날짜" 및 "ODBC 시간이 초과 되었습니다." 같은 속성을 설명 하는 SQL 문을 포함 하는 데이터 액세스 개체 저장 하지 않고 임시 쿼리 정의 개체를 만들 수도 있지만 편리-훨씬 더 효율적인-일반적으로 저장 하려면 데이터베이스에서 쿼리를 다시 사용 합니다. A [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체의 저장 된 쿼리 정의 포함 하는 QueryDefs 컬렉션 이라는 컬렉션을 유지 합니다.  
  
> [!NOTE]
>  DAO 데이터베이스 클래스에 ODBC Open Database Connectivity ()를 기반으로 하는 MFC 데이터베이스 클래스와 다릅니다. 모든 DAO 데이터베이스 클래스 이름이 "CDao" 접두사가 있습니다. DAO 클래스의 ODBC 데이터 원본에 액세스할 수 있습니다. 일반적으로 기반으로 DAO MFC 클래스는 ODBC;에 따라 MFC 클래스 보다 더욱 강력한 DAO 기반 클래스를 통해 자신의 데이터베이스 엔진을 통해 ODBC 드라이버를 포함 한 데이터를 액세스할 수 있습니다. 또한 DAO 기반 클래스를 직접 DAO 호출 하지 않고는 클래스를 통해 테이블을 추가 하는 등의 데이터 정의 언어 (DDL) 작업을 지원 합니다.  
  
## <a name="usage"></a>용도  
 쿼리 정의 개체 하거나 쿼리를 저장 된 기존 작업할 하거나 작성 하 여 새 쿼리나 임시 쿼리를 저장:  
  
1.  모든 경우에서 먼저 작성 한 `CDaoQueryDef` 에 대 한 포인터를 제공 하는 개체는 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 쿼리 속해 있는 개체입니다.  
  
2.  대상에 따라 다음을 수행 합니다.  
  
    -   쿼리를 저장 된 기존를 사용 하려면 쿼리 정의 개체의 호출 [열려](#open) 멤버 함수, 저장 된 쿼리의 이름을 제공 합니다.  
  
    -   저장된 된 새 쿼리를 만들려면 쿼리 정의 개체의 호출 [만들기](#create) 멤버 함수를 쿼리 이름을 제공 합니다. 다음 호출 [추가](#append) 데이터베이스의 QueryDefs 컬렉션에 추가 하 여 쿼리를 저장 합니다. **만들기** 열린 상태에 쿼리 정의 저장 하므로 호출한 후 **만들기** 호출 하지 않으면 **열**합니다.  
  
    -   임시 쿼리 정의 만들려면 호출 **만들기**합니다. 쿼리 이름에 대 한 빈 문자열을 전달 합니다. 호출 하지 마십시오 **Append**합니다.  
  
 호출 하는 쿼리 정의 개체를 사용 하 여 완료 하면 해당 [닫기](#close) 멤버 함수를 쿼리 정의 개체를 삭제 합니다.  
  
> [!TIP]
>  저장 된 쿼리를 만드는 가장 쉬운 방법은 만들고 Microsoft Access를 사용 하 여 데이터베이스에 저장 하는 합니다. 그런 다음 수를 열고 MFC 코드에서 사용 합니다.  
  
## <a name="purposes"></a>목적  
 다음과 같은 용도로 중 하나에 대 한 쿼리 정의 개체를 사용할 수 있습니다.  
  
-   만들려면는 `CDaoRecordset` 개체  
  
-   개체를 호출 하려면 **Execute** 직접 실행 쿼리 또는 SQL 통과 쿼리를 실행 하는 멤버 함수  
  
 모든 종류의 쿼리를 선택, 작업, 크로스탭, 삭제, 업데이트를 포함 하 여 쿼리 정의 개체를 사용 하 고, 테이블 만들기, 데이터 정의 SQL 통과, union, 추가 하 고, 한 대량 쿼리 수 있습니다. 쿼리 형식은 SQL 문 제공 하는 내용에 따라 결정 됩니다. 쿼리 형식에 대 한 정보를 참조 하십시오.는 **Execute** 및 [GetType](#gettype) 멤버 함수입니다. 레코드 집합 행을 반환 하는 것에 대 한 일반적으로 사용 되 쿼리, 일반적으로 사용 하 여는 **선택...**  키워드입니다. **실행** 은 대량 작업 중에 가장 많이 사용 합니다. 자세한 내용은 참조 [Execute](#execute) 및 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)합니다.  
  
## <a name="querydefs-and-recordsets"></a>쿼리 정 및 레코드 집합  
 쿼리 정의 개체를 만드는 데는 `CDaoRecordset` 개체를 일반적으로 생성 하거나 위에 설명 된 대로 쿼리 정의 열어야 합니다. 다음 호출 하는 경우 쿼리 정의 개체에 대 한 포인터를 전달 하는 레코드 집합 개체를 작성 [cdaorecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open)합니다. 전달 하면 쿼리 정의 열린 상태에 있어야 합니다. 자세한 내용은 클래스를 참조 하십시오. [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)합니다.  
  
 열린 상태에 있지 않는 (쿼리 정의 대 한 가장 일반적인 사용) 레코드 집합을 만들려면 쿼리 정의 사용할 수 없습니다. 쿼리 정의 호출 하 여 열린 상태에 배치 **열고** 또는 **만들기**합니다.  
  
## <a name="external-databases"></a>외부 데이터베이스  
 쿼리 정의 개체는 외부 데이터베이스 엔진의 네이티브 SQL 언어를 사용 하는 것이 좋습니다. 예를 들어 (Microsoft SQL Server에 사용 됨) 처럼 Transact SQL 쿼리를 만들고 쿼리 정의 개체에 저장할 수 있습니다. Microsoft Jet 데이터베이스 엔진을 기반으로 하지 SQL 쿼리를 사용 해야 할 때 외부 데이터 원본을 가리키는 연결 문자열을 제공 해야 합니다. 유효한 연결 문자열이 포함 된 쿼리는 데이터베이스 엔진을 무시 하 고 처리를 위해 외부 데이터베이스 서버에 직접 쿼리를 전달 합니다.  
  
> [!TIP]
>  ODBC 테이블을 사용 하는 기본 방법은 Microsoft Jet에 연결할 것 (합니다. MDB) 데이터베이스입니다.  
  
 관련된 정보에 대 한 "QueryDef 개체", "QueryDefs 컬렉션" 및 "CdbDatabase 개체" DAO SDK에서 항목을 참조 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoQueryDef`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
##  <a name="append"></a>CDaoQueryDef::Append  
 이 멤버 함수를 호출한 후 호출 [만들기](#create) 새 쿼리 정의 개체를 만듭니다.  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>설명  
 **추가** 데이터베이스의 QueryDefs 컬렉션에 개체를 추가 하 여 쿼리 정의 데이터베이스에 저장 합니다. 추가 하지 않고 임시 개체로 쿼리 정의 사용할 수 있지만 호출 해야 유지 하도록 하려는 경우 **Append**합니다.  
  
 임시 쿼리 정의 개체를 추가 하려는 경우 MFC 형식의 예외를 throw 하는 [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다.  
  
##  <a name="canupdate"></a>CDaoQueryDef::CanUpdate  
 쿼리 정의 수정할 수 있는지 여부를 확인 하려면이 함수를 호출-예: 해당 이름이 나 SQL 문자열을 변경 합니다.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>반환 값  
 쿼리 정의; 수정이 허용 된 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 경우에 쿼리 정의 수정할 수 있습니다.  
  
-   읽기 전용으로 열려 있는 데이터베이스에서 따르지 않습니다.  
  
-   업데이트 권한이 있는 데이터베이스에 대 한 합니다.  
  
     이 보안 기능을 구현 하는지 여부에 따라 달라 집니다. MFC 보안;에 대 한 지원을 제공 하지 않습니다. 또는 구현 해야 해당 사용자가 직접 직접 DAO 호출 하 여 Microsoft Access를 사용 하 여 합니다. DAO 도움말의 "사용 권한 Property" 항목을 참조 하십시오.  
  
##  <a name="cdaoquerydef"></a>CDaoQueryDef::CDaoQueryDef  
 생성 된 **CDaoQueryDef** 개체입니다.  
  
```  
CDaoQueryDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDatabase`  
 열린에 대 한 포인터 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체입니다.  
  
### <a name="remarks"></a>설명  
 개체는 데이터베이스의 QueryDefs 컬렉션, 컬렉션에 저장 될 새 쿼리 또는를 저장할 임시 쿼리를 저장 하는 기존 쿼리 정의 나타낼 수 있습니다. 다음 단계는 쿼리 정의의 형식에 따라 달라 집니다.  
  
-   개체는 기존 쿼리 정의 나타내는 경우 개체의 호출 [열려](#open) 멤버 함수를 초기화 합니다.  
  
-   개체를 저장할 새 쿼리 정의 나타내는 경우 개체의 호출 [만들기](#create) 멤버 함수입니다. 개체는 데이터베이스 QueryDefs 컬렉션에 추가합니다. 그런 다음 호출 `CDaoQueryDef` 개체의 특성을 설정 하는 멤버 함수입니다. 마지막으로 호출 [Append](#append)합니다.  
  
-   개체가 나타내는 임시 쿼리 정의 (데이터베이스에 저장 하지 않음), 호출 **만들기**, 쿼리 이름에 대 한 빈 문자열을 전달 합니다. 호출한 후 **만들기**, 직접 해당 특성을 설정 하 여 쿼리 정의 초기화 합니다. 호출 하지 마십시오 **Append**합니다.  
  
 쿼리 정의의 특성을 설정 하려면 사용할 수 있습니다는 [SetName](#setname), [SetSQL](#setsql), [SetConnect](#setconnect), [SetODBCTimeout](#setodbctimeout), 및 [SetReturnsRecords](#setreturnsrecords) 멤버 함수입니다.  
  
 쿼리 정의 개체를 마치면 호출 해당 [닫기](#close) 멤버 함수입니다. 사용 하 여 쿼리 정의에 대 한 포인터를 사용 하도록 설정한 경우는 **삭제** 연산자를 c + + 개체를 제거 합니다.  
  
##  <a name="close"></a>CDaoQueryDef::Close  
 쿼리 정의 개체를 사용 하 여 완료 하면이 멤버 함수를 호출 합니다.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>설명  
 쿼리 정의 닫으면 기본 DAO 개체를 해제 하지만 저장 된 DAO 쿼리 정의 개체 또는 c + +를 제거 하지 않습니다 `CDaoQueryDef` 개체입니다. 이것이 동일 [CDaoDatabase::DeleteQueryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef), DAO (없는 경우 임시 쿼리 정의)에 데이터베이스의 QueryDefs 컬렉션에서 쿼리 정의 삭제 하 합니다.  
  
##  <a name="create"></a>CDaoQueryDef::Create  
 이 저장된 된 새 쿼리 또는 새 임시 쿼리를 만드는 함수를 호출 합니다.  
  
```  
virtual void Create(
    LPCTSTR lpszName = NULL,  
    LPCTSTR lpszSQL = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 데이터베이스에 저장 된 쿼리의 고유 이름입니다. 문자열에 대 한 자세한 DAO 도움말의 "CreateQueryDef 메서드" 항목을 참조 합니다. 빈 문자열이 면 하는 기본값을 그대로 적용 하는 경우에 임시 쿼리 정의 생성 됩니다. 이러한 쿼리 QueryDefs 컬렉션에 저장 되지 않습니다.  
  
 `lpszSQL`  
 쿼리를 정의 하는 SQL 문자열입니다. 기본값에 동의 하면 **NULL**, 나중에 호출 해야 [SetSQL](#setsql) 문자열을 설정 하려면. 그때 까지는 쿼리 정의 되지 않습니다. 그러나 레코드 집합; 정의 되지 않은 쿼리를 사용할 수 있습니다. 자세한 내용은 설명 부분을 참조 하십시오. SQL 문은 쿼리 정의 QueryDefs 컬렉션에 추가 하기 전에 정의 되어야 합니다.  
  
### <a name="remarks"></a>설명  
 에 있는 이름을 전달 하는 경우 `lpszName`를 호출할 수 있습니다 [추가](#append) 데이터베이스의 QueryDefs 컬렉션의 쿼리 정의 저장 하려면. 그렇지 않으면 개체는 임시 쿼리 정의 하 고 저장 되지 않습니다. 두 경우 모두 쿼리 정의가 열린 상태 이므로 하거나 만드는 데 사용할 수는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체 또는 쿼리 정의 호출 [Execute](#execute) 멤버 함수입니다.  
  
 SQL 문을 지정 하지 않으면 `lpszSQL`를 사용 하 여 쿼리를 실행할 수 없습니다 **Execute** 하지만 레코드 집합을 만드는 데 사용할 수 있습니다. 이 경우 MFC는 레코드 집합의 기본 SQL 문을 사용합니다.  
  
##  <a name="execute"></a>CDaoQueryDef::Execute  
 쿼리 정의 개체에 의해 정의 된 쿼리를 실행 하려면이 함수를 호출 합니다.  
  
```  
virtual void Execute(int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>매개 변수  
 `nOptions`  
 쿼리의 특징을 결정 하는 정수입니다. 관련된 정보에 대 한 DAO 도움말의 "메서드 실행" 항목을 참조 합니다. 비트 OR 연산자를 사용할 수 있습니다 ( **&#124;**)이이 인수에 대 한 다음과 같은 상수를 결합 합니다.  
  
- **dbDenyWrite** 다른 사용자에 게 쓰기 권한을 거부 합니다.  
  
- **dbInconsistent** 일관성 없는 업데이트 합니다.  
  
- **dbConsistent** 업데이트 일관성.  
  
- **dbSQLPassThrough** SQL 통과 합니다. ODBC 데이터베이스 처리를 위해 전달 될 SQL 문의 하면 됩니다.  
  
- **dbFailOnError** 기본값입니다. 오류가 발생 한 경우 업데이트와 보고서 오류도 롤백할 사용자.  
  
- **dbSeeChanges** 다른 사용자가 편집 중인 데이터를 변경 하는 경우 런타임 오류가 발생 합니다.  
  
> [!NOTE]
>  에 대 한 설명은 용어 "일관성이 없는" 및 "일관" DAO 도움말의 "메서드 실행" 항목을 참조 합니다.  
  
### <a name="remarks"></a>설명  
 만이 방식으로 실행을 위해 사용 되는 쿼리 정의 개체는 다음 쿼리 유형 중 하나를 나타낼 수 있습니다.  
  
-   실행 쿼리  
  
-   SQL 통과 쿼리  
  
 **실행** select 쿼리의 같은 레코드를 반환 하는 쿼리에 작동 하지 않습니다. **실행** 은 일반적으로 사용 대량 작업 쿼리를 같은 **업데이트**, **삽입**, 또는 **SELECT INTO**, 또는 데이터 정의 언어 (DDL) 작업입니다.  
  
> [!TIP]
>  Microsoft Jet에 테이블을 연결 하는 ODBC 데이터 원본으로 작업 하는 기본 방법은 (합니다. MDB) 데이터베이스입니다. 자세한 내용은 DAO 도움말의 "DAO와 외부 데이터베이스 액세스" 항목을 참조 합니다.  
  
 호출 된 [GetRecordsAffected](#getrecordsaffected) 가장 최근의 영향을 받는 레코드 수를 확인 하려면 쿼리 정의 개체의 멤버 함수 **Execute** 호출 합니다. 예를 들어 `GetRecordsAffected` 삭제, 업데이트 또는 삽입 작업 쿼리를 실행 하는 경우 레코드의 수에 대 한 정보를 반환 합니다. 반환 된 수는 cascade를 업데이트 하거나 삭제 하는 경우 관련된 테이블의 변경 내용이 적용 반영 되지 않습니다.  
  
 둘 모두를 포함 하는 경우 **dbInconsistent** 및 **dbConsistent** 결과 기본적으로 둘 다를 포함 하는 경우 또는 **dbInconsistent**합니다.  
  
 **실행** 레코드 집합을 반환 하지 않습니다. 사용 하 여 **Execute** 레코드를 선택 하는 쿼리에 MFC 형식의 예외를 throw 하면 [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다.  
  
##  <a name="getconnect"></a>CDaoQueryDef::GetConnect  
 쿼리 정의 데이터 원본과 관련 된 연결 문자열을 가져오지이 멤버 함수를 호출 합니다.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 쿼리 정의 대 한 연결 문자열을 포함 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 ODBC 데이터 원본 및 특정 ISAM 드라이버 에서만 사용 됩니다. Microsoft Jet 사용 되지 않습니다 (합니다. MDB) 데이터베이스 이 경우 `GetConnect` 빈 문자열을 반환 합니다. 자세한 내용은 참조 [SetConnect](#setconnect)합니다.  
  
> [!TIP]
>  ODBC 테이블 작업을 하는 기본 방법은에 내용을 추가 하는 프로그램입니다. MDB 데이터베이스입니다. 자세한 내용은 DAO 도움말의 "DAO와 외부 데이터베이스 액세스" 항목을 참조 합니다.  
  
 연결 문자열에 대 한 자세한 내용은 DAO 도움말의 "연결 속성" 항목을 참조 하십시오.  
  
##  <a name="getdatecreated"></a>CDaoQueryDef::GetDateCreated  
 쿼리 정의 개체가 만들어진 날짜 가져오고이 멤버 함수를 호출 합니다.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>반환 값  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 날짜 및 쿼리 정의 만든 시간을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.  
  
##  <a name="getdatelastupdated"></a>CDaoQueryDef::GetDateLastUpdated  
 마지막으로 수정한 날짜 쿼리 정의 개체를 가져오고이 멤버 함수 호출-때의 모든 속성 변경 된 해당 이름, 해당 SQL 문자열 또는 연결 문자열 등입니다.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>반환 값  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 날짜 및 쿼리 정의 마지막으로 수정한 시간을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.  
  
##  <a name="getfieldcount"></a>CDaoQueryDef::GetFieldCount  
 쿼리의 필드 수를 검색 하려면이 함수를 호출 합니다.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>반환 값  
 쿼리에 정의 된 필드 수를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 `GetFieldCount`쿼리 정의의 모든 필드를 반복 하는 데 유용 합니다. 이 위해 사용 하 여 `GetFieldCount` 함께에서 [GetFieldInfo](#getfieldinfo)합니다.  
  
##  <a name="getfieldinfo"></a>CDaoQueryDef::GetFieldInfo  
 다양 한 종류의 쿼리 정의에 정의 된 필드에 대 한 정보를 가져오려면이 함수를 호출 합니다.  
  
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
 인덱스에 의해 조회에 대 한 쿼리 정의 필드 컬렉션에서 원하는 필드의 0부터 시작 하는 인덱스입니다.  
  
 `fieldinfo`  
 에 대 한 참조는 `CDaoFieldInfo` 요청 된 정보를 반환 하는 개체입니다.  
  
 `dwInfoOptions`  
 검색할 필드에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 함께 반환 하는 함수를 입히기 무엇 여기 나열 됩니다.  
  
- `AFX_DAO_PRIMARY_INFO`(기본값) 이름, 유형, 크기, 속성  
  
- `AFX_DAO_SECONDARY_INFO`기본 정보 더하기: 필요한 서 수 위치, 따옴표, 원본 필드, 외부 이름, 원본 테이블, 데이터 정렬 순서  
  
- `AFX_DAO_ALL_INFO`기본 및 보조 정보 더하기: Default Value, 유효성 검사 텍스트 유효성 검사 규칙  
  
 `lpszName`  
 이름별으로 조회에 대 한 원하는 필드의 이름을 포함 하는 문자열입니다. 사용할 수는 [CString](../../atl-mfc-shared/reference/cstringt-class.md)합니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 설명은에서 반환 되는 정보 `fieldinfo`, 참조는 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조입니다. 이 구조에 아래 설명 된 정보에 해당 하는 멤버가 `dwInfoOptions` 위에 있습니다. 한 수준의 정보를 요청 하는 경우 모든 이전 수준의 정보를 얻습니다.  
  
##  <a name="getname"></a>CDaoQueryDef::GetName  
 쿼리 정의 나타내는 쿼리의 이름을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>반환 값  
 쿼리의 이름입니다.  
  
### <a name="remarks"></a>설명  
 쿼리 정의 이름은 고유한 사용자 정의 이름입니다. 쿼리 정의 이름에 대 한 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.  
  
##  <a name="getodbctimeout"></a>CDaoQueryDef::GetODBCTimeout  
 ODBC 데이터 원본에 쿼리 시간이 초과 되기 전에 현재 제한 시간을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
short GetODBCTimeout();
```  
  
### <a name="return-value"></a>반환 값  
 수 (초)을 쿼리 시간이 초과 됩니다.  
  
### <a name="remarks"></a>설명  
 이 시간 제한에 대 한 내용은 DAO 도움말의 "ODBCTimeout Property" 항목을 참조 하십시오.  
  
> [!TIP]
>  ODBC 테이블을 사용 하는 기본 방법은 Microsoft Jet에 연결할 것 (합니다. MDB) 데이터베이스입니다. 자세한 내용은 DAO 도움말의 "DAO와 외부 데이터베이스 액세스" 항목을 참조 합니다.  
  
##  <a name="getparametercount"></a>CDaoQueryDef::GetParameterCount  
 저장 된 쿼리에서 매개 변수 개수를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
short GetParameterCount();
```  
  
### <a name="return-value"></a>반환 값  
 쿼리에 정의 된 매개 변수의 수입니다.  
  
### <a name="remarks"></a>설명  
 `GetParameterCount`쿼리 정의에서 모든 매개 변수를 통해 반복 하는 데 유용 합니다. 이 위해 사용 하 여 `GetParameterCount` 함께에서 [GetParameterInfo](#getparameterinfo)합니다.  
  
 관련된 정보에 대 한 "Parameter 개체", "매개 변수 컬렉션" 및 "매개 변수 선언 ()"에서 SQL DAO 도움말 항목을 참조 합니다.  
  
##  <a name="getparameterinfo"></a>CDaoQueryDef::GetParameterInfo  
 쿼리 정의에 정의 된 매개 변수 정보를 가져오려면이 함수를 호출 합니다.  
  
```  
void GetParameterInfo(
    int nIndex,  
    CDaoParameterInfo& paraminfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetParameterInfo(
    LPCTSTR lpszName,  
    CDaoParameterInfo& paraminfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 인덱스에 의해 조회에 대 한 쿼리 정의 매개 변수 컬렉션에서 원하는 매개 변수의 0부터 시작 하는 인덱스입니다.  
  
 `paraminfo`  
 에 대 한 참조는 [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) 요청 된 정보를 반환 하는 개체입니다.  
  
 `dwInfoOptions`  
 매개 변수를 검색 하는 방법에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션 함수를 반환 하면 어떤 함께 여기에 나열 되어:  
  
- `AFX_DAO_PRIMARY_INFO`(기본값) 이름, 형식  
  
 `lpszName`  
 이름별으로 조회에 대 한 원하는 매개 변수의 이름을 포함 하는 문자열입니다. 사용할 수는 [CString](../../atl-mfc-shared/reference/cstringt-class.md)합니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 설명은에서 반환 되는 정보 `paraminfo`, 참조는 [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) 구조입니다. 이 구조에 아래 설명 된 정보에 해당 하는 멤버가 `dwInfoOptions` 위에 있습니다.  
  
 관련된 정보에 대 한 "매개 변수 선언 ()"에서 SQL DAO 도움말 항목을 참조 합니다.  
  
##  <a name="getparamvalue"></a>CDaoQueryDef::GetParamValue  
 쿼리 정의 매개 변수 컬렉션에 저장 된 지정된 된 매개 변수의 현재 값을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual COleVariant GetParamValue(LPCTSTR lpszName);  
virtual COleVariant GetParamValue(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 매개 변수 이름별으로 조회에 대해 원하는 값의 이름입니다.  
  
 `nIndex`  
 인덱스에 의해 조회에 대 한 쿼리 정의 매개 변수 컬렉션에서 매개 변수의 0부터 시작 하는 인덱스입니다. 호출 하 여이 값을 가져올 수 [GetParameterCount](#getparametercount) 및 [GetParameterInfo](#getparameterinfo)합니다.  
  
### <a name="return-value"></a>반환 값  
 클래스의 개체 [COleVariant](../../mfc/reference/colevariant-class.md) 매개 변수의 값이 들어 있는입니다.  
  
### <a name="remarks"></a>설명  
 매개 변수 이름 또는 컬렉션에서 서 수 위치에 액세스할 수 있습니다.  
  
 관련된 정보에 대 한 "매개 변수 선언 ()"에서 SQL DAO 도움말 항목을 참조 합니다.  
  
##  <a name="getrecordsaffected"></a>CDaoQueryDef::GetRecordsAffected  
 마지막 호출 영향을 받는 레코드 수를 확인 하려면이 함수를 호출 [Execute](#execute)합니다.  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>반환 값  
 영향을 받는 레코드 수입니다.  
  
### <a name="remarks"></a>설명  
 반환 된 수는 cascade를 업데이트 하거나 삭제 하는 경우 관련된 테이블의 변경 내용이 적용 반영 되지 않습니다.  
  
 관련된 내용은 DAO 도움말의 "RecordsAffected Property" 항목을 참조 하십시오.  
  
##  <a name="getreturnsrecords"></a>CDaoQueryDef::GetReturnsRecords  
 쿼리 정의 레코드를 반환 하는 쿼리 기반 인지 여부를 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetReturnsRecords();
```  
  
### <a name="return-value"></a>반환 값  
 레코드를 반환 하는 쿼리를 기반으로 하는 쿼리 정의 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 통과 쿼리를 SQL에만 사용 됩니다. SQL 쿼리에 대 한 자세한 내용은 참조는 [Execute](#execute) 멤버 함수입니다. SQL 통과 쿼리 사용에 대 한 자세한 내용은 참조는 [SetReturnsRecords](#setreturnsrecords) 멤버 함수입니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "ReturnsRecords Property" 항목을 참조 합니다.  
  
##  <a name="getsql"></a>CDaoQueryDef::GetSQL  
 쿼리 정의 기반이 되는 쿼리를 정의 하는 SQL 문을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetSQL();
```  
  
### <a name="return-value"></a>반환 값  
 쿼리 정의 기반이 되는 쿼리를 정의 하는 SQL 문입니다.  
  
### <a name="remarks"></a>설명  
 다음 키워드, 테이블 이름 등에 대 한 문자열을 parse 때문일 수 있습니다.  
  
 관련된 정보에 대 한 "SQL Property", "비교의 Microsoft Jet 데이터베이스 엔진 SQL 및 ANSI SQL" 및 "쿼리는 데이터베이스와 SQL에서 코드" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="gettype"></a>CDaoQueryDef::GetType  
 쿼리 정의의 쿼리 유형을 결정 하려면이 멤버 함수를 호출 합니다.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>반환 값  
 쿼리 정의에 정의 된 쿼리 형식입니다. 값에 대 한 설명을 참조 하세요.  
  
### <a name="remarks"></a>설명  
 쿼리 형식에에서 지정 된 내용을 쿼리 정의 SQL 문자열 또는 호출 하는 기존 쿼리 정의 쿼리 정의 만들 때 설정한 [SetSQL](#setsql) 멤버 함수입니다. 이 함수에서 반환 하는 쿼리 유형을 다음 값 중 하나일 수 있습니다.  
  
- **dbQSelect** 선택  
  
- **dbQAction** 동작  
  
- **dbQCrosstab** 크로스탭  
  
- **dbQDelete** 삭제  
  
- **dbQUpdate** 업데이트  
  
- **dbQAppend** 추가  
  
- **dbQMakeTable** 테이블 만들기  
  
- **dbQDDL** 데이터 정의  
  
- **dbQSQLPassThrough** 통과  
  
- **dbQSetOperation** 공용 구조체  
  
- **dbQSPTBulk** 사용한 **dbQSQLPassThrough** 레코드를 반환 하지 않는 쿼리를 지정 합니다.  
  
> [!NOTE]
>  설정 하지 않으면 SQL 통과 쿼리를 만들려면는 **dbSQLPassThrough** 상수입니다. 이 설정은 자동으로 Microsoft Jet 데이터베이스 엔진에 의해 쿼리 정의 개체를 만들고 연결 문자열을 설정 합니다.  
  
 SQL 문자열에 대 한 정보를 참조 하십시오. [GetSQL](#getsql)합니다. 쿼리 형식에 대 한 정보를 참조 하십시오. [Execute](#execute)합니다.  
  
##  <a name="isopen"></a>CDaoQueryDef::IsOpen  
 확인 하려면이 함수를 호출 여부는 `CDaoQueryDef` 개체가 현재 열려 있습니다.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우에는 `CDaoQueryDef` 개체는 현재 열려 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 호출에 사용 하기 전에 쿼리 정의 열린 상태에 있어야 [Execute](#execute) 만들 수는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체입니다. 에 넣는 querydef 열린 상태 호출 하거나 [만들기](#create) (에 대해 새 쿼리 정의) 또는 [열고](#open) (기존 쿼리 정의)에 대 한 합니다.  
  
##  <a name="m_pdatabase"></a>CDaoQueryDef::m_pDatabase  
 에 대 한 포인터는 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) querydef 개체와 연결 된 개체입니다.  
  
### <a name="remarks"></a>설명  
 데이터베이스에 직접 액세스 해야 할 경우이 포인터를 사용 하 여-예를 들어, 다른 쿼리 정의 또는 레코드 집합에 대 한 포인터를 가져올 수는 데이터베이스 컬렉션에서 개체입니다.  
  
##  <a name="m_pdaoquerydef"></a>CDaoQueryDef::m_pDAOQueryDef  
 기본 DAO querydef 개체에 대 한 OLE 인터페이스에 대 한 포인터를 포함합니다.  
  
### <a name="remarks"></a>설명  
 이 포인터는 완전 하 고 다른 클래스와의 일관성을 위해 제공 됩니다. 그러나 MFC DAO querydefs를 보다 완전 하 게 캡슐화 하기 때문에 없는 필요할 수 있습니다. 이 옵션을 사용할 수행 하는 경우 이렇게 신중 하 게-해야 할 사항을 알고 있는 경우가 아니면 포인터의 값을 변경 하지 않는 특히 합니다.  
  
##  <a name="open"></a>CDaoQueryDef::Open  
 데이터베이스의 QueryDefs 컬렉션에 이미 저장 된 쿼리 정의 열려면이 멤버 함수를 호출 합니다.  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 열에 저장 된 쿼리 정의의 이름을 포함 하는 문자열입니다. 사용할 수는 [CString](../../atl-mfc-shared/reference/cstringt-class.md)합니다.  
  
### <a name="remarks"></a>설명  
 호출할 수 있습니다 쿼리 정의 열면 해당 [Execute](#execute) 만들려는 쿼리 정의 사용 하 여 또는 멤버 함수는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체입니다.  
  
##  <a name="setconnect"></a>CDaoQueryDef::SetConnect  
 쿼리 정의 개체의 연결 문자열을 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszConnect`  
 관련 된 연결 문자열을 포함 하는 문자열 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체입니다.  
  
### <a name="remarks"></a>설명  
 연결 문자열은 ODBC 및 필요에 따라 특정 ISAM 드라이버 추가 정보를 전달 하기 위해 사용 됩니다. Microsoft Jet에 사용 되지 않습니다 (합니다. 데이터베이스 MDB)입니다.  
  
> [!TIP]
>  ODBC 테이블 작업을 하는 기본 방법은에 내용을 추가 하는 프로그램입니다. MDB 데이터베이스입니다.  
  
 ODBC 데이터 원본에 SQL 통과 쿼리를 나타내는 쿼리 정의 실행 하기 전에 연결 문자열을 설정 `SetConnect` 호출 [SetReturnsRecords](#setreturnsrecords) 쿼리 레코드를 반환 하는지 여부를 지정할 수 있습니다.  
  
 연결 문자열의 구조 및 연결 문자열 구성 요소 예제에 대 한 자세한 내용은 DAO 도움말의 "연결 속성" 항목을 참조 하십시오.  
  
##  <a name="setname"></a>CDaoQueryDef::SetName  
 임시 하지 않은 쿼리 정의의 이름을 변경 하려는 경우이 함수를 호출 합니다.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 연결 된 실제적 쿼리에 대 한 새 이름을 포함 하는 문자열 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체입니다.  
  
### <a name="remarks"></a>설명  
 쿼리 정의 이름은 고유한, 사용자 정의 이름입니다. 호출할 수 있습니다 `SetName` 쿼리 정의 하기 전에 개체 QueryDefs 컬렉션에 추가 됩니다.  
  
##  <a name="setodbctimeout"></a>CDaoQueryDef::SetODBCTimeout  
 ODBC 데이터 원본에 쿼리 시간이 초과 되기 전에 제한 시간을 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetODBCTimeout(short nODBCTimeout);
```  
  
### <a name="parameters"></a>매개 변수  
 *nODBCTimeout*  
 수 (초)을 쿼리 시간이 초과 됩니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수를 사용 하면 기본 수 (초) 이후 연결 된 데이터 원본 "제한 시간입니다." 작업을 재정의 합니다. 네트워크 액세스 문제, 과도 한 쿼리 처리 시간 및 등으로 인해 작업 시간이 초과 될 수 있습니다. 호출 `SetODBCTimeout` 쿼리 제한 시간 값을 변경 하려는 경우이 쿼리 정의 사용 하 여 쿼리를 실행 하기 전에. (ODBC 연결을 다시 사용 하는 대로 제한 시간 값은 동일한 연결에서 모든 클라이언트에 대해 동일 합니다.)  
  
 쿼리 시간 제한의 기본값은 60 초입니다.  
  
##  <a name="setparamvalue"></a>CDaoQueryDef::SetParamValue  
 런타임에 쿼리 정의에서 매개 변수 값을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual void SetParamValue(
    LPCTSTR lpszName,  
    const COleVariant& varValue);

 
virtual void SetParamValue(
    int nIndex,  
    const COleVariant& varValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 매개 변수 값을 설정의 이름입니다.  
  
 `varValue`  
 값을 설정 설명 부분을 참조 하십시오.  
  
 `nIndex`  
 쿼리 정의 매개 변수 컬렉션에서 매개 변수의 서 수 위치입니다. 호출 하 여이 값을 가져올 수 [GetParameterCount](#getparametercount) 및 [GetParameterInfo](#getparameterinfo)합니다.  
  
### <a name="remarks"></a>설명  
 매개 변수는 쿼리 정의 SQL 문자열의 일부로 설정 이미 있어야 합니다. 매개 변수 이름 또는 컬렉션에서 서 수 위치에 액세스할 수 있습니다.  
  
 으로 설정 하려면 값을 지정 된 `COleVariant` 개체입니다. 원하는 값과의 형식을 설정 하는 방법에 대 한 정보에 대 한 프로그램 `COleVariant` 개체 클래스를 참조 하십시오. [COleVariant](../../mfc/reference/colevariant-class.md)합니다.  
  
##  <a name="setreturnsrecords"></a>CDaoQueryDef::SetReturnsRecords  
 이 외부 데이터베이스에는 SQL 통과 쿼리를 설정 하는 과정의 일부로 함수를 호출 합니다.  
  
```  
void SetReturnsRecords(BOOL bReturnsRecords);
```  
  
### <a name="parameters"></a>매개 변수  
 *bReturnsRecords*  
 전달 **TRUE** 외부 데이터베이스에 대 한 쿼리; 레코드를 반환 하는 경우 이렇게 하지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 이 경우 쿼리 정의 만들고 해야 다른를 사용 하 여 해당 속성을 설정할 `CDaoQueryDef` 멤버 함수입니다. 외부 데이터베이스에 대 한 참조 [SetConnect](#setconnect)합니다.  
  
##  <a name="setsql"></a>CDaoQueryDef::SetSQL  
 쿼리 정의 실행 하는 SQL 문을 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszSQL`  
 실행에 적합 한 전체 SQL 문을 포함 하는 문자열입니다. 이 문자열의 구문은 DBMS에 따라 하는 쿼리 대상입니다. Microsoft Jet 데이터베이스 엔진에서 사용 되는 구문 설명에서는 "건물 SQL 문 코드"를 여러 DAO 도움말 항목을 참조 합니다.  
  
### <a name="remarks"></a>설명  
 일반적인 사용 `SetSQL` 는 통과 SQL 쿼리에서 사용 하기 위해 쿼리 정의 개체를 설정 합니다. (대상 DBMS에서 SQL 통과 쿼리 구문의 DBMS에 대 한 설명서 참조).  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset 클래스](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoDatabase 클래스](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoException 클래스](../../mfc/reference/cdaoexception-class.md)
