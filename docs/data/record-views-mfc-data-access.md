---
title: "레코드 뷰  (MFC Data Access) | Microsoft Docs"
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
  - "DAO[C++], 레코드 뷰"
  - "데이터베이스[C++], 레코드 뷰"
  - "폼[C++], 데이터 액세스 작업"
  - "MFC[C++], 레코드 뷰"
  - "ODBC 레코드 집합[C++], 레코드 뷰"
  - "레코드 뷰[C++]"
ms.assetid: 562122d9-01d8-4284-acf6-ea109ab0408d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 레코드 뷰  (MFC Data Access)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 섹션의 내용은 MFC ODBC 및 DAO 클래스에만 적용됩니다.  OLE DB 레코드 뷰에 대한 자세한 내용은 [COleDBRecordView](../mfc/reference/coledbrecordview-class.md) 및 [OLE DB 레코드 뷰 사용](../data/oledb/using-ole-db-record-views.md)을 참조하세요.  
  
 폼 기반 데이터 액세스 응용 프로그램을 지원하기 위해 클래스 라이브러리는 [CRecordView](../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) 클래스를 제공합니다.  레코드 뷰는 해당 컨트롤이 [레코드 집합](../data/odbc/recordset-odbc.md) 개체의 필드 데이터 멤버에 직접 매핑되며, 데이터 소스의 테이블 또는 쿼리 결과의 해당 열에 간접적으로 매핑되는 폼 뷰 개체입니다.  해당 기본 클래스인 [CFormView](../mfc/reference/cformview-class.md)와 마찬가지로 `CRecordView` 및 `CDaoRecordView`도 대화 상자 템플릿 리소스를 기반으로 합니다.  
  
## 폼 사용  
 폼은 다음과 같은 여러 데이터 액세스 작업에 유용합니다.  
  
-   데이터 입력  
  
-   데이터의 읽기 전용 검사 수행  
  
-   데이터 업데이트  
  
## 레코드 뷰에 대한 추가 자료  
 아래 항목의 자료는 ODBC 기반 및 DAO 기반 클래스 둘 다에 적용됩니다.  ODBC의 경우 `CRecordView`를 사용하고 DAO의 경우에는 `CDaoRecordView`를 사용합니다.  
  
 다음과 같은 내용을 다룹니다.  
  
-   [레코드 뷰 클래스의 기능](../data/features-of-record-view-classes-mfc-data-access.md)  
  
-   [레코드 뷰의 데이터 교환](../data/data-exchange-for-record-views-mfc-data-access.md)  
  
-   [레코드 뷰를 사용하여 작업할 때의 사용자 작업](../data/your-role-in-working-with-a-record-view-mfc-data-access.md)  
  
-   [레코드 뷰 디자인 및 만들기](../data/designing-and-creating-a-record-view-mfc-data-access.md)  
  
-   [레코드 뷰 사용](../data/using-a-record-view-mfc-data-access.md)  
  
## 참고 항목  
 [데이터 엑세스 프로그래밍 \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)   
 [ODBC 드라이버 목록](../data/odbc/odbc-driver-list.md)