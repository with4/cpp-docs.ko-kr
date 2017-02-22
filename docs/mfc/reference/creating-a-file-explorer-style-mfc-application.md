---
title: "파일 탐색기 스타일 MFC 응용 프로그램 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfcexplorer.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "브라우저, 탐색기 스타일 응용 프로그램"
  - "탐색기 스타일 응용 프로그램, 만들기"
  - "MFC 응용 프로그램, Windows 탐색기 스타일"
ms.assetid: f843ab5d-2d5d-41ca-88a4-badc0d2f8052
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# 파일 탐색기 스타일 MFC 응용 프로그램 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Many Windows system applications use the user interface \(UI\) for File Explorer.  When you start File Explorer, for example, you see an application with a vertical splitter bar dividing the client area.  클라이언트 영역의 왼쪽 창에는 탐색 및 검색 기능이 제공되고 오른쪽 창에는 왼쪽 창에서 선택한 항목과 관련된 세부 사항이 표시됩니다.  사용자가 왼쪽 창에서 항목을 클릭하면 오른쪽 창의 내용이 다시 채워집니다.  MDI 응용 프로그램에서는 **보기** 메뉴의 명령을 사용하여 오른쪽 창에 표시되는 세부 사항의 정도를 변경할 수 있습니다. SDI 또는 다중 최상위 문서 응용 프로그램에서는 도구 모음 단추만을 사용하여 세부 사항을 변경할 수 있습니다.  
  
 창의 내용은 응용 프로그램에 따라 다릅니다.  파일 시스템 브라우저에서는 왼쪽 창에 디렉터리나 컴퓨터의 계층 구조 보기 또는 컴퓨터 그룹이 표시되고 오른쪽 창에는 폴더, 개별 파일 또는 컴퓨터와 그 세부 사항이 표시됩니다.  내용은 반드시 파일이 아닐 수도 있습니다.  전자 메일 메시지, 오류 보고서 또는 데이터베이스에 있는 그 밖의 항목일 수 있습니다.  
  
 마법사에서는 다음과 같은 클래스를 만듭니다.  
  
-   **CLeftView** 클래스는 클라이언트 영역의 왼쪽 창을 정의합니다.  이 클래스는 항상 [CTreeView](../../mfc/reference/ctreeview-class.md)에서 파생됩니다.  
  
-   C*ProjName*View 클래스는 클라이언트 영역의 오른쪽 창을 정의합니다.  기본적으로 이 클래스는 [CListView](../../mfc/reference/clistview-class.md)에서 파생되지만 마법사의 [생성된 클래스](../../mfc/reference/generated-classes-mfc-application-wizard.md) 페이지의 **기본 클래스** 목록에서 지정하는 클래스에 따라 다른 형식의 뷰가 될 수도 있습니다.  
  
 생성된 응용 프로그램에 SDI\(Single Document Interface\), MDI\(Multiple Document Interface\) 또는 다중 최상위 문서 아키텍처가 포함될 수 있습니다.  응용 프로그램에서 만드는 각 프레임 창은 [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md)를 사용하여 세로로 나뉩니다.  이 응용 프로그램 형식의 각 분할 창 내에 별개의 컨트롤 뷰가 있다는 점을 제외하면, 이 응용 프로그램 형식을 코딩하는 것은 분할 창을 사용하는 일반 MFC 응용 프로그램을 코딩하는 것과 비슷합니다.  
  
 오른쪽 창에서 기본 목록 뷰를 사용할 경우, 마법사는 추가 메뉴 선택 항목\(MDI 응용 프로그램의 경우만\)과 도구 모음 단추를 만들어 뷰의 스타일을 큰 아이콘, 작은 아이콘, 간단히, 자세히 모드 사이에서 전환할 수 있도록 합니다.  
  
### To begin creating a File Explorer\-style MFC executable  
  
1.  [MFC 응용 프로그램 만들기](../../mfc/reference/creating-an-mfc-application.md)의 지시를 따릅니다.  
  
2.  In the MFC Application Wizard [Application Type](../../mfc/reference/application-type-mfc-application-wizard.md) page, select the **File Explorer** project style.  
  
3.  마법사의 다른 페이지에서 원하는 기타 옵션을 설정합니다.  
  
4.  **마침**을 클릭하여 기초 응용 프로그램을 생성합니다.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [여러 문서 형식, 뷰 및 프레임 창](../../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [파생 뷰 클래스](../../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [응용 프로그램 디자인 선택](../../mfc/application-design-choices.md)  
  
## 참고 항목  
 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)   
 [웹 브라우저 스타일 MFC 응용 프로그램 만들기](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)   
 [폼 기반 MFC 응용 프로그램 만들기](../../mfc/reference/creating-a-forms-based-mfc-application.md)