---
title: "창 스타일 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WS_MINIMIZEBOX"
  - "WS_SIZEBOX"
  - "WS_CLIPCHILDREN"
  - "WS_TILED"
  - "WS_GROUP"
  - "WS_VSCROLL"
  - "WS_CHILD"
  - "WS_TABSTOP"
  - "WS_HSCROLL"
  - "WS_THICKFRAME"
  - "WS_DISABLED"
  - "WS_POPUP"
  - "WS_ICONIC"
  - "WS_MAXIMIZE"
  - "WS_VISIBLE"
  - "WS_POPUPWINDOW"
  - "WS_TILEDWINDOW"
  - "WS_DLGFRAME"
  - "WS_MINIMIZE"
  - "WS_CAPTION"
  - "WS_OVERLAPPED"
  - "WS_BORDER"
  - "WS_MAXIMIZEBOX"
  - "WS_OVERLAPPEDWINDOW"
  - "WS_SYSMENU"
  - "WS_CHILDWINDOW"
  - "WS_CLIPSIBLINGS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "스타일, windows"
  - "창 스타일"
  - "창 스타일, MFC"
  - "WS_BORDER 상수"
  - "WS_CAPTION 상수"
  - "WS_CHILD 상수"
  - "WS_CHILDWINDOW 상수"
  - "WS_CLIPCHILDREN 상수"
  - "WS_CLIPSIBLINGS 상수"
  - "WS_DISABLED 상수"
  - "WS_DLGFRAME 상수"
  - "WS_GROUP 상수"
  - "WS_HSCROLL 상수"
  - "WS_ICONIC 상수"
  - "WS_MAXIMIZE 상수"
  - "WS_MAXIMIZEBOX 상수"
  - "WS_MINIMIZE 상수"
  - "WS_MINIMIZEBOX 상수"
  - "WS_OVERLAPPED 상수"
  - "WS_OVERLAPPEDWINDOW 상수"
  - "WS_POPUP 상수"
  - "WS_POPUPWINDOW 상수"
  - "WS_SIZEBOX 상수"
  - "WS_SYSMENU 상수"
  - "WS_TABSTOP 상수"
  - "WS_THICKFRAME 상수"
  - "WS_TILED 상수"
  - "WS_TILEDWINDOW 상수"
  - "WS_VISIBLE 상수"
  - "WS_VSCROLL 상수"
ms.assetid: c85ffbe4-f4ff-4227-917a-48ec4a411842
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 창 스타일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   `WS_BORDER` 크기 조정 테두리가 있는 창을 만듭니다.  
  
-   **WS\_CAPTION** 제목 표시줄이 있는 창을 만듭니다\(`WS_BORDER` 스타일 의미\).  **WS\_DLGFRAME** 스타일과 함께 사용할 수 없습니다.  
  
-   **WS\_CHILD** 자식 창을 만듭니다.  `WS_POPUP` 스타일과 함께 사용할 수 없습니다.  
  
-   **WS\_CHILDWINDOW WS\_CHILD** 스타일과 동일합니다.  
  
-   **WS\_CLIPCHILDREN** 부모 창 안에서 그릴 경우 자식 창이 차지하는 영역을 제외합니다.  부모 창을 만들 때 사용합니다.  
  
-   **WS\_CLIPSIBLINGS** 서로 상대적인 하위 창을 잘라냅니다. 즉, 특정 하위 창이 paint 메시지를 받으면 **WS\_CLIPSIBLINGS** 스타일은 중첩된 다른 모든 하위 창을 업데이트되는 하위 창의 영역 밖으로 잘라냅니다. \(**WS\_CLIPSIBLINGS**가 지정되지 않았고 자식 창이 겹친 경우, 자식 창의 클라이언트 영역 안에서 그리면 인근 자식 창의 클라이언트 영역 안에서 그릴 수 있습니다.\) **WS\_CHILD** 스타일만 사용합니다.  
  
-   **WS\_DISABLED** 처음에 비활성화되어 있는 창을 만듭니다.  
  
-   **WS\_DLGFRAME** 이중 테두리가 있고 제목이 없는 창을 만듭니다.  
  
