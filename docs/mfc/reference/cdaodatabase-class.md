---
title: "CDaoDatabase 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoDatabase
- AFXDAO/CDaoDatabase
- AFXDAO/CDaoDatabase::CDaoDatabase
- AFXDAO/CDaoDatabase::CanTransact
- AFXDAO/CDaoDatabase::CanUpdate
- AFXDAO/CDaoDatabase::Close
- AFXDAO/CDaoDatabase::Create
- AFXDAO/CDaoDatabase::CreateRelation
- AFXDAO/CDaoDatabase::DeleteQueryDef
- AFXDAO/CDaoDatabase::DeleteRelation
- AFXDAO/CDaoDatabase::DeleteTableDef
- AFXDAO/CDaoDatabase::Execute
- AFXDAO/CDaoDatabase::GetConnect
- AFXDAO/CDaoDatabase::GetName
- AFXDAO/CDaoDatabase::GetQueryDefCount
- AFXDAO/CDaoDatabase::GetQueryDefInfo
- AFXDAO/CDaoDatabase::GetQueryTimeout
- AFXDAO/CDaoDatabase::GetRecordsAffected
- AFXDAO/CDaoDatabase::GetRelationCount
- AFXDAO/CDaoDatabase::GetRelationInfo
- AFXDAO/CDaoDatabase::GetTableDefCount
- AFXDAO/CDaoDatabase::GetTableDefInfo
- AFXDAO/CDaoDatabase::GetVersion
- AFXDAO/CDaoDatabase::IsOpen
- AFXDAO/CDaoDatabase::Open
- AFXDAO/CDaoDatabase::SetQueryTimeout
- AFXDAO/CDaoDatabase::m_pDAODatabase
- AFXDAO/CDaoDatabase::m_pWorkspace
dev_langs:
- C++
helpviewer_keywords:
- CDaoDatabase [MFC], CDaoDatabase
- CDaoDatabase [MFC], CanTransact
- CDaoDatabase [MFC], CanUpdate
- CDaoDatabase [MFC], Close
- CDaoDatabase [MFC], Create
- CDaoDatabase [MFC], CreateRelation
- CDaoDatabase [MFC], DeleteQueryDef
- CDaoDatabase [MFC], DeleteRelation
- CDaoDatabase [MFC], DeleteTableDef
- CDaoDatabase [MFC], Execute
- CDaoDatabase [MFC], GetConnect
- CDaoDatabase [MFC], GetName
- CDaoDatabase [MFC], GetQueryDefCount
- CDaoDatabase [MFC], GetQueryDefInfo
- CDaoDatabase [MFC], GetQueryTimeout
- CDaoDatabase [MFC], GetRecordsAffected
- CDaoDatabase [MFC], GetRelationCount
- CDaoDatabase [MFC], GetRelationInfo
- CDaoDatabase [MFC], GetTableDefCount
- CDaoDatabase [MFC], GetTableDefInfo
- CDaoDatabase [MFC], GetVersion
- CDaoDatabase [MFC], IsOpen
- CDaoDatabase [MFC], Open
- CDaoDatabase [MFC], SetQueryTimeout
- CDaoDatabase [MFC], m_pDAODatabase
- CDaoDatabase [MFC], m_pWorkspace
ms.assetid: 8ff5b342-964d-449d-bef1-d0ff56aadf6d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 48646e0635098aceea957f93015a5de93515096d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdaodatabase-class"></a>CDaoDatabase 클래스
데이터 작업을 할 수 있는 통로인 데이터베이스에 대한 연결을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDaoDatabase : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoDatabase::CDaoDatabase](#cdaodatabase)|`CDaoDatabase` 개체를 생성합니다. 호출 **열려** 개체는 데이터베이스에 연결 하려면.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoDatabase::CanTransact](#cantransact)|데이터베이스에서 트랜잭션을 지원 하면 0이 아닌 값을 반환 합니다.|  
|[CDaoDatabase::CanUpdate](#canupdate)|0이 아닌 경우 반환 된 `CDaoDatabase` 개체를 업데이트할 수 (읽기 전용이 아닌).|  
|[CDaoDatabase::Close](#close)|데이터베이스 연결을 닫습니다.|  
|[CDaoDatabase::Create](#create)|기본 DAO 데이터베이스 개체를 만들고 초기화는 `CDaoDatabase` 개체입니다.|  
|[CDaoDatabase::CreateRelation](#createrelation)|데이터베이스에서 테이블 간의 새 관계를 정의합니다.|  
|[CDaoDatabase::DeleteQueryDef](#deletequerydef)|데이터베이스의 QueryDefs 컬렉션에 저장 하는 쿼리 정의 개체를 삭제 합니다.|  
|[CDaoDatabase::DeleteRelation](#deleterelation)|데이터베이스에서 테이블 간의 기존 관계를 삭제합니다.|  
|[CDaoDatabase::DeleteTableDef](#deletetabledef)|데이터베이스에 테이블의 정의 삭제합니다. 실제 테이블 및 모든 관련 데이터를 삭제합니다.|  
|[CDaoDatabase::Execute](#execute)|실행 쿼리를 실행합니다. 호출 **Execute** 에 결과 반환 하는 쿼리 예외를 throw 합니다.|  
|[CDaoDatabase::GetConnect](#getconnect)|연결 하는 데 사용 되는 연결 문자열을 반환 된 `CDaoDatabase` 데이터베이스에는 개체입니다. ODBC에 사용 합니다.|  
|[CDaoDatabase::GetName](#getname)|현재 사용 중인 데이터베이스의 이름을 반환 합니다.|  
|[CDaoDatabase::GetQueryDefCount](#getquerydefcount)|데이터베이스에 대해 정의 된 쿼리의 수를 반환 합니다.|  
|[CDaoDatabase::GetQueryDefInfo](#getquerydefinfo)|데이터베이스에 정의 된 지정 된 쿼리에 대 한 정보를 반환 합니다.|  
|[CDaoDatabase::GetQueryTimeout](#getquerytimeout)|반환 (초) 후 데이터베이스 쿼리 작업 시간이 초과 됩니다. 영향을 줌 이후의 모든 열, 새로 추가, 업데이트 및 운영 및 ODBC 데이터 원본에 대 한 다른 작업 (전용)와 같은 편집 **Execute** 호출 합니다.|  
|[CDaoDatabase::GetRecordsAffected](#getrecordsaffected)|마지막 업데이트에 의해 영향을 받는 레코드 수가 반환 편집 또는 추가 작업을 호출 하 여 **Execute**합니다.|  
|[CDaoDatabase::GetRelationCount](#getrelationcount)|데이터베이스의 테이블 간에 정의 된 관계 수를 반환 합니다.|  
|[CDaoDatabase::GetRelationInfo](#getrelationinfo)|데이터베이스의 테이블 간에 정의 된 지정 된 관계에 대 한 정보를 반환 합니다.|  
|[CDaoDatabase::GetTableDefCount](#gettabledefcount)|데이터베이스에 정의 된 테이블을 반환 합니다.|  
|[CDaoDatabase::GetTableDefInfo](#gettabledefinfo)|데이터베이스에 지정된 된 테이블에 대 한 정보를 반환합니다.|  
|[CDaoDatabase::GetVersion](#getversion)|데이터베이스에 연결 된 데이터베이스 엔진의 버전을 반환 합니다.|  
|[CDaoDatabase::IsOpen](#isopen)|0이 아닌 경우 반환 된 `CDaoDatabase` 개체가 현재 데이터베이스에 연결 되어 있습니다.|  
|[CDaoDatabase::Open](#open)|데이터베이스에 연결이 됩니다.|  
|[CDaoDatabase::SetQueryTimeout](#setquerytimeout)|설정 (초) 후 데이터베이스 쿼리 (ODBC 데이터 소스에만 해당)에 대해 작업 시간이 초과 됩니다. 열고 하 새로 추가 업데이트 및 삭제 작업 하는 모든 후속에 영향을 줍니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoDatabase::m_pDAODatabase](#m_pdaodatabase)|기본 DAO 데이터베이스 개체에 대 한 포인터입니다.|  
|[CDaoDatabase::m_pWorkspace](#m_pworkspace)|에 대 한 포인터는 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 데이터베이스를 포함 하는 트랜잭션 공간을 정의 하는 개체입니다.|  
  
## <a name="remarks"></a>설명  
 지원 되는 데이터베이스 형식에 대 한 정보를 참조 하십시오.는 [GetName](../../mfc/reference/cdaoworkspace-class.md#getname) 멤버 함수입니다. 하나 이상 포함할 수도 있습니다 `CDaoDatabase` 지정 된 "작업 영역,"가 나타내는 개체를 한 번에 활성화할는 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 개체입니다. 작업 영역 데이터베이스 컬렉션 이라고 하는 열려 있는 데이터베이스 개체의 컬렉션을 유지 합니다.  
  
> [!NOTE]
>  MFC DAO 데이터베이스 클래스는 ODBC를 기반으로 하는 MFC 데이터베이스 클래스 별개입니다. 모든 DAO 데이터베이스 클래스 이름이 "CDao" 접두사가 있습니다. 클래스 `CDaoDatabase` ODBC 클래스의 것과 비슷한 인터페이스를 제공 [CDatabase](../../mfc/reference/cdatabase-class.md)합니다. 주요 차이점은 `CDatabase` DBMS를 DBMS에 대 한 ODBC Open Database Connectivity () 및 ODBC 드라이버를 통해 액세스 합니다. `CDaoDatabase`Microsoft Jet 데이터베이스 엔진에 따라 데이터 액세스 개체 (DAO)를 통해 데이터에 액세스 합니다. 일반적으로 기반으로 DAO MFC 클래스는 ODBC;에 따라 MFC 클래스 보다 더욱 강력한 DAO 기반 클래스를 통해 자신의 데이터베이스 엔진을 통해 ODBC 드라이버를 포함 한 데이터를 액세스할 수 있습니다. 또한 DAO 기반 클래스를 직접 DAO 호출 하지 않고는 클래스를 통해 테이블을 추가 하는 등의 데이터 정의 언어 (DDL) 작업을 지원 합니다.  
  
## <a name="usage"></a>사용법  
 레코드 집합 개체를 만들 때 암시적으로 데이터베이스 개체를 만들 수 있습니다. 하지만 데이터베이스 개체를 명시적으로 만들 수도 있습니다. 기존 데이터베이스를 명시적으로 사용 하려면 `CDaoDatabase`, 다음 중 하나를 수행 합니다.  
  
-   생성 된 `CDaoDatabase` 열린에 대 한 포인터를 전달 하는 개체 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 개체입니다.  
  
-   생성 또는 `CDaoDatabase` (MFC 임시 작업 영역 개체를 생성 하는 데 사용) 작업 영역을 지정 하지 않고 개체입니다.  
  
 만들려면 새 Microsoft Jet (합니다. MDB) 데이터베이스를 생성 한 `CDaoDatabase` 개체와 호출 해당 [만들기](#create) 멤버 함수입니다. 수행 *하지* 호출 **열려** 후 **만들기**합니다.  
  
 기존 데이터베이스를 열려면 생성 한 `CDaoDatabase` 개체와 호출 해당 [열고](#open) 멤버 함수입니다.  
  
 이러한 기술 중 하나는 작업 영역 데이터베이스 컬렉션에 DAO 데이터베이스 개체를 추가 하 고 데이터 연결을 엽니다. 그런 다음 작성할 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), 또는 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 이러한 개체에 대 한 생성자를 전달 하는 연결 된 데이터베이스에 대해 작업 개체는 에 대 한 포인터에 `CDaoDatabase` 개체입니다. 호출 작업을 마치면 연결을 사용 하는 [닫기](#close) 멤버 함수를 파괴는 `CDaoDatabase` 개체입니다. **닫기** 이전에 닫지 않은 모든 레코드 집합을 닫습니다.  
  
## <a name="transactions"></a>트랜잭션  
 데이터베이스 트랜잭션 처리 작업 영역에서 제공 되는-참조는 [BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans), [CommitTrans](../../mfc/reference/cdaoworkspace-class.md#committrans), 및 [롤백](../../mfc/reference/cdaoworkspace-class.md#rollback) 클래스의 멤버 함수 `CDaoWorkspace` .  
  
## <a name="odbc-connections"></a>ODBC 연결  
 Microsoft Jet에 외부 테이블을 연결 하는 ODBC 데이터 원본으로 작업 하는 것이 좋습니다 (합니다. MDB) 데이터베이스입니다.  
  
## <a name="collections"></a>컬렉션  
 각 데이터베이스 테이블 정의 쿼리 정의 레코드 집합 및 관계 개체의 컬렉션을 유지 관리합니다. 클래스 `CDaoDatabase` 이러한 개체를 조작 하기 위한 멤버 함수를 제공 합니다.  
  
> [!NOTE]
>  개체는 MFC 데이터베이스 개체에 있는 DAO에 저장 됩니다. MFC 개체 관계 아니라 테이블 정의 쿼리 및 레코드 집합 개체에 대 한 클래스를 제공합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoDatabase`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
##  <a name="cantransact"></a>CDaoDatabase::CanTransact  
 데이터베이스 트랜잭션을 허용 하는지 여부를 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL CanTransact();
```  
  
### <a name="return-value"></a>반환 값  
 데이터베이스에서 트랜잭션을;를 지원 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 트랜잭션은은 데이터베이스의 작업 영역에서 관리 됩니다.  
  
##  <a name="canupdate"></a>CDaoDatabase::CanUpdate  
 확인 하려면이 함수를 호출 여부는 `CDaoDatabase` 개체 업데이트를 허용 합니다.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우에는 `CDaoDatabase` 업데이트를 허용 하는 개체, 그렇지 않으면 0 전달 하거나 사용자가 나타내는 **TRUE** 에 `bReadOnly` 열릴 때는 `CDaoDatabase` 개체나 데이터베이스 자체는 읽기 전용입니다. 참조는 [열려](#open) 멤버 함수입니다.  
  
### <a name="remarks"></a>설명  
 데이터베이스 업데이트 가능성에 대 한 내용은, DAO 도움말의 "업데이트할 수 있는 속성" 항목을 참조 하십시오.  
  
##  <a name="cdaodatabase"></a>CDaoDatabase::CDaoDatabase  
 `CDaoDatabase` 개체를 생성합니다.  
  
```  
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *pWorkspace*  
 에 대 한 포인터는 `CDaoWorkspace` 은 새 데이터베이스 개체를 포함 하는 개체입니다. 기본값에 동의 하면 **NULL**, 생성자 만듭니다 임시 `CDaoWorkspace` 기본 DAO 작업 영역을 사용 하는 개체입니다. 작업 영역 개체를 통해에 대 한 포인터를 가져올 수 있습니다는 [m_pWorkspace](#m_pworkspace) 데이터 멤버입니다.  
  
### <a name="remarks"></a>설명  
 새 Microsoft Jet 만들려는 경우에 개체를 생성 한 후 (합니다. MDB), 데이터베이스 개체의 [만들기](#create) 멤버 함수입니다. 인 경우 대신 개체의 호출 기존 데이터베이스를 열어 [열려](#open) 멤버 함수입니다.  
  
 호출 해야 개체를 마치면 해당 [닫기](#close) 멤버 함수를 삭제 합니다는 `CDaoDatabase` 개체입니다.  
  
 포함을 편리 하 게 찾을 수 있습니다는 `CDaoDatabase` 문서 클래스의 개체입니다.  
  
> [!NOTE]
>  A `CDaoDatabase` 열 경우 개체도 암시적으로 생성 한 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체는 기존에 포인터를 전달 하지 않고 `CDaoDatabase` 개체입니다. 레코드 집합 개체를 닫을 때이 데이터베이스 개체가 닫혀 있습니다.  
  
##  <a name="close"></a>CDaoDatabase::Close  
 데이터베이스에서 연결을 끊고 닫고 모든 열려 있는 레코드 집합이, 테이블 정의 데이터베이스에 연결 된 쿼리 정의 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>설명  
 이러한 개체를 직접이 멤버 함수를 호출 하기 전에 것이 좋습니다. 닫기는 `CDaoDatabase` 개체는 연결 된 데이터베이스 컬렉션에서 제거 [작업 영역](../../mfc/reference/cdaoworkspace-class.md)합니다. 때문에 **닫기** 제거 하지 않습니다는 `CDaoDatabase` 개체를 열거나 동일한 데이터베이스 또는 다른 데이터베이스 개체를 다시 사용할 수 있습니다.  
  
> [!CAUTION]
>  호출의 [업데이트](../../mfc/reference/cdaorecordset-class.md#update) (있을 경우 보류 중인 편집) 멤버 함수 및 **닫습니다** 데이터베이스를 종결 하기 전에 모든 열려 recordset 개체에 멤버 함수입니다. 선언 하는 함수를 종료 하면 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 또는 `CDaoDatabase` 스택, 개체 데이터베이스가 닫혀, 저장 되지 않은 모든 변경 내용이 손실, 보류 중인 모든 트랜잭션을 롤백합니다 및 데이터에 보류 중인 모든 편집 내용이 손실 됩니다.  
  
> [!CAUTION]
>  모든 레코드 집합 개체는 열기, 데이터베이스 개체를 닫으려고 또는 해당 특정 작업 영역에 속하는 모든 데이터베이스 개체가 열려 있는 동안 작업 영역 개체를 닫기 하려고 하면 해당 레코드 집합 개체를 닫고 수 있는 모든 보류 중인 업데이트 또는 편집 롤백됩니다. 그에 해당 하는 데이터베이스 개체 열려 있는 동안 작업 영역 개체를 닫기 하려고 하면 작업을 닫는 중 닫히지 않은 recordset 개체에 발생할 수 있습니다. 해당 특정 작업 공간 개체에 속하는 모든 데이터베이스 개체를 닫습니다. 데이터베이스 개체를 닫지 않는 경우 MFC 디버그 빌드에 어설션 오류를 보고 합니다.  
  
 데이터베이스 개체는 함수 범위 외부에 정의 된 닫지 않고 함수를 종료 하는 경우 데이터베이스 개체가 명시적으로 닫을 때까지 유지 됩니다 또는 정의 된 모듈의 범위를 벗어납니다.  
  
##  <a name="create"></a>CDaoDatabase::Create  
 만들려면 새 Microsoft Jet (합니다. MDB)를 생성 하면이 멤버 함수 호출, 데이터베이스는 `CDaoDatabase` 개체입니다.  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    LPCTSTR lpszLocale = dbLangGeneral,  
    int dwOptions = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 사용자가 만드는 데이터베이스 파일의 이름을 나타내는 문자열 식입니다. 수의 전체 경로 및 파일 이름, 예: "c:\\\MYDB 합니다. MDB "입니다. 이름을 제공 해야 합니다. 파일 이름 확장명을 지정 하지 마십시오 하는 경우. MDB 추가 됩니다. 네트워크 경로 네트워크에 균일 한 명명 규칙 (UNC)를 지 원하는 경우와 같은 지정할 수도 있습니다 "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB"입니다. Microsoft Jet만 (합니다. 이 멤버 함수를 사용 하 여 MDB) 데이터베이스 파일을 만들 수 있습니다. (때문에 문자열 리터럴에 필요한 이중 백슬래시 "\\" c + + 이스케이프 문자입니다.)  
  
 `lpszLocale`  
 데이터베이스를 만드는 중에 사용할 정렬 순서를 지정 하는 데 사용 하는 문자열 식입니다. 기본값은 **dbLangGeneral**합니다. 가능한 값은 다음과 같습니다.  
  
- **dbLangGeneral** 영어, 독일어, 프랑스어, 포르투갈어, 이탈리아어, 및 현대 스페인어  
  
- **dbLangArabic** 아랍어  
  
- **dbLangCyrillic** 러시아어  
  
- **dbLangCzech** 체코어  
  
- **dbLangDutch** 네덜란드어  
  
- **dbLangGreek** 그리스어  
  
- **dbLangHebrew** 히브리어  
  
- **dbLangHungarian** 헝가리어  
  
- **dbLangIcelandic** 아이슬란드어  
  
- **dbLangNordic** 북유럽 언어 (Microsoft Jet 데이터베이스 엔진 버전 1.0만)  
  
- **dbLangNorwdan** 노르웨이어 및 덴마크어  
  
- **dbLangPolish** 폴란드어  
  
- **dbLangSpanish** 스페인어  
  
- **dbLangSwedfin** 스웨덴어 및 핀란드어  
  
- **dbLangTurkish** 터키어  
  
 `dwOptions`  
 하나 이상의 옵션을 나타내는 정수입니다. 가능한 값은 다음과 같습니다.  
  
- **dbEncrypt** 암호화 된 데이터베이스를 만듭니다.  
  
- **dbVersion10** Microsoft Jet 데이터베이스 버전 1.0과 함께 데이터베이스를 만듭니다.  
  
- **dbVersion11** Microsoft Jet 데이터베이스 버전 1.1 있는 데이터베이스를 만듭니다.  
  
- **dbVersion20** Microsoft Jet 데이터베이스 버전 2.0에 있는 데이터베이스를 만듭니다.  
  
- **dbVersion30** Microsoft Jet 데이터베이스 버전 3.0 있는 데이터베이스를 만듭니다.  
  
 암호화 상수를 생략 하면 암호화 되지 않은 데이터베이스 생성 됩니다. 하나의 버전 상수를 지정할 수 있습니다. 버전 상수를 생략 하면 Microsoft Jet 데이터베이스 버전 3.0을 사용 하는 데이터베이스 생성 됩니다.  
  
> [!CAUTION]
>  데이터베이스 암호화 되지 않은 경우 가능한 경우 직접 데이터베이스를 구성 하는 이진 디스크 파일을 읽을 수의 사용자/암호 보안을 구현 하는 경우에입니다.  
  
### <a name="remarks"></a>설명  
 **만들** 데이터베이스 파일 및 기본 DAO 데이터베이스 개체를 만들고 c + + 개체를 초기화 합니다. 개체는 연결 된 작업 영역 데이터베이스 컬렉션에 추가 됩니다. 데이터베이스 개체가 열린 상태입니다. 호출 하지 마십시오 **열려** 후 **만들기**합니다.  
  
> [!NOTE]
>  와 **만들기**, Microsoft Jet만 만들 수 있습니다 (합니다. 데이터베이스 MDB)입니다. ODBC 데이터베이스 또는 ISAM 데이터베이스를 만들 수 없습니다.  
  
##  <a name="createrelation"></a>CDaoDatabase::CreateRelation  
 데이터베이스의 기본 테이블의 하나 이상의 필드와 있는 외래 테이블 (데이터베이스에 다른 테이블)의 하나 이상의 필드 간 관계를 설정 하려면이 함수를 호출 합니다.  
  
```  
void CreateRelation(
    LPCTSTR lpszName,  
    LPCTSTR lpszTable,  
    LPCTSTR lpszForeignTable,  
    long lAttributes,  
    LPCTSTR lpszField,  
    LPCTSTR lpszForeignField);  
  
void CreateRelation(CDaoRelationInfo& relinfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 Relation 개체의 고유 이름입니다. 이름은 문자로 시작 해야 하며 최대 40 자까지 포함할 수 있습니다. 숫자를 포함할 수 있습니다 및 밑줄 문자는 문장 부호 또는 공백을 포함할 수 없습니다.  
  
 `lpszTable`  
 관계에서 기본 테이블의 이름입니다. MFC는 테이블이 존재 하지 않는 형식의 예외를 throw [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다.  
  
 `lpszForeignTable`  
 관계에서 외래 테이블의 이름입니다. MFC는 테이블이 존재 하지 않는 형식의 예외를 throw `CDaoException`합니다.  
  
 `lAttributes`  
 관계 형식에 대 한 정보를 포함 하는 long 값입니다. 무엇 보다도 참조 무결성 적용 하려면이 값을 사용할 수 있습니다. 비트 OR 연산자를 사용할 수 있습니다 ( **&#124;**) (으로 조합 적합)는 다음 값 중 하나를 결합 하 합니다.  
  
- **dbRelationUnique** 한 일 관계입니다.  
  
- **dbRelationDontEnforce** 관계가 않습니다 (참조 무결성)를 적용 합니다.  
  
- **dbRelationInherited** 관계는 두 개의 연결 된 테이블을 포함 하는 고정 데이터베이스에 존재 합니다.  
  
- **중** 계단식 업데이트를 수행 합니다 (연속 변경에 대 한 자세한에 대 한 설명 참조).  
  
- **dbRelationDeleteCascade** 삭제 연계 됩니다.  
  
 *lpszField*  
 기본 테이블에 있는 필드의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터 (로 명명 `lpszTable`).  
  
 *lpszForeignField*  
 외래 테이블에 있는 필드의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터 (로 명명 `lpszForeignTable`).  
  
 *relinfo*  
 에 대 한 참조는 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) 만들려는 관계에 대 한 정보를 포함 합니다.  
  
### <a name="remarks"></a>설명  
 관계 쿼리 또는 외부 데이터베이스에서 연결된 된 테이블을 포함할 수 없습니다.  
  
 관계의 두 테이블의 필드 하나에 포함 되어 있을 경우 첫 번째 버전의 함수를 사용 합니다. 관계에 여러 필드가 포함 되어 있을 경우 두 번째 버전을 사용 합니다. 관계에는 필드의 최대 수는 14입니다.  
  
 이 작업은 원본 DAO 관계 개체를 만듭니다. 하지만 관계 개체의 MFC의 캡슐화 클래스 내에 포함 되어 있으므로 MFC 구현 정보는 `CDaoDatabase`합니다. MFC는 관계식에 대 한 클래스를 제공 하지 않습니다.  
  
 개체의 하위 작업을 활성화 하는 특성 관계를 설정 하면 데이터베이스 엔진이 자동으로 업데이트 하거나이 관련된 기본 키 테이블에 변경 될 때 하나 이상의 다른 테이블에서 레코드를 삭제 합니다.  
  
 예를 들어 Customers 테이블과 Orders 테이블 간의 cascade delete 관계를 설정 합니다. Customers 테이블에서 레코드를 삭제 하면 해당 고객에 게 관련 된 Orders 테이블의 레코드 삭제 됩니다. 또한, 주문 테이블과 다른 테이블 간의 cascade delete 관계를 설정 하는 경우 Customers 테이블에서 레코드를 삭제 하면 해당 테이블의 레코드 삭제 자동으로 됩니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "CreateRelation Method" 항목을 참조 합니다.  
  
##  <a name="deletequerydef"></a>CDaoDatabase::DeleteQueryDef  
 지정 된 쿼리 정의 삭제 하려면이 함수를 호출-쿼리 저장-에서 `CDaoDatabase` QueryDefs 개체의 컬렉션입니다.  
  
```  
void DeleteQueryDef(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 삭제 하는 저장 된 쿼리의 이름입니다.  
  
### <a name="remarks"></a>설명  
 그 후에 쿼리 하는 데이터베이스에 더 이상 정의 됩니다.  
  
 쿼리 정의 개체를 생성 하는 방법에 대 한 내용은 클래스를 참조 하십시오. [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)합니다. 특정와 연결 하는 쿼리 정의 개체는 `CDaoDatabase` 를 생성할 때 개체는 `CDaoQueryDef` 개체, 데이터베이스 개체에 대 한 포인터 전달 합니다.  
  
##  <a name="deleterelation"></a>CDaoDatabase::DeleteRelation  
 데이터베이스 개체의 Relations 컬렉션에서 기존 관계를 삭제 하려면이 함수를 호출 합니다.  
  
```  
void DeleteRelation(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 삭제할 관계의 이름입니다.  
  
### <a name="remarks"></a>설명  
 그런 다음 관계를 더 이상 존재합니다.  
  
 관련된 정보에 대 한 "Delete 메서드" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="deletetabledef"></a>CDaoDatabase::DeleteTableDef  
 지정된 된 테이블 및 모든 해당 데이터를 삭제 하려면이 멤버 함수 호출의 `CDaoDatabase` 개체의 TableDefs 컬렉션입니다.  
  
```  
void DeleteTableDef(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 삭제할 테이블 정의의 이름입니다.  
  
### <a name="remarks"></a>설명  
 그런 다음 해당 테이블은 더 이상 데이터베이스에 정의 됩니다.  
  
> [!NOTE]
>  매우를 시스템 테이블을 삭제 하지 않도록 주의 해야 합니다.  
  
 테이블 정의 개체를 생성 하는 방법에 대 한 내용은 클래스를 참조 하십시오. [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)합니다. 테이블 정의 개체는 특정와 연결 하는 `CDaoDatabase` 를 생성할 때 개체는 `CDaoTableDef` 개체, 데이터베이스 개체에 대 한 포인터 전달 합니다.  
  
 관련된 정보에 대 한 "Delete 메서드" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="execute"></a>CDaoDatabase::Execute  
 실행 쿼리를 실행 하거나 데이터베이스에서 SQL 문을 실행 하려면이 멤버 함수를 호출 합니다.  
  
```  
void Execute(
    LPCTSTR lpszSQL,  
    int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszSQL`  
 실행 하는 유효한 SQL 명령이 포함 된 null로 끝나는 문자열에 대 한 포인터입니다.  
  
 `nOptions`  
 쿼리의 무결성에 관련 된 옵션을 지정 하는 정수입니다. 비트 OR 연산자를 사용할 수 있습니다 ( **&#124;**) 다음 상수 중 하나를 결합 하 (적합 한 조합을 제공-예를 들어 사용자는 결합 하지 **dbInconsistent** 와**dbConsistent**):  
  
- **dbDenyWrite** 다른 사용자에 게 쓰기 권한을 거부 합니다.  
  
- **dbInconsistent** 업데이트 일관성 없음 (기본값).  
  
- **dbConsistent** 업데이트 일관성.  
  
- **dbSQLPassThrough** SQL 통과 합니다. SQL 문 처리에 대 한 ODBC 데이터 원본에 전달 하도록 하면 됩니다.  
  
- **dbFailOnError** 오류가 발생 하는 경우 업데이트를 롤백합니다.  
  
- **dbSeeChanges** 다른 사용자가 편집 중인 데이터를 변경 하는 경우 런타임 오류가 발생 합니다.  
  
> [!NOTE]
>  두 **dbInconsistent** 및 **dbConsistent** 포함 되어 있거나 둘 다 포함 된 경우 결과가 기본값입니다. 에 대 한 설명은이 상수 DAO 도움말의 "메서드 실행" 항목을 참조 합니다.  
  
### <a name="remarks"></a>설명  
 **실행** 실행 쿼리 또는 결과 반환 하지 않는 통과 쿼리를 SQL에 대해서만 작동 합니다. 레코드를 반환 하는 select 쿼리에 작동 하지 않습니다.  
  
 정 및 실행 쿼리에 대 한 정보를 "실행 쿼리" 및 DAO 도움말의 "메서드 실행" 항목을 참조 합니다.  
  
> [!TIP]
>  구문상으로 정확한 SQL 문 및 적절 한 사용 권한이 제공 되는 **Execute** 멤버 함수도 실패 하지 것입니다. 그렇지 않으면 단일 행을 수정 되거나 삭제 될 수 있습니다. 따라서 항상 사용는 **dbFailOnError** 옵션을 사용 하는 경우는 **Execute** 멤버 함수를 쿼리 삭제 또는 업데이트를 실행 합니다. 이 옵션을 사용 하면 형식의 예외를 throw 하는 MFC [CDaoException](../../mfc/reference/cdaoexception-class.md) 영향을 받는 레코드 수 없도록 잠기지 및 업데이트 하거나 삭제할 수 없는 경우 성공한 모든 변경 내용이 롤백됩니다. 항상 호출할 수 있는 참고 `GetRecordsAffected` 레코드 개수 영향을 볼 수 있습니다.  
  
 호출 된 [GetRecordsAffected](#getrecordsaffected) 가장 최근의 영향을 받는 레코드 수를 확인 하려면 데이터베이스 개체의 멤버 함수 **Execute** 호출 합니다. 예를 들어 `GetRecordsAffected` 삭제, 업데이트 또는 삽입 작업 쿼리를 실행 하는 경우 레코드의 수에 대 한 정보를 반환 합니다. 반환 된 수는 cascade를 업데이트 하거나 삭제 하는 경우 관련된 테이블의 변경 내용이 적용 반영 되지 않습니다.  
  
 **실행** 레코드 집합을 반환 하지 않습니다. 사용 하 여 **Execute** 레코드를 선택 하는 쿼리에 MFC 형식의 예외를 throw 하면 `CDaoException`합니다. (없을 없는 `ExecuteSQL` 유사 멤버 함수 `CDatabase::ExecuteSQL`.)  
  
##  <a name="getconnect"></a>CDaoDatabase::GetConnect  
 연결 하는 데 사용 되는 연결 문자열을 검색 하려면이 멤버 함수 호출의 `CDaoDatabase` ODBC 또는 ISAM 데이터베이스에는 개체입니다.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>반환 값  
 경우에 연결 문자열 [열려](#open) ODBC 데이터 원본에서 성공적으로 호출 않았으면 빈 문자열입니다. For Microsoft Jet (합니다. MDB) 데이터베이스 문자열은 항상 비어 사용 하도록 설정 하지 않으면는 **dbSQLPassThrough** 함께 사용 하는 옵션은 [Execute](#execute) 멤버 함수 또는 레코드 집합을 여는 데 사용 합니다.  
  
### <a name="remarks"></a>설명  
 열려 있는 데이터베이스 또는 통과 쿼리를 사용 하는 데이터베이스의 원본에 대 한 정보를 제공 하는 문자열입니다. 데이터베이스 유형 지정자와 세미콜론으로 구분 된 0 개 이상의 매개 변수에 연결 문자열 구성 됩니다.  
  
> [!NOTE]
>  MFC DAO 클래스를 사용 하 여 ODBC 통해 데이터 원본에 연결 하려면 연결된 된 테이블을 통한 연결 보다 덜 효율적입니다.  
  
> [!NOTE]
>  연결 문자열은 ODBC 및 필요에 따라 특정 ISAM 드라이버 추가 정보를 전달 하기 위해 사용 됩니다. 에 사용 되지 않습니다. MDB 데이터베이스입니다. Microsoft Jet 데이터베이스 기본 테이블에 대 한 연결 문자열은 빈 문자열 ("") 사용 하는 경우 해당 SQL 통과 쿼리의 위의 반환 값에서 설명 된 대로 제외 하 고 있습니다.  
  
 참조는 [열려](#open) 멤버 함수에 대 한 설명은 어떻게 연결 문자열이 생성 됩니다. 연결 문자열 설정 되 면는 **열려** 호출을 사용할 수 있습니다 나중 유형, 경로, 데이터베이스의 사용자 ID, 암호 또는 ODBC 데이터 원본을 확인 하려면 설정을 확인 하도록 합니다.  
  
##  <a name="getname"></a>CDaoDatabase::GetName  
 이 기존 데이터베이스 파일의 이름을 현재 열려 있는 데이터베이스의 이름 또는 등록 된 ODBC 데이터 원본의 이름을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 데이터베이스의 파일 이름과 전체 경로 그렇지 않으면 빈 [CString](../../atl-mfc-shared/reference/cstringt-class.md)합니다.  
  
### <a name="remarks"></a>설명  
 네트워크에서 일정 한 명명 규칙 (UNC)를 지 원하는 네트워크 경로 지정할 수도 있습니다-예를 들어 "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB 합니다. MDB "입니다. (때문에 문자열 리터럴에 필요한 이중 백슬래시 "\\" c + + 이스케이프 문자입니다.)  
  
 예를 들어 제목에는이 이름이 표시 하려면 될 수 있습니다. 이름을 검색 하는 동안 오류가 발생 하는 경우 MFC 형식의 예외를 throw 하는 [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다.  
  
> [!NOTE]
>  성능 향상을 위해 외부 데이터베이스에 액세스할 때 권장 된 부착 Microsoft Jet 데이터베이스에 외부 데이터베이스 테이블 (합니다. MDB) 데이터 원본에 직접 연결 하는 대신 합니다.  
  
 데이터베이스 유형 파일 또는 디렉터리에, 다음과 같이 경로가 가리키는으로 표시 됩니다.  
  
|경로 이름 가리킵니다.|데이터베이스 유형|  
|--------------------------|-------------------|  
|. MDB 파일|Microsoft Jet 데이터베이스 (Microsoft Access)|  
|포함 된 디렉터리입니다. DBF 파일|dBASE 데이터베이스|  
|포함 된 디렉터리입니다. XLS 파일|Microsoft Excel 데이터베이스|  
|포함 된 디렉터리입니다. PDX 파일|Paradox 데이터베이스|  
|적절 하 게 서식이 지정 된 텍스트 데이터베이스 파일이 포함 된 디렉터리|텍스트 형식 데이터베이스|  
  
 SQL Server 및 Oracle과 같은 ODBC 데이터베이스에 대 한 데이터베이스의 연결 문자열 ODBC에서 등록 된 데이터 원본 이름 (DSN)를 식별 합니다.  
  
##  <a name="getquerydefcount"></a>CDaoDatabase::GetQueryDefCount  
 데이터베이스의 QueryDefs 컬렉션에 정의 된 쿼리의 수를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
short GetQueryDefCount();
```  
  
### <a name="return-value"></a>반환 값  
 데이터베이스에 정의 된 쿼리의 수입니다.  
  
### <a name="remarks"></a>설명  
 `GetQueryDefCount`QueryDefs 컬렉션에서 모든 쿼리를 반복 하는 경우 유용 합니다. 컬렉션에서 지정된 된 쿼리에 대 한 정보를 얻으려면 참조 [GetQueryDefInfo](#getquerydefinfo)합니다.  
  
##  <a name="getquerydefinfo"></a>CDaoDatabase::GetQueryDefInfo  
 다양 한 종류의 데이터베이스에 정의 된 쿼리에 대 한 정보를 가져오려면이 함수를 호출 합니다.  
  
```  
void GetQueryDefInfo(
    int nIndex,  
    CDaoQueryDefInfo& querydefinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetQueryDefInfo(
    LPCTSTR lpszName,  
    CDaoQueryDefInfo& querydefinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 미리 정의 된 쿼리에서 인덱스에 의해 조회에 대 한 데이터베이스의 QueryDefs 컬렉션의 인덱스입니다.  
  
 *querydefinfo*  
 에 대 한 참조는 [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md) 요청 된 정보를 반환 하는 개체입니다.  
  
 `dwInfoOptions`  
 검색할 레코드 집합에 대 한 정보를 지정 하는 옵션입니다. 레코드 집합에 대 한 반환 하는 함수를 입히기 무엇과 함께 사용할 수 있는 옵션 여기 나열 됩니다.  
  
- `AFX_DAO_PRIMARY_INFO`(기본값) 이름, 형식  
  
- `AFX_DAO_SECONDARY_INFO`기본 정보 더하기: 생성 날짜, 마지막 업데이트 날짜, 레코드를 반환, 업데이트 가능  
  
- `AFX_DAO_ALL_INFO`기본 및 보조 정보 더하기: SQL, 연결, ODBCTimeout  
  
 `lpszName`  
 이름별으로 조회에 대 한 데이터베이스에 정의 된 쿼리의 이름을 포함 하는 문자열입니다.  
  
### <a name="remarks"></a>설명  
 QueryDefs 컬렉션 데이터베이스의 인덱스 또는 쿼리 이름 쿼리를 선택할 수 있도록 두 가지 버전의 함수가 제공 됩니다.  
  
 에 대 한 설명은에서 반환 되는 정보 *querydefinfo*, 참조는 [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md) 구조입니다. 이 구조에는 항목의 설명에 위에 나열 된 정보에 해당 하는 멤버가 `dwInfoOptions`합니다. 한 수준의 정보를 요청 하는 경우 모든 이전 수준의 정보를 얻습니다.  
  
##  <a name="getquerytimeout"></a>CDaoDatabase::GetQueryTimeout  
 연결 된 데이터베이스에 대 한 후속 작업 시간이 초과 하기 전까지 허용 시간 (초)의 현재 수를 검색 하려면이 함수를 호출 합니다.  
  
```  
short GetQueryTimeout();
```  
  
### <a name="return-value"></a>반환 값  
 초에서 제한 시간 값을 포함 하는 짧은 정수입니다.  
  
### <a name="remarks"></a>설명  
 네트워크 액세스 문제, 과도 한 쿼리 처리 시간 및 등으로 인해 작업 시간이 초과 될 수 있습니다. 열려 있는 모든 설정이 사용 되는 동안에 영향을, 새로 추가, 업데이트 및 삭제와 연결 된 모든 레코드 집합에 대 한 작업 `CDaoDatabase` 개체입니다. 호출 하 여 현재 시간 제한 설정을 변경할 수 있습니다 [SetQueryTimeout](#setquerytimeout)합니다. 연 후 레코드 집합에 대 한 쿼리 제한 시간 값을 변경 하는 경우에 레코드 집합에 대 한 값을 변경 되지 않습니다. 예를 들어, 후속 [이동](../../mfc/reference/cdaorecordset-class.md#move) 작업 새 값을 사용 하지 않습니다. 기본값은 데이터베이스 엔진 초기화 될 때 처음 설정 됩니다.  
  
 쿼리 시간 제한에 대 한 기본 값은 Windows 레지스트리에서 가져옵니다. 레지스트리 문자열 없음 이면 기본값은 60 초입니다. 일부 데이터베이스 쿼리 제한 시간 값을 설정 하는 기능을 지원 합니다. 쿼리 제한 시간 값이 0 설정 하는 경우 시간 제한 없이 발생 합니다. 및 데이터베이스와의 통신에 응답 하지 않을 수 있습니다. 개발 하는 동안이 동작이 유용할 수 있습니다. 호출이 실패 하는 경우 MFC 형식의 예외를 throw 하는 [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "QueryTimeout Property" 항목을 참조 합니다.  
  
##  <a name="getrecordsaffected"></a>CDaoDatabase::GetRecordsAffected  
 가장 최근 호출에 의해 영향을 받는 레코드 수를 확인 하려면이 멤버 함수 호출의 [Execute](#execute) 멤버 함수입니다.  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>반환 값  
 영향을 받는 레코드 수를 포함 하는 long 정수입니다.  
  
### <a name="remarks"></a>설명  
 반환 값에는 삭제, 업데이트 또는 쿼리를 실행 하 여 삽입 된 레코드 수가 들어 **Execute**합니다. 반환 된 수는 cascade를 업데이트 하거나 삭제 하는 경우 관련된 테이블의 변경 내용이 적용 반영 되지 않습니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "RecordsAffected Property" 항목을 참조 합니다.  
  
##  <a name="getrelationcount"></a>CDaoDatabase::GetRelationCount  
 데이터베이스의 테이블 간에 정의 된 관계 수를 가져오려면이 함수를 호출 합니다.  
  
```  
short GetRelationCount();
```  
  
### <a name="return-value"></a>반환 값  
 데이터베이스의 테이블 간에 정의 된 관계 수입니다.  
  
### <a name="remarks"></a>설명  
 **GetRelationCount** 데이터베이스의 관계 컬렉션에 정의 된 모든 관계를 반복 하는 경우 유용 합니다. 컬렉션에서 지정 된 관계에 대 한 정보를 얻으려면 참조 [GetRelationInfo](#getrelationinfo)합니다.  
  
 개념을 설명 하기 관계식을 Suppliers 테이블 및 제품 테이블에 일 대 다 관계를 가질 수 있는 것이 좋습니다. 이 관계에서 한 공급 둘 이상의 제품을 제공할 수 있습니다. 다른 관계는 일대일 및 다 대 다입니다.  
  
##  <a name="getrelationinfo"></a>CDaoDatabase::GetRelationInfo  
 이 데이터베이스의 Relations 컬렉션에서 지정 된 관계에 대 한 정보를 가져오는 함수를 호출 합니다.  
  
```  
void GetRelationInfo(
    int nIndex,  
    CDaoRelationInfo& relinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetRelationInfo(
    LPCTSTR lpszName,  
    CDaoRelationInfo& relinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 인덱스에 의해 조회에 대 한 데이터베이스의 Relations 컬렉션에서 관계 개체의 인덱스입니다.  
  
 *relinfo*  
 에 대 한 참조는 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) 요청 된 정보를 반환 하는 개체입니다.  
  
 `dwInfoOptions`  
 관계를 검색 하는 방법에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 관계에 대 한 반환 하는 함수를 입히기 무엇 함께 여기에 나열 됩니다.  
  
- `AFX_DAO_PRIMARY_INFO`(기본값) 이름, 테이블, 외래 테이블  
  
- `AFX_DAO_SECONDARY_INFO`필드 정보 특성  
  
 필드 정보가 [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) 관계에 관련 된 기본 테이블에서 필드를 포함 하는 개체입니다.  
  
 `lpszName`  
 이름별으로 조회에 대 한 관계 개체의 이름을 포함 하는 문자열입니다.  
  
### <a name="remarks"></a>설명  
 이 함수의 두 가지 버전 인덱스 또는 이름으로 액세스를 제공합니다. 에 대 한 설명은에서 반환 되는 정보 *relinfo*, 참조는 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) 구조입니다. 이 구조에는 항목의 설명에 위에 나열 된 정보에 해당 하는 멤버가 `dwInfoOptions`합니다. 한 수준에서 정보를 요청 하는 경우 또한도 모든 이전 수준에서 정보를 가져옵니다.  
  
> [!NOTE]
>  개체의 하위 작업을 활성화 하는 특성 관계를 설정 하는 경우 ( **dbRelationUpdateCascades** 또는 **dbRelationDeleteCascades**), Microsoft Jet 데이터베이스 엔진을 자동으로 업데이트 하거나 관련된 기본 키 테이블에 변경 될 때 하나 이상의 다른 테이블의 레코드를 삭제 합니다. 예를 들어 Customers 테이블과 Orders 테이블 간의 cascade delete 관계를 설정 합니다. Customers 테이블에서 레코드를 삭제 하면 해당 고객에 게 관련 된 Orders 테이블의 레코드 삭제 됩니다. 또한, 주문 테이블과 다른 테이블 간의 cascade delete 관계를 설정 하는 경우 Customers 테이블에서 레코드를 삭제 하면 해당 테이블의 레코드 삭제 자동으로 됩니다.  
  
##  <a name="gettabledefcount"></a>CDaoDatabase::GetTableDefCount  
 데이터베이스에 정의 된 테이블의 수를 검색 하려면이 함수를 호출 합니다.  
  
```  
short GetTableDefCount();
```  
  
### <a name="return-value"></a>반환 값  
 데이터베이스에 정의 된 테이블 정의의 수입니다.  
  
### <a name="remarks"></a>설명  
 `GetTableDefCount`데이터베이스의 TableDefs 컬렉션의 모든 테이블 정의 반복 하는 경우 유용 합니다. 컬렉션에서 지정된 된 테이블에 대 한 정보를 얻으려면 참조 [GetTableDefInfo](#gettabledefinfo)합니다.  
  
##  <a name="gettabledefinfo"></a>CDaoDatabase::GetTableDefInfo  
 다양 한 종류의 데이터베이스에 정의 된 테이블에 대 한 정보를 가져오려면이 함수를 호출 합니다.  
  
```  
void GetTableDefInfo(
    int nIndex,  
    CDaoTableDefInfo& tabledefinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetTableDefInfo(
    LPCTSTR lpszName,  
    CDaoTableDefInfo& tabledefinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 인덱스에 의해 조회에 대 한 데이터베이스의 테이블 정의 컬렉션에 테이블 정의 개체의 인덱스입니다.  
  
 `tabledefinfo`  
 에 대 한 참조는 [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) 요청 된 정보를 반환 하는 개체입니다.  
  
 `dwInfoOptions`  
 검색할 테이블에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 관계에 대 한 반환 하는 함수를 입히기 무엇 함께 여기에 나열 됩니다.  
  
- `AFX_DAO_PRIMARY_INFO`(기본값) 이름, 업데이트, 특성  
  
- `AFX_DAO_SECONDARY_INFO`기본 정보 더하기: 만든 날짜가 마지막 업데이트 날짜, 원본 테이블 이름, 연결  
  
- `AFX_DAO_ALL_INFO`기본 및 보조 정보 더하기: 유효성 검사 규칙을 유효성 검사 텍스트 레코드 수  
  
 `lpszName`  
 이름별으로 조회에 대 한 테이블 정의 개체의 이름입니다.  
  
### <a name="remarks"></a>설명  
 데이터베이스의 TableDefs 컬렉션에서 인덱스 또는 테이블의 이름 테이블을 선택할 수 있도록 두 가지 버전의 함수가 제공 됩니다.  
  
 에 대 한 설명은에서 반환 되는 정보 `tabledefinfo`, 참조는 [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) 구조입니다. 이 구조에는 항목의 설명에 위에 나열 된 정보에 해당 하는 멤버가 `dwInfoOptions`합니다. 한 수준에서 정보를 요청 하는 경우 모든 상위 수준의에 대 한 정보를 가져옵니다.  
  
> [!NOTE]
>  `AFX_DAO_ALL_INFO` 옵션 얻으려고 느릴 수 있는 정보를 제공 합니다. 이 경우 테이블의 레코드 수를 계산 시간이 오래 걸릴 경우 레코드 수 수 있습니다.  
  
##  <a name="getversion"></a>CDaoDatabase::GetVersion  
 Microsoft Jet 데이터베이스 파일의 버전을 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetVersion();
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체에 연결 된 데이터베이스 파일의 버전을 나타내는입니다.  
  
### <a name="remarks"></a>설명  
 반환 되는 값 "major.minor"; 버전 번호를 나타냅니다. 예를 들어 "3.0"입니다. 제품 버전 번호 (예를 들어 3.0) (3) 버전 번호, 마침표, 및 릴리스 번호 (0)으로 이루어져 있습니다. 누계 버전 1.0, 1.1, 2.0 및 3.0 됩니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "버전 Property" 항목을 참조 합니다.  
  
##  <a name="isopen"></a>CDaoDatabase::IsOpen  
 확인 하려면이 함수를 호출 여부는 `CDaoDatabase` 개체는 데이터베이스에서 현재 열려 있습니다.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우에는 `CDaoDatabase` 개체는 현재 열려 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="m_pdaodatabase"></a>CDaoDatabase::m_pDAODatabase  
 DAO 데이터베이스 개체 내부에 대 한 OLE 인터페이스에 대 한 포인터는 `CDaoDatabase` 개체입니다.  
  
### <a name="remarks"></a>설명  
 DAO 인터페이스를 직접 액세스 해야 할 경우이 포인터를 사용 합니다.  
  
 DAO 호출 하는 방법에 대 한 정보에 대 한 참조를 직접 [기술 참고 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)합니다.  
  
##  <a name="m_pworkspace"></a>CDaoDatabase::m_pWorkspace  
 에 대 한 포인터는 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 데이터베이스 개체가 포함 된 개체입니다.  
  
### <a name="remarks"></a>설명  
 작업 영역에 직접 액세스 해야 할 경우이 포인터를 사용 하 여-예: 작업 영역의 데이터베이스 컬렉션에서 다른 데이터베이스 개체에 대 한 포인터를 가져올 수 있습니다.  
  
##  <a name="open"></a>CDaoDatabase::Open  
 새로 생성 된 초기화 하려면이 멤버 함수를 호출 해야 `CDaoDatabase` 기존 데이터베이스를 나타내는 개체입니다.  
  
```  
virtual void Open(
    LPCTSTR lpszName,  
    BOOL bExclusive = FALSE,  
    BOOL bReadOnly = FALSE,  
    LPCTSTR lpszConnect = _T(""));
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 기존 Microsoft Jet의 이름에 해당 하는 문자열 식 (합니다. MDB) 데이터베이스 파일입니다. 파일 이름 확장명이 경우 필수입니다. 네트워크 경로 네트워크에 균일 한 명명 규칙 (UNC)를 지 원하는 경우와 같은 지정할 수도 있습니다 "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB 합니다. MDB "입니다. (때문에 문자열 리터럴에 필요한 이중 백슬래시 "\\" c + + 이스케이프 문자입니다.)  
  
 사용 하는 경우 몇 가지 고려 사항이 적용 `lpszName`합니다. 하는 경우 해당:  
  
-   다른 사용자가 MFC throw 형식의 예외에 대 한 단독 액세스를 위해 이미 열려 있는 데이터베이스를 참조 [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다. 사용자 데이터베이스를 사용할 수 없다는 것을 알 수 있도록 해당 예외를 트래핑 합니다.  
  
-   빈 문자열 ("") 및 *lpszConnect* "; ODBC"는 사용자 데이터베이스를 선택할 수 있도록 등록 된 모든 ODBC 데이터 원본 이름 목록을 하는 대화 상자가 표시 됩니다. ODBC 데이터 원본에 직접 연결 하지 마십시오 연결된 된 테이블을 대신 사용 합니다.  
  
-   그렇지 않으면 기존 데이터베이스 또는 유효한 ODBC 데이터 원본 이름, MFC throw 형식의 예외를 참조 하지 않습니다 `CDaoException`합니다.  
  
> [!NOTE]
>  DAO 오류 코드에 대 한 내용은 DAOERR를 참조 하십시오. H 파일입니다. 관련된 정보에 대 한 트랩 가능한 데이터 액세스의 "오류" DAO 도움말 항목을 참조 합니다.  
  
 `bExclusive`  
 부울 값이 **TRUE** 데이터베이스가 비공유 단독 액세스를 위해 열어야 하는 경우 및 **FALSE** 데이터베이스가 공유 액세스를 위해 열리는 경우. 이 인수를 생략 하면 데이터베이스를 공유 액세스에 대 한 열입니다.  
  
 `bReadOnly`  
 부울 값이 **TRUE** 데이터베이스가 읽기 전용 액세스를 위해 열어야 하는 경우 및 **FALSE** 데이터베이스가 읽기/쓰기용으로 열 경우. 이 인수를 생략 하면 데이터베이스를 읽기/쓰기 액세스에 대 한 열입니다. 종속 된 모든 레코드는이 특성을 상속합니다.  
  
 `lpszConnect`  
 데이터베이스를 여는 데 사용 하는 문자열 식입니다. 이 문자열은 ODBC 인수를 연결 합니다. 소스 문자열 제공할 전용 및 읽기 전용 인수를 제공 해야 합니다. Microsoft Jet 데이터베이스의 경우 (합니다. MDB)이이 문자열이 비어 있습니다. (""). 기본값에 대 한 구문- **_T**("")-응용 프로그램의 이식성 ANSI 뿐만 아니라 유니코드에 대 한 빌드를 제공 합니다.  
  
### <a name="remarks"></a>설명  
 **열기** 기본 DAO 개체는 데이터베이스에 연결 합니다. 초기화 될 때까지 레코드 집합, tabledef 또는 querydef 개체를 생성 하는 데이터베이스 개체를 사용할 수 없습니다. **열기** 데이터베이스 개체의 연결 된 작업 영역 데이터베이스 컬렉션에 추가 합니다.  
  
 다음과 같이 매개 변수를 사용 합니다.  
  
-   Microsoft Jet을 여는 경우 (합니다. MDB) 데이터베이스를 사용 하 여는 `lpszName` 매개 변수를 전달에 대 한 빈 문자열은 `lpszConnect` 매개 변수 또는 형식의 암호 문자열 pass "; PWD 암호 = "암호로 보호 된 데이터베이스가 있으면 (합니다. MDB 데이터베이스에만 해당)입니다.  
  
-   ODBC 데이터 소스를 여는 경우에 유효한 ODBC 연결 문자열을 전달 `lpszConnect` 에 빈 문자열 및 `lpszName`합니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "OpenDatabase Method" 항목을 참조 합니다.  
  
> [!NOTE]
>  ISAM 데이터베이스 및 ODBC 데이터 원본을 포함 하 여 외부 데이터베이스에 액세스할 때 성능 향상을 위해 것이 좋습니다 Microsoft Jet 엔진 데이터베이스에 외부 데이터베이스 테이블을 연결 하는 (합니다. MDB) 데이터 원본에 직접 연결 하는 대신 합니다.  
  
 있기 연결 시도가 시간 초과 대 한 경우 예를 들어 DBMS 호스트를 사용할 수 없습니다. 연결 시도가 실패 하면 **열려** 형식의 예외를 throw [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다.  
  
 나머지 설명은 ODBC 데이터베이스에만 적용 됩니다.  
  
 데이터베이스가 ODBC 데이터베이스 및 매개 변수를 프로그램 **열려** 호출 연결을 만드는 데 충분 한 정보를 포함 하지 않습니다, ODBC 드라이버는 사용자 로부터 필요한 정보를 얻기 위해 대화 상자를 엽니다. 호출 하는 경우 **열려**, 연결 문자열을 `lpszConnect`, 개인적으로 저장 되 고 호출 하 여 ´ ï ´는 [GetConnect](#getconnect) 멤버 함수입니다.  
  
 호출 하기 전에 고유한 대화 상자를 열 수 있습니다 **열고** 에서 암호와 같은 사용자 정보를 가져오는 다음 해당 정보를 추가 연결 문자열에 전달할 **열고**합니다. 응용 프로그램이 호출 시간 (아마도 Windows 레지스트리)에 전달 하면 다음 재사용할 수 있도록 연결 문자열을 저장 하려는 경우 또는 **열려** 에 `CDaoDatabase` 개체입니다.  
  
 여러 수준의 로그인 권한 부여에 대 한 연결 문자열을 사용할 수도 있습니다 (각각에 대 한 다른 `CDaoDatabase` 개체) 또는 다른 데이터베이스 관련 정보를 전달 합니다.  
  
##  <a name="setquerytimeout"></a>CDaoDatabase::SetQueryTimeout  
 연결 된 데이터베이스 시간 제한에 대 한 후속 작업 하기 전까지 허용 시간 (초) 기본값을 재정의 하려면이 함수를 호출 합니다.  
  
```  
void SetQueryTimeout(short nSeconds);
```  
  
### <a name="parameters"></a>매개 변수  
 `nSeconds`  
 쿼리 시도 하기 전까지 허용 시간 (초)의 수 제한 시간이 초과 합니다.  
  
### <a name="remarks"></a>설명  
 네트워크 액세스 문제, 과도 한 쿼리 처리 시간 및 등으로 인해 작업 시간이 초과 될 수 있습니다. 호출 `SetQueryTimeout` 레코드 집합을 열기 전에 또는 레코드 집합의를 호출 하기 전에 [AddNew](../../mfc/reference/cdaorecordset-class.md#addnew), [업데이트](../../mfc/reference/cdaorecordset-class.md#update), 또는 [삭제](../../mfc/reference/cdaorecordset-class.md#delete) 멤버 함수는 쿼리를 변경 하려면 제한 시간 값입니다. 설정은 모든 후속 [열려](../../mfc/reference/cdaorecordset-class.md#open), `AddNew`, **업데이트**, 및 **삭제** 와 연결 된 모든 레코드 집합에 대 한 호출 `CDaoDatabase` 개체입니다. 연 후 레코드 집합에 대 한 쿼리 제한 시간 값을 변경 하는 경우에 레코드 집합에 대 한 값을 변경 되지 않습니다. 예를 들어, 후속 [이동](../../mfc/reference/cdaorecordset-class.md#move) 작업 새 값을 사용 하지 않습니다.  
  
 쿼리 시간 제한의 기본값은 60 초입니다. 일부 데이터베이스 쿼리 제한 시간 값을 설정 하는 기능을 지원 합니다. 쿼리 제한 시간 값이 0 설정 하는 경우 시간 제한 없이 발생 합니다. 데이터베이스와의 통신 응답 하지 않을 수 있습니다. 개발 하는 동안이 동작이 유용할 수 있습니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "QueryTimeout Property" 항목을 참조 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDaoWorkspace 클래스](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoRecordset 클래스](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)   
 [CDatabase 클래스](../../mfc/reference/cdatabase-class.md)   
 [CDaoException 클래스](../../mfc/reference/cdaoexception-class.md)
