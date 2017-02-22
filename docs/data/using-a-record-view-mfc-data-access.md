---
title: "레코드 뷰 사용  (MFC Data Access) | Microsoft Docs"
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
  - "레코드 뷰, 기본 코드 사용자 지정"
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 레코드 뷰 사용  (MFC Data Access)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 마법사가 자동으로 작성하는 레코드 뷰의 기본 코드를 사용자 지정하는 일반적인 방법을 설명합니다.  보통 [필터](../data/odbc/recordset-filtering-records-odbc.md) 또는 [매개 변수](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)를 사용하여 레코드 선택을 제한하고, 경우에 따라 레코드를 [정렬](../data/odbc/recordset-sorting-records-odbc.md)하고 SQL 문을 사용자 지정합니다.  
  
 이 정보는 [CRecordView](../mfc/reference/crecordview-class.md)\(ODBC\) 및 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)\(DAO\) 둘 다에 적용됩니다.  
  
 `CRecordView` 또는 `CDaoRecordView`를 사용하는 것은 [CFormView](../mfc/reference/cformview-class.md)를 사용하는 것과 거의 비슷합니다.  기본적인 방식은 레코드 뷰를 사용하여 단일 레코드 집합의 레코드를 표시하고 필요에 따라 업데이트하는 것입니다.  뿐만 아니라 [레코드 뷰: 두 번째 레코드 집합에서 목록 상자 채우기](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)의 설명에 따라 기타 레코드 집합을 사용할 수도 있습니다.  
  
## 참고 항목  
 [레코드 뷰  \(MFC Data Access\)](../data/record-views-mfc-data-access.md)   
 [ODBC 드라이버 목록](../data/odbc/odbc-driver-list.md)