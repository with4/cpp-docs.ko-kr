---
title: "CFieldExchange Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFieldExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFieldExchange class"
  - "데이터 형식[C++], 사용자 지정"
  - "enum FieldType"
  - "enum FieldType, CFieldExchange"
  - "FieldType enumeration"
  - "RFX (record field exchange) [C++]"
  - "RFX (record field exchange) [C++], classes for"
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CFieldExchange Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

레코드 필드 교환 \(RFX\) 및 데이터베이스 클래스에서 사용 되는 대량 레코드 필드 교환 \(Bulk RFX\) 루틴을 지원 합니다.  
  
## 구문  
  
```  
  
class CFieldExchange  
  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CFieldExchange::IsFieldType](../Topic/CFieldExchange::IsFieldType.md)|현재 작업 인 경우 0이 아닌 반환 업데이트 되는 필드 형식에 적절 한.|  
|[CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md)|레코드 집합 데이터 멤버의 형식을 지정 합니다.\-열 또는 매개 변수\-다음 호출 될 때까지 모든 다음 RFX 함수 호출 표시 `SetFieldType`.|  
  
## 설명  
 `CFieldExchange`기본 클래스에 없는 것입니다.  
  
 사용자 지정 데이터 형식 또는 대량 행 페치가 구현 되어 데이터 교환 루틴을 작성 하는 경우이 클래스를 사용 합니다. 그렇지 않으면 직접이 클래스를 사용 되지 않습니다.  RFX 및 Bulk RFX는 데이터 소스에서 현재 레코드의 해당 필드와 레코드 집합 개체의 필드 데이터 멤버 간에 데이터를 교환 합니다.  
  
> [!NOTE]
>  개방형 데이터베이스 연결 \(ODBC\) 클래스 대신 데이터 액세스 개체 \(DAO\) 클래스를 작업 하는 경우 클래스 사용  [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) 대신 합니다.  자세한 내용은  [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md).  
  
 A `CFieldExchange` 개체 제공 레코드 필드 교환 또는 대량 레코드 필드 교환 하기 위해 필요한 컨텍스트 정보를 배치 합니다.  `CFieldExchange`개체는 바인딩 매개 변수 및 필드 데이터 멤버를 포함 하 여 현재 레코드의 필드에서 다양 한 플래그를 설정 하 고 작업을 지원 합니다.  정의 된 형식의 데이터 멤버를 레코드 집합 클래스에 RFX 및 Bulk RFX 작업 수행의 `enum`**FieldType** 에서 `CFieldExchange`.  가능한  **FieldType** 값입니다.  
  
-   **CFieldExchange::outputColumn** 필드 데이터 멤버에 대 한.  
  
-   **CFieldExchange::inputParam** 또는  **CFieldExchange::param** 입력된 매개 변수 데이터 멤버에 대 한.  
  
-   **CFieldExchange::outputParam** 출력 매개 변수 데이터 멤버에 대 한.  
  
-   **CFieldExchange::inoutParam** 입\/출력 매개 변수 데이터 멤버에 대 한.  
  
 대부분 클래스의 멤버 함수와 데이터 멤버의 사용자 지정 RFX 루틴을 작성 하는 데 제공 됩니다.  사용 하면 `SetFieldType` 자주 합니다.  자세한 내용은 문서를 참조 하십시오.  [RFX \(레코드 필드 교환\)](../../data/odbc/record-field-exchange-rfx.md) 및  [레코드 집합 \(ODBC\)](../../data/odbc/recordset-odbc.md).  대량 행 페칭 \(fetching\)에 대 한 자세한 내용은  [레코드 집합: 레코드 페치 대량 \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  RFX 및 Bulk RFX 전역 함수에 대 한 자세한 내용은  [레코드 필드 교환 함수](../../mfc/reference/record-field-exchange-functions.md) MFC 매크로 전역 변수 섹션을 참조 합니다.  
  
## 상속 계층 구조  
 `CFieldExchange`  
  
## 요구 사항  
 **헤더:**  afxdb.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)