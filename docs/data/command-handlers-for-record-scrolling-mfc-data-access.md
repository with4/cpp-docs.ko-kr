---
title: "레코드 스크롤에 대한 명령 처리기  (MFC Data Access) | Microsoft Docs"
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
  - "레코드 스크롤[C++]"
  - "레코드 뷰[C++], 스크롤"
  - "레코드 스크롤"
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 레코드 스크롤에 대한 명령 처리기  (MFC Data Access)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CRecordView](../mfc/reference/crecordview-class.md) 및 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) 클래스는 다음 표준 명령에 대한 기본 명령 처리 기능을 제공합니다.  
  
-   **ID\_RECORD\_MOVE\_FIRST**  
  
-   **ID\_RECORD\_MOVE\_LAST**  
  
-   **ID\_RECORD\_MOVE\_NEXT**  
  
-   **ID\_RECORD\_MOVE\_PREV**  
  
 `CRecordView` 및 `CDaoRecordView` 클래스의 `OnMove` 멤버 함수는 레코드 간을 이동하는 4개 명령에 대해 모두 기본 명령 처리 기능을 제공합니다.  이러한 명령을 실행하면 RFX 또는 DFX는 새 레코드를 레코드 집합의 필드에 로드하고 DDX는 레코드 폼의 컨트롤로 값을 이동합니다.  RFX에 대한 자세한 내용은 [RFX\(레코드 필드 교환\)](../data/odbc/record-field-exchange-rfx.md)를 참조하세요.  
  
> [!NOTE]
>  표준 레코드 탐색 명령과 연결된 모든 사용자 인터페이스 개체에 대해 이러한 표준 명령 ID를 사용해야 합니다.  
  
## 참고 항목  
 [레코드 뷰에서의 탐색 지원](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)