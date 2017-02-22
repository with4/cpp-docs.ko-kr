---
title: "CDaoDatabase Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoDatabase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoDatabase class"
  - "CDaoDatabase class, and workspace"
  - "CDaoDatabase class, vs. CDatabase class"
  - "CDatabase 클래스, vs. CDaoDatabase class"
  - "데이터베이스 클래스[C++], DAO"
ms.assetid: 8ff5b342-964d-449d-bef1-d0ff56aadf6d
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDaoDatabase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터베이스 연결을을 통해 데이터를 조작할 수 있습니다 나타냅니다.  
  
## 구문  
  
```  
class CDaoDatabase : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDaoDatabase::CDaoDatabase](../Topic/CDaoDatabase::CDaoDatabase.md)|`CDaoDatabase` 개체를 생성합니다.  호출  **열려** 개체는 데이터베이스에 연결할 수 있습니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDaoDatabase::CanTransact](../Topic/CDaoDatabase::CanTransact.md)|데이터베이스에서 트랜잭션을 지원할 경우 0이 아닌 값을 반환 합니다.|  
|[CDaoDatabase::CanUpdate](../Topic/CDaoDatabase::CanUpdate.md)|0이 아닌 경우 반환 된 `CDaoDatabase` 개체는 업데이트할 수 있는 \(읽기 전용\).|  
|[CDaoDatabase::Close](../Topic/CDaoDatabase::Close.md)|데이터베이스 연결을 닫습니다.|  
|[CDaoDatabase::Create](../Topic/CDaoDatabase::Create.md)|내부 DAO 데이터베이스 개체를 만들고 초기화는 `CDaoDatabase` 개체입니다.|  
|[CDaoDatabase::CreateRelation](../Topic/CDaoDatabase::CreateRelation.md)|데이터베이스에 새 테이블 간의 관계를 정의합니다.|  
|[CDaoDatabase::DeleteQueryDef](../Topic/CDaoDatabase::DeleteQueryDef.md)|데이터베이스의 QueryDefs 컬렉션에 저장 된 쿼리 정의 개체를 삭제 합니다.|  
|[CDaoDatabase::DeleteRelation](../Topic/CDaoDatabase::DeleteRelation.md)|데이터베이스에서 테이블 간의 기존 관계를 삭제합니다.|  
|[CDaoDatabase::DeleteTableDef](../Topic/CDaoDatabase::DeleteTableDef.md)|데이터베이스에서 테이블의 정의 삭제합니다.  실제 테이블 및 모든 데이터를 삭제합니다.|  
|[CDaoDatabase::Execute](../Topic/CDaoDatabase::Execute.md)|실행 쿼리를 실행합니다.  호출  **실행** 예외를 throw 하는 결과 반환 하는 쿼리를 합니다.|  
|[CDaoDatabase::GetConnect](../Topic/CDaoDatabase::GetConnect.md)|연결 하는 데 사용 되는 연결 문자열을 반환의 `CDaoDatabase` 데이터베이스 개체입니다.  ODBC를 사용 합니다.|  
|[CDaoDatabase::GetName](../Topic/CDaoDatabase::GetName.md)|현재 사용 중인 데이터베이스의 이름을 반환 합니다.|  
|[CDaoDatabase::GetQueryDefCount](../Topic/CDaoDatabase::GetQueryDefCount.md)|쿼리는 데이터베이스에 대 한 정의 반환 합니다.|  
|[CDaoDatabase::GetQueryDefInfo](../Topic/CDaoDatabase::GetQueryDefInfo.md)|지정한 쿼리 정의 데이터베이스에 대 한 정보를 반환 합니다.|  
|[CDaoDatabase::GetQueryTimeout](../Topic/CDaoDatabase::GetQueryTimeout.md)|반환 작업 초 후 데이터베이스 쿼리 시간 초과 됩니다.  모든 후속 영향 열기, 새로 추가, 업데이트 및 작업 및 다른 작업을 ODBC 데이터 원본 \(만\) 같은 편집  **실행** 호출 합니다.|  
|[CDaoDatabase::GetRecordsAffected](../Topic/CDaoDatabase::GetRecordsAffected.md)|반환 레코드 수를 영향을 마지막으로 업데이트를 편집 또는 추가 작업을 호출 하 여 또는  **실행**.|  
|[CDaoDatabase::GetRelationCount](../Topic/CDaoDatabase::GetRelationCount.md)|데이터베이스에서 테이블 간에 정의 된 관계를 반환 합니다.|  
|[CDaoDatabase::GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md)|지정 된 데이터베이스의 테이블 간에 정의 된 관계에 대 한 정보를 반환 합니다.|  
|[CDaoDatabase::GetTableDefCount](../Topic/CDaoDatabase::GetTableDefCount.md)|데이터베이스에 정의 된 테이블의 수를 반환 합니다.|  
|[CDaoDatabase::GetTableDefInfo](../Topic/CDaoDatabase::GetTableDefInfo.md)|데이터베이스에서 지정한 테이블에 대 한 정보를 반환합니다.|  
|[CDaoDatabase::GetVersion](../Topic/CDaoDatabase::GetVersion.md)|데이터베이스와 연관 된 데이터베이스 엔진의 버전을 반환 합니다.|  
|[CDaoDatabase::IsOpen](../Topic/CDaoDatabase::IsOpen.md)|0이 아닌 경우 반환 된 `CDaoDatabase` 개체는 현재 데이터베이스에 연결 합니다.|  
|[CDaoDatabase::Open](../Topic/CDaoDatabase::Open.md)|데이터베이스에 연결 합니다.|  
|[CDaoDatabase::SetQueryTimeout](../Topic/CDaoDatabase::SetQueryTimeout.md)|설정 작업 \(ODBC 데이터 원본만\)에서 초 후 데이터베이스 쿼리 시간 초과 됩니다.  모든 후속 영향 열기, 새로 추가, 업데이트 및 삭제 작업.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDaoDatabase::m\_pDAODatabase](../Topic/CDaoDatabase::m_pDAODatabase.md)|내부 DAO 데이터베이스 개체에 대 한 포인터입니다.|  
|[CDaoDatabase::m\_pWorkspace](../Topic/CDaoDatabase::m_pWorkspace.md)|에 대 한 포인터는  [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 데이터베이스를 포함 하는 트랜잭션 영역을 정의 하는 개체입니다.|  
  
## 설명  
 지원 되는 데이터베이스 형식에 대 한 내용은  [GetName](../Topic/CDaoWorkspace::GetName.md) 멤버 함수입니다.  하나를 가질 수 있습니다 `CDaoDatabase` 작업 "표시 되는 지정 된 영역 에서" 한 번에 활성 객체는  [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 개체입니다.  작업 영역의 Databases 컬렉션 이라는 열려 있는 데이터베이스 개체의 컬렉션을 유지 관리 합니다.  
  
> [!NOTE]
>  MFC DAO 데이터베이스 클래스는 ODBC 기반 MFC 데이터베이스 클래스와는 별개입니다.  모든 DAO 데이터베이스 클래스 이름을 "CDao" 접두사가 있습니다.  클래스 `CDaoDatabase` ODBC 클래스와 비슷한 인터페이스를 제공 합니다.  [CDatabase](../../mfc/reference/cdatabase-class.md).  주요 차이점 `CDatabase` 해당 DBMS에 대 한 개방형 데이터베이스 연결 \(ODBC\) 및 ODBC 드라이버를 통해 DBMS에 액세스 합니다.  `CDaoDatabase`데이터를 통해는 DAO \(데이터 액세스 개체에서 Microsoft Jet 데이터베이스 엔진 기반\)을 액세스 합니다.  일반적으로 mfc에서 DAO 기반 ODBC 기반 mfc 보다 더. DAO 기반 클래스를 통해 자신의 데이터베이스 엔진을 통해 ODBC 드라이버를 포함 하 여 데이터를 액세스할 수 있습니다.  DAO 기반 클래스에도 테이블은 클래스를 통해 DAO를 직접 호출 하지 않고도 추가 데이터 정의 언어 \(DDL\) 작업을 지원 합니다.  
  
## 용도  
 레코드 집합 개체를 만들 때 암시적으로 데이터베이스 개체를 만들 수 있습니다.  또한 데이터베이스 개체를 명시적으로 만들 수 있습니다.  기존 데이터베이스를 명시적으로 사용 하도록 `CDaoDatabase`, 다음 중 하나를 수행 합니다.  
  
-   생성 된 `CDaoDatabase` 개체를 open에 전달 하는 포인터를  [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 개체.  
  
-   또는 생성 된 `CDaoDatabase` \(MFC는 임시 작업 영역 개체를 만듭니다\) 작업 영역을 지정 하지 않고 개체.  
  
 새 Microsoft Jet를 만들려면 \(.MDB\) 데이터베이스 생성은 `CDaoDatabase` 호출 및 개체의  [만들기](../Topic/CDaoDatabase::Create.md) 멤버 함수.  하지  *하지* 전화  **열려** 후  **만들기**.  
  
 기존 데이터베이스를 열려면 구성에 `CDaoDatabase` 호출 및 개체의  [열](../Topic/CDaoDatabase::Open.md) 멤버 함수.  
  
 이러한 기법 중 DAO 데이터베이스 개체는 작업 영역의 Databases 컬렉션에 추가 하 고 데이터에 연결을 합니다.  다음 구성  [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md),  [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), 또는  [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 연결 된 데이터베이스에서 작동 하는 개체 포인터를 이러한 개체에 대 한 생성자를 전달 하면 `CDaoDatabase` 개체.  연결을 사용 하 여 완료 되 면 호출의  [닫기](../Topic/CDaoDatabase::Close.md) 멤버 함수 및 파괴는 `CDaoDatabase` 개체.  **닫기** 가 닫기 이전에 레코드 집합을 닫습니다.  
  
## 트랜잭션  
 트랜잭션 처리 데이터베이스 작업 영역 수준에서 제공 됩니다\-참조는  [BeginTrans](../Topic/CDaoWorkspace::BeginTrans.md),  [CommitTrans](../Topic/CDaoWorkspace::CommitTrans.md), 및  [롤백](../Topic/CDaoWorkspace::Rollback.md) 클래스의 멤버 함수 `CDaoWorkspace`.  
  
## ODBC 연결  
 외부 테이블을 Microsoft Jet에 연결할 ODBC 데이터 원본으로 작동 하는 권장된 방법입니다 \(.MDB\) 데이터베이스입니다.  
  
## 컬렉션  
 각 데이터베이스 자체 tabledef, querydef, recordset 및 관계 개체의 컬렉션을 유지 관리합니다.  클래스 `CDaoDatabase` 이러한 개체를 조작 하기 위한 멤버 함수를 제공 합니다.  
  
> [!NOTE]
>  개체 DAO의 MFC 데이터베이스 개체 없습니다 저장 됩니다.  MFC 테이블 정의 쿼리 정 및 레코드 집합 개체에 대 한 하지만 관계 개체에 대 한 클래스를 제공합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoDatabase`  
  
## 요구 사항  
 **헤더:**  afxdao.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CDaoException Class](../../mfc/reference/cdaoexception-class.md)