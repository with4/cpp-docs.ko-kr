---
title: CDaoWorkspace 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoWorkspace
- AFXDAO/CDaoWorkspace
- AFXDAO/CDaoWorkspace::CDaoWorkspace
- AFXDAO/CDaoWorkspace::Append
- AFXDAO/CDaoWorkspace::BeginTrans
- AFXDAO/CDaoWorkspace::Close
- AFXDAO/CDaoWorkspace::CommitTrans
- AFXDAO/CDaoWorkspace::CompactDatabase
- AFXDAO/CDaoWorkspace::Create
- AFXDAO/CDaoWorkspace::GetDatabaseCount
- AFXDAO/CDaoWorkspace::GetDatabaseInfo
- AFXDAO/CDaoWorkspace::GetIniPath
- AFXDAO/CDaoWorkspace::GetIsolateODBCTrans
- AFXDAO/CDaoWorkspace::GetLoginTimeout
- AFXDAO/CDaoWorkspace::GetName
- AFXDAO/CDaoWorkspace::GetUserName
- AFXDAO/CDaoWorkspace::GetVersion
- AFXDAO/CDaoWorkspace::GetWorkspaceCount
- AFXDAO/CDaoWorkspace::GetWorkspaceInfo
- AFXDAO/CDaoWorkspace::Idle
- AFXDAO/CDaoWorkspace::IsOpen
- AFXDAO/CDaoWorkspace::Open
- AFXDAO/CDaoWorkspace::RepairDatabase
- AFXDAO/CDaoWorkspace::Rollback
- AFXDAO/CDaoWorkspace::SetDefaultPassword
- AFXDAO/CDaoWorkspace::SetDefaultUser
- AFXDAO/CDaoWorkspace::SetIniPath
- AFXDAO/CDaoWorkspace::SetIsolateODBCTrans
- AFXDAO/CDaoWorkspace::SetLoginTimeout
- AFXDAO/CDaoWorkspace::m_pDAOWorkspace
dev_langs:
- C++
helpviewer_keywords:
- CDaoWorkspace [MFC], CDaoWorkspace
- CDaoWorkspace [MFC], Append
- CDaoWorkspace [MFC], BeginTrans
- CDaoWorkspace [MFC], Close
- CDaoWorkspace [MFC], CommitTrans
- CDaoWorkspace [MFC], CompactDatabase
- CDaoWorkspace [MFC], Create
- CDaoWorkspace [MFC], GetDatabaseCount
- CDaoWorkspace [MFC], GetDatabaseInfo
- CDaoWorkspace [MFC], GetIniPath
- CDaoWorkspace [MFC], GetIsolateODBCTrans
- CDaoWorkspace [MFC], GetLoginTimeout
- CDaoWorkspace [MFC], GetName
- CDaoWorkspace [MFC], GetUserName
- CDaoWorkspace [MFC], GetVersion
- CDaoWorkspace [MFC], GetWorkspaceCount
- CDaoWorkspace [MFC], GetWorkspaceInfo
- CDaoWorkspace [MFC], Idle
- CDaoWorkspace [MFC], IsOpen
- CDaoWorkspace [MFC], Open
- CDaoWorkspace [MFC], RepairDatabase
- CDaoWorkspace [MFC], Rollback
- CDaoWorkspace [MFC], SetDefaultPassword
- CDaoWorkspace [MFC], SetDefaultUser
- CDaoWorkspace [MFC], SetIniPath
- CDaoWorkspace [MFC], SetIsolateODBCTrans
- CDaoWorkspace [MFC], SetLoginTimeout
- CDaoWorkspace [MFC], m_pDAOWorkspace
ms.assetid: 64f60de6-4df1-4d4a-a65b-c489b5257d52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b249f8069ba12772d21d170b67236a5f013290ac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377216"
---
# <a name="cdaoworkspace-class"></a>CDaoWorkspace 클래스
단일 사용자가 로그인부터 로그인까지 암호로 보호되고 명명된 데이터베이스 세션을 관리합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDaoWorkspace : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoWorkspace::CDaoWorkspace](#cdaoworkspace)|작업 영역 개체를 만듭니다. 그 후에 호출 **만들기** 또는 **열려**합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoWorkspace::Append](#append)|데이터베이스 엔진의 작업 영역 컬렉션을 새로 만든된 작업 영역을 추가합니다.|  
|[CDaoWorkspace::BeginTrans](#begintrans)|열려 있는 모든 데이터베이스 작업 영역에서에 적용 되는 새 트랜잭션을 시작 합니다.|  
|[CDaoWorkspace::Close](#close)|작업 영역 및 포함 된 개체를 모두 닫습니다. 보류 중인 트랜잭션이 롤백됩니다.|  
|[CDaoWorkspace::CommitTrans](#committrans)|현재 트랜잭션을 완료 하 고 변경 내용을 저장 합니다.|  
|[CDaoWorkspace::CompactDatabase](#compactdatabase)|압축 (또는 중복) 데이터베이스입니다.|  
|[CDaoWorkspace::Create](#create)|새 DAO 작업 영역 개체를 만듭니다.|  
|[CDaoWorkspace::GetDatabaseCount](#getdatabasecount)|작업 영역 데이터베이스 컬렉션에서 DAO 데이터베이스 개체 수를 반환합니다.|  
|[CDaoWorkspace::GetDatabaseInfo](#getdatabaseinfo)|작업 영역 데이터베이스 컬렉션에 정의 된 지정된 된 DAO 데이터베이스에 대 한 정보를 반환 합니다.|  
|[CDaoWorkspace::GetIniPath](#getinipath)|Windows 레지스트리에 엔진의 초기화 설정이 Microsoft Jet 데이터베이스의 위치를 반환합니다.|  
|[CDaoWorkspace::GetIsolateODBCTrans](#getisolateodbctrans)|데이터 원본에 대 한 여러 연결을 강제 같은 ODBC 데이터 소스와 관련 된 여러 트랜잭션을 통해 격리 된 요소가 있는지 여부를 나타내는 값을 반환 합니다.|  
|[CDaoWorkspace::GetLoginTimeout](#getlogintimeout)|사용자가 ODBC 데이터베이스에 로그인 하려고 할 때 오류가 발생 하기 전에 시간 (초)을 반환 합니다.|  
|[CDaoWorkspace::GetName](#getname)|작업 영역 개체에 대 한 사용자 정의 이름을 반환합니다.|  
|[CDaoWorkspace::GetUserName](#getusername)|반환 작업 영역을 만들 때 사용자 이름을 지정 합니다. 작업 영역 소유자의 이름입니다.|  
|[CDaoWorkspace::GetVersion](#getversion)|작업 영역과 연결 된 데이터베이스 엔진의 버전을 포함 하는 문자열을 반환 합니다.|  
|[CDaoWorkspace::GetWorkspaceCount](#getworkspacecount)|데이터베이스 엔진의 작업 영역 컬렉션에서 DAO 작업 영역 개체의 수를 반환합니다.|  
|[CDaoWorkspace::GetWorkspaceInfo](#getworkspaceinfo)|데이터베이스 엔진의 작업 영역 컬렉션에 정의 된 지정한 DAO 작업 영역에 대 한 정보를 반환 합니다.|  
|[CDaoWorkspace::Idle](#idle)|데이터베이스 엔진을 백그라운드 작업을 수행할 수 있습니다.|  
|[CDaoWorkspace::IsOpen](#isopen)|연 작업 영역을 0이 아닌 반환 합니다.|  
|[CDaoWorkspace::Open](#open)|DAO의 기본 작업 영역과 연결 된 작업 영역 개체를 명시적으로 엽니다.|  
|[CDaoWorkspace::RepairDatabase](#repairdatabase)|손상된 된 데이터베이스를 복구 하려고 합니다.|  
|[CDaoWorkspace::Rollback](#rollback)|현재 트랜잭션을 종료 하 고 변경 내용을 저장 하지 않습니다.|  
|[CDaoWorkspace::SetDefaultPassword](#setdefaultpassword)|데이터베이스 엔진에는 특정 암호 없이 workspace 개체를 만들 때 사용 하는 암호를 설정 합니다.|  
|[CDaoWorkspace::SetDefaultUser](#setdefaultuser)|특정 사용자 이름 없이 작업 영역 개체를 만들 때 데이터베이스 엔진을 사용 하는 사용자 이름을 설정 합니다.|  
|[CDaoWorkspace::SetIniPath](#setinipath)|Windows 레지스트리에 Microsoft Jet 데이터베이스의 위치 엔진의 초기화 설정의 설정합니다.|  
|[CDaoWorkspace::SetIsolateODBCTrans](#setisolateodbctrans)|데이터 원본에 대 한 여러 연결을 강제 적용 하 여 동일한 ODBC 데이터 소스와 관련 된 여러 트랜잭션을 격리 되어 있는지 여부를 지정 합니다.|  
|[CDaoWorkspace::SetLoginTimeout](#setlogintimeout)|사용자가 ODBC 데이터 원본에 로그인 하려고 할 때 오류가 발생 하기 전에 시간 (초)을 설정 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoWorkspace::m_pDAOWorkspace](#m_pdaoworkspace)|기본 DAO 영역 개체를 가리킵니다.|  
  
## <a name="remarks"></a>설명  
 대부분의 경우에서 여러 개의 작업 영역 필요는 없지만 하 고 명시적 작업 영역 개체를 만들 필요가 없기 데이터베이스 및 레코드 집합 개체를 열 때 DAO의 기본 작업 영역을 사용 합니다. 그러나에서 필요한 경우에 추가 작업 영역 개체를 만들어 한 번에 여러 세션을 실행할 수 있습니다. 각 작업 영역 개체 자체의 데이터베이스 컬렉션에서 여러 열려 있는 데이터베이스 개체를 포함할 수 있습니다. 작업 영역은 기본적으로 트랜잭션 관리자 모두에서 "트랜잭션 공간입니다." 동일한 열려 있는 데이터베이스의 집합을 지정 하 mfc에서  
  
> [!NOTE]
>  DAO 데이터베이스 클래스에 ODBC Open Database Connectivity ()를 기반으로 하는 MFC 데이터베이스 클래스와 다릅니다. DAO 데이터베이스 클래스 이름의 접두사가 "CDao". 일반적으로 기반으로 DAO MFC 클래스는 ODBC를 기반으로 MFC 클래스 보다 더 수 있습니다. DAO 기반 클래스 ODBC 드라이버를 포함 하 여 Microsoft Jet 데이터베이스 엔진을 통해 데이터에 액세스 합니다. 또한 데이터베이스를 만들고 테이블 및 필드는 클래스를 통해 직접 DAO 호출 하지 않고도 추가 등의 데이터 정의 언어 (DDL) 작업을 지원 합니다.  
  
## <a name="capabilities"></a>기능  
 클래스 `CDaoWorkspace` 다음을 제공 합니다.  
  
-   명시적 액세스를 데이터베이스 엔진을 초기화 하 여 만든 기본 작업 영역으로 필요한 경우. 일반적으로 사용 하면 DAO의 기본 작업 영역을 암시적으로 데이터베이스 및 레코드 집합 개체를 만들고 있습니다.  
  
-   모든 데이터베이스에 트랜잭션을 적용 하는 트랜잭션 공간에서 작업 영역을 엽니다. 별도 트랜잭션 공간을 관리할 수 있도록 추가 작업 영역을 만들 수 있습니다.  
  
-   기본 Microsoft Jet 데이터베이스 엔진의 여러 속성에 대 한 인터페이스 (정적 멤버 함수 참조). 열기 작업 영역에서 만들거나 하기 전에 정적 멤버 함수를 호출 또는 만들기를 열고 데이터베이스 엔진을 초기화 합니다.  
  
-   에 추가 된 모든 활성 작업 영역을 저장 하는 데이터베이스 엔진의 작업 영역 컬렉션에 액세스 합니다. 만들고 및 작업 영역 컬렉션에 추가 하지 않고 작업할 수도 있습니다.  
  
## <a name="security"></a>보안  
 MFC dao에서 보안 제어 기능에 사용 되는 사용자 및 그룹 컬렉션을 구현 하지 않습니다. DAO에서 이러한 요소를 필요 하면 프로그램 해야 이러한 직접 DAO 인터페이스를 직접 호출을 통해. 자세한 내용은 참조 [기술 참고 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)합니다.  
  
## <a name="usage"></a>사용법  
 클래스를 사용할 수 `CDaoWorkspace` 에:  
  
-   기본 작업 영역을 명시적으로 열어야 합니다.  
  
     일반적으로 기본 작업 영역을 사용 하 여 암시적는-new 열 때 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체입니다. 하지만 명시적으로 액세스 해야 할 수-예를 들어 access 데이터베이스 엔진 속성 또는 작업 영역 컬렉션입니다. 아래의 "기본 작업 영역을 암시적 사용"을 참조 하십시오.  
  
-   새 작업 영역을 만듭니다. 호출 [Append](#append) 작업 영역 컬렉션에 추가 하려는 경우.  
  
-   작업 영역 컬렉션에서 기존 작업 영역을 엽니다.  
  
 새 작업 영역을 만드는 존재 하지 않는 아래에서 설명 하는 컬렉션 작업 영역에는 [만들기](#create) 멤버 함수입니다. 작업 영역 개체에 어떤 방식으로 데이터베이스 엔진 세션 간에 유지 되지 않습니다. 응용 프로그램이 MFC를 정적으로 연결 하는 경우 응용 프로그램을 끝내기 초기화를 취소 하면 데이터베이스 엔진입니다. 응용 프로그램이 MFC에 동적으로 링크 되어 있는 경우에 MFC DLL이 언로드될 때 데이터베이스 엔진 초기화 되지 않았습니다.  
  
 명시적으로 기본 작업 영역 열기 또는 작업 영역 컬렉션에서 기존 작업 영역을 열고 아래에 설명 된 [열려](#open) 멤버 함수입니다.  
  
 작업 영역을 닫으면 작업 영역 세션 종료는 [닫기](#close) 멤버 함수입니다. **닫기** 닫지 않은 이전에 커밋되지 않은 트랜잭션을 롤백하는 모든 데이터베이스를 닫습니다.  
  
## <a name="transactions"></a>트랜잭션  
 DAO; 작업 영역 수준에서 트랜잭션을 관리합니다 따라서 트랜잭션을 여러 열려 데이터베이스와 함께 작업 영역에서 모든 데이터베이스에 적용 합니다. 예를 들어 두 개의 데이터베이스는 커밋되지 않은 업데이트 하 고 호출 [CommitTrans](#committrans), 업데이트를 모두 커밋됩니다. 단일 데이터베이스에 대 한 트랜잭션 제한 하려는 경우에 대 한 별도 작업 영역 개체가 필요 합니다.  
  
## <a name="implicit-use-of-the-default-workspace"></a>기본 작업 영역을 암시적 사용  
 MFC는 DAO의 기본 작업 영역을 다음과 같은 경우에 암시적으로 사용합니다.  
  
-   새 만들면 `CDaoDatabase` 개체 있지만 그렇게 하지 않으면 기존 통해 `CDaoWorkspace` MFC에 의해 생성 된 임시 작업 영역 개체, DAO의 기본 작업 영역에 해당 하는 개체입니다. 이렇게 하면 여러 데이터베이스에 대 한 모든 데이터베이스 개체의 경우 기본 작업 영역에 연결 합니다. 통해 데이터베이스의 작업 영역에 액세스할 수 있습니다는 `CDaoDatabase` 데이터 멤버입니다.  
  
-   마찬가지로, 만들면는 `CDaoRecordset` 개체에 대 한 포인터를 제공 하지 않고는 `CDaoDatabase` 개체, MFC는 임시 데이터베이스 개체를 만듭니다. 및 확장 하면 임시 작업 영역 개체입니다. 레코드 집합의 데이터베이스 및 간접적으로 해당 작업 영역을 통해 액세스할 수 있습니다는 `CDaoRecordset` 데이터 멤버입니다.  
  
## <a name="other-operations"></a>다른 작업  
 다른 데이터베이스 작업과 제공 되는데, 예: 손상 된 데이터베이스를 복구 또는 데이터베이스를 압축 합니다.  
  
 직접 DAO 호출 하는 방법에 대 한 및 DAO 보안에 대 한 정보를 참조 하십시오. [기술 참고 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoWorkspace`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
##  <a name="append"></a>  CDaoWorkspace::Append  
 이 멤버 함수를 호출한 후 호출 [만들기](#create)합니다.  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>설명  
 **추가** 새로 만든된 작업 영역 개체는 데이터베이스 엔진의 작업 영역 컬렉션에 추가 합니다. 작업 영역 데이터베이스 엔진 세션 간에 유지 되지 않습니다. 디스크에 없는 메모리에만 저장 됩니다. 작업 영역을 추가할 필요가 없습니다. 그렇지 않은 경우 계속 사용할 수 있습니다.  
  
 추가 되는 작업 영역에에서 남아 작업 영역 컬렉션에서 활성, 열린 상태를 호출할 때까지 해당 [닫기](#close) 멤버 함수입니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "추가 방법" 항목을 참조 합니다.  
  
##  <a name="begintrans"></a>  CDaoWorkspace::BeginTrans  
 이 트랜잭션을 시작 하도록 함수를 호출 합니다.  
  
```  
void BeginTrans();
```  
  
### <a name="remarks"></a>설명  
 호출한 후 **BeginTrans**, 트랜잭션을 커밋하는 경우 데이터 나 데이터베이스 구조에 수행한 업데이트 내용이 적용 됩니다. 작업 영역에서 단일 트랜잭션을 정의 하므로 트랜잭션 작업 영역에서 열려 있는 모든 데이터베이스에 적용 됩니다. 두 가지 방법을 사용 하 여 트랜잭션을 완료할 수 있습니다.  
  
-   호출 된 [CommitTrans](#committrans) 멤버 함수를 데이터 원본의 변경 내용을 저장 하 고 트랜잭션을 커밋합니다.  
  
-   호출 또는 [롤백](#rollback) 트랜잭션을 취소 하려면 멤버 함수입니다.  
  
 보류 중인 트랜잭션은 모두 롤백 트랜잭션이 보류 중일 때 작업 영역 개체 또는 데이터베이스 개체를 닫는 합니다.  
  
 다른 ODBC 데이터 원본에 있는 하나의 ODBC 데이터 원본에서 트랜잭션은 격리 해야 할 경우 참조는 [SetIsolateODBCTrans](#setisolateodbctrans) 멤버 함수입니다.  
  
##  <a name="cdaoworkspace"></a>  CDaoWorkspace::CDaoWorkspace  
 `CDaoWorkspace` 개체를 생성합니다.  
  
```  
CDaoWorkspace();
```  
  
### <a name="remarks"></a>설명  
 C + + 개체를 생성 한 후 두 가지 옵션이 있습니다.  
  
-   개체의 [열고](#open) 멤버 함수를 작업 영역 컬렉션에서 기존 개체를 열기 또는 기본 작업 영역을 엽니다.  
  
-   개체의 또는 [만들기](#create) 멤버 함수는 새 DAO 작업 영역 개체를 만듭니다. 통해을 참조할 수 있는 새 작업 영역 세션을 명시적으로 시작 된 `CDaoWorkspace` 개체입니다. 호출한 후 **만들기**를 호출할 수 있습니다 [Append](#append) 작업 영역 데이터베이스 엔진의 작업 영역 컬렉션에 추가 하려는 경우.  
  
 클래스 개요를 참조 하십시오. [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 만들려면 명시적으로 중지 해야 하는 방법에 대 한 정보에 대 한 한 `CDaoWorkspace` 개체입니다. 열 때 암시적으로 생성 하는 작업 영역을 사용 하는 일반적으로 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체를 열 때 또는 작업 영역을 지정 하지 않고는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 데이터베이스 개체를 지정 하지 않고 개체입니다. 이 방법으로 만든 MFC DAO 개체는 한 번 생성 되 고 다시 사용 하는 DAO의 기본 작업 영역을 사용 합니다.  
  
 작업 영역 및 해당 포함 된 개체를 해제 하려면 작업 영역 개체의 호출 [닫기](#close) 멤버 함수입니다.  
  
##  <a name="close"></a>  CDaoWorkspace::Close  
 이 작업 영역 개체를 닫는 함수를 호출 합니다.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>설명  
 작업 영역 열기 개체를 닫아도 하는 기본 DAO 개체를 해제 되 고 작업 영역을 사용 하면 작업 영역 컬렉션의 멤버인 경우 컬렉션에서 제거 합니다. 호출 **닫기** 이 좋습니다.  
  
> [!CAUTION]
>  개체를 작업 영역을 닫으면 작업 영역에서 모든 열린 데이터베이스. 이 인해도 종결 되는 데이터베이스의 모든 레코드 집합 열기 및 모든 보류 중인 편집 내용이 또는 업데이트 내용이 롤백됩니다. 관련된 정보에 대 한 참조는 [CDaoDatabase::Close](../../mfc/reference/cdaodatabase-class.md#close), [CDaoRecordset::Close](../../mfc/reference/cdaorecordset-class.md#close), [CDaoTableDef::Close](../../mfc/reference/cdaotabledef-class.md#close), 및 [CDaoQueryDef::Close](../../mfc/reference/cdaoquerydef-class.md#close) 멤버 함수입니다.  
  
 작업 영역 개체; 저장 되지 않습니다. 이러한 참조에 존재 하는 동안에 존재 합니다. 즉, 하는 데이터베이스 엔진 세션이 종료 될 때 작업 영역 및 해당 데이터베이스 컬렉션 유지 되지 않습니다. 다시 만들어야으로 다음 세션에 대 한 작업 영역 및 데이터베이스를 다시 열어 합니다.  
  
 관련된 정보에 대 한 "Close 메서드" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="committrans"></a>  CDaoWorkspace::CommitTrans  
 트랜잭션을 커밋하는이 함수를 호출-편집 하 고 업데이트의 그룹 작업 영역에서 하나 이상의 데이터베이스에 저장 합니다.  
  
```  
void CommitTrans();
```  
  
### <a name="remarks"></a>설명  
 트랜잭션이 변경 데이터베이스의 데이터 또는 호출 하 여 시작 하 고 해당 구조에 구성 된 [BeginTrans](#begintrans)합니다. 트랜잭션을 완료 하는 경우 하나 커밋하거나 롤백하지 다시 (변경 내용을 취소)와 [롤백](#rollback)합니다. 기본적으로 트랜잭션 없이 레코드의 업데이트를 커밋할 즉시 됩니다. 호출 **BeginTrans** 호출할 때까지 지연 될 업데이트의 기여를 사용 하면 **CommitTrans**합니다.  
  
> [!CAUTION]
>  하나의 작업 영역 내에서 트랜잭션은 항상 전체 작업 영역에 이며 하나의 데이터베이스 또는 레코드 집합으로 제한 되지 않습니다. 둘 이상의 데이터베이스 또는 작업 영역 트랜잭션 내에서 레코드 집합에 대 한 작업을 수행 하는 경우 **CommitTrans** 업데이트를 보류 중인 모든 커밋 및 **롤백** 해당 데이터베이스에 대 한 모든 작업을 복원 하 고 레코드 집합입니다.  
  
 데이터베이스 또는 보류 중인 트랜잭션 작업 영역을 닫으면 트랜잭션이 모두 롤백됩니다.  
  
> [!NOTE]
>  2 단계 커밋 장치가 없습니다. 한 번의 업데이트 커밋에 실패 하는 경우 다른 여전히 주 복제본은 커밋합니다.  
  
##  <a name="compactdatabase"></a>  CDaoWorkspace::CompactDatabase  
 지정 된 Microsoft Jet 압축 하려면이 멤버 함수 호출 (합니다. MDB) 데이터베이스입니다.  
  
```  
static void PASCAL CompactDatabase(
    LPCTSTR lpszSrcName,  
    LPCTSTR lpszDestName,  
    LPCTSTR lpszLocale = dbLangGeneral,  
    int nOptions = 0);

 
static void PASCAL CompactDatabase(
    LPCTSTR lpszSrcName,  
    LPCTSTR lpszDestName,  
    LPCTSTR lpszLocale,  
    int nOptions,  
    LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszSrcName`  
 기존 열의 이름에는 데이터베이스를 닫혀 있습니다. 것이 전체 경로 파일 이름, 예: "c:\\\MYDB 합니다. MDB "입니다. 파일 이름 확장명이 지정 해야 합니다. 네트워크 경로 네트워크에 균일 한 명명 규칙 (UNC)를 지 원하는 경우와 같은 지정할 수도 있습니다 "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB 합니다. MDB "입니다. (때문에 경로 문자열에 필요한 이중 백슬래시 "\\" c + + 이스케이프 문자입니다.)  
  
 `lpszDestName`  
 만들고 있는 압축된 된 데이터베이스의 전체 경로입니다. 으로 네트워크 경로를 지정할 수도 있습니다 `lpszSrcName`합니다. 사용할 수 없습니다는 `lpszDestName` 로 동일한 데이터베이스 파일을 지정 하려면 인수 `lpszSrcName`합니다.  
  
 `lpszPassword`  
 암호로 보호 된 데이터베이스를 압축할 때 사용 되는 암호입니다. 버전을 사용 하는 경우 `CompactDatabase` 암호를 사용 하는 모든 매개 변수를 제공 해야 합니다. 또한 연결 매개 변수 이기 때문에 필요한 다음과 같은 특수 한 서식,:; PWD = `lpszPassword`합니다. 예를 들어:; PWD = "정상적인"입니다. (선행 세미콜론은 필요 합니다.)  
  
 `lpszLocale`  
 만들기 위한 데이터 정렬 순서를 지정 하는 데 사용 하는 문자열 식 `lpszDestName`합니다. 기본값을 그대로 사용 하 여이 인수를 생략 하면 **dbLangGeneral** (아래 참조)는 이전 데이터베이스의 새 데이터베이스의 로캘을 같습니다. 가능한 값은 다음과 같습니다.  
  
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
  
 `nOptions`  
 대상 데이터베이스에 대 한 하나 이상의 옵션을 나타내는 `lpszDestName`합니다. 기본값을 그대로 사용 하 여이 인수를 생략 하면는 `lpszDestName` 동일한 암호화와 동일한 버전으로 `lpszSrcName`합니다. 결합할 수는 **dbEncrypt** 또는 **dbDecrypt** 비트 OR 연산자를 사용 하 여 버전 옵션 중 하나가 지정 된 옵션입니다. 데이터베이스 엔진 버전이 아닌 데이터베이스 형식 지정 하는 가능한 값은 같습니다.  
  
- **dbEncrypt** 압축 하는 동안 데이터베이스를 암호화 합니다.  
  
- **dbDecrypt** 압축 하는 동안 데이터베이스의 암호를 해독 합니다.  
  
- **dbVersion10** 압축 하는 동안 Microsoft Jet 데이터베이스 엔진 버전 1.0을 사용 하는 데이터베이스를 만듭니다.  
  
- **dbVersion11** 압축 하는 동안 Microsoft Jet 데이터베이스 엔진 버전 1.1을 사용 하는 데이터베이스를 만듭니다.  
  
- **dbVersion20** 압축 하는 동안 Microsoft Jet 데이터베이스 엔진 버전 2.0을 사용 하는 데이터베이스를 만듭니다.  
  
- **dbVersion30** 압축 하는 동안 Microsoft Jet 데이터베이스 엔진 버전 3.0을 사용 하는 데이터베이스를 만듭니다.  
  
 사용할 수 있습니다 **dbEncrypt** 또는 **dbDecrypt** 옵션 인수의 암호화 하거나 암호를 해독 데이터베이스는 압축 여부를 지정 합니다. 암호화 하는 상수를 생략 하는 경우 또는 둘 모두를 포함 하는 경우 **dbDecrypt** 및 **dbEncrypt**, `lpszDestName` 와 같은 암호화 갖습니다 `lpszSrcName`합니다. Options 인수에 버전 상수 중 하나를 사용 하 여 압축된 된 데이터베이스에 대 한 데이터 형식 버전을 지정할 수 있습니다. 이 상수의 데이터 형식 버전에만 영향을 줍니다 `lpszDestName`합니다. 하나의 버전 상수를 지정할 수 있습니다. 버전 상수를 생략 하면 `lpszDestName` 동일한 버전으로 갖습니다 `lpszSrcName`합니다. 압축할 수 `lpszDestName` 일치 하는 버전에만 또는 이후의 `lpszSrcName`합니다.  
  
> [!CAUTION]
>  데이터베이스 암호화 되지 않은 경우 가능한 경우 직접 데이터베이스를 구성 하는 이진 디스크 파일을 읽을 수의 사용자/암호 보안을 구현 하는 경우에입니다.  
  
### <a name="remarks"></a>설명  
 데이터베이스의 데이터를 변경 하면 데이터베이스 파일 조각화 될 수 있습니다 및 필요한 경우 보다 더 많은 디스크 공간을 사용 합니다. 정기적으로 프로그램 데이터베이스에 데이터베이스 파일을 압축 해야 합니다. 압축된 된 데이터베이스는 일반적으로 작습니다. 또한 복사 하는 데이터베이스를 압축 하는 동안 정렬 순서, 암호화, 또는 데이터 형식 버전을 변경할 수 있습니다.  
  
> [!CAUTION]
>  `CompactDatabase` 멤버 함수는 변환 하지 않습니다 올바르게 Microsoft Access 데이터베이스를 완전 한 버전에서 다른 합니다. 데이터 형식에만 변환 됩니다. Microsoft Access 정의 개체를 가급적, 변환 되지 않습니다. 그러나 데이터가 올바르게 변환 됩니다.  
  
> [!TIP]
>  사용할 수도 있습니다 `CompactDatabase` 데이터베이스 파일을 복사 합니다.  
  
 데이터베이스 압축에 대 한 자세한 내용은 DAO 도움말의 "CompactDatabase Method" 항목을 참조 합니다.  
  
##  <a name="create"></a>  CDaoWorkspace::Create  
 새 DAO workspace 개체를 만들고 MFC와 연결 하려면이 함수를 호출 `CDaoWorkspace` 개체입니다.  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    LPCTSTR lpszUserName,  
    LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 새 작업 영역 개체의 고유 이름을 지정 하는 최대 14 자 문자열입니다. 이름을 제공 해야 합니다. 관련된 정보에 대 한 항목 DAO 도움말의 "Name 속성"을 참조 합니다.  
  
 *lpszUserName*  
 작업 공간의 소유자의 사용자 이름입니다. 요구 사항에 대 한 참조는 `lpszDefaultUser` 매개 변수를는 [SetDefaultUser](#setdefaultuser) 멤버 함수입니다. 관련된 정보에 대 한 항목 DAO 도움말의 "UserName 속성"을 참조 합니다.  
  
 `lpszPassword`  
 새 작업 영역 개체에 대 한 암호입니다. 암호 최대 14 자까지 가능 하며 ASCII 0 (null)를 제외한 모든 문자를 포함할 수 있습니다. 암호는 대/소문자 구분 합니다. 관련된 정보에 대 한 DAO 도움말의 "암호 Property" 항목을 참조 합니다.  
  
### <a name="remarks"></a>설명  
 다음은 전체 생성 프로세스가입니다.  
  
1.  생성 된 [CDaoWorkspace](#cdaoworkspace) 개체입니다.  
  
2.  개체의 **만들기** 멤버 함수를 기본 DAO 작업 영역을 만듭니다. 작업 영역 이름을 지정 해야 합니다.  
  
3.  필요에 따라 호출 [Append](#append) 작업 영역 데이터베이스 엔진의 작업 영역 컬렉션에 추가 하려는 경우. 작업 영역에 추가 하지 않고 작업할 수 있습니다.  
  
 후의 **만들기** 열린 상태를 사용할 준비가 호출이, 영역 개체입니다. 호출 하지 않으면 **열려** 후 **만들기**합니다. 호출 하지 않으면 **만들기** 작업 영역의 작업 영역 컬렉션에 이미 있는 경우. **만들** 이미 응용 프로그램에 대 한 초기화 되지 않은 경우에 데이터베이스 엔진을 초기화 합니다.  
  
##  <a name="getdatabasecount"></a>  CDaoWorkspace::GetDatabaseCount  
 작업 영역 데이터베이스 컬렉션에서 DAO 데이터베이스 개체의 수를 검색 하려면이 함수를 호출-작업 영역에서 열려 있는 데이터베이스의 수입니다.  
  
```  
short GetDatabaseCount();
```  
  
### <a name="return-value"></a>반환 값  
 작업 영역에서 열려 있는 데이터베이스의 수입니다.  
  
### <a name="remarks"></a>설명  
 `GetDatabaseCount` 작업 영역 데이터베이스 컬렉션에 정의 된 모든 데이터베이스를 반복 하는 경우 유용 합니다. 컬렉션에서 지정된 된 데이터베이스에 대 한 정보를 얻으려면 참조 [GetDatabaseInfo](#getdatabaseinfo)합니다. 일반적인 사용법은 호출 `GetDatabaseCount` 열려 있는 데이터베이스 수에 대 한 다음 해당 번호를 사용으로 루프 인덱스에 대 한 반복된 호출 `GetDatabaseInfo`합니다.  
  
##  <a name="getdatabaseinfo"></a>  CDaoWorkspace::GetDatabaseInfo  
 다양 한 종류의 작업 영역 데이터베이스를 열에 대 한 정보를 가져오려면이 함수를 호출 합니다.  
  
```  
void GetDatabaseInfo(
    int nIndex,  
    CDaoDatabaseInfo& dbinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetDatabaseInfo(
    LPCTSTR lpszName,  
    CDaoDatabaseInfo& dbinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 인덱스에 의해 조회에는 작업 영역 데이터베이스 컬렉션에서 데이터베이스 개체의 0부터 시작 하는 인덱스입니다.  
  
 `dbinfo`  
 에 대 한 참조는 [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) 요청 된 정보를 반환 하는 개체입니다.  
  
 `dwInfoOptions`  
 검색할 데이터베이스에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 함께 반환 하는 함수를 입히기 무엇 여기 나열 됩니다.  
  
- `AFX_DAO_PRIMARY_INFO` (기본값) 이름, 업데이트 가능한 트랜잭션  
  
- `AFX_DAO_SECONDARY_INFO` 기본 정보 더하기: 버전, 데이터 정렬 순서, 쿼리 제한 시간  
  
- `AFX_DAO_ALL_INFO` 기본 및 보조 정보 더하기: 연결  
  
 `lpszName`  
 이름별으로 조회에 대 한 데이터베이스 개체의 이름입니다. 이름을 고유 하 게 새 작업 영역 개체의 이름을 지정 하는 최대 14 자 문자열입니다.  
  
### <a name="remarks"></a>설명  
 한 버전의 함수를 사용 하면 인덱스는 데이터베이스를 찾을 수 있습니다. 다른 버전에서는 데이터베이스 이름으로 조회할 수 있습니다.  
  
 에 대 한 설명은에서 반환 되는 정보 `dbinfo`, 참조는 [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) 구조입니다. 이 구조에는 항목의 설명에 위에 나열 된 정보에 해당 하는 멤버가 `dwInfoOptions`합니다. 한 수준에서 정보를 요청할 때 모든 상위 수준의에 대 한 정보를 가져옵니다.  
  
##  <a name="getinipath"></a>  CDaoWorkspace::GetIniPath  
 Microsoft Jet 데이터베이스의 위치를 Windows 레지스트리에 엔진의 초기화 설정을 가져오려면이 함수를 호출 합니다.  
  
```  
static CString PASCAL GetIniPath();
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 레지스트리 위치를 포함 합니다.  
  
### <a name="remarks"></a>설명  
 데이터베이스 엔진에 대 한 설정에 대 한 정보를 가져올 위치를 사용할 수 있습니다. 반환 되는 정보는 실제로 레지스트리 하위 키의 이름입니다.  
  
 관련된 정보에 대 한 "IniPath 속성" 및 "사용자 지정 Windows 레지스트리 설정에 대 한 데이터 액세스" DAO 도움말의 항목을 참조 합니다.  
  
##  <a name="getisolateodbctrans"></a>  CDaoWorkspace::GetIsolateODBCTrans  
 작업 영역에 대 한 DAO IsolateODBCTrans 속성의 현재 값을 가져오려면이 함수를 호출 합니다.  
  
```  
BOOL GetIsolateODBCTrans();
```  
  
### <a name="return-value"></a>반환 값  
 ODBC 트랜잭션 격리; 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 경우에 따라 보류 중인 여러 동시 트랜잭션이 동일한 ODBC 데이터베이스에 있어야 할 수 있습니다. 이 작업을 수행 하려면 각 트랜잭션에 대 한 별도 작업 영역을 엽니다. 각 작업 영역 데이터베이스에는 자체 ODBC 연결 수 있지만,이 경우 시스템 성능이 저하 염두에서에 둬야 합니다. 트랜잭션 격리 일반적으로 필요 하지 않으므로 기본적으로 ODBC 연결에서 동일한 사용자가 연 여러 작업 영역 개체에서 공유 됩니다.  
  
 Microsoft SQL Server와 같은 일부 ODBC 서버는 단일 연결에서 동시 트랜잭션을 허용 하지 않습니다. 이러한 데이터베이스에 대해 보류 중인 한 번에 둘 이상의 트랜잭션 해야 할 경우 IsolateODBCTrans 속성을 설정 **TRUE** 열어야 하는 즉시 각 작업 영역에 있습니다. 이렇게 하면 각 작업 영역에 대 한 별도 ODBC 연결 됩니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "IsolateODBCTrans Property" 항목을 참조 합니다.  
  
##  <a name="getlogintimeout"></a>  CDaoWorkspace::GetLoginTimeout  
 작업 영역에 대 한 DAO LoginTimeout 속성의 현재 값을 가져오려면이 함수를 호출 합니다.  
  
```  
static short PASCAL GetLoginTimeout();
```  
  
### <a name="return-value"></a>반환 값  
 ODBC 데이터베이스에 로그인 하려고 할 때 오류가 발생 하기 전에 시간 (초) 수입니다.  
  
### <a name="remarks"></a>설명  
 이 값은 ODBC 데이터베이스에 로그인 하려고 할 때 오류가 발생 하기 전에 시간 (초) 수를 나타냅니다. LoginTimeout 기본값은 20 초입니다. LoginTimeout을 0으로 설정 하는 경우 제한 시간이 없음을 발생 하 고 데이터 소스와의 통신 응답 하지 않을 수 있습니다.  
  
 네트워크 오류로 인해 연결이 실패할 수 있습니다, Microsoft SQL Server와 같은 ODBC 데이터베이스에 로그인 하려고 하는 경우 서버가 실행 중이 아니므로 또는 합니다. 기본값에 대 한 20 초를 위해 대기 중인 연결 하는 대신 데이터베이스 엔진에서 오류가 발생 하기 전에 대기 하는 시간을 지정할 수 있습니다. 외부 서버 데이터베이스에 대 한 쿼리를 실행 하는 등의 다른 이벤트의 숫자 부분으로 암시적으로 발생 서버에 로그인 합니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "LoginTimeout Property" 항목을 참조 합니다.  
  
##  <a name="getname"></a>  CDaoWorkspace::GetName  
 DAO 작업 영역 개체 내부의 사용자 정의 이름을 가져오려면이 함수를 호출는 `CDaoWorkspace` 개체입니다.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) DAO 영역 개체의 사용자 정의 이름을 포함 합니다.  
  
### <a name="remarks"></a>설명  
 이름은 이름으로 데이터베이스 엔진의 작업 영역 컬렉션에서 DAO workspace 개체에 액세스 하는 데 유용 합니다.  
  
 관련된 정보에 대 한 항목 DAO 도움말의 "Name 속성"을 참조 합니다.  
  
##  <a name="getusername"></a>  CDaoWorkspace::GetUserName  
 작업 영역의 소유자의 이름을 가져오려면이 함수를 호출 합니다.  
  
```  
CString GetUserName();
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 영역 개체의 소유자를 나타내는입니다.  
  
### <a name="remarks"></a>설명  
 를 가져오거나 작업 영역 소유자에 대 한 사용 권한을 설정 하려면 사용 권한을 속성 설정을; 확인 하려면 직접 DAO 호출 사용 권한을 결정이 해당 사용자에 게 있습니다. 사용 권한, 사용 하는 시스템이 필요 합니다. MDA 파일입니다.  
  
 DAO 호출 하는 방법에 대 한 정보에 대 한 참조를 직접 [기술 참고 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)합니다. 관련된 정보에 대 한 항목 DAO 도움말의 "UserName 속성"을 참조 합니다.  
  
##  <a name="getversion"></a>  CDaoWorkspace::GetVersion  
 사용 중인 Microsoft Jet 데이터베이스 엔진의 버전을 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
static CString PASCAL GetVersion();
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체에 연결 된 데이터베이스 엔진의 버전을 나타내는입니다.  
  
### <a name="remarks"></a>설명  
 반환 되는 값 "major.minor"; 버전 번호를 나타냅니다. 예를 들어 "3.0"입니다. 제품 버전 번호 (예를 들어 3.0) (3) 버전 번호, 마침표, 및 릴리스 번호 (0)으로 이루어져 있습니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "버전 Property" 항목을 참조 합니다.  
  
##  <a name="getworkspacecount"></a>  CDaoWorkspace::GetWorkspaceCount  
 데이터베이스 엔진의 작업 영역 컬렉션에서 DAO 작업 영역 개체의 수를 검색 하려면이 함수를 호출 합니다.  
  
```  
short GetWorkspaceCount();
```  
  
### <a name="return-value"></a>반환 값  
 작업 영역 컬렉션에서 열기 작업 영역 수를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 이 개수는 열린 작업 영역 컬렉션에 추가 되지 포함 되지 않습니다. `GetWorkspaceCount` 작업 영역 컬렉션에 정의 된 모든 작업 영역을 반복 하는 경우 유용 합니다. 컬렉션에서 지정된 된 작업 영역에 대 한 정보를 얻으려면 참조 [GetWorkspaceInfo](#getworkspaceinfo)합니다. 일반적인 사용법은 호출 `GetWorkspaceCount` 열기 작업 영역 수에 대 한 다음 해당 번호를 사용으로 루프 인덱스에 대 한 반복된 호출 `GetWorkspaceInfo`합니다.  
  
##  <a name="getworkspaceinfo"></a>  CDaoWorkspace::GetWorkspaceInfo  
 다양 한 종류의 세션에서 작업 영역 열기에 대 한 정보를 가져오려면이 함수를 호출 합니다.  
  
```  
void GetWorkspaceInfo(
    int nIndex,  
    CDaoWorkspaceInfo& wkspcinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetWorkspaceInfo(
    LPCTSTR lpszName,  
    CDaoWorkspaceInfo& wkspcinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 인덱스에 의해 조회에 대 한 작업 영역 컬렉션에서 데이터베이스 개체의 0부터 시작 하는 인덱스입니다.  
  
 `wkspcinfo`  
 에 대 한 참조는 [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) 요청 된 정보를 반환 하는 개체입니다.  
  
 `dwInfoOptions`  
 작업 영역을 검색 하는 방법에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 함께 반환 하는 함수를 입히기 무엇 여기 나열 됩니다.  
  
- `AFX_DAO_PRIMARY_INFO` (기본값) 이름  
  
- `AFX_DAO_SECONDARY_INFO` 기본 정보 더하기: 사용자 이름  
  
- `AFX_DAO_ALL_INFO` 기본 및 보조 정보 더하기: ODBCTrans 격리  
  
 `lpszName`  
 이름별으로 조회에 대 한 작업 영역 개체의 이름입니다. 이름을 고유 하 게 새 작업 영역 개체의 이름을 지정 하는 최대 14 자 문자열입니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 설명은에서 반환 되는 정보 `wkspcinfo`, 참조는 [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) 구조입니다. 이 구조에는 항목의 설명에 위에 나열 된 정보에 해당 하는 멤버가 `dwInfoOptions`합니다. 한 수준에서 정보를 요청 하는 경우 상위 수준의에 대 한 정보를 가져옵니다.  
  
##  <a name="idle"></a>  CDaoWorkspace::Idle  
 호출 **Idle** 에 제공 하기 위해 데이터베이스 엔진 강한 데이터 처리로 인해 최신 상태가 아닐 수 있습니다 하는 백그라운드 작업을 수행할 수 있습니다.  
  
```  
static void PASCAL Idle(int nAction = dbFreeLocks);
```  
  
### <a name="parameters"></a>매개 변수  
 `nAction`  
 유휴 처리 하는 동안 수행할 동작입니다. 유효한 작업은 현재 **dbFreeLocks**합니다.  
  
### <a name="remarks"></a>설명  
 없는 레코드 집합의 모든 레코드를 최신 상태로 유지 하는 데 충분 한 백그라운드 처리 시간이 다중 사용자, 멀티태스킹 환경에서 더욱 그렇습니다.  
  
> [!NOTE]
>  호출 **Idle** Microsoft Jet 데이터베이스 엔진의 버전 3.0 사용 하 여 만든 데이터베이스와 필요 하지 않습니다. 사용 하 여 **Idle** 이전 버전을 사용 하 여 만든 데이터베이스에 대해서만 합니다.  
  
 일반적으로 읽기 잠금이 해제 되 고 로컬 다이너셋 형식 레코드 집합 개체의 데이터 (마우스 움직임 포함) 다른 동작이 발생 하는 경우에 업데이트 됩니다. 주기적으로 호출 하는 경우 **Idle**, 백그라운드 처리를 해제 하 여 작업을 처리 하는 시간으로 데이터베이스 엔진 필요 없는 읽기 잠금을 제공 합니다. 지정 하는 **dbFreeLocks** 상수 인수로 서 모든 읽기 잠금이 해제 될 때까지 처리를 지연 합니다.  
  
 이 멤버 함수는 응용 프로그램의 여러 인스턴스를 실행 하지 않는 단일 사용자 환경에 필요 하지 않습니다. **Idle** 멤버 함수는 데이터베이스 엔진이 데이터를 플러시하지를 디스크에 메모리의 잠금을 해제 하기 때문에 다중 사용자 환경에서 성능을 증가할 수 있습니다. 트랜잭션의 작업 포함 하 여 읽기 잠금을 해제할 수도 있습니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "유휴 Method" 항목을 참조 합니다.  
  
##  <a name="isopen"></a>  CDaoWorkspace::IsOpen  
 확인 하려면이 함수를 호출 여부는 `CDaoWorkspace` 개체가 열려-즉, 여부 MFC 개체에 의해 초기화에 대 한 호출 [열고](#open) 호출이 나 [만들기](#create)합니다.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>반환 값  
 작업 영역 개체가 열려 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 함수를 호출할 수는 멤버의 모든 열린 상태에 있는 작업 영역입니다.  
  
##  <a name="m_pdaoworkspace"></a>  CDaoWorkspace::m_pDAOWorkspace  
 기본 DAO workspace 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 데이터 멤버를 사용 하 여 기본 DAO 개체에 대 한 액세스를 지시 해야 하는 경우. 이 포인터를 통해 DAO 개체의 인터페이스를 호출할 수 있습니다.  
  
 DAO 개체에 직접 액세스 하는 방법에 대 한 정보를 참조 하십시오. [기술 참고 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)합니다.  
  
##  <a name="open"></a>  CDaoWorkspace::Open  
 DAO의 기본 작업 영역과 연결 된 작업 영역 개체를 명시적으로 엽니다.  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 열려는 DAO 작업 영역 개체의 이름-고유 하 게 작업 영역 이름을 지정 하는 최대 14 문자가 있는 문자열입니다. 기본값을 그대로 **NULL** 를 명시적으로 기본 작업 영역을 열어야 합니다. 명명 요구 사항에 대 한 참조는 `lpszName` 에 대 한 매개 변수 [만들기](#create)합니다. 관련된 정보에 대 한 항목 DAO 도움말의 "Name 속성"을 참조 합니다.  
  
### <a name="remarks"></a>설명  
 생성 한 후 한 `CDaoWorkspace` 개체, 다음 중 하나를 수행 하려면이 함수를 호출 합니다.  
  
-   기본 작업 영역을 명시적으로 열어야 합니다. 전달 **NULL** 에 대 한 `lpszName`합니다.  
  
-   기존 `CDaoWorkspace` 개체, 이름 기준으로 작업 영역 컬렉션의 구성원입니다. 기존 작업 영역 개체에 대 한 올바른 이름을 전달 합니다.  
  
 **열고** 열린 상태에 작업 영역 개체를 넣고 이미 응용 프로그램에 대 한 초기화 되지 않은 경우에 데이터베이스 엔진을 초기화 합니다.  
  
 하지만 많은 `CDaoWorkspace` 작업 영역이 열린 후에 함수를 호출할 수는 멤버를 호출 하기 전에 하지만 c + + 개체의 생성 한 후 데이터베이스 엔진에서 작동 하는 다음 멤버 함수를 사용할 수 있는 **열기** :  
  
||||  
|-|-|-|  
|[만들기](#create)|[GetVersion](#getversion)|[SetDefaultUser](#setdefaultuser)|  
|[GetIniPath](#getinipath)|[Idle](#idle)|[SetIniPath](#setinipath)|  
|[GetLoginTimeout](#getlogintimeout)|[SetDefaultPassword](#setdefaultpassword)|[SetLoginTimeout](#setlogintimeout)|  
  
##  <a name="repairdatabase"></a>  CDaoWorkspace::RepairDatabase  
 Microsoft Jet 데이터베이스 엔진에 액세스 하는 손상된 된 데이터베이스를 복구 하는 경우이 함수를 호출 합니다.  
  
```  
static void PASCAL RepairDatabase(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 경로 기존 Microsoft Jet 엔진 데이터베이스 파일에 대 한 파일 이름입니다. 경로 생략 하면 현재 디렉터리만 검색 됩니다. 시스템 일정 한 명명 규칙 (UNC)를 지 원하는 경우와 같은 네트워크 경로도 지정할 수 있습니다: "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB 합니다. MDB "입니다. (때문에 경로 문자열에 이중 백슬래시는 필요 "\\" c + + 이스케이프 문자입니다.)  
  
### <a name="remarks"></a>설명  
 지정한 데이터베이스를 닫아야 `lpszName` 복구 하기 전에. 다중 사용자 환경에서는 다른 사용자가 사용할 수 없습니다 `lpszName` 복구 하려는 동안 열입니다. 경우 `lpszName` 이 닫혀 있지 않거나 사용할 수 없는 독점적인 사용을 위해 오류가 발생 합니다.  
  
 이 멤버 함수는 불완전 한 쓰기 작업으로 손상 된 표시 된 데이터베이스를 복구 하려고 합니다. Microsoft Jet 데이터베이스 엔진을 사용 하 여 응용 프로그램 전원 가동 중단 또는 컴퓨터 하드웨어 문제 때문에 예기치 않게 종료 발생할 수 있습니다. 작업 및 호출을 완료 하는 경우는 [닫기](../../mfc/reference/cdaodatabase-class.md#close) 데이터베이스가 표시 되지 것입니다으로 손상 된, 또는 멤버 함수는 일반적인 방법으로 응용 프로그램을 종료 합니다.  
  
> [!NOTE]
>  데이터베이스를 수정한 후 이기도 사용 하 여 압축 하는 것이 좋습니다는 [CompactDatabase](#compactdatabase) 멤버 함수는 파일을 조각 모음을 수행 하 고 디스크 공간을 복구 합니다.  
  
 데이터베이스 복구에 대 한 자세한 내용은 DAO 도움말의 "것 이었습니다 Method" 항목을 참조 합니다.  
  
##  <a name="rollback"></a>  CDaoWorkspace::Rollback  
 현재 트랜잭션이 종료 되 고 트랜잭션이 시작 되기 전에 해당 상태를 작업 영역에서 모든 데이터베이스를 복원 하려면이 멤버 함수를 호출 합니다.  
  
```  
void Rollback();
```  
  
### <a name="remarks"></a>설명  
  
> [!CAUTION]
>  하나의 작업 영역 개체 내에서 트랜잭션은 항상 전체 작업 영역에 이며 하나의 데이터베이스 또는 레코드 집합으로 제한 되지 않습니다. 둘 이상의 데이터베이스 또는 작업 영역 트랜잭션 내에서 레코드 집합에 대 한 작업을 수행 하는 경우 **롤백** 모든 해당 데이터베이스 및 레코드 집합에 대 한 모든 작업을 복원 합니다.  
  
 작업 영역 개체를 저장 하거나 보류 중인 모든 트랜잭션을 롤백하는 하지 않고 닫으면 트랜잭션이 자동으로 롤백됩니다. 호출 하는 경우 [CommitTrans](#committrans) 또는 **롤백** 먼저 호출 하지 않고 [BeginTrans](#begintrans), 오류가 발생 합니다.  
  
> [!NOTE]
>  트랜잭션을 시작할 때 데이터베이스 엔진 워크스테이션에서 TEMP 환경 변수로 지정 된 디렉터리에 보관 파일에서 해당 작업을 기록 합니다. 트랜잭션 로그 파일 임시 드라이브에 사용 가능한 저장소를 소모를 하는 경우 데이터베이스 엔진 MFC throw 하면는 `CDaoException` (DAO 오류 2004). 이 시점에서 호출 하는 경우 **CommitTrans**, 무제한 작업으로 커밋됩니다. 하지만 나머지 완료 되지 않은 작업이 손실 되 고 작업에 다시 시작 해야 합니다. 호출 **롤백** 트랜잭션 로그를 해제 하 고 트랜잭션의 모든 작업이 롤백됩니다.  
  
##  <a name="setdefaultpassword"></a>  CDaoWorkspace::SetDefaultPassword  
 특정 암호 없이 workspace 개체를 만들 때 데이터베이스 엔진에 사용 되는 기본 암호를 설정 하려면이 함수를 호출 합니다.  
  
```  
static void PASCAL SetDefaultPassword(LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszPassword`  
 기본 암호입니다. 암호 최대 14 자까지 가능 하며 ASCII 0 (null)를 제외한 모든 문자를 포함할 수 있습니다. 암호는 대/소문자 구분 합니다.  
  
### <a name="remarks"></a>설명  
 호출 후 만들 새 작업 영역을 설정 하는 기본 암호 적용 됩니다. 후속 작업 영역을 만들 때 필요가 없습니다에 암호를 지정 하는 [만들기](#create) 호출 합니다.  
  
 사용 하려면이 멤버 함수:  
  
1.  생성 한 `CDaoWorkspace` 개체 되지만 호출 하지 않으면 **만들기**합니다.  
  
2.  호출 `SetDefaultPassword` 및 원하는 경우 [SetDefaultUser](#setdefaultuser)합니다.  
  
3.  호출 **만들기** 이 작업 영역 개체 또는 이후의 조건에 대 한 하지 않고 암호를 지정 합니다.  
  
 기본적으로 DefaultUser 속성 "admin"으로 설정 되 고 해야 속성을 빈 문자열 ("").  
  
 보안에 대 한 자세한 DAO 도움말의 "사용 권한 Property" 항목을 참조 하십시오. 관련된 정보에 대 한 "해야 속성" 및 DAO 도움말의 "DefaultUser Property" 항목을 참조 합니다.  
  
##  <a name="setdefaultuser"></a>  CDaoWorkspace::SetDefaultUser  
 특정 사용자 이름 없이 작업 영역 개체를 만들 때 데이터베이스 엔진을 사용 하는 기본 사용자 이름을 설정 하려면이 함수를 호출 합니다.  
  
```  
static void PASCAL SetDefaultUser(LPCTSTR lpszDefaultUser);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszDefaultUser`  
 기본 사용자 이름입니다. 사용자 이름 길이 1 ~ 20 자 수 있으며 영문자, 악센트 부호가 있는 문자, 숫자, 공백 및 기호를 제외 하 고 포함: "(인용 부호 제외) / (슬래시), \ (백슬래시) \[ \] (괄호): (콜론) &#124; 드 ( 파이프) \< (덜-기호 보다), > (큰-기호 보다), + (더하기 기호) = (작거나 기호); (세미콜론), (쉼표), (물음표) * (별표)을 앞에 공백, 및 제어 문자 (ASCII 00 ASCII 31). 관련된 정보에 대 한 항목 DAO 도움말의 "UserName 속성"을 참조 합니다.  
  
### <a name="remarks"></a>설명  
 기본 사용자 이름을 설정 하는 호출 후 만들 새 작업 영역에 적용 됩니다. 후속 작업 영역을 만들 때 필요가 없습니다에 사용자 이름을 지정 하는 [만들기](#create) 호출 합니다.  
  
 사용 하려면이 멤버 함수:  
  
1.  생성 한 `CDaoWorkspace` 개체 되지만 호출 하지 않으면 **만들기**합니다.  
  
2.  호출 `SetDefaultUser` 및 원하는 경우 [SetDefaultPassword](#setdefaultpassword)합니다.  
  
3.  호출 **만들기** 이 작업 영역 개체 또는 이후의 조건에 대 한 관계 없이 사용자 이름을 지정 합니다.  
  
 기본적으로 DefaultUser 속성 "admin"으로 설정 되 고 해야 속성을 빈 문자열 ("").  
  
 관련된 정보에 대 한 "DefaultUser 속성" 및 DAO 도움말의 "해야 Property" 항목을 참조 합니다.  
  
##  <a name="setinipath"></a>  CDaoWorkspace::SetIniPath  
 Microsoft Jet 데이터베이스 엔진에 대 한 Windows 레지스트리 설정의 위치를 지정 하려면이 멤버 함수를 호출 합니다.  
  
```  
static void PASCAL SetIniPath(LPCTSTR lpszRegistrySubKey);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszRegistrySubkey*  
 Microsoft Jet 데이터베이스 엔진 설정 및 설치 가능한 ISAM 데이터베이스에 필요한 매개 변수 위치에 대 한 Windows 레지스트리 하위 키의 이름을 포함 하는 문자열입니다.  
  
### <a name="remarks"></a>설명  
 호출 `SetIniPath` 특별 한 설정을 지정 해야 하는 경우에 합니다. 자세한 내용은 DAO 도움말의 "IniPath Property" 항목을 참조 하십시오.  
  
> [!NOTE]
>  호출 `SetIniPath` 응용 프로그램 설치 하는 동안 하지 때 응용 프로그램을 실행 합니다. `SetIniPath` 모든 작업 영역, 데이터베이스 또는 레코드 집합; 열기 전에 호출 해야 합니다. 그렇지 않은 경우 MFC는 예외가 throw 됩니다.  
  
 사용자가 제공한 레지스트리 설정을 사용 하 여 데이터베이스 엔진을 구성 하려면이 메커니즘을 사용할 수 있습니다. 이 특성의 범위는 응용 프로그램으로 제한 하 고 응용 프로그램을 다시 시작 하지 않아도 변경할 수 없습니다.  
  
##  <a name="setisolateodbctrans"></a>  CDaoWorkspace::SetIsolateODBCTrans  
 작업 영역에 대 한 DAO IsolateODBCTrans 속성의 값을 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetIsolateODBCTrans(BOOL bIsolateODBCTrans);
```  
  
### <a name="parameters"></a>매개 변수  
 *bIsolateODBCTrans*  
 전달 **TRUE** ODBC 트랜잭션 격리를 시작 하려는 경우. 전달 **FALSE** ODBC 트랜잭션 격리를 중지 하려는 경우.  
  
### <a name="remarks"></a>설명  
 경우에 따라 보류 중인 여러 동시 트랜잭션이 동일한 ODBC 데이터베이스에 있어야 할 수 있습니다. 이 작업을 수행 하려면 각 트랜잭션에 대 한 별도 작업 영역을 엽니다. 각 작업 영역 데이터베이스에는 자체 ODBC 연결 수 있지만,이 경우 시스템 성능이 저하 됩니다. 트랜잭션 격리 일반적으로 필요 하지 않으므로 기본적으로 ODBC 연결에서 동일한 사용자가 연 여러 작업 영역 개체에서 공유 됩니다.  
  
 Microsoft SQL Server와 같은 일부 ODBC 서버는 단일 연결에서 동시 트랜잭션을 허용 하지 않습니다. 이러한 데이터베이스에 대해 보류 중인 한 번에 둘 이상의 트랜잭션 해야 할 경우 IsolateODBCTrans 속성을 설정 **TRUE** 열어야 하는 즉시 각 작업 영역에 있습니다. 이렇게 하면 각 작업 영역에 대 한 별도 ODBC 연결 됩니다.  
  
##  <a name="setlogintimeout"></a>  CDaoWorkspace::SetLoginTimeout  
 작업 영역에 대 한 DAO LoginTimeout 속성의 값을 설정 하려면이 함수를 호출 합니다.  
  
```  
static void PASCAL SetLoginTimeout(short nSeconds);
```  
  
### <a name="parameters"></a>매개 변수  
 `nSeconds`  
 ODBC 데이터베이스에 로그인 하려고 할 때 오류가 발생 하기 전에 시간 (초) 수입니다.  
  
### <a name="remarks"></a>설명  
 이 값은 ODBC 데이터베이스에 로그인 하려고 할 때 오류가 발생 하기 전에 시간 (초) 수를 나타냅니다. LoginTimeout 기본값은 20 초입니다. LoginTimeout을 0으로 설정 하는 경우 제한 시간이 없음을 발생 하 고 데이터 소스와의 통신 응답 하지 않을 수 있습니다.  
  
 네트워크 오류로 인해 연결이 실패할 수 있습니다, Microsoft SQL Server와 같은 ODBC 데이터베이스에 로그인 하려고 하는 경우 서버가 실행 중이 아니므로 또는 합니다. 기본값에 대 한 20 초를 위해 대기 중인 연결 하는 대신 데이터베이스 엔진에서 오류가 발생 하기 전에 대기 하는 시간을 지정할 수 있습니다. 외부 서버 데이터베이스에 대 한 쿼리를 실행 하는 등의 다른 이벤트의 숫자 부분으로 암시적으로 발생 서버에 로그온 합니다. 제한 시간 값은 LoginTimeout 속성의 현재 설정에 따라 결정 됩니다.  
  
 관련된 정보에 대 한 DAO 도움말의 "LoginTimeout Property" 항목을 참조 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase 클래스](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset 클래스](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoException 클래스](../../mfc/reference/cdaoexception-class.md)
