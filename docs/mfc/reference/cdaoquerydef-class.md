---
title: "CDaoQueryDef 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- QueryDef objects
- CDaoQueryDef class
- queries [Visual Studio], defining
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0bf06c68bb7072aa1907e4c730848cca9ff5e7d0
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

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
|[CDaoQueryDef::CDaoQueryDef](#cdaoquerydef)|생성 된 **CDaoQueryDef** 개체입니다. 그런 다음 호출 **열려** 또는 **만들기**필요에 따라 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoQueryDef::Append](#append)|데이터베이스의 QueryDefs 컬렉션으로 저장된 된 쿼리를 쿼리 정의 추가합니다.|  
|[CDaoQueryDef::CanUpdate](#canupdate)|쿼리는 데이터베이스를 업데이트할 수 있으면&0;이 아닌 값을 반환 합니다.|  
|[CDaoQueryDef::Close](#close)|쿼리 정의 개체를 닫습니다. 함께 작업을 마치면 c + + 개체를 삭제 합니다.|  
|[CDaoQueryDef::Create](#create)|기본 DAO 쿼리 정의 개체를 만듭니다. 쿼리 정의 사용 하 여 임시 쿼리 또는 호출 **추가** 데이터베이스에 저장 합니다.|  
|[CDaoQueryDef::Execute](#execute)|쿼리 정의 개체에 의해 정의 된 쿼리를 실행 합니다.|  
|[CDaoQueryDef::GetConnect](#getconnect)|쿼리 정의와 관련 된 연결 문자열을 반환 합니다. 데이터 소스를 식별 하는 연결 문자열. (Sql 통과 쿼리의 고, 그렇지 않으면 빈 문자열입니다.)|  
|[CDaoQueryDef::GetDateCreated](#getdatecreated)|저장된 된 쿼리를 만든 날짜를 반환 합니다.|  
|[CDaoQueryDef::GetDateLastUpdated](#getdatelastupdated)|저장된 된 쿼리를 마지막으로 수정한 날짜를 반환 합니다.|  
|[CDaoQueryDef::GetFieldCount](#getfieldcount)|쿼리 정의에 정의 된 필드 수를 반환 합니다.|  
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|쿼리에 정의 된 지정된 된 필드에 대 한 정보를 반환 합니다.|  
|[CDaoQueryDef::GetName](#getname)|쿼리 정의의 이름을 반환합니다.|  
|[CDaoQueryDef::GetODBCTimeout](#getodbctimeout)|(한 ODBC 쿼리)에 대 한 ODBC에서 사용 되는 시간 제한 값을 반환 합니다. 쿼리 정의 실행할 때. 이 작업을 완료 하는 쿼리 수 있도록 기간 결정 합니다.|  
|[CDaoQueryDef::GetParameterCount](#getparametercount)|쿼리에 정의 된 매개 변수 개수를 반환 합니다.|  
|[CDaoQueryDef::GetParameterInfo](#getparameterinfo)|쿼리에 지정 된 매개 변수에 대 한 정보를 반환합니다.|  
|[CDaoQueryDef::GetParamValue](#getparamvalue)|쿼리에 지정 된 매개 변수의 값을 반환합니다.|  
|[CDaoQueryDef::GetRecordsAffected](#getrecordsaffected)|쿼리가 실행의 영향을 받는 레코드의 수를 반환 합니다.|  
|[CDaoQueryDef::GetReturnsRecords](#getreturnsrecords)|레코드를 반환 하는 쿼리 정의에 정의 된 쿼리의 경우&0;이 아닌 값을 반환 합니다.|  
|[CDaoQueryDef::GetSQL](#getsql)|쿼리 정의에 정의 된 쿼리를 지정 하는 SQL 문자열을 반환 합니다.|  
|[CDaoQueryDef::GetType](#gettype)|쿼리 유형을 반환: 삭제, 업데이트, 추가, 테이블 만들기 및 등입니다.|  
|[CDaoQueryDef::IsOpen](#isopen)|쿼리 정의 개방형이 고 실행 될 경우&0;이 아닌 값을 반환 합니다.|  
|[CDaoQueryDef::Open](#open)|데이터베이스의 QueryDefs 컬렉션에 저장 된 쿼리는 기존 정의 엽니다.|  
|[CDaoQueryDef::SetConnect](#setconnect)|ODBC 데이터 원본에서 SQL 통과 쿼리를 위한 연결 문자열을 설정합니다.|  
|[CDaoQueryDef::SetName](#setname)|쿼리 정의 만들 때 사용 중인 이름 바꾸기 저장 된 쿼리의 이름을 설정 합니다.|  
|[CDaoQueryDef::SetODBCTimeout](#setodbctimeout)|사용 되는 ODBC에서 (ODBC 쿼리) 사용 하는 시간 제한 값을 설정 하는 쿼리 정의 실행할 때.|  
|[CDaoQueryDef::SetParamValue](#setparamvalue)|쿼리에 지정 된 매개 변수의 값을 설정합니다.|  
|[CDaoQueryDef::SetReturnsRecords](#setreturnsrecords)|쿼리 정의 레코드를 반환 하는지 여부를 지정 합니다. 이 특성을 설정 **TRUE** 는 통과 쿼리를 SQL에만 유효 합니다.|  
|[CDaoQueryDef::SetSQL](#setsql)|쿼리 정의에 정의 된 쿼리를 지정 하는 SQL 문자열을 설정 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoQueryDef::m_pDAOQueryDef](#m_pdaoquerydef)|기본 DAO 쿼리 정의 개체에 대 한 OLE 인터페이스에 대 한 포인터입니다.|  
|[CDaoQueryDef::m_pDatabase](#m_pdatabase)|에 대 한 포인터는 `CDaoDatabase` 쿼리 정의 연결 된 개체입니다. 쿼리 정의 또는 데이터베이스에 저장 되어 있습니다.|  
  
## <a name="remarks"></a>주의  
 쿼리 정의 쿼리를과 "만든 날짜" 및 "ODBC 시간이 초과 되었습니다."와 같은 속성을 설명 하는 SQL 문을 포함 하는 데이터 액세스 개체 저장 하지 않고 임시 쿼리 정의 개체를 만들 수도 있지만 것이 편리-좀 더 효율적으로 하 고-일반적으로 저장 하는 데이터베이스의 쿼리를 다시 사용 합니다. A [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체는 컬렉션의 저장 된 쿼리 정의 포함 하는 쿼리 정의 컬렉션 이라는 유지 합니다.  
  
> [!NOTE]
>  DAO 데이터베이스 클래스에 연결 ODBC (Open Database)을 기반으로 하는 MFC 데이터베이스 클래스와 구별 됩니다. 모든 DAO 데이터베이스 클래스 이름이 "CDao" 접두사가 있습니다. DAO 클래스의 ODBC 데이터 원본에 액세스할 수 있습니다. 일반적으로 기반으로 DAO MFC 클래스는 ODBC;에 따라 MFC 클래스 보다 더 가능 DAO 기반 클래스를 통해 자신의 데이터베이스 엔진을 통해 ODBC 드라이버를 포함 한 데이터를 액세스할 수 있습니다. DAO 기반 클래스는 또한 DAO를 직접 호출 하지 않고는 클래스를 통해 테이블을 추가 하는 등의 데이터 정의 언어 (DDL) 작업을 지원 합니다.  
  
## <a name="usage"></a>용도  
 개체를 사용 쿼리 정의 하거나 작업 쿼리를 저장 된 기존 또는 새 쿼리나 임시 쿼리를 저장 합니다.  
  
1.  모든 경우에 생성 되어 먼저는 `CDaoQueryDef` 에 대 한 포인터를 제공 하는 개체는 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 쿼리 속해 있는 개체입니다.  
  
2.  원하는 작업에 따라 다음을 수행 합니다.  
  
    -   쿼리를 저장 된 기존를 사용 하려면 쿼리 정의 개체의 호출 [열려](#open) 멤버 함수, 저장 된 쿼리의 이름을 제공 합니다.  
  
    -   저장된 된 새 쿼리를 만들려면 쿼리 정의 개체의 호출 [만들기](#create) 멤버 함수를 쿼리의 이름을 제공 합니다. 다음 호출 [추가](#append) 데이터베이스의 QueryDefs 컬렉션에 추가 하 여 쿼리를 저장 합니다. **만들기** 쿼리 정의 열린 상태로 설정 하므로 호출한 후 **만들기** 호출 하지 않으면 **열고**합니다.  
  
    -   임시 쿼리 정의 만들려면 호출 **만들기**합니다. 쿼리 이름에 대 한 빈 문자열을 전달 합니다. 호출 하지 마십시오 **추가**합니다.  
  
 호출 작업을 마치면 쿼리 정의 개체를 사용 하 여 해당 [닫기](#close) 멤버 함수, 다음 쿼리 정의 개체를 삭제 합니다.  
  
> [!TIP]
>  저장 된 쿼리를 만드는 가장 쉬운 방법은를 만들고 Microsoft Access를 사용 하 여 데이터베이스에 저장 됩니다. 그런 다음 열고 하 고 MFC 코드에서 사용할 수 있습니다.  
  
## <a name="purposes"></a>목적으로  
 다음과 같은 용도로 중 하나에 대 한 쿼리 정의 개체를 사용할 수 있습니다.  
  
-   만들려는 `CDaoRecordset` 개체  
  
-   개체의 호출을 **Execute** 직접 실행 쿼리 또는 SQL 통과 쿼리를 실행 하는 멤버 함수  
  
 쿼리를 선택, 동작, 크로스탭, 삭제, 업데이트를 포함 하 여 모든 유형에 대 한 쿼리 정의 개체를 사용 하 고, 테이블 만들기, 데이터 정의 SQL 통과, union, 추가 하 고, 대량 쿼리 수 있습니다. 쿼리 형식은 SQL 문을 제공 하는 내용에 따라 결정 됩니다. 쿼리 형식에 대 한 내용은 참조는 **Execute** 및 [GetType](#gettype) 멤버 함수입니다. 레코드 집합 행을 반환 하는 것에 대 한 일반적으로 사용 되 쿼리, 일반적으로 사용 하 여 **선택... ** 키워드입니다. **실행** 대량 작업을 위해 가장 많이 사용 됩니다. 자세한 내용은 참조 [Execute](#execute) 및 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)합니다.  
  
## <a name="querydefs-and-recordsets"></a>쿼리 정 및 레코드 집합  
 쿼리 정의 개체를 만드는 데는 `CDaoRecordset` 개체를 일반적으로 만들거나 위에서 설명한 것 처럼 쿼리 정의 엽니다. 그런 다음 호출 하는 경우 쿼리 정의 개체에 대 한 포인터를 전달 하는 레코드 집합 개체를 작성할 [cdaorecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open)합니다. 전달 하면 쿼리 정의 열린 상태에 있어야 합니다. 자세한 내용은 클래스를 참조 하십시오. [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)합니다.  
  
 열린 상태에 있지 않으면 (쿼리 정의 대 한 가장 일반적인 사용) 레코드 집합을 만들려면 쿼리 정의 사용할 수 없습니다. 쿼리 정의 호출 하 여 열린 상태에 들어갑니다 **열고** 또는 **만들기**합니다.  
  
## <a name="external-databases"></a>외부 데이터베이스  
 쿼리 정의 개체는 외부 데이터베이스 엔진의 네이티브 SQL 언어를 사용 하는 것이 좋습니다. 예를 들어 (Microsoft SQL Server에 사용 됨) 처럼 Transact SQL 쿼리를 만들고 쿼리 정의 개체에 저장할 수 있습니다. Microsoft Jet 데이터베이스 엔진을 기반으로 하지 SQL 쿼리를 사용 해야 할 경우 외부 데이터 원본을 가리키는 연결 문자열을 제공 해야 합니다. 유효한 연결 문자열을 사용 하 여 쿼리는 데이터베이스 엔진을 건너뛰고 처리에 대 한 외부 데이터베이스 서버에 직접 쿼리를 전달 합니다.  
  
> [!TIP]
>  ODBC 테이블 작업을 수행 하는 기본 방법은 Microsoft Jet에 연결 하는 (합니다. MDB) 데이터베이스입니다.  
  
 관련된 정보에 대 한 "QueryDef 개체", "QueryDefs 컬렉션" 및 "CdbDatabase 개체" DAO SDK에서 항목을 참조 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoQueryDef`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
##  <a name="append"></a>CDaoQueryDef::Append  
 이 멤버 함수를 호출한 후에 호출 [만들기](#create) 새 쿼리 정의 개체를 만듭니다.  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>주의  
 **추가** 데이터베이스의 QueryDefs 컬렉션에 개체를 추가 하 여 쿼리 정의 데이터베이스에 저장 합니다. 추가 하지 않고 임시 개체로 쿼리 정의 사용할 수 있지만 유지 되 게 하려면를 호출 해야 **추가**합니다.  
  
 MFC 형식의 예외를 throw 한 임시 쿼리 정의 개체를 추가 하려고 하면 [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다.  
  
##  <a name="canupdate"></a>CDaoQueryDef::CanUpdate  
 쿼리 정의 수정할 수 있는지 여부를 확인 하려면이 함수를 호출-예: 이름 또는 SQL 문자열을 변경 합니다.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>반환 값  
 쿼리 정의; 수정이 허용 된 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 경우에 쿼리 정의 수정할 수 있습니다.  
  
-   읽기 전용으로 열려 있는 데이터베이스에서 따르지 않습니다.  
  
-   데이터베이스에 대 한 업데이트 권한을 해야 합니다.  
  
     이 보안 기능을 구현 하는지 여부에 따라 다릅니다. MFC 보안;에 대 한 지원을 제공 하지 않습니다. 구현 해야이 직접 DAO를 직접 호출 하거나 Microsoft Access를 사용 하 여. DAO 도움말의 "권한 속성" 항목을 참조 하십시오.  
  
##  <a name="cdaoquerydef"></a>CDaoQueryDef::CDaoQueryDef  
 생성 된 **CDaoQueryDef** 개체입니다.  
  
```  
CDaoQueryDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDatabase`  
 열기에 대 한 포인터 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 개체는 데이터베이스의 QueryDefs 컬렉션, 컬렉션에 저장 될 새 쿼리 또는 임시 쿼리를 저장할 수에 저장 하는 기존 쿼리 정의 나타낼 수 있습니다. 다음 단계에서는 쿼리 정의의 형식에 따라 달라 집니다.  
  
-   개체는 기존 쿼리 정의 나타내는 경우 해당 개체의 호출 [열려](#open) 멤버 함수를 초기화 합니다.  
  
-   개체를 저장할 새 쿼리 정의 나타내는 경우 해당 개체의 호출 [만들기](#create) 멤버 함수입니다. 이 데이터베이스의 QueryDefs 컬렉션에 개체를 추가합니다. 그런 다음 호출 `CDaoQueryDef` 개체의 특성을 설정 하는 멤버 함수입니다. 마지막으로 호출 [추가](#append)합니다.  
  
-   개체가 나타내는 임시 쿼리 정의 (데이터베이스에 저장 하지 않음), 호출 **만들기**, 쿼리 이름에 대 한 빈 문자열을 전달 합니다. 호출한 후 **만들기**, 해당 특성을 직접 설정 하 여 쿼리 정의 초기화 합니다. 호출 하지 마십시오 **추가**합니다.  
  
 쿼리 정의의 특성을 설정 하려면 사용할 수는 [SetName](#setname), [SetSQL](#setsql), [SetConnect](#setconnect), [SetODBCTimeout](#setodbctimeout), 및 [SetReturnsRecords](#setreturnsrecords) 멤버 함수입니다.  
  
 쿼리 정의 개체를 완료 하면 호출의 [닫기](#close) 멤버 함수입니다. 사용 하 여 쿼리 정의에 대 한 포인터를 사용 하도록 설정한 경우는 **삭제** 연산자를 c + + 개체를 소멸 시킵니다.  
  
##  <a name="close"></a>CDaoQueryDef::Close  
 쿼리 정의 개체를 사용 하 여 완료 하면이 멤버 함수를 호출 합니다.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>주의  
 쿼리 정의 닫으면 기본 DAO 개체를 해제 하지만 저장 된 DAO 쿼리 정의 개체 또는 c + + 소멸 시 키 지 않습니다 `CDaoQueryDef` 개체입니다. 이것이 동일 [CDaoDatabase::DeleteQueryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef), DAO (없는 경우 임시 쿼리 정의)에서 데이터베이스의 QueryDefs 컬렉션에서 쿼리 정의 삭제 하 합니다.  
  
##  <a name="create"></a>CDaoQueryDef::Create  
 이 새 저장 된 쿼리 또는 새 임시 쿼리를 만드는 함수를 호출 합니다.  
  
```  
virtual void Create(
    LPCTSTR lpszName = NULL,  
    LPCTSTR lpszSQL = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 데이터베이스에 저장 하는 쿼리의 고유 이름입니다. 문자열에 대 한 자세한 DAO 도움말의 "CreateQueryDef 메서드" 항목을 참조 합니다. 빈 문자열을 하는 기본값을 적용 하는 경우에 임시 쿼리 정의 생성 됩니다. 이러한 쿼리 QueryDefs 컬렉션에 저장 되지 않습니다.  
  
 `lpszSQL`  
 쿼리를 정의 하는 SQL 문자열입니다. 기본값을 적용 하는 경우 **NULL**, 나중에 호출 해야 [SetSQL](#setsql) 문자열을 설정 합니다. 그때 까지는 쿼리 정의 되지 않습니다. 그러나; 레코드 집합을 열려고 정의 되지 않은 쿼리를 사용할 수 있습니다. 자세한 내용은 설명 부분을 참조 합니다. SQL 문의 쿼리 정의 QueryDefs 컬렉션에 추가 하기 전에 정의 되어야 합니다.  
  
### <a name="remarks"></a>주의  
 에 이름을 전달 하는 경우 `lpszName`를 호출할 수 있습니다 [추가](#append) 데이터베이스의 QueryDefs 컬렉션에 쿼리 정의 저장 합니다. 그렇지 않으면 개체가 임시 쿼리 정의 이며 저장 되지 않습니다. 두 경우 모두 쿼리 정의에 열린 상태로 되며 하거나 만드는 데 사용할 수는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 쿼리 정의 호출 또는 개체 [Execute](#execute) 멤버 함수입니다.  
  
 SQL 문을 제공 하지 않으면 `lpszSQL`를 사용 하 여 쿼리를 실행할 수 없습니다 **Execute** 하지만 레코드 집합을 만들려면 사용할 수 있습니다. 이 경우 MFC는 레코드 집합의 기본 SQL 문을 사용합니다.  
  
##  <a name="execute"></a>CDaoQueryDef::Execute  
 쿼리 정의 개체에 정의 된 쿼리를 실행 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual void Execute(int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>매개 변수  
 `nOptions`  
 쿼리의 특징을 결정 하는 정수입니다. 관련된 내용은 DAO 도움말의 "메서드 실행" 항목을 참조 합니다. 비트 OR 연산자를 사용할 수 있습니다 ( **|**)이이 인수에 대 한 다음 상수를 결합 하 여:  
  
- **dbDenyWrite** 다른 사용자에 게 쓰기 권한을 거부 합니다.  
  
- **dbInconsistent** 일관성 없는 업데이트 합니다.  
  
- **dbConsistent** 대 한 일관적인 업데이트 합니다.  
  
- **dbSQLPassThrough** SQL 통과 합니다. 때문에 SQL 문이 ODBC 데이터베이스 처리를 위해 전달 될 수 있습니다.  
  
- **dbFailOnError** 기본값입니다. 롤백 오류가 발생 하는 경우 업데이트 하 고 오류 보고서 사용자에 게 있습니다.  
  
- **dbSeeChanges** 다른 사용자가 편집 중인 데이터를 변경 하는 경우 런타임 오류가 발생 합니다.  
  
> [!NOTE]
>  에 대 한 설명은 용어 "일관성이 없는" 및 "일관성" DAO 도움말의 "메서드 실행" 항목을 참조 합니다.  
  
### <a name="remarks"></a>주의  
 만이 방식으로 실행을 위해 사용 되는 쿼리 정의 개체는 다음 쿼리 유형 중 하나를 나타낼 수 있습니다.  
  
-   실행 쿼리  
  
-   SQL 통과 쿼리  
  
 **실행** 선택 쿼리와 같은 레코드를 반환 하는 쿼리에 대해서는 작동 하지 않습니다. **실행** 은 일반적으로 사용 대량 작업 쿼리와 같은 **업데이트**, **삽입**, 또는 **SELECT INTO**, 또는 데이터 정의 언어 (DDL) 작업에 대 한 합니다.  
  
> [!TIP]
>  Microsoft Jet에 테이블을 연결 하는 ODBC 데이터 원본을 사용 하는 기본 방법은 (합니다. MDB) 데이터베이스입니다. 자세한 내용은 DAO 도움말의 "DAO와 외부 데이터베이스에 액세스" 항목을 참조 하십시오.  
  
 호출 된 [GetRecordsAffected](#getrecordsaffected) 가장 최근의 영향을 받는 레코드 수를 결정 하는 쿼리 정의 개체의 멤버 함수 **Execute** 를 호출 합니다. 예를 들어 `GetRecordsAffected` 삭제, 업데이트 또는 삽입 작업 쿼리를 실행 하는 경우 레코드의 수에 대 한 정보를 반환 합니다. 반환 되는 개수가 cascade를 업데이트 하거나 삭제 하는 경우 관련된 테이블의 변경 내용이 적용 하는 것을 반영 되지 않습니다.  
  
 둘 모두를 포함 하는 경우 **dbInconsistent** 및 **dbConsistent** 결과 기본적으로 모두를 포함 하는 경우 또는 **dbInconsistent**합니다.  
  
 **실행** 레코드 집합을 반환 하지 않습니다. 사용 하 여 **Execute** 레코드를 선택 하는 쿼리를 사용 하면 형식의 예외를 throw 하는 MFC [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다.  
  
##  <a name="getconnect"></a>CDaoQueryDef::GetConnect  
 쿼리 정의 데이터 원본과 관련 된 연결 문자열을 가져오기 위해이 함수를 호출 합니다.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 쿼리 정의 대 한 연결 문자열을 포함 합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 ODBC 데이터 원본 및 특정 ISAM 드라이버에만 사용 됩니다. Microsoft Jet 함께 사용 하지 않는 (합니다. MDB) 데이터베이스 이 경우 `GetConnect` 빈 문자열을 반환 합니다. 자세한 내용은 참조 [SetConnect](#setconnect)합니다.  
  
> [!TIP]
>  ODBC 테이블 작업을 수행 하는 기본 방법은 연결 하는 프로그램입니다. MDB 데이터베이스입니다. 자세한 내용은 DAO 도움말의 "DAO와 외부 데이터베이스에 액세스" 항목을 참조 하십시오.  
  
 연결 문자열에 대 한 내용은 DAO 도움말에서 "연결 속성" 항목을 참조 하십시오.  
  
##  <a name="getdatecreated"></a>CDaoQueryDef::GetDateCreated  
 쿼리 정의 개체를 만든 날짜를 가져오려는이 멤버 함수를 호출 합니다.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>반환 값  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 날짜 및 쿼리 정의 만든 시간을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.  
  
##  <a name="getdatelastupdated"></a>CDaoQueryDef::GetDateLastUpdated  
 이 멤버 함수 개체를 가져와 날짜 쿼리 정의 마지막으로 업데이트 하는 호출-경우 해당 속성 중 하나라도 변경 된 해당 이름, 해당 SQL 문자열 또는 연결 문자열 등입니다.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>반환 값  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 날짜와 시간을 쿼리 정의 마지막으로 업데이트를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.  
  
##  <a name="getfieldcount"></a>CDaoQueryDef::GetFieldCount  
 쿼리의 필드의 개수를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>반환 값  
 쿼리에 정의 된 필드 수를 지정 합니다.  
  
### <a name="remarks"></a>주의  
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
 인덱스에 의해 조회에 대 한 쿼리 정의 필드 컬렉션에서 원하는 필드의&0;부터 시작 하는 인덱스입니다.  
  
 `fieldinfo`  
 에 대 한 참조는 `CDaoFieldInfo` 요청 된 정보를 반환 하는 개체입니다.  
  
 `dwInfoOptions`  
 검색할 필드에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 한 원인을 반환 하는 함수를 함께 여기에 나열 됩니다.  
  
- `AFX_DAO_PRIMARY_INFO`(기본값) 이름, 유형, 크기, 속성  
  
- `AFX_DAO_SECONDARY_INFO`더하기 기호는 기본 정보: 필요한 서 수 위치, 길이가&0; 허용, 원본 필드, 외부 이름, 원본 테이블, 데이터 정렬 순서  
  
- `AFX_DAO_ALL_INFO`기본 및 보조 정보 더하기: Default Value, 유효성 검사 텍스트 유효성 검사 규칙  
  
 `lpszName`  
 이름별으로 조회에 대 한 원하는 필드의 이름을 포함 하는 문자열입니다. 사용할 수는 [CString](../../atl-mfc-shared/reference/cstringt-class.md)합니다.  
  
### <a name="remarks"></a>주의  
 반환 되는 정보에 대 한 `fieldinfo`, 참조는 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조입니다. 이 구조는 아래 설명 된 정보에 해당 하는 멤버 `dwInfoOptions` 위에 있습니다. 한 수준의 정보를 요청 하는 경우 모든 이전 수준의 정보를 얻습니다.  
  
##  <a name="getname"></a>CDaoQueryDef::GetName  
 쿼리 정의 나타내는 쿼리의 이름을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>반환 값  
 쿼리의 이름입니다.  
  
### <a name="remarks"></a>주의  
 쿼리 정의 이름은 고유한 사용자 정의 이름입니다. 쿼리 정의 이름에 대 한 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 하십시오.  
  
##  <a name="getodbctimeout"></a>CDaoQueryDef::GetODBCTimeout  
 ODBC 데이터 원본에 쿼리 시간이 초과 되기 전에 현재 제한 시간을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
short GetODBCTimeout();
```  
  
### <a name="return-value"></a>반환 값  
 초를 쿼리 하기 전에 시간이 초과 됩니다.  
  
### <a name="remarks"></a>주의  
 이 제한 시간에 대 한 내용은 DAO 도움말에서 "ODBCTimeout 속성" 항목을 참조 합니다.  
  
> [!TIP]
>  ODBC 테이블 작업을 수행 하는 기본 방법은 Microsoft Jet에 연결 하는 (합니다. MDB) 데이터베이스입니다. 자세한 내용은 DAO 도움말의 "DAO와 외부 데이터베이스에 액세스" 항목을 참조 하십시오.  
  
##  <a name="getparametercount"></a>CDaoQueryDef::GetParameterCount  
 저장 된 쿼리에서 매개 변수 개수를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
short GetParameterCount();
```  
  
### <a name="return-value"></a>반환 값  
 쿼리에 정의 된 매개 변수 개수입니다.  
  
### <a name="remarks"></a>주의  
 `GetParameterCount`쿼리 정의에서 모든 매개 변수를 반복 하는 데 유용 합니다. 이 위해 사용 하 여 `GetParameterCount` 함께에서 [GetParameterInfo](#getparameterinfo)합니다.  
  
 관련된 정보에 대 한 "매개 변수 개체", "매개 변수 컬렉션" 및 "매개 변수 선언 ()"에서 SQL DAO 도움말 항목을 참조 합니다.  
  
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
 인덱스에 의해 조회에 대 한 쿼리 정의 매개 변수 컬렉션에서 원하는 매개 변수의&0;부터 시작 하는 인덱스입니다.  
  
 `paraminfo`  
 에 대 한 참조는 [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) 요청 된 정보를 반환 하는 개체입니다.  
  
 `dwInfoOptions`  
 매개 변수를 검색 하는 방법에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 함수를 반환 하면 어떤 함께 여기 나열 됩니다.  
  
- `AFX_DAO_PRIMARY_INFO`(기본값) 이름, 유형  
  
 `lpszName`  
 이름별으로 조회에 대 한 원하는 매개 변수 이름을 포함 하는 문자열입니다. 사용할 수는 [CString](../../atl-mfc-shared/reference/cstringt-class.md)합니다.  
  
### <a name="remarks"></a>주의  
 반환 되는 정보에 대 한 `paraminfo`, 참조는 [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) 구조입니다. 이 구조는 아래 설명 된 정보에 해당 하는 멤버 `dwInfoOptions` 위에 있습니다.  
  
 관련된 정보에 대 한 매개 변수 선언 ("SQL") DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="getparamvalue"></a>CDaoQueryDef::GetParamValue  
 쿼리 정의 매개 변수 컬렉션에 저장 된 지정된 된 매개 변수의 현재 값을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual COleVariant GetParamValue(LPCTSTR lpszName);  
virtual COleVariant GetParamValue(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 매개 변수 이름으로 조회에 대해 원하는 값의 이름입니다.  
  
 `nIndex`  
 인덱스에 의해 조회에 대 한 쿼리 정의 매개 변수 컬렉션에 있는 매개 변수의&0;부터 시작 하는 인덱스입니다. 호출 하 여이 값을 구할 수 [GetParameterCount](#getparametercount) 및 [GetParameterInfo](#getparameterinfo)합니다.  
  
### <a name="return-value"></a>반환 값  
 클래스의 개체 [COleVariant](../../mfc/reference/colevariant-class.md) 매개 변수의 값이 포함 된 합니다.  
  
### <a name="remarks"></a>주의  
 매개 변수 이름 또는 서 수 위치는 컬렉션에 액세스할 수 있습니다.  
  
 관련된 정보에 대 한 매개 변수 선언 ("SQL") DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="getrecordsaffected"></a>CDaoQueryDef::GetRecordsAffected  
 마지막 호출에 의해 영향을 받은 레코드 수를 확인 하려면이 함수를 호출 [Execute](#execute)합니다.  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>반환 값  
 영향을 받는 레코드 수입니다.  
  
### <a name="remarks"></a>주의  
 반환 되는 개수가 cascade를 업데이트 하거나 삭제 하는 경우 관련된 테이블의 변경 내용이 적용 하는 것을 반영 되지 않습니다.  
  
 관련된 내용은 DAO 도움말에서 "RecordsAffected 속성" 항목을 참조 하십시오.  
  
##  <a name="getreturnsrecords"></a>CDaoQueryDef::GetReturnsRecords  
 쿼리 정의 레코드를 반환 하는 쿼리 기반 인지 여부를 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetReturnsRecords();
```  
  
### <a name="return-value"></a>반환 값  
 레코드; 현재 레코드를 반환 하는 쿼리를 기반으로 하는 쿼리 정의 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 통과 쿼리를 SQL에만 사용 됩니다. SQL 쿼리에 대 한 자세한 내용은 참조는 [Execute](#execute) 멤버 함수입니다. SQL 통과 쿼리 사용에 대 한 자세한 내용은 참조는 [SetReturnsRecords](#setreturnsrecords) 멤버 함수입니다.  
  
 관련된 내용은 DAO 도움말의 "ReturnsRecords 속성" 항목을 참조 합니다.  
  
##  <a name="getsql"></a>CDaoQueryDef::GetSQL  
 쿼리 정의 기반이 되는 쿼리를 정의 하는 SQL 문을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetSQL();
```  
  
### <a name="return-value"></a>반환 값  
 쿼리 정의 기반이 되는 쿼리를 정의 하는 SQL 문입니다.  
  
### <a name="remarks"></a>주의  
 다음 키워드, 테이블 이름 등에 대 한 문자열을 parse 것입니다.  
  
 관련된 내용은 "SQL Property", "비교의 Microsoft Jet 데이터베이스 엔진 및 ANSI SQL" 및 "쿼리는 데이터베이스와 SQL에서 코드" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="gettype"></a>CDaoQueryDef::GetType  
 쿼리 정의의 쿼리 유형을 결정 하려면이 멤버 함수를 호출 합니다.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>반환 값  
 쿼리 정의에 정의 된 쿼리의 형식입니다. 값에 대 한 설명을 참조 하십시오.  
  
### <a name="remarks"></a>주의  
 이 쿼리 형식에에서 지정한 쿼리 정의 SQL 문자열 또는 호출 하는 기존 쿼리 정의 쿼리 정의 만들 때 설정한 [SetSQL](#setsql) 멤버 함수입니다. 이 함수에서 반환 하는 쿼리 유형을 다음 값 중 하나일 수 있습니다.  
  
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
  
- **dbQSPTBulk** 사용한 **dbQSQLPassThrough** 레코드를 반환 하지 않는 쿼리를 지정할 수 있습니다.  
  
> [!NOTE]
>  설정 하지 않는 SQL 통과 쿼리를 만들려면는 **dbSQLPassThrough** 상수입니다. 이 설정은 자동으로 Microsoft Jet 데이터베이스 엔진에 의해 쿼리 정의 개체를 만들고 연결 문자열을 설정 합니다.  
  
 SQL 문자열에 대 한 정보를 참조 하십시오. [GetSQL](#getsql)합니다. 쿼리 형식에 대 한 정보를 참조 하십시오. [Execute](#execute)합니다.  
  
##  <a name="isopen"></a>CDaoQueryDef::IsOpen  
 확인 하려면이 함수를 호출 여부는 `CDaoQueryDef` 개체가 현재 열려 있습니다.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 값은 `CDaoQueryDef` 개체는 현재 열려 있는 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 호출 하는 데 사용할 쿼리 정의 열린 상태에 있어야 [Execute](#execute) 하거나 만들 수는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체입니다. 모드로 쿼리 정의 열린 상태로 호출 하거나 [만들기](#create) (새 쿼리 정의)에 대 한 또는 [열고](#open) (기존는 쿼리 정의)에 대 한 합니다.  
  
##  <a name="m_pdatabase"></a>CDaoQueryDef::m_pDatabase  
 에 대 한 포인터는 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 쿼리 정의 개체와 연결 된 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 포인터를 사용 하 여 데이터베이스에 직접 액세스 하는 경우-예를 들어를 다른 쿼리 정의 또는 레코드 집합에 대 한 포인터를 가져올 데이터베이스의 컬렉션의 개체입니다.  
  
##  <a name="m_pdaoquerydef"></a>CDaoQueryDef::m_pDAOQueryDef  
 기본 DAO 쿼리 정의 개체에 대 한 OLE 인터페이스에 대 한 포인터를 포함합니다.  
  
### <a name="remarks"></a>주의  
 이 포인터는 완전 하 고 다른 클래스와의 일관성을 위해 제공 됩니다. 그러나 MFC DAO 쿼리 정의 보다 완벽 하 게 캡슐화 하므로 가능성이 매우 낮으므로 꼭 필요할 것입니다. 이 옵션을 사용할 수행 하는 경우 이렇게 신중 하 게-있습니다 수행 하는 것을 알 수 없는 경우 포인터의 값을 변경 하지 않는 특히 합니다.  
  
##  <a name="open"></a>CDaoQueryDef::Open  
 데이터베이스의 QueryDefs 컬렉션에 이미 저장 된 쿼리 정의 열려면이 멤버 함수를 호출 합니다.  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 열에 저장 된 쿼리 정의의 이름을 포함 하는 문자열입니다. 사용할 수는 [CString](../../atl-mfc-shared/reference/cstringt-class.md)합니다.  
  
### <a name="remarks"></a>주의  
 쿼리 정의 연 후 호출할 수 있습니다 해당 [Execute](#execute) 멤버 함수 또는 사용 하 여 만들려는 쿼리 정의 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체입니다.  
  
##  <a name="setconnect"></a>CDaoQueryDef::SetConnect  
 쿼리 정의 개체의 연결 문자열을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszConnect`  
 관련 된 연결 문자열을 포함 하는 문자열 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 연결 문자열은 ODBC 및 필요에 따라 특정 ISAM 드라이버 추가 정보를 전달 하기 위해 사용 됩니다. Microsoft Jet에 사용 되지 않습니다 (합니다. MDB) 데이터베이스입니다.  
  
> [!TIP]
>  ODBC 테이블 작업을 수행 하는 기본 방법은 연결 하는 프로그램입니다. MDB 데이터베이스입니다.  
  
 ODBC 데이터 원본에 SQL 통과 쿼리를 나타내는 쿼리 정의 실행 하기 전에 연결 문자열을 설정 `SetConnect` 호출 [SetReturnsRecords](#setreturnsrecords) 쿼리 레코드를 반환 하는지 여부를 지정 합니다.  
  
 연결 문자열의 구조 및 연결 문자열 구성의 예에 대 한 자세한 내용은 DAO 도움말에서 "연결 속성" 항목을 참조 하십시오.  
  
##  <a name="setname"></a>CDaoQueryDef::SetName  
 임시 하지 않은 쿼리 정의의 이름을 변경 하려는 경우이 멤버 함수를 호출 합니다.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 연결 된 실제적 쿼리에 대 한 새 이름을 포함 하는 문자열 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 쿼리 정의 이름은 고유한, 사용자 정의 이름입니다. 호출할 수 있습니다 `SetName` 쿼리 정의 하기 전에 개체 QueryDefs 컬렉션에 추가 됩니다.  
  
##  <a name="setodbctimeout"></a>CDaoQueryDef::SetODBCTimeout  
 ODBC 데이터 원본에 쿼리 시간 초과 되기 전의 제한 시간을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetODBCTimeout(short nODBCTimeout);
```  
  
### <a name="parameters"></a>매개 변수  
 *nODBCTimeout*  
 초를 쿼리 하기 전에 시간이 초과 됩니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수를 사용 하면 연결된 된 데이터 원본 "제한 시간입니다."에 대 한 후속 작업 (초) 기본값 재정의 네트워크 액세스 문제, 과도 한 쿼리 처리 시간 및 등으로 인해 작업 시간이 초과 될 수 있습니다. 호출 `SetODBCTimeout` 쿼리 제한 시간 값을 변경 하려는 경우이 쿼리 정의 사용 하 여 쿼리를 실행 하기 전에 합니다. (ODBC 연결을 다시 사용, 시간 제한 값 때 동일한 연결에서 모든 클라이언트에 대해 동일 합니다.)  
  
 쿼리 시간 제한의 기본값은 60 초입니다.  
  
##  <a name="setparamvalue"></a>CDaoQueryDef::SetParamValue  
 런타임에 쿼리 정의에서 매개 변수의 값을 설정 하려면이 멤버 함수를 호출 합니다.  
  
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
 매개 변수를 설정 하려는 값의 이름입니다.  
  
 `varValue`  
 값을 설정 합니다. 설명을 참조 하십시오.  
  
 `nIndex`  
 쿼리 정의 매개 변수 컬렉션에 매개 변수의 서 수 위치입니다. 호출 하 여이 값을 구할 수 [GetParameterCount](#getparametercount) 및 [GetParameterInfo](#getparameterinfo)합니다.  
  
### <a name="remarks"></a>주의  
 매개 변수 쿼리 정의 SQL 문자열의 일부로 설정 이미 있어야 합니다. 매개 변수 이름 또는 서 수 위치는 컬렉션에 액세스할 수 있습니다.  
  
 으로 설정 하려면 값을 지정 된 `COleVariant` 개체입니다. 원하는 값 및 형식에 설정 하는 방법에 대 한 내용은 프로그램 `COleVariant` 개체 클래스를 참조 하십시오. [COleVariant](../../mfc/reference/colevariant-class.md)합니다.  
  
##  <a name="setreturnsrecords"></a>CDaoQueryDef::SetReturnsRecords  
 외부 데이터베이스에 SQL 통과 쿼리를 설정 하는 과정의 일부로이 멤버 함수를 호출 합니다.  
  
```  
void SetReturnsRecords(BOOL bReturnsRecords);
```  
  
### <a name="parameters"></a>매개 변수  
 *bReturnsRecords*  
 전달 **TRUE** 외부 데이터베이스에 대 한 쿼리, 레코드를 반환 하는 경우, 그러지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 이러한 경우에는 쿼리 정의 만들고 해야 다른를 사용 하 여 해당 속성을 설정할 `CDaoQueryDef` 멤버 함수입니다. 외부 데이터베이스에 대 한 참조 [SetConnect](#setconnect)합니다.  
  
##  <a name="setsql"></a>CDaoQueryDef::SetSQL  
 쿼리 정의 실행 하는 SQL 문을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszSQL`  
 실행에 적합 한 전체 SQL 문을 포함 하는 문자열입니다. 이 문자열의 구문은 DBMS에 따라 하는 쿼리 대상입니다. Microsoft Jet 데이터베이스 엔진에서 사용 되는 구문 토론, "건물 SQL 문을 코드" DAO 도움말의 항목을 참조 합니다.  
  
### <a name="remarks"></a>주의  
 일반적인 사용 `SetSQL` 는 통과 SQL 쿼리에서 사용 하기 위해 쿼리 정의 개체를 설정 합니다. (대상 DBMS에서 SQL 통과 쿼리 구문의 DBMS에 대 한 설명서 참조).  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset 클래스](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoDatabase 클래스](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoException 클래스](../../mfc/reference/cdaoexception-class.md)