-   **WS\_GROUP** 사용자가 한 컨트롤에서 다음 컨트롤로 화살표 키를 사용하여 이동할 수 있도록 컨트롤 그룹의 첫 번째 컨트롤을 지정합니다.  첫 번째 컨트롤 이후 **WS\_GROUP** 스타일을 **FALSE**로 지정하여 정의된 모든 컨트롤은 동일한 그룹에 속합니다.  **WS\_GROUP** 스타일의 다음 컨트롤에는 다음 그룹\(다음 시작 되는 위치 즉, 그룹 끝\)을 시작합니다.  
  
-   **WS\_HSCROLL** 가로 스크롤 막대가 있는 창을 만듭니다.  
  
-   **WS\_ICONIC** 처음에 최소화되어 있는 창을 만듭니다.  **WS\_MINIMIZE** 스타일과 동일합니다.  
  
-   **WS\_MAXIMIZE** 최대 크기의 창을 만듭니다.  
  
-   **WS\_MAXIMIZEBOX** 최대화 단추가 있는 창을 만듭니다.  
  
-   **WS\_MINIMIZE** 처음에 최소화되어 있는 창을 만듭니다.  **WS\_OVERLAPPED** 스타일만 사용합니다.  
  
-   **WS\_MINIMIZEBOX** 최소화 단추가 있는 창을 만듭니다.  
  
-   **WS\_OVERLAPPED** 겹친 창을 만듭니다.  중첩된 창에는 일반적으로 제목과 테두리가 있습니다.  
  
-   **WS\_OVERLAPPEDWINDOW WS\_OVERLAPPED**, **WS\_CAPTION**, **WS\_SYSMENU**, **WS\_THICKFRAME**, **WS\_MINIMIZEBOX** 및 **WS\_MAXIMIZEBOX** 스타일을 사용하여 겹친 창을 만듭니다.  
  
-   `WS_POPUP` 팝업 창을 만듭니다.  **WS\_CHILD** 스타일과 함께 사용할 수 없습니다.  
  
-   **WS\_POPUPWINDOW** `WS_BORDER`, `WS_POPUP` 및 **WS\_SYSMENU** 스타일을 사용하여 팝업 창을 만듭니다.  **WS\_CAPTION** 스타일은 **WS\_POPUPWINDOW** 스타일과 결합하여 컨트롤 메뉴를 표시할 수 있습니다.  
  
-   **WS\_SIZEBOX** 크기 조정 테두리가 있는 창을 만듭니다.  **WS\_THICKFRAME** 스타일과 동일합니다.  
  
-   **WS\_SYSMENU** 창의 제목 표시줄에 컨트롤 메뉴 상자를 만듭니다.  Windows 제목 표시줄에만 사용합니다.  
  
-   **WS\_TABSTOP** 사용자가 TAB 키를 사용하여 이동할 수 있는 컨트롤 중 하나를 지정합니다.  TAB 키를 사용하면 **WS\_TABSTOP** 스타일로 지정된 다음 컨트롤로 이동합니다.  
  
-   **WS\_THICKFRAME** 창에 창 크기를 조정할 수 있는 두꺼운 프레임을 만듭니다.  
  
-   **WS\_TILED** 겹친 창을 만듭니다.  중첩된 창에는 제목 표시줄과 테두리가 있습니다.  **WS\_OVERLAPPED** 스타일과 동일합니다.  
  
-   **WS\_TILEDWINDOW WS\_OVERLAPPED**, **WS\_CAPTION**, **WS\_SYSMENU**, **WS\_THICKFRAME**, **WS\_MINIMIZEBOX** 및 **WS\_MAXIMIZEBOX** 스타일을 사용하여 겹친 창을 만듭니다.  **WS\_OVERLAPPEDWINDOW** 스타일과 동일합니다.  
  
-   **WS\_VISIBLE** 처음에 표시되는 창을 만듭니다.  
  
-   **WS\_VSCROLL** 세로 스크롤 막대가 있는 창을 만듭니다.  
  
## 참고 항목  
 [MFC에서 사용하는 스타일](../../mfc/reference/styles-used-by-mfc.md)   
 [CWnd::Create](../Topic/CWnd::Create.md)   
 [CWnd::CreateEx](../Topic/CWnd::CreateEx.md)   
 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)