---
title: "레코드 집합: 책갈피와 절대 위치 (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SetAbsolutePosition
dev_langs: C++
helpviewer_keywords:
- CDBVariant class, bookmarks
- absolute positions, ODBC recordsets
- bookmarks, CDBVariant
- bookmarks, ODBC recordsets
- ODBC recordsets, absolute positions
- ODBC recordsets, bookmarks
- cursors [ODBC], absolute position in recordsets
- recordsets, bookmarks
- bookmarks
- SetAbsolutePosition method
- recordsets, absolute positions
- positioning records
- SetBookmark method
- record positioning
- GetBookmark method
- SetAbsolutePosition method, bookmarks
ms.assetid: 189788d6-33c1-41c5-9265-97db2a5d43cc
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b4d703d49173ba950f073342de014127e5696202
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="recordset-bookmarks-and-absolute-positions-odbc"></a>레코드 집합: 책갈피와 절대 위치(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 레코드 집합을 탐색할 때 특정 레코드를 반환 하는 방법은 주로 해야 합니다. 레코드의 책갈피와 절대 위치에는 이러한 두 가지 방법을 제공합니다.  
  
 이 항목에 설명 합니다.  
  
-   [책갈피를 사용 하는 방법](#_core_bookmarks_in_mfc_odbc)합니다.  
  
-   [절대 위치를 사용 하 여 현재 레코드를 설정 하는 방법](#_core_absolute_positions_in_mfc_odbc)합니다.  
  
##  <a name="_core_bookmarks_in_mfc_odbc"></a>MFC ODBC의 책갈피  
 책갈피는 레코드를 고유 하 게 식별합니다. 레코드 집합을 탐색할 때 항상 보장이 없는 레코드의 절대 위치 레코드 집합에서 레코드를 삭제할 수 있습니다. 레코드의 위치를 추적 하기 위해 신뢰할 수 있는 방법은 책갈피를 사용 하는 것입니다. 클래스 `CRecordset` 멤버 함수를 제공 합니다.  
  
-   변수에 저장할 수 있도록 현재 레코드의 책갈피 가져오기 ([GetBookmark](../../mfc/reference/crecordset-class.md#getbookmark)).  
  
-   책갈피 변수의 앞부분에 나오는 저장를 지정 하 여 지정된 된 레코드를 신속 하 게 이동 ([SetBookmark](../../mfc/reference/crecordset-class.md#setbookmark)).  
  
 다음 예제에는 현재 레코드를 표시 하 고 나중에 돌아가서 하려면 이러한 멤버 함수를 사용 하는 방법을 보여 줍니다.  
  
```  
// rs is a CRecordset or  
// CRecordset-derived object  
  
CDBVariant varRecordToReturnTo;  
rs.GetBookmark( varRecordToReturnTo );  
  
// More code in which you  
// move to other records  
  
rs.SetBookmark( varRecordToReturnTo );  
```  
  
 기본 데이터 형식을 추출할 필요가 없습니다는 [CDBVariant 클래스](../../mfc/reference/cdbvariant-class.md) 개체입니다. 사용 하 여 값을 할당 `GetBookmark` 사용 하 여 해당 책갈피 돌아가려면 `SetBookmark`합니다.  
  
> [!NOTE]
>  ODBC 드라이버와 레코드 집합 형식에 따라 책갈피 지원 되지 않을 수 있습니다. 책갈피를 호출 하 여 사용할 수 있는지 여부를 쉽게 확인할 수 있습니다 [CRecordset::CanBookmark](../../mfc/reference/crecordset-class.md#canbookmark)합니다. 또한 책갈피는 지원 되는 경우 명시적으로 선택 해야 지정 하 여 구현 하는 데는 **CRecordset::useBookmarks** 옵션에 [crecordset:: Open](../../mfc/reference/crecordset-class.md#open) 멤버 함수입니다. 특정 레코드 집합 작업 후 책갈피의 지 속성을 확인 해야 합니다. 예를 들어 경우 없습니다 **Requery** 레코드 집합 책갈피가 더 이상 유효할 수 없습니다. 호출 [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) 안전 하 게 호출할 수 있는지 여부를 확인 하려면 `SetBookmark`합니다.  
  
##  <a name="_core_absolute_positions_in_mfc_odbc"></a>MFC ODBC의 절대 위치  
 책갈피 외 클래스 `CRecordset` 는 서 수 위치를 지정 하 여 현재 레코드를 설정할 수 있습니다. 절대 위치 라고 합니다.  
  
> [!NOTE]
>  절대 위치 앞 으로만 이동 가능한 레코드 집합에 제공 되지 않습니다. 앞 으로만 이동 가능한 레코드 집합에 대 한 자세한 내용은 참조 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)합니다.  
  
 절대 위치를 사용 하 여 현재 레코드 포인터를 이동 하려면 호출 [CRecordset::SetAbsolutePosition](../../mfc/reference/crecordset-class.md#setabsoluteposition)합니다. 값을 전달 하는 경우 `SetAbsolutePosition`, 서 수 위치 레코드가 현재 해당 하는 레코드입니다.  
  
> [!NOTE]
>  레코드의 절대 위치는 신뢰할 수 없습니다. 레코드 집합에서 레코드를 삭제 하는 경우 모든 후속 레코드의 서 수 위치 변경 합니다. 책갈피는 현재 레코드를 이동 하기 위한 권장된 방법입니다. 자세한 내용은 참조 [MFC ODBC의 책갈피](#_core_bookmarks_in_mfc_odbc)합니다.  
  
 레코드 집합 탐색에 대 한 자세한 내용은 참조 [레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)