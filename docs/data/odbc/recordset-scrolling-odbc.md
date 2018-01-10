---
title: "레코드 집합: 스크롤 (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- recordsets [C++], end of
- recordsets [C++], beginning of
- navigation [C++], recordsets
- recordsets [C++], moving to records
- ODBC recordsets, scrolling
- recordsets [C++], navigating
- scrolling [C++], recordsets
- Move method (recordsets)
ms.assetid: f38d2dcb-1e88-4e41-af25-98b00c276be4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 34dcfb9cb1d45710accba2ee6155e3c741b727be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-scrolling-odbc"></a>레코드 집합: 스크롤(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 레코드 집합을 연 후 필요한 값을 표시 하려면 레코드에 액세스할 수 계산을 수행, 보고서를 생성 했으며 등 레코드 집합 내에서 레코드를 이동 하면 스크롤입니다.  
  
 이 항목에 설명 합니다.  
  
-   [레코드 집합에서 다른 하나의 레코드 스크롤 하는 방법](#_core_scrolling_from_one_record_to_another)합니다.  
  
-   [아래 스크롤 지원 되는 상황과 지원 되지 않습니다](#_core_when_scrolling_is_supported)합니다.  
  
##  <a name="_core_scrolling_from_one_record_to_another"></a>레코드 스크롤  
 클래스 `CRecordset` 제공는 **이동** 레코드 집합 내에서 스크롤할 수 있도록 멤버 함수입니다. 이러한 함수는 행 집합에서 현재 레코드를 이동합니다. 대량 행 페치를 구현한 경우에 **이동** 작업은 행 집합의 크기에 따라 레코드 집합의 위치를 변경 합니다. 대량 행 페치를 호출 하지 않은 경우는 **이동** 함수 위치를 변경 하는 레코드 집합 한 각 시간입니다. 대량 행 페치에 대 한 자세한 내용은 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
> [!NOTE]
>  레코드 집합을 탐색할 때 삭제 된 레코드 하지 건너뛸 수 있습니다. 자세한 내용은 참조는 [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) 멤버 함수입니다.  
  
 이외에 **이동** 함수 `CRecordset` 끝을 지나서 또는 레코드 집합의 시작 부분 앞 스크롤가 있는지 여부를 확인 하기 위한 멤버 함수를 제공 합니다.  
  
 스크롤 가능한 레코드 집합 인지를 확인 하려면 호출 된 `CanScroll` 멤버 함수입니다.  
  
#### <a name="to-scroll"></a>스크롤할 수  
  
1.  하나의 레코드 또는 행 집합을 전달: 호출 된 [MoveNext](../../mfc/reference/crecordset-class.md#movenext) 멤버 함수입니다.  
  
2.  이전 레코드 또는 행 집합: 호출 된 [MovePrev](../../mfc/reference/crecordset-class.md#moveprev) 멤버 함수입니다.  
  
3.  레코드 집합의 첫 번째 레코드를: 호출 된 [MoveFirst](../../mfc/reference/crecordset-class.md#movefirst) 멤버 함수입니다.  
  
4.  마지막 행 집합 또는 레코드 집합의 마지막 레코드로: 호출 된 [MoveLast](../../mfc/reference/crecordset-class.md#movelast) 멤버 함수입니다.  
  
5.  *N* 현재 위치를 기준으로 레코드: 호출 된 [이동](../../mfc/reference/crecordset-class.md#move) 멤버 함수입니다.  
  
#### <a name="to-test-for-the-end-or-the-beginning-of-the-recordset"></a>끝 또는 레코드 집합의 시작 부분에 대 한 테스트 하려면  
  
1.  마지막 레코드를 지나서 스크롤 했습니까? 호출 된 [IsEOF](../../mfc/reference/crecordset-class.md#iseof) 멤버 함수입니다.  
  
2.  첫 번째 레코드의 (뒤로 이동) 스크롤 했습니까? 호출 된 [IsBOF](../../mfc/reference/crecordset-class.md#isbof) 멤버 함수입니다.  
  
 다음 코드 예제에서는 `IsBOF` 및 `IsEOF` 어느 방향으로 스크롤할 때 레코드 집합의 한계를 검색 합니다.  
  
```  
// Open a recordset; first record is current  
CCustSet rsCustSet( NULL );  
rsCustSet.Open( );  
  
if( rsCustSet.IsBOF( ) )  
    return;  
    // The recordset is empty  
  
// Scroll to the end of the recordset, past  
// the last record, so no record is current  
while ( !rsCustSet.IsEOF( ) )  
    rsCustSet.MoveNext( );  
  
// Move to the last record  
rsCustSet.MoveLast( );  
  
// Scroll to beginning of the recordset, before  
// the first record, so no record is current  
while( !rsCustSet.IsBOF( ) )  
    rsCustSet.MovePrev( );  
  
// First record is current again  
rsCustSet.MoveFirst( );  
```  
  
 `IsEOF`레코드 집합은 마지막 레코드를 지난 배치 되 면 0이 아닌 값을 반환 합니다. `IsBOF`레코드 집합 (하기 전에 모든 레코드)는 첫 번째 레코드에 있으면 0이 아닌 값을 반환 합니다. 두 경우 모두에서 작동 하도록 현재 레코드가 있습니다. 호출 하는 경우 `MovePrev` 때 `IsBOF` 이미 **TRUE** 호출 또는 `MoveNext` 때 `IsEOF` 이미 **TRUE**, 프레임 워크를 throw 한 `CDBException`합니다. 사용할 수도 있습니다 `IsBOF` 및 `IsEOF` 빈 레코드 집합에 대 한 확인 합니다.  
  
 레코드 집합 탐색에 대 한 자세한 내용은 참조 [레코드 집합: 책갈피와 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)합니다.  
  
##  <a name="_core_when_scrolling_is_supported"></a>스크롤이 지원 되는  
 원래 SQL 스크롤 앞 으로만 제공 하지만 ODBC 스크롤 기능을 확장 합니다. 드라이버의 ODBC API 규칙에 따라 수준에 따라 응용 프로그램이 작동 하는 ODBC 드라이버에 따라 스크롤에 대 한 지원의 사용 가능한 수준을 메모리로 ODBC 커서 라이브러리가 로드 되었는지 여부 및 합니다. 자세한 내용은 참조 [ODBC](../../data/odbc/odbc-basics.md) 및 [ODBC: ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)합니다.  
  
> [!TIP]
>  커서 라이브러리 사용 되는지 여부를 제어할 수 있습니다. 참조는 `bUseCursorLib` 및 `dwOptions` 매개 변수를 [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open)합니다.  
  
> [!NOTE]
>  MFC DAO 클래스와 달리 MFC ODBC 클래스 집합을 제공 하지 않습니다 **찾을** 조건을 지정한 다음 (또는 이전) 레코드에 맞는 찾는 대 한 작동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)   
 [CRecordset::CanScroll](../../mfc/reference/crecordset-class.md#canscroll)   
 [CRecordset::CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)   
 [레코드 집합: 레코드 필터링(ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)