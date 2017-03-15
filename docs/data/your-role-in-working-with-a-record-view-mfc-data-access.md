---
title: "레코드 뷰를 사용하여 작업할 때의 사용자 작업  (MFC Data Access) | Microsoft Docs"
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
  - "MFC, 레코드 뷰"
  - "레코드 뷰, 기본 코드 사용자 지정"
ms.assetid: 691e89a5-ff21-4ca3-9278-69d4678288bb
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 레코드 뷰를 사용하여 작업할 때의 사용자 작업  (MFC Data Access)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 테이블에는 레코드 뷰를 사용하기 위해 일반적으로 수행해야 하는 작업과 프레임워크에서 자동으로 수행하는 작업이 나와 있습니다.  
  
### 레코드 뷰 사용: 개발자의 작업과 프레임워크에서 수행하는 작업  
  
|사용자|프레임워크|  
|---------|-----------|  
|Visual C\+\+ 대화 상자 편집기를 사용하여 폼을 디자인합니다.|컨트롤이 있는 대화 상자 템플릿 리소스를 만듭니다.|  
|[MFC 응용 프로그램 마법사](../mfc/reference/database-support-mfc-application-wizard.md)를 사용하여 [CRecordView](../mfc/reference/crecordview-class.md) 및 [CRecordset](../mfc/reference/crecordset-class.md) 또는 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) 및 [CDaoRecordset](../mfc/reference/cdaorecordset-class.md)에서 파생되는 클래스를 만듭니다.|클래스를 자동으로 작성합니다.|  
|레코드 뷰 컨트롤을 레코드 집합 필드 데이터 멤버에 매핑합니다.|컨트롤과 레코드 집합 필드 간에 DDX를 제공합니다.|  
||메뉴 또는 도구 모음 단추에서 **처음으로 이동**, **마지막으로 이동**, **다음으로 이동** 및 **이전으로 이동** 명령의 기본 명령 처리기를 제공합니다.|  
||데이터 소스에 대한 변경 내용을 업데이트합니다.|  
|\[선택 사항\] 두 번째 레코드 집합의 데이터로 목록 상자 또는 콤보 상자나 기타 컨트롤을 채우는 코드를 작성합니다.||  
|\[선택 사항\] 특수 유효성 검사용 코드를 작성합니다.||  
|\[선택 사항\] 레코드를 추가하거나 삭제하는 코드를 작성합니다.||  
  
 데이터베이스를 사용할 때는 폼 기반 프로그래밍 방식만 사용할 수 있습니다.  다른 사용자 인터페이스를 사용하거나 사용자 인터페이스를 사용하지 않는 응용 프로그램에 대한 자세한 내용은 [MFC: 문서 및 뷰를 이용한 데이터베이스 클래스 사용](../data/mfc-using-database-classes-with-documents-and-views.md) 및 [MFC: 문서 및 뷰를 이용하지 않는 데이터베이스 클래스 사용](../data/mfc-using-database-classes-without-documents-and-views.md)을 참조하세요.  데이터베이스 레코드를 표시하는 다른 방식은 [CListView](../mfc/reference/clistview-class.md) 및 [CTreeView](../mfc/reference/ctreeview-class.md)를 참조하세요.  
  
## 참고 항목  
 [레코드 뷰  \(MFC Data Access\)](../data/record-views-mfc-data-access.md)   
 [ODBC 드라이버 목록](../data/odbc/odbc-driver-list.md)