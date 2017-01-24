---
title: "레코드 뷰 클래스의 기능  (MFC Data Access) | Microsoft Docs"
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
  - "레코드 뷰 클래스"
  - "레코드 뷰, 클래스"
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 레코드 뷰 클래스의 기능  (MFC Data Access)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CFormView](../mfc/reference/cformview-class.md) 클래스를 사용하여 폼 기반 데이터 액세스 프로그래밍을 수행할 수는 있지만 일반적으로는 [CRecordView](../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) 클래스에서 파생하는 것이 보다 효율적입니다.  `CRecordView` 및 `CDaoRecordView`는 해당 `CFormView` 기능 외에 다음 작업도 수행합니다.  
  
-   폼 컨트롤과 연결된 레코드 집합 개체 간에 DDX\(대화 상자 데이터 교환\) 기능을 제공합니다.  
  
-   관련 레코드 집합 개체의 레코드를 탐색할 수 있도록 처음으로 이동, 다음으로 이동, 이전으로 이동 및 마지막으로 이동 명령을 처리합니다.  
  
-   사용자가 다른 레코드로 이동할 때 현재 레코드에 대한 변경 내용을 업데이트합니다.  
  
 탐색에 대한 자세한 내용은 [레코드 뷰: 레코드 뷰에서의 탐색 지원](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)을 참조하세요.  
  
## 참고 항목  
 [레코드 뷰  \(MFC Data Access\)](../data/record-views-mfc-data-access.md)   
 [ODBC 드라이버 목록](../data/odbc/odbc-driver-list.md)