---
title: "CDaoWorkspace Class | Microsoft Docs"
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
  - "CDaoWorkspace"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoWorkspace class"
  - "DAO workspaces [C++]"
  - "DAO workspaces [C++], CDaoWorkspace class"
  - "database engine [C++], accessing via workspace"
  - "DDLs[C++]"
  - "default workspaces [C++]"
  - "default workspaces [C++], DAO"
  - "기본값[C++], 작업 영역"
  - "ODBC 클래스[C++], vs. DAO classes"
  - "persistence [C++], DAO workspace"
  - "security [MFC]"
  - "security [MFC], DAO workspaces"
  - "sessions [C++], DAO workspace"
  - "transaction spaces [C++]"
  - "transaction spaces [C++], DAO workspace"
  - "Workspace class"
  - "workspaces [C++], DAO"
  - "workspaces [C++], default"
  - "workspaces [C++], interface to database engine"
  - "workspaces [C++], 지속성"
  - "Workspaces collection"
ms.assetid: 64f60de6-4df1-4d4a-a65b-c489b5257d52
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoWorkspace Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

명명 된, 암호로 보호 된 데이터베이스 세션 단일 사용자가 로그 오프에서 로그인을 관리합니다.  
  
## 구문  
  
```  
class CDaoWorkspace : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDaoWorkspace::CDaoWorkspace](../Topic/CDaoWorkspace::CDaoWorkspace.md)|작업 영역 개체를 만듭니다.  나중에 호출  **만들기** 또는  **열려**.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDaoWorkspace::Append](../Topic/CDaoWorkspace::Append.md)|데이터베이스 엔진의 Workspaces 컬렉션에는 새로 만든된 작업 영역을 추가합니다.|  
|[CDaoWorkspace::BeginTrans](../Topic/CDaoWorkspace::BeginTrans.md)|작업 공간에서 열린 모든 데이터베이스에 적용 하는 새 트랜잭션을 시작 합니다.|  
|[CDaoWorkspace::Close](../Topic/CDaoWorkspace::Close.md)|작업 영역 및 포함 된 개체를 모두 닫습니다.  보류 중인 트랜잭션이 롤백됩니다.|  
|[CDaoWorkspace::CommitTrans](../Topic/CDaoWorkspace::CommitTrans.md)|현재 트랜잭션이 완료 되 고 변경 내용을 저장 합니다.|  
|[CDaoWorkspace::CompactDatabase](../Topic/CDaoWorkspace::CompactDatabase.md)|압축 또는 복제 데이터베이스.|  
|[CDaoWorkspace::Create](../Topic/CDaoWorkspace::Create.md)|DAO 작업 영역 개체를 새로 만듭니다.|  
|[CDaoWorkspace::GetDatabaseCount](../Topic/CDaoWorkspace::GetDatabaseCount.md)|DAO 데이터베이스 개체는 작업 영역의 Databases 컬렉션에서 반환합니다.|  
|[CDaoWorkspace::GetDatabaseInfo](../Topic/CDaoWorkspace::GetDatabaseInfo.md)|정의 작업 영역의 Databases 컬렉션에 지정 된 DAO 데이터베이스에 대 한 정보를 반환 합니다.|  
|[CDaoWorkspace::GetIniPath](../Topic/CDaoWorkspace::GetIniPath.md)|Microsoft Jet 데이터베이스 엔진의 초기화 설정이 Windows 레지스트리에서 반환.|  
|[CDaoWorkspace::GetIsolateODBCTrans](../Topic/CDaoWorkspace::GetIsolateODBCTrans.md)|여러 데이터 소스 연결 강제로 동일한 ODBC 데이터 원본과 관련 된 여러 트랜잭션을 통해 격리 된 있는지 여부를 나타내는 값을 반환 합니다.|  
|[CDaoWorkspace::GetLoginTimeout](../Topic/CDaoWorkspace::GetLoginTimeout.md)|사용자가 ODBC 데이터베이스에 로그온 하려고 할 때 오류가 발생 하기 전에 시간을 초 단위로 반환 합니다.|  
|[CDaoWorkspace::GetName](../Topic/CDaoWorkspace::GetName.md)|Workspace 개체의 사용자 정의 이름을 반환합니다.|  
|[CDaoWorkspace::GetUserName](../Topic/CDaoWorkspace::GetUserName.md)|반환 때 작업 영역을 만든 사용자 이름을 지정 합니다.  작업 영역 소유자의 이름입니다.|  
|[CDaoWorkspace::GetVersion](../Topic/CDaoWorkspace::GetVersion.md)|작업 영역과 관련 된 데이터베이스 엔진의 버전을 포함 하는 문자열을 반환 합니다.|  
|[CDaoWorkspace::GetWorkspaceCount](../Topic/CDaoWorkspace::GetWorkspaceCount.md)|데이터베이스 엔진의 Workspaces 컬렉션에 DAO 작업 영역 개체를 반환합니다.|  
|[CDaoWorkspace::GetWorkspaceInfo](../Topic/CDaoWorkspace::GetWorkspaceInfo.md)|데이터베이스 엔진 작업 영역 컬렉션에 정의 된 지정 된 DAO 작업 영역에 대 한 정보를 반환 합니다.|  
|[CDaoWorkspace::Idle](../Topic/CDaoWorkspace::Idle.md)|데이터베이스 엔진을 백그라운드 작업을 수행할 수 있습니다.|  
|[CDaoWorkspace::IsOpen](../Topic/CDaoWorkspace::IsOpen.md)|연 작업 영역에 있는 경우 0이 아닌 반환 합니다.|  
|[CDaoWorkspace::Open](../Topic/CDaoWorkspace::Open.md)|DAO의 기본 작업 영역에 연결 된 작업 공간 객체를 명시적으로 열립니다.|  
|[CDaoWorkspace::RepairDatabase](../Topic/CDaoWorkspace::RepairDatabase.md)|손상 된 데이터베이스를 복구 하려고 시도 합니다.|  
|[CDaoWorkspace::Rollback](../Topic/CDaoWorkspace::Rollback.md)|현재 트랜잭션을 종료 하 고 변경 내용을 저장 하지 않습니다.|  
|[CDaoWorkspace::SetDefaultPassword](../Topic/CDaoWorkspace::SetDefaultPassword.md)|특정 암호 없이 작업 영역 개체를 만들 때 데이터베이스 엔진이 사용 하는 암호를 설정 합니다.|  
|[CDaoWorkspace::SetDefaultUser](../Topic/CDaoWorkspace::SetDefaultUser.md)|특정 사용자 이름 없이 작업 영역 개체를 만들 때 데이터베이스 엔진이 사용 하는 사용자 이름을 설정 합니다.|  
|[CDaoWorkspace::SetIniPath](../Topic/CDaoWorkspace::SetIniPath.md)|위치는 Microsoft Jet 데이터베이스 엔진의 초기화 설정이 Windows 레지스트리를 설정합니다.|  
|[CDaoWorkspace::SetIsolateODBCTrans](../Topic/CDaoWorkspace::SetIsolateODBCTrans.md)|여러 데이터 소스 연결을 강제 적용 하 여 동일한 ODBC 데이터 원본과 관련 된 여러 트랜잭션을 격리 하는 여부를 지정 합니다.|  
|[CDaoWorkspace::SetLoginTimeout](../Topic/CDaoWorkspace::SetLoginTimeout.md)|사용자가 ODBC 데이터 원본에 로그인 하려고 할 때 오류가 발생 하기 전에 시간을 초 단위로 설정 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDaoWorkspace::m\_pDAOWorkspace](../Topic/CDaoWorkspace::m_pDAOWorkspace.md)|내부 DAO 작업 영역 개체를 가리킵니다.|  
  
## 설명  
 대부분의 경우 여러 작업을 해야 합니다 및 명시적 작업 영역 개체를 만들 필요가 없습니다. 데이터베이스 및 레코드 집합 개체를 열 때 DAO의 기본 작업 영역을 사용 합니다.  그러나 필요한 경우에 여러 세션 한 번에 추가 작업 공간 객체를 만들어 실행할 수 있습니다.  각 작업 영역 개체는 데이터베이스 컬렉션에 열려 있는 데이터베이스 개체를 여러 개 포함할 수 있습니다.  MFC에서 작업 영역 열기 데이터베이스 집합이 모두 동일한에서 "트랜잭션 공간" 지정 주로 트랜잭션 관리자입니다.  
  
> [!NOTE]
>  DAO 데이터베이스 클래스는 개방형 데이터베이스 연결 \(ODBC\)에 따라 MFC 데이터베이스 클래스와는 별개입니다.  모든 DAO 데이터베이스 클래스 이름을 "CDao" 접두사가 있습니다.  일반적으로 mfc에서 DAO 기반 ODBC 기반 mfc 보다 더.  DAO 기반 클래스는 ODBC 드라이버를 포함 하 여 Microsoft Jet 데이터베이스 엔진을 통해 데이터에 액세스 합니다.  또한 데이터베이스 만들기 및 테이블 및 필드는 클래스를 통해 직접 DAO를 호출 하지 않고도 추가 데이터 정의 언어 \(DDL\) 작업을 지원 합니다.  
  
## 기능  
 클래스 `CDaoWorkspace` 는 다음을 제공 합니다.  
  
-   명시적 액세스 데이터베이스 엔진을 초기화 하 여 만든 기본 작업 영역에 필요한 경우.  일반적으로 DAO의 기본 작업 영역 암시적으로 데이터베이스 및 레코드 집합 개체를 만들어 사용 합니다.  
  
-   작업 영역에서에 트랜잭션의 모든 데이터베이스에 적용 되는 트랜잭션 영역을 엽니다.  별도 트랜잭션 영역을 관리 하려면 추가 작업 공간을 만들 수 있습니다.  
  
-   내부 Microsoft Jet 데이터베이스 엔진의 여러 속성을 인터페이스 \(정적 멤버 함수 참조\).  열기 또는 작업 영역을 만들기 전에 정적 멤버 함수를 호출 하거나 만들 열리면 데이터베이스 엔진을 초기화 합니다.  
  
-   Access 데이터베이스 엔진이 Workspaces 컬렉션에 추가 된 모든 활성 작업 공간에 저장 합니다.  작성 하 고 해당 컬렉션에 추가 하지 않고 작업 공간으로 작업할 수도 있습니다.  
  
## 보안  
 MFC dao에서 보안 컨트롤을 사용 하는 사용자 및 그룹 모음 구현 하지 않습니다.  DAO의 특징을 해야 하는 경우 직접 DAO 인터페이스에 대 한 직접 호출을 통해 프로그래밍할 해야 합니다.  에 대 한 내용은  [기술 참고 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
## 용도  
 클래스를 사용 하면 `CDaoWorkspace` 합니다.  
  
-   명시적으로 기본 작업 영역을 엽니다.  
  
     일반적으로 사용 하는 기본 작업 영역을 암시적으로, 열면 새  [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 또는  [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체입니다.  하지만 명시적으로 액세스 해야 합니다 예를 들어 데이터베이스 엔진 속성 액세스 또는 Workspaces 컬렉션에.  아래 "기본 작업 영역 암시적 사용"을 참조 하십시오.  
  
-   새 작업 영역을 만듭니다.  호출  [추가](../Topic/CDaoWorkspace::Append.md) Workspaces 컬렉션에 추가 하려는 경우.  
  
-   Workspaces 컬렉션에서 기존 작업 영역을 엽니다.  
  
 새 작업 영역 만들기가 존재 하지 않는 컬렉션에서 설명 되는 작업 영역에 있는  [만들기](../Topic/CDaoWorkspace::Create.md) 멤버 함수입니다.  작업 영역 개체는 datababase 엔진 세션 간에 유지 되지 않습니다.  MFC 응용 프로그램을 정적으로 링크 하는 경우 데이터베이스 엔진을 응용 프로그램 종료를 초기화 하지 않습니다.  응용 프로그램이 MFC에 동적으로 링크 하는 경우 MFC DLL이 언로드될 때 데이터베이스 엔진 초기화 되지 않습니다.  
  
 기본 작업 영역을 명시적으로 열거나 Workspaces 컬렉션에서 기존 작업 영역을 여는 아래 설명 된  [열려](../Topic/CDaoWorkspace::Open.md) 멤버 함수.  
  
 작업 영역을 닫고 작업 영역 세션 종료는  [닫기](../Topic/CDaoWorkspace::Close.md) 멤버 함수입니다.  **닫기** 가 닫기 이전에 커밋되지 않은 트랜잭션을 롤백하고 데이터베이스를 닫습니다.  
  
## 트랜잭션  
 DAO 작업 영역에서 트랜잭션을 관리 합니다. 따라서 트랜잭션을 여러 열린 데이터베이스와 작업 영역에 있는 모든 데이터베이스에 적용 됩니다.  예를 들어, 두 개의 데이터베이스 경우 한 커밋되지 않은 업데이트 하 고 호출  [CommitTrans](../Topic/CDaoWorkspace::CommitTrans.md), 업데이트를 모두 적용 됩니다.  단일 데이터베이스 트랜잭션을 제한 하려는 경우 별도 작업 영역 개체를 해야 합니다.  
  
## 암시적 기본 작업 영역 사용  
 MFC DAO의 기본 작업 영역에 다음과 같은 상황에서 암시적으로 사용합니다.  
  
-   새로 만들면 `CDaoDatabase` 개체 있지만 기존 통해 그렇게 하지 `CDaoWorkspace` 개체를 MFC 만든 임시 작업 영역 개체를 DAO의 기본 작업 영역에 해당 합니다.  여러 데이터베이스에 대해 이렇게 하면 모든 데이터베이스 개체의 기본 작업 영역으로 연결 됩니다.  데이터베이스의 작업 영역을 통해 액세스할 수 있는 `CDaoDatabase` 데이터 멤버입니다.  
  
-   마찬가지로 만들 경우는 `CDaoRecordset` 개체에 대 한 포인터를 제공 하지 않고는 `CDaoDatabase` 개체를 MFC 임시 데이터베이스 개체를 만들 확장, 임시 작업 영역 개체 및.  레코드 집합의 데이터베이스와 간접적으로 해당 작업 영역을 통해 액세스할 수 있는 `CDaoRecordset` 데이터 멤버.  
  
## 다른 작업  
 손상 된 데이터베이스 복구 또는 압축 데이터베이스 같은 다른 데이터베이스 작업 또한 제공 됩니다.  
  
 DAO를 직접 호출 및 DAO 보안에 대 한 내용은  [기술 참고 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoWorkspace`  
  
## 요구 사항  
 **헤더:**  afxdao.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoException Class](../../mfc/reference/cdaoexception-class.md)