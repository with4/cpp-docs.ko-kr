---
title: "레코드 집합: 대량 레코드 추가(ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "레코드 집합에 대량 레코드 추가"
  - "ODBC 레코드 집합, 레코드 추가"
  - "레코드 집합, 레코드 추가"
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 레코드 집합: 대량 레코드 추가(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 MFC [CRecordset](../../mfc/reference/crecordset-class.md) 클래스에는 테이블에 새 레코드를 대량으로 추가할 때 효율성을 높이는 최적화 기능이 포함되어 있습니다.  
  
> [!NOTE]
>  이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 개체에 적용됩니다.  대량 행 페치를 사용하는 경우 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
 [CRecordset::Open](../Topic/CRecordset::Open.md) 멤버 함수의 **dwOptions** 매개 변수에 새로 추가된 새 옵션인 **optimizeBulkAdd**는 **Requery** 또는 **Close**를 호출하지 않고 여러 개의 레코드를 연속적으로 추가하는 경우 성능을 향상시킵니다.  **Update**를 처음 호출하기 전에 더티였던 필드만이 다음 `AddNew`\/**Update** 호출 시 더티로 표시됩니다.  
  
 데이터베이스 클래스를 사용하여 레코드 추가, 편집 및 삭제 작업에 **::SQLSetPos** ODBC API 함수를 활용하는 경우에는 이러한 최적화 기능이 필요하지 않습니다.  
  
 ODBC 커서 라이브러리가 로드되었거나 ODBC 드라이버에서 **::SQLSetPos**를 통한 추가, 편집 및 삭제를 지원하지 않는 경우 최적화를 이용하면 대량 추가 작업의 성능이 향상됩니다.  이러한 최적화를 활성화하려면 레코드 집합에 대한 **Open** 호출에서 **dwOptions** 매개 변수를 다음과 같이 설정합니다.  
  
```  
appendOnly | optimizeBulkAdd  
```  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 레코드 추가, 업데이트 및 삭제\(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [레코드 집합: 레코드 잠금\(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)