---
title: "레코드 집합: 레코드 집합의 레코드 업데이트 방법(ODBC) | Microsoft Docs"
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
  - "ODBC 레코드 집합, 업데이트"
  - "레코드, 업데이트"
  - "레코드 집합, 레코드 편집"
  - "레코드 집합, 업데이트"
  - "레코드 집합 업데이트"
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 레코드 집합: 레코드 집합의 레코드 업데이트 방법(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 레코드 집합은 데이터 소스에서 레코드를 선택할 수 있을 뿐 아니라 선택한 레코드를 업데이트 또는 삭제할 수 있고 새 레코드를 추가할 수도 있습니다.  연결된 데이터 소스의 업데이트 가능 여부, 레코드 집합 개체를 만들 때 지정한 옵션, 만들어진 SQL 등 세 가지 요인에 의해 레코드 집합의 업데이트 가능성이 결정됩니다.  
  
> [!NOTE]
>  `CRecordset` 개체의 기반이 되는 SQL은 레코드 집합의 업데이트 가능성에 영향을 줄 수 있습니다.  예를 들어 SQL에 조인이나 **GROUP BY** 절이 있으면 MFC에서는 업데이트 가능성을 **FALSE**로 설정합니다.  
  
> [!NOTE]
>  이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 개체에 적용됩니다.  대량 행 페치를 사용하는 경우 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
 다음은 이 항목에서 설명하는 내용입니다.  
  
-   [레코드 집합 업데이트에서 사용자의 역할](#_core_your_role_in_recordset_updating) 및 프레임워크의 역할  
  
-   [편집 버퍼로서의 레코드 집합](#_core_the_edit_buffer) 및 [다이너셋과 스냅숏의 차이](#_core_dynasets_and_snapshots).  
  
 [레코드 집합: AddNew, Edit 및 Delete의 작동 방식\(ODBC\)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)에서는 레코드 집합 측면에서 이들 함수의 역할을 설명합니다.  
  
 [레코드 집합: 업데이트에 대한 추가 정보\(ODBC\)](../../data/odbc/recordset-more-about-updates-odbc.md)에서는 트랜잭션이 업데이트에 주는 영향, 레코드 집합을 닫거나 스크롤하는 것이 진행 중인 업데이트에 주는 영향, 업데이트가 다른 사용자의 업데이트와 상호 작용하는 방법 등을 설명함으로써 레코드 집합 업데이트에 대해 전반적으로 설명합니다.  
  
##  <a name="_core_your_role_in_recordset_updating"></a> 레코드 집합 업데이트에서 사용자의 역할  
 다음 표에서는 레코드 집합을 사용하여 레코드를 추가, 편집 및 삭제할 때 프레임워크에서 수행하는 역할과 함께 사용자의 역할을 보여 줍니다.  
  
### 레코드 집합 업데이트: 사용자와 프레임워크  
  
|사용자|프레임워크|  
|---------|-----------|  
|데이터 소스를 업데이트\(또는 추가\)할 수 있는지 여부를 결정합니다.|데이터 소스의 업데이트 가능성 또는 추가 가능성을 테스트하는 [CDatabase](../../mfc/reference/cdatabase-class.md) 멤버 함수를 제공합니다.|  
|업데이트할 수 있는 모든 형식의 레코드 집합을 엽니다.||  
|`CanUpdate`나 `CanAppend`와 같은 `CRecordset` 업데이트 함수를 호출하여 레코드 집합을 업데이트할 수 있는지 여부를 확인합니다.||  
|레코드 집합 멤버 함수를 호출하여 레코드를 추가, 편집 및 삭제합니다.|레코드 집합 개체와 데이터 소스 간 데이터 교환 방법을 관리합니다.|  
|트랜잭션을 사용하여 업데이트 프로세스를 제어할 수도 있습니다.|`CDatabase` 멤버 함수를 제공하여 트랜잭션을 지원합니다.|  
  
 트랜잭션에 대한 자세한 내용은 [트랜잭션\(ODBC\)](../../data/odbc/transaction-odbc.md)을 참조하십시오.  
  
##  <a name="_core_the_edit_buffer"></a> 편집 버퍼  
 레코드 집합의 필드 데이터 멤버는 단일 레코드\(현재 레코드\)를 포함하는 편집 버퍼의 역할을 합니다.  업데이트 작업에서는 이 버퍼를 사용하여 현재 레코드에 작업을 수행합니다.  
  
-   레코드를 추가할 때 편집 버퍼는 새 레코드를 만드는 데 사용됩니다.  레코드 추가를 마치면 이전의 현재 레코드가 다시 현재 레코드로 됩니다.  
  
-   레코드를 업데이트\(편집\)할 때 편집 버퍼는 레코드 집합의 필드 데이터 멤버에 새 값을 설정하는 데 사용됩니다.  업데이트를 마치면 업데이트된 레코드가 여전히 현재 레코드로 표시됩니다.  
  
 [AddNew](../Topic/CRecordset::AddNew.md) 또는 [Edit](../Topic/CRecordset::Edit.md)를 호출하면 나중에 필요할 때 복원할 수 있도록 현재 레코드가 저장됩니다.  [Delete](../Topic/CRecordset::Delete.md)를 호출하면 현재 레코드가 저장되지 않고 삭제된 것으로 표시되며 다른 레코드로 스크롤해야 합니다.  
  
> [!NOTE]
>  편집 버퍼는 레코드 삭제 시 아무 역할도 하지 않습니다.  현재 레코드를 삭제하면 레코드는 삭제된 것으로 표시되며 다른 레코드로 스크롤할 때까지 레코드 집합은 "현재 레코드가 없는" 상태가 됩니다.  
  
##  <a name="_core_dynasets_and_snapshots"></a> 다이너셋과 스냅숏  
 [다이너셋](../../data/odbc/dynaset.md)은 레코드로 스크롤할 때 해당 레코드의 내용을 새로 고칩니다.  [스냅숏](../../data/odbc/snapshot.md)은 해당 레코드의 정적 상태를 나타내므로 [Requery](../Topic/CRecordset::Requery.md)를 호출하지 않으면 레코드의 내용이 새로 고쳐지지 않습니다.  다이너셋의 모든 기능을 사용하려면 적절한 ODBC API 지원 수준을 따르는 ODBC 드라이버를 사용하여 작업해야 합니다.  자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md) 및 [다이너셋](../../data/odbc/dynaset.md)을 참조하십시오.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: AddNew, Edit 및 Delete의 작동 방식\(ODBC\)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)