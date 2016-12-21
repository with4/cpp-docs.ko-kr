---
title: "CDatabase Class | Microsoft Docs"
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
  - "CDatabase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDatabase 클래스"
  - "데이터베이스 클래스[C++], ODBC"
  - "데이터베이스 연결[C++], CDatabase 클래스"
  - "MFC[C++], ODBC"
  - "ODBC[C++], CDatabase 클래스"
  - "ODBC database class"
ms.assetid: bd0de70a-e3c3-4441-bcaa-bbf434426ca8
caps.latest.revision: 24
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDatabase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

연결을을 통해 데이터 소스를 조작할 수 있습니다 나타냅니다.  
  
## 구문  
  
```  
  
class CDatabase : public CObject  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDatabase::CDatabase](../Topic/CDatabase::CDatabase.md)|`CDatabase` 개체를 생성합니다.  호출 하 여 개체를 초기화 해야 `OpenEx` 또는  **열려**.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDatabase::BeginTrans](../Topic/CDatabase::BeginTrans.md)|"트랜잭션" 시작\-일련의 가역 호출 하는 `AddNew`,  **편집**,  **삭제**, 및  **업데이트** 클래스의 멤버 함수 `CRecordset` \-연결 된 데이터 소스에서.  데이터 원본에 대 한 트랜잭션을 지원 해야  **BeginTrans** 적용 하려면.|  
|[CDatabase::BindParameters](../Topic/CDatabase::BindParameters.md)|매개 변수를 바인딩할 수 `CDatabase::ExecuteSQL`.|  
|[CDatabase::Cancel](../Topic/CDatabase::Cancel.md)|두 번째 스레드가 프로세스 또는 비동기 작업을 취소합니다.|  
|[CDatabase::CanTransact](../Topic/CDatabase::CanTransact.md)|데이터 소스가 트랜잭션을 지원할 경우 0이 아닌 값을 반환 합니다.|  
|[CDatabase::CanUpdate](../Topic/CDatabase::CanUpdate.md)|0이 아닌 경우 반환 된 `CDatabase` 개체는 업데이트할 수 있는 \(읽기 전용\).|  
|[CDatabase::Close](../Topic/CDatabase::Close.md)|데이터 원본 연결을 닫습니다.|  
|[CDatabase::CommitTrans](../Topic/CDatabase::CommitTrans.md)|시작 하는 트랜잭션이 완료  **BeginTrans**.  데이터 소스 변경 명령에서 트랜잭션이 수행 됩니다.|  
|[CDatabase::ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md)|SQL 문을 실행합니다.  데이터 레코드가 반환 됩니다.|  
|[CDatabase::GetBookmarkPersistence](../Topic/CDatabase::GetBookmarkPersistence.md)|Recordset 개체에서 책갈피를 유지 하는 작업을 식별 합니다.|  
|[CDatabase::GetConnect](../Topic/CDatabase::GetConnect.md)|연결 하는 데 사용 하는 ODBC 연결 문자열을 반환의 `CDatabase` 데이터 소스 개체입니다.|  
|[CDatabase::GetCursorCommitBehavior](../Topic/CDatabase::GetCursorCommitBehavior.md)|열려 있는 recordset 개체는 트랜잭션을 커밋의 효과 식별 합니다.|  
|[CDatabase::GetCursorRollbackBehavior](../Topic/CDatabase::GetCursorRollbackBehavior.md)|열려 있는 recordset 개체에서 트랜잭션을 롤백하는 효과 식별 합니다.|  
|[CDatabase::GetDatabaseName](../Topic/CDatabase::GetDatabaseName.md)|현재 사용 중인 데이터베이스의 이름을 반환 합니다.|  
|[CDatabase::IsOpen](../Topic/CDatabase::IsOpen.md)|0이 아닌 경우 반환의 `CDatabase` 개체는 현재 데이터 원본에 연결 합니다.|  
|[CDatabase::OnSetOptions](../Topic/CDatabase::OnSetOptions.md)|표준 연결 옵션을 설정 하는 프레임 워크에서 호출 됩니다.  기본 구현은 쿼리 시간 제한 값을 설정합니다.  호출 하 여 이러한 옵션을 설정할 수 있습니다 `SetQueryTimeout`.|  
|[CDatabase::Open](../Topic/CDatabase::Open.md)|데이터 원본 \(odbc\)을 통해 연결 합니다.|  
|[CDatabase::OpenEx](../Topic/CDatabase::OpenEx.md)|데이터 원본 \(odbc\)을 통해 연결 합니다.|  
|[CDatabase::Rollback](../Topic/CDatabase::Rollback.md)|현재 트랜잭션 동안 변경 내용을 취소 합니다.  에 정의 된 데이터 소스를 이전 상태로 반환 된  **BeginTrans** 호출을 변경 하지 않고.|  
|[CDatabase::SetLoginTimeout](../Topic/CDatabase::SetLoginTimeout.md)|데이터 원본 연결을 시도 하는 시간 초과 후 시간을 초 단위로 설정 합니다.|  
|[CDatabase::SetQueryTimeout](../Topic/CDatabase::SetQueryTimeout.md)|집합 작업 초 후 데이터베이스 쿼리 시간 초과 됩니다.  이후의 모든 레코드 집합에 영향을 미치는  **열려**, `AddNew`,  **편집**, 및  **삭제** 호출 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDatabase::m\_hdbc](../Topic/CDatabase::m_hdbc.md)|데이터 소스를 개방형 데이터베이스 연결 \(ODBC\) 연결 핸들  형식  **HDBC**.|  
  
## 설명  
 데이터 소스는 일부 데이터베이스 관리 시스템 \(DBMS\)에서 호스팅되는 데이터의 특정 인스턴스입니다.  Microsoft SQL Server, Microsoft Access, Borland dBASE 및 xBASE 등이 있습니다.  하나를 가질 수 있습니다 `CDatabase` 개체를 현재 응용 프로그램에서 한 번.  
  
> [!NOTE]
>  개방형 데이터베이스 연결 \(ODBC\) 클래스 대신 데이터 액세스 개체 \(DAO\) 클래스를 작업 하는 경우 클래스 사용  [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 대신 합니다.  자세한 내용은  [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md).  
  
 사용 `CDatabase`, 구성는 `CDatabase` 호출 및 개체의 `OpenEx` 멤버 함수.  연결을 엽니다.  다음 구성 `CRecordset` 개체가 연결 된 데이터 소스에서 운영에 대 한 전달 레코드 집합 생성자에 대 한 포인터를 `CDatabase` 개체입니다.  연결을 사용 하 여 완료 되 면 호출의  **닫기** 멤버 함수 및 파괴는 `CDatabase` 개체.  **닫기** 가 닫기 이전에 레코드 집합을 닫습니다.  
  
 에 대 한 자세한 내용은 `CDatabase`, 문서를 참조 하십시오.  [데이터 원본 \(ODBC\)](../../data/odbc/data-source-odbc.md) 및  [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDatabase`  
  
## 요구 사항  
 **헤더:**  afxdb.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)