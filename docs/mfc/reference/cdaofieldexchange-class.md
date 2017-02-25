---
title: "CDaoFieldExchange Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoFieldExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoFieldExchange class"
  - "DAO(Data Access Objects), record field exchange (DFX)"
  - "DFX(DAO 레코드 필드 교환)"
  - "DFX(DAO 레코드 필드 교환), DAO Record Field Exchange"
  - "exchanging data between databases and recordsets"
  - "field exchange"
  - "field exchange, record for DAO classes"
  - "RFX(레코드 필드 교환)"
  - "RFX(레코드 필드 교환), DAO 클래스"
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDaoFieldExchange Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

DAO 데이터베이스 클래스에서 사용 되는 DAO 레코드 필드 교환 \(DFX\) 루틴을 지원 합니다.  
  
## 구문  
  
```  
class CDaoFieldExchange  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDaoFieldExchange::IsValidOperation](../Topic/CDaoFieldExchange::IsValidOperation.md)|현재 작업 인 경우 0이 아닌 반환 업데이트 되는 필드 형식에 적절 한.|  
|[CDaoFieldExchange::SetFieldType](../Topic/CDaoFieldExchange::SetFieldType.md)|레코드 집합 데이터 멤버의 형식을 지정 합니다.\-열 또는 매개 변수\-DFX 함수에 대 한 모든 후속 호출 될 때까지 다음 호출을 나타내는 `SetFieldType`.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDaoFieldExchange::m\_nOperation](../Topic/CDaoFieldExchange::m_nOperation.md)|DFX 호출 하려면 레코드 집합의 현재 수행 중인 작업 `DoFieldExchange` 멤버 함수입니다.|  
|[CDaoFieldExchange::m\_prs](../Topic/CDaoFieldExchange::m_prs.md)|작업 수행 중인 DFX를 레코드 집합에 대 한 포인터입니다.|  
  
## 설명  
 `CDaoFieldExchange`기본 클래스에 없는 것입니다.  
  
 사용자 지정 데이터 형식에 대 한 데이터 교환 루틴을 작성 하는 경우이 클래스를 사용 합니다. 그렇지 않으면 직접이 클래스를 사용 되지 않습니다.  DFX는 필드 데이터 멤버 간 데이터 교환에  [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체와 데이터 소스에서 현재 레코드의 해당 필드.  DFX는 데이터 원본에서 및 데이터 원본에 양방향 모두에서 교환을 관리합니다.  참조  [기술 참고 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) 사용자 정의 DFX 루틴에 대 한 정보.  
  
> [!NOTE]
>  DAO 데이터베이스 클래스는 개방형 데이터베이스 연결 \(ODBC\)에 따라 MFC 데이터베이스 클래스와는 별개입니다.  모든 DAO 데이터베이스 클래스 이름을 "CDao" 접두사가 있습니다.  여전히 DAO 클래스가 ODBC 데이터 소스를 액세스 할 수 있습니다.  일반적으로 mfc에서 DAO 기반 ODBC 기반 mfc 보다 더.  DAO 기반 클래스를 통해 자신의 데이터베이스 엔진을 통해 ODBC 드라이버를 포함 하 여 데이터를 액세스할 수 있습니다.  또한 추가 DAO를 직접 호출 하지 않고 클래스를 통해 테이블 데이터 정의 언어 \(DDL\) 작업을 지원 합니다.  
  
> [!NOTE]
>  DAO 레코드 필드 교환 \(DFX\) ODBC 기반 MFC 데이터베이스 클래스에서 레코드 필드 교환 \(RFX\)와 유사한 것 \(`CDatabase`, `CRecordset`\).  RFX를 이해 하는 경우 DFX를 쉽게 사용할 검색 됩니다.  
  
 A `CDaoFieldExchange` 컨텍스트 정보 필요한 DAO에 대 한 레코드 필드 교환에 개체를 제공 합니다.  `CDaoFieldExchange`개체는 바인딩 매개 변수 및 필드 데이터 멤버를 포함 하 여 현재 레코드의 필드에서 다양 한 플래그를 설정 하 고 작업을 지원 합니다.  DFX 연산의 수행 정의 형식의 데이터 멤버를 레코드 집합 클래스에는 `enum`**FieldType** 에서 `CDaoFieldExchange`.  가능한  **FieldType** 값입니다.  
  
-   **CDaoFieldExchange::outputColumn** 필드 데이터 멤버에 대 한.  
  
-   **CDaoFieldExchange::param** 매개 변수 데이터 멤버에 대 한.  
  
 [IsValidOperation](../Topic/CDaoFieldExchange::IsValidOperation.md) 멤버 함수 사용자 정의 DFX 루틴을 작성 하는 데 제공 됩니다.  사용 하면  [SetFieldType](../Topic/CDaoFieldExchange::SetFieldType.md) 에서 사용자  [CDaoRecordset::DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md) 함수입니다.  DFX 전역 함수에 대 한 자세한 내용은  [레코드 필드 교환 함수](../../mfc/reference/record-field-exchange-functions.md).  데이터 종류에 대 한 사용자 정의 DFX 루틴을 작성 하는 방법에 대 한 자세한 내용은 참조 하십시오.  [기술 참고 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).  
  
## 상속 계층 구조  
 `CDaoFieldExchange`  
  
## 요구 사항  
 **헤더:**  afxdao.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)