---
title: "레코드 집합: 책갈피와 절대 위치(ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SetAbsolutePosition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "절대 위치, ODBC 레코드 집합"
  - "책갈피"
  - "책갈피, CDBVariant"
  - "책갈피, ODBC 레코드 집합"
  - "CDBVariant 클래스, 책갈피"
  - "커서[ODBC], 레코드 집합에서의 절대 위치"
  - "GetBookmark 메서드"
  - "ODBC 레코드 집합, 절대 위치"
  - "ODBC 레코드 집합, 책갈피"
  - "레코드 위치 지정"
  - "레코드 위치 지정"
  - "레코드 집합, 절대 위치"
  - "레코드 집합, 책갈피"
  - "SetAbsolutePosition 메서드"
  - "SetAbsolutePosition 메서드, 책갈피"
  - "SetBookmark 메서드"
ms.assetid: 189788d6-33c1-41c5-9265-97db2a5d43cc
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 레코드 집합: 책갈피와 절대 위치(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 레코드 집합을 탐색할 때 특정 레코드로 되돌아갈 수 있는 방법이 필요합니다.  이 경우 레코드의 책갈피와 절대 위치를 사용하면 됩니다.  
  
 다음은 이 항목에서 설명하는 내용입니다.  
  
-   [책갈피 사용 방법](#_core_bookmarks_in_mfc_odbc).  
  
-   [절대 위치를 사용하여 현재 레코드를 설정하는 방법](#_core_absolute_positions_in_mfc_odbc).  
  
##  <a name="_core_bookmarks_in_mfc_odbc"></a> MFC ODBC의 책갈피  
 책갈피는 레코드를 고유하게 식별합니다.  레코드 집합에서 레코드가 삭제될 수도 있으므로 레코드 집합을 탐색할 때 항상 레코드의 절대 위치를 이용할 수 있는 것은 아닙니다.  레코드의 위치를 추적하는 확실한 방법은 책갈피를 사용하는 것입니다.  `CRecordset` 클래스는 다음과 같은 목적에 사용할 수 있는 멤버 함수를 제공합니다.  
  
-   변수에 저장할 수 있도록 현재 레코드의 책갈피 가져오기\([GetBookmark](../Topic/CRecordset::GetBookmark.md)\)  
  
-   이전에 변수에 저장된 책갈피를 지정하여 특정 레코드로 빠르게 이동\([SetBookmark](../Topic/CRecordset::SetBookmark.md)\)  
  
 다음 예제에서는 이러한 멤버 함수를 사용하여 현재 레코드를 표시하고 나중에 해당 레코드로 되돌아가는 방법을 보여 줍니다.  
  
```  
// rs is a CRecordset or  
// CRecordset-derived object  
  
CDBVariant varRecordToReturnTo;  
rs.GetBookmark( varRecordToReturnTo );  
  
// More code in which you  
// move to other records  
  
rs.SetBookmark( varRecordToReturnTo );  
```  
  
 이 경우 [CDBVariant Class](../../mfc/reference/cdbvariant-class.md) 개체에서 내부 데이터 형식을 추출할 필요가 없습니다.  대신 `GetBookmark`를 사용하여 값을 할당하고 `SetBookmark`를 사용하여 해당 책갈피로 되돌아갑니다.  
  
> [!NOTE]
>  ODBC 드라이버 및 레코드 집합 형식에 따라 책갈피가 지원되지 않을 수도 있습니다.  [CRecordset::CanBookmark](../Topic/CRecordset::CanBookmark.md)를 호출하여 책갈피가 지원되는지 여부를 쉽게 확인할 수 있습니다.  또한 책갈피가 지원되면 [CRecordset::Open](../Topic/CRecordset::Open.md) 멤버 함수에서 **CRecordset::useBookmarks** 옵션을 지정하여 책갈피를 구현하도록 명시적으로 선택해야 하며  특정 레코드 집합을 사용하여 작업한 다음에는 책갈피의 지속성을 확인해야 합니다.  예를 들어, 레코드 집합을 **Requery**하면 책갈피가 더 유효하지 않을 수도 있습니다.  [CDatabase::GetBookmarkPersistence](../Topic/CDatabase::GetBookmarkPersistence.md)를 호출하여 안전하게 `SetBookmark`를 호출할 수 있는지 여부를 확인합니다.  
  
##  <a name="_core_absolute_positions_in_mfc_odbc"></a> MFC ODBC에서의 절대 위치  
 `CRecordset` 클래스에서는 책갈피 외에 서수 위치를 지정하여 현재 레코드를 설정할 수 있는데  이를 절대 위치라고 합니다.  
  
> [!NOTE]
>  앞으로만 이동 가능한 레코드 집합에서는 절대 위치를 사용할 수 없습니다.  앞으로만 이동 가능한 레코드 집합에 대한 자세한 내용은 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)을 참조하십시오.  
  
 절대 위치를 사용하여 현재 레코드 포인터를 이동하려면 [CRecordset::SetAbsolutePosition](../Topic/CRecordset::SetAbsolutePosition.md)을 호출합니다.  `SetAbsolutePosition`에 값을 전달하면 해당 서수 위치의 레코드가 현재 레코드로 됩니다.  
  
> [!NOTE]
>  레코드의 절대 위치는 신뢰할 수 없습니다.  예를 들어, 사용자가 레코드 집합에서 레코드를 삭제하면 뒤에 오는 모든 레코드의 서수 위치가 달라집니다.  따라서 현재 레코드를 이동할 때는 책갈피를 사용하는 것이 좋습니다.  자세한 내용은 [MFC ODBC의 책갈피](#_core_bookmarks_in_mfc_odbc)를 참조하십시오.  
  
 레코드 집합 탐색에 대한 자세한 내용은 [레코드 집합: 스크롤\(ODBC\)](../../data/odbc/recordset-scrolling-odbc.md)을 참조하십시오.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)