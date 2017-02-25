---
title: "레코드 집합: 스크롤(ODBC) | Microsoft Docs"
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
  - "Move 메서드(레코드 집합)"
  - "탐색[C++], 레코드 집합"
  - "ODBC 레코드 집합, 스크롤"
  - "레코드 집합[C++], 시작"
  - "레코드 집합[C++], 끝"
  - "레코드 집합[C++], 레코드로 이동"
  - "레코드 집합[C++], 탐색"
  - "스크롤[C++], 레코드 집합"
ms.assetid: f38d2dcb-1e88-4e41-af25-98b00c276be4
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 레코드 집합: 스크롤(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 레코드 집합을 연 다음에는 값을 표시하고 계산하고 보고서를 만드는 등의 작업을 위해 레코드에 액세스해야 합니다.  이 경우 스크롤을 사용하여 레코드 집합의 레코드 간을 이동할 수 있습니다.  
  
 다음은 이 항목에서 설명하는 내용입니다.  
  
-   [레코드 집합의 한 레코드에서 다른 레코드로 스크롤하는 방법](#_core_scrolling_from_one_record_to_another)  
  
-   [스크롤이 지원되는 상황과 지원되지 않는 상황](#_core_when_scrolling_is_supported)  
  
##  <a name="_core_scrolling_from_one_record_to_another"></a> 레코드 간 스크롤  
 `CRecordset` 클래스에는 레코드 집합에서 스크롤하기 위한 **Move** 멤버 함수가 있습니다.  이 함수는 행 집합 단위로 현재 레코드를 이동시킵니다.  대량 행 페치를 구현한 경우 **Move** 작업을 수행하면 행 집합의 크기만큼 레코드 집합의 위치가 이동되며  그렇지 않은 경우에는 레코드 집합의 위치가 한 번에 한 레코드씩만 **이동**됩니다.  대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
> [!NOTE]
>  참고   레코드 집합에서 이동할 때 삭제된 레코드를 건너뛰지 않을 수도 있습니다.  자세한 내용은 [IsDeleted](../Topic/CRecordset::IsDeleted.md) 멤버 함수를 참조하십시오.  
  
 `CRecordset`에는 **Move** 함수 외에 레코드 집합의 끝을 지나거나 시작 부분보다 앞으로 스크롤했는지 여부를 확인하기 위한 멤버 함수가 포함되어 있습니다.  
  
 레코드 집합에서 스크롤할 수 있는지 여부를 확인하려면 `CanScroll` 멤버 함수를 호출합니다.  
  
#### 다음과 같이 멤버 함수를 호출합니다.  
  
1.  다음 레코드 또는 행 집합으로, 즉 앞으로 스크롤하려면 [MoveNext](../Topic/CRecordset::MoveNext.md) 멤버 함수를 호출합니다.  
  
2.  이전 레코드 또는 행 집합으로, 즉 뒤로 스크롤하려면 [MovePrev](../Topic/CRecordset::MovePrev.md) 멤버 함수를 호출합니다.  
  
3.  레코드 집합의 첫째 레코드로: [MoveFirst](../Topic/CRecordset::MoveFirst.md) 멤버 함수를 호출합니다.  
  
4.  레코드 집합의 마지막 레코드나 마지막 행 집합으로 스크롤하려면 [MoveLast](../Topic/CRecordset::MoveLast.md) 멤버 함수를 호출합니다.  
  
5.  현재 위치를 기준으로 N 개의 레코드를 스크롤: [Move](../Topic/CRecordset::Move.md) 멤버 함수를 호출합니다.  
  
#### 레코드 집합의 끝 또는 처음인지 테스트하려면  
  
1.  마지막 레코드보다 뒤로 스크롤했는지 확인하려면  [IsEOF](../Topic/CRecordset::IsEOF.md) 멤버 함수를 호출합니다.  
  
2.  첫째 레코드보다 앞으로 스크롤했는지 확인하려면  [IsBOF](../Topic/CRecordset::IsBOF.md) 멤버 함수를 호출합니다.  
  
 다음 코드 예제에서는 `IsBOF`와 `IsEOF`를 사용하여 앞이나 뒤로 스크롤할 때 레코드 집합의 처음과 끝을 감지합니다.  
  
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
  
 `IsEOF`는 레코드 집합이 마지막 레코드를 지난 위치에 있는 경우 0이 아닌 값을 반환합니다.  `IsBOF`는 레코드 집합이 첫 번째 레코드의 앞\(모든 레코드 앞\)에 있으면 0이 아닌 값을 반환합니다.  두 경우 모두에서 현재 레코드에 대해서는 아무런 작업도 수행되지 않습니다.  `IsBOF`가 이미 **TRUE**일 때 `MovePrev`를 호출하거나 `IsEOF`가 이미 **TRUE**일 때 `MoveNext`를 호출하면 프레임워크에서 `CDBException`이 발생합니다.  `IsBOF`와 `IsEOF`를 사용하여 레코드 집합이 비어 있는지 확인할 수도 있습니다.  
  
 레코드 집합 탐색에 대한 자세한 내용은 [레코드 집합: 책갈피와 절대 위치\(ODBC\)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)를 참조하십시오.  
  
##  <a name="_core_when_scrolling_is_supported"></a> 스크롤이 지원되는 경우  
 SQL은 원래 앞으로만 스크롤하도록 되어 있는 반면 ODBC에서는 보다 확장된 스크롤 기능을 제공됩니다.  사용할 수 있는 스크롤 지원 수준은 응용 프로그램에서 사용할 ODBC 드라이버, 드라이버의 ODBC API 규칙 수준 및 ODBC 커서 라이브러리가 메모리에 로드되는지 여부에 따라 달라집니다.  자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md) 및 [ODBC: ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)를 참조하십시오.  
  
> [!TIP]
>  커서 라이브러리를 사용할지 여부를 제어할 수 있습니다.  [CDatabase::Open](../Topic/CDatabase::Open.md) 함수의 `bUseCursorLib` 및 `dwOptions` 매개 변수를 참조하십시오.  
  
> [!NOTE]
>  MFC DAO 클래스와는 달리 MFC ODBC 클래스에서는 지정한 기준에 맞는 다음 또는 이전 레코드를 찾는 데 사용하는 **Find** 함수 집합이 제공되지 않습니다.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [CRecordset::CanScroll](../Topic/CRecordset::CanScroll.md)   
 [CRecordset::CheckRowsetError](../Topic/CRecordset::CheckRowsetError.md)   
 [레코드 집합: 레코드 필터링\(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md)