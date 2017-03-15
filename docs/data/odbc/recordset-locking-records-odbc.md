---
title: "레코드 집합: 레코드 잠금(ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "데이터[C++], 잠금"
  - "잠금[C++], 레코드 집합"
  - "ODBC 레코드 집합[C++], 레코드 잠금"
  - "낙관적 잠금"
  - "낙관적 잠금, ODBC"
  - "ODBC에서 비관적 잠금"
  - "레코드 집합[C++], 레코드 잠금"
ms.assetid: 8fe8fcfe-b55a-41a8-9136-94a7cd1e4806
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 레코드 집합: 레코드 잠금(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 다음은 이 항목에서 설명하는 내용입니다.  
  
-   [사용 가능한 레코드 잠금 종류](#_core_record.2d.locking_modes)  
  
-   [업데이트 동안 레코드 집합의 레코드를 잠그는 방법](#_core_locking_records_in_your_recordset)  
  
 레코드 집합을 사용하여 데이터 소스에서 레코드를 업데이트하는 경우 다른 사용자가 동시에 업데이트할 수 없도록 응용 프로그램에서 해당 레코드를 잠글 수 있습니다.  동시에 두 사용자가 레코드를 업데이트할 수 없도록 시스템에서 제어하지 않는 한 동시에 두 사용자가 업데이트하는 레코드의 상태는 정의되지 않습니다.  
  
> [!NOTE]
>  이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 개체에 적용됩니다.  대량 행 페치를 구현한 경우 이 내용 중 일부는 적용되지 않습니다.  예를 들어 **Edit**와 **Update** 멤버 함수를 호출할 수 없습니다.  대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
##  <a name="_core_record.2d.locking_modes"></a> 레코드 잠금 모드  
 데이터베이스 클래스는 다음 두 가지 [레코드 잠금 모드](../Topic/CRecordset::SetLockingMode.md)를 제공합니다.  
  
-   낙관적 잠금\(기본값\)  
  
-   비관적 잠금  
  
 레코드 업데이트 작업은 세 단계로 이루어집니다.  
  
1.  [Edit](../Topic/CRecordset::Edit.md) 멤버 함수를 호출하여 작업을 시작합니다.  
  
2.  현재 레코드의 해당 필드를 변경합니다.  
  
3.  [Update](../Topic/CRecordset::Update.md) 멤버 함수를 호출하여 작업을 마치고 정상적으로 업데이트를 커밋합니다.  
  
 낙관적 잠금은 **Update**가 호출된 동안에만 데이터 소스에서 레코드를 잠급니다.  다중 사용자 환경에서 낙관적 잠금을 사용하는 경우 응용 프로그램에서 **Update** 실패 조건을 처리해야 합니다.  비관적 잠금은 **Edit** 호출 즉시 레코드를 잠그고 **Update**를 호출할 때까지 잠금을 해제하지 않습니다. 잠금 실패는 **Update**에서 반환하는 **FALSE** 값이 아닌 `CDBException` 메커니즘을 통해 표시됩니다.  비관적 잠금에서는 동일한 레코드에 동시에 액세스하는 경우 응용 프로그램의 **Update** 처리가 완료될 때까지 기다려야 할 수도 있으므로 다른 사용자에 대해서는 성능이 저하될 수 있습니다.  
  
##  <a name="_core_locking_records_in_your_recordset"></a> 레코드 집합의 레코드 잠금  
 레코드 집합 개체의 [잠금 모드](#_core_record.2d.locking_modes)를 기본 모드에서 다른 모드로 변경하려면 **Edit**를 호출하기 전에 변경해야 합니다.  
  
#### 레코드 집합의 현재 잠금 모드를 변경하려면  
  
1.  **CRecordset::pessimistic** 또는 **CRecordset::optimistic**을 지정하여 [SetLockingMode](../Topic/CRecordset::SetLockingMode.md) 멤버 함수를 호출합니다.  
  
 새 잠금 모드는 다른 모드로 다시 변경하거나 레코드 집합을 닫을 때까지 유효합니다.  
  
> [!NOTE]
>  현재 비관적 잠금을 지원하는 ODBC 드라이버는 많지 않습니다.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 조인 수행\(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md)   
 [레코드 집합: 레코드 추가, 업데이트 및 삭제\(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)