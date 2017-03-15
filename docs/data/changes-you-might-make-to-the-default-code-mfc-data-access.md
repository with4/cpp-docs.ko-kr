---
title: "기본 코드에 수행할 수 있는 변경  (MFC Data Access) | Microsoft Docs"
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
  - "레코드 뷰[C++], 기본 코드 사용자 지정"
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 기본 코드에 수행할 수 있는 변경  (MFC Data Access)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[MFC 응용 프로그램 마법사](../mfc/reference/database-support-mfc-application-wizard.md)는 단일 테이블의 모든 레코드를 선택하는 레코드 집합 클래스를 자동으로 작성합니다.  다음 방식 중 하나 이상을 사용하여 해당 동작을 수정하는 경우가 많습니다.  
  
-   레코드 집합에 대해 필터 또는 정렬 순서를 설정합니다.  이 작업은 레코드 집합 개체를 생성한 후 해당 **Open** 멤버 함수를 호출하기 전에 `OnInitialUpdate`에서 수행합니다.  자세한 내용은 [레코드 집합: 레코드 필터링\(ODBC\)](../data/odbc/recordset-filtering-records-odbc.md) 및 [레코드 집합: 레코드 정렬\(ODBC\)](../data/odbc/recordset-sorting-records-odbc.md)을 참조하세요.  
  
-   레코드 집합을 매개 변수화합니다.  이 경우 필터 후의 실제 런타임 매개 변수 값을 지정합니다.  자세한 내용은 [레코드 집합: 레코드 집합 매개 변수화\(ODBC\)](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)를 참조하세요.  
  
-   사용자 지정된 SQL 문자열을 [Open](../Topic/CRecordset::Open.md) 멤버 함수에 전달합니다.  이 기술을 사용하여 수행할 수 있는 작업에 대한 설명은 [SQL: 레코드 집합의 SQL 문 사용자 지정\(ODBC\)](../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md)을 참조하세요.  
  
## 참고 항목  
 [레코드 뷰 사용](../data/using-a-record-view-mfc-data-access.md)