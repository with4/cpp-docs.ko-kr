---
title: "CDaoQueryDef Class | Microsoft Docs"
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
  - "CDaoQueryDef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoQueryDef class"
  - "쿼리[Visual Studio], 정의"
  - "QueryDef objects"
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoQueryDef Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

쿼리 정의 또는 쿼리 "정의" 일반적으로 한 데이터베이스에 저장 된 나타냅니다.  
  
## 구문  
  
```  
class CDaoQueryDef : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDaoQueryDef::CDaoQueryDef](../Topic/CDaoQueryDef::CDaoQueryDef.md)|생성 된  **CDaoQueryDef**  개체입니다.  다음 호출  **열려** 또는  **만들기**필요에 따라.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDaoQueryDef::Append](../Topic/CDaoQueryDef::Append.md)|쿼리 정의 저장 된 쿼리로 데이터베이스의 QueryDefs 컬렉션에 추가합니다.|  
|[CDaoQueryDef::CanUpdate](../Topic/CDaoQueryDef::CanUpdate.md)|쿼리는 데이터베이스를 업데이트할 수 있으면 0이 아닌 값을 반환 합니다.|  
|[CDaoQueryDef::Close](../Topic/CDaoQueryDef::Close.md)|쿼리 정의 개체를 닫습니다.  작업을 끝낸 때는 C\+\+ 개체를 소멸 시킵니다.|  
|[CDaoQueryDef::Create](../Topic/CDaoQueryDef::Create.md)|내부 DAO 쿼리 정의 개체를 만듭니다.  쿼리 정의 사용 하 여 임시 쿼리 또는 호출으로  **추가** 데이터베이스에 저장 합니다.|  
|[CDaoQueryDef::Execute](../Topic/CDaoQueryDef::Execute.md)|Querydef 개체에 의해 정의 된 쿼리를 실행 합니다.|  
|[CDaoQueryDef::GetConnect](../Topic/CDaoQueryDef::GetConnect.md)|쿼리 정의에 관련 된 연결 문자열을 반환 합니다.  데이터 원본 연결 문자열을 식별합니다.  \(SQL 통과에 쿼리. 그렇지 않으면 빈 문자열입니다.\)|  
|[CDaoQueryDef::GetDateCreated](../Topic/CDaoQueryDef::GetDateCreated.md)|저장 된 쿼리를 만든 날짜를 반환 합니다.|  
|[CDaoQueryDef::GetDateLastUpdated](../Topic/CDaoQueryDef::GetDateLastUpdated.md)|저장 된 쿼리를 마지막으로 업데이트 된 날짜를 반환 합니다.|  
|[CDaoQueryDef::GetFieldCount](../Topic/CDaoQueryDef::GetFieldCount.md)|쿼리 정의에서 정의 된 필드 수를 반환 합니다.|  
|[CDaoQueryDef::GetFieldInfo](../Topic/CDaoQueryDef::GetFieldInfo.md)|지정 된 쿼리에 정의 된 필드에 대 한 정보를 반환 합니다.|  
|[CDaoQueryDef::GetName](../Topic/CDaoQueryDef::GetName.md)|쿼리 정의의 이름을 반환합니다.|  
|[CDaoQueryDef::GetODBCTimeout](../Topic/CDaoQueryDef::GetODBCTimeout.md)|제한 시간 값 \(에 대 한 ODBC 쿼리\)를 사용 하는 ODBC에서 반환 쿼리 정의 실행 됩니다.  이 기간 쿼리 작업을 완료 하려면 허용 하도록 결정 합니다.|  
|[CDaoQueryDef::GetParameterCount](../Topic/CDaoQueryDef::GetParameterCount.md)|쿼리에 정의 된 매개 변수를 반환 합니다.|  
|[CDaoQueryDef::GetParameterInfo](../Topic/CDaoQueryDef::GetParameterInfo.md)|쿼리에 지정 된 매개 변수에 대 한 정보를 반환합니다.|  
|[CDaoQueryDef::GetParamValue](../Topic/CDaoQueryDef::GetParamValue.md)|쿼리에 지정 된 매개 변수의 값을 반환합니다.|  
|[CDaoQueryDef::GetRecordsAffected](../Topic/CDaoQueryDef::GetRecordsAffected.md)|여 실행 쿼리를 영향을 받는 레코드 수를 반환 합니다.|  
|[CDaoQueryDef::GetReturnsRecords](../Topic/CDaoQueryDef::GetReturnsRecords.md)|쿼리 정의에서 정의 된 쿼리가 레코드를 반환 하는 경우 0이 아닌 값을 반환 합니다.|  
|[CDaoQueryDef::GetSQL](../Topic/CDaoQueryDef::GetSQL.md)|쿼리 정의에서 정의 된 쿼리를 지정 하는 SQL 문자열을 반환 합니다.|  
|[CDaoQueryDef::GetType](../Topic/CDaoQueryDef::GetType.md)|쿼리 형식을 반환: 삭제, 업데이트, 추가, 테이블 만들기 및 등.|  
|[CDaoQueryDef::IsOpen](../Topic/CDaoQueryDef::IsOpen.md)|쿼리 정의 열려 있고 실행할 수 있는 경우 0이 아닌 값을 반환 합니다.|  
|[CDaoQueryDef::Open](../Topic/CDaoQueryDef::Open.md)|데이터베이스의 QueryDefs 컬렉션에 저장 된 기존 쿼리를 엽니다.|  
|[CDaoQueryDef::SetConnect](../Topic/CDaoQueryDef::SetConnect.md)|SQL 통과 쿼리의 연결 문자열은 ODBC 데이터 원본에 설정합니다.|  
|[CDaoQueryDef::SetName](../Topic/CDaoQueryDef::SetName.md)|저장 된 쿼리의 쿼리 정의 만들 때 사용 중인 이름 바꾸기 이름을 설정 합니다.|  
|[CDaoQueryDef::SetODBCTimeout](../Topic/CDaoQueryDef::SetODBCTimeout.md)|\(에 대 한 ODBC 쿼리\) 사용 하 여 ODBC 시간 초과 값을 설정 하는 쿼리를 실행 합니다.|  
|[CDaoQueryDef::SetParamValue](../Topic/CDaoQueryDef::SetParamValue.md)|쿼리에 지정 된 매개 변수의 값을 설정합니다.|  
|[CDaoQueryDef::SetReturnsRecords](../Topic/CDaoQueryDef::SetReturnsRecords.md)|쿼리 정의 레코드를 반환 하는지 여부를 지정 합니다.  이 특성을 설정  **TRUE** SQL 통과 쿼리에만 유효 합니다.|  
|[CDaoQueryDef::SetSQL](../Topic/CDaoQueryDef::SetSQL.md)|쿼리 정의에서 정의 된 쿼리를 지정 하는 SQL 문자열을 설정 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDaoQueryDef::m\_pDAOQueryDef](../Topic/CDaoQueryDef::m_pDAOQueryDef.md)|내부 DAO 쿼리 정의 개체의 OLE 인터페이스 포인터입니다.|  
|[CDaoQueryDef::m\_pDatabase](../Topic/CDaoQueryDef::m_pDatabase.md)|에 대 한 포인터는 `CDaoDatabase` 쿼리 정의 된 연결 된 개체입니다.  쿼리 정의 또는 데이터베이스에 저장 되어 있습니다.|  
  
## 설명  
 쿼리 정의 쿼리와 같은 "만든 날짜" 및 "ODBC 시간 초과" 속성을 설명 하는 SQL 문이 포함 된 데이터 액세스 개체입니다. 저장 하지 않고 임시 querydef 개체를 만들 수 있지만 편리\-훨씬 더 효율적인\-일반적으로 저장 하는 데이터베이스 쿼리에서 재사용 합니다.  A  [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 라는 QueryDefs 컬렉션의 저장 된 쿼리 정의 포함 하는 컬렉션에서 개체를 유지 관리 합니다.  
  
> [!NOTE]
>  DAO 데이터베이스 클래스는 개방형 데이터베이스 연결 \(ODBC\)에 따라 MFC 데이터베이스 클래스와는 별개입니다.  모든 DAO 데이터베이스 클래스 이름을 "CDao" 접두사가 있습니다.  여전히 DAO 클래스가 ODBC 데이터 소스를 액세스 할 수 있습니다.  일반적으로 mfc에서 DAO 기반 ODBC 기반 mfc 보다 더. DAO 기반 클래스를 통해 자신의 데이터베이스 엔진을 통해 ODBC 드라이버를 포함 하 여 데이터를 액세스할 수 있습니다.  DAO 기반 클래스에도 테이블은 클래스를 통해 DAO를 직접 호출 하지 않고도 추가 데이터 정의 언어 \(DDL\) 작업을 지원 합니다.  
  
## 용도  
 쿼리 정의 개체 쿼리 저장 기존의 작업 하거나 새로 만들려면 쿼리나 임시 쿼리 저장 사용할:  
  
1.  모든 경우에는 먼저 구성에 `CDaoQueryDef` 개체에 대 한 포인터를 제공 하는  [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체 쿼리에 속한.  
  
2.  다음 따라 다음을 수행 합니다.  
  
    -   기존 저장 쿼리 사용 하려면 쿼리 정의 개체 호출  [열려](../Topic/CDaoQueryDef::Open.md) 멤버 함수, 저장 된 쿼리의 이름을 제공 합니다.  
  
    -   새 저장 된 쿼리를 만들려면 쿼리 정의 개체를 호출 합니다.  [만들기](../Topic/CDaoQueryDef::Create.md) 멤버 함수를 쿼리의 이름을 제공 합니다.  다음 호출  [추가](../Topic/CDaoQueryDef::Append.md) 데이터베이스의 QueryDefs 컬렉션에 추가 하 여 쿼리를 저장 합니다.  **만들기** 쿼리 정의 열린 상태로 전환 후 전화 등  **만들기** 호출 하지 않아야  **열**.  
  
    -   임시 쿼리 정의 만들려면 호출  **만들기**.  쿼리 이름에 대해 빈 문자열을 전달 합니다.  호출 하지 않습니다  **추가**.  
  
 Querydef 개체를 사용 하 여 완료 되 면 호출의  [닫기](../Topic/CDaoQueryDef::Close.md) 멤버 함수입니다. 다음 쿼리 정의 개체를 파괴 하십시오.  
  
> [!TIP]
>  저장 된 쿼리를 만드는 가장 쉬운 방법은 작성 하 고 Microsoft Access를 사용 하 여 데이터베이스에 저장할 수 있습니다.  다음 열 및 MFC 코드를 사용 하 여 수 있습니다.  
  
## 목적  
 다음과 같은 목적으로 쿼리 정의 개체를 사용할 수 있습니다.  
  
-   만들 수 있는 `CDaoRecordset` 개체  
  
-   호출 개체의  **실행** 멤버 함수를 직접 실행 쿼리 또는 SQL 통과 쿼리를 실행 하려면  
  
 모든 종류의 선택, 동작, 크로스탭, 삭제, 업데이트 쿼리를 사용 하 여 querydef 개체 추가, 테이블 만들기, 데이터 정의 SQL 통과, 통합, 고 대량 쿼리 수 있습니다.  쿼리 형식은 제공 SQL 문의 내용에 따라 결정 됩니다.  쿼리 형식에 대 한 내용은  **실행** 및  [GetType](../Topic/CDaoQueryDef::GetType.md) 멤버 함수.  레코드 집합에 대 한 행 반환는 일반적으로, 일반적으로 사용 하는 쿼리는  **선택...**  키워드.  **실행** 대량 작업에 대해 가장 일반적으로 사용 됩니다.  자세한 내용은  [실행](../Topic/CDaoQueryDef::Execute.md) 및  [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
## 쿼리 정 및 레코드 집합  
 Querydef 개체를 만드는 데는 `CDaoRecordset` 개체에서 일반적으로 만들거나 위에서 설명한 것 처럼 쿼리 정의 엽니다.  다음 레코드 집합 개체를 호출 하면 querydef 개체에 포인터를 전달 구성  [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md).  전달 하 여 쿼리 정의에서 열린 상태 여야 합니다.  자세한 내용은 클래스를 참조 하십시오.  [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 열린 상태 아니면 레코드 세트 \(쿼리 정의 가장 일반적인 용도\)을 만들려면 쿼리 정의 사용할 수 없습니다.  호출 하 여 쿼리 정의 열린 상태로 유지  **열** 또는  **만들기**.  
  
## 외부 데이터베이스  
 쿼리 정의 개체는 외부 데이터베이스 엔진의 기본 SQL 언어를 사용 하는 기본 방법입니다.  예를 들어, \(Microsoft SQL Server 사용 됨\) 관리법 SQL 쿼리를 만들고 querydef 개체에 저장할 수 있습니다.  Microsoft Jet 데이터베이스 엔진에 기반 하지 SQL 쿼리를 사용 하는 경우 외부 데이터 원본을 가리키는 연결 문자열을 제공 해야 합니다.  유효한 연결 문자열을 쿼리로 데이터베이스 엔진 건너뛰고 처리에 대 한 외부 데이터베이스 서버에 직접 쿼리를 전달 합니다.  
  
> [!TIP]
>  ODBC 테이블에서 작업할 수 있는 Microsoft Jet에 연결할 것 \(.MDB\) 데이터베이스입니다.  
  
 관련된 내용은 "QueryDefs 컬렉션", "CdbDatabase 개체" DAO SDK의 "쿼리 정의 개체" 항목을 참조 하십시오.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoQueryDef`  
  
## 요구 사항  
 **헤더:**  afxdao.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoException Class](../../mfc/reference/cdaoexception-class.md)