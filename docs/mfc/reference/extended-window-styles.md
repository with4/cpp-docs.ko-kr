---
title: "확장 창 스타일 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WS_EX_TOOLWINDOW"
  - "WS_EX_LEFTSCROLLBAR"
  - "WS_EX_RTLREADING"
  - "WS_EX_WINDOWEDGE"
  - "WS_EX_CLIENTEDGE"
  - "WS_EX_STATICEDGE"
  - "WS_EX_LTRREADING"
  - "WS_EX_DLGMODALFRAME"
  - "WS_EX_RIGHTSCROLLBAR"
  - "WS_EX_CONTROLPARENT"
  - "WS_EX_ACCEPTFILES"
  - "WS_EX_TRANSPARENT"
  - "WS_EX_RIGHT"
  - "WS_EX_APPWINDOW"
  - "WS_EX_TOPMOST"
  - "WS_EX_CONTEXTHELP"
  - "WS_EX_MDICHILD"
  - "WS_EX_LEFT"
  - "WS_EX_OVERLAPPEDWINDOW"
  - "WS_EX_PALETTEWINDOW"
  - "WS_EX_NOPARENTNOTIFY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "확장 창 스타일"
  - "스타일, windows"
  - "WS_EX_ACCEPTFILES 상수"
  - "WS_EX_APPWINDOW 상수"
  - "WS_EX_CLIENTEDGE 상수"
  - "WS_EX_CONTEXTHELP 상수"
  - "WS_EX_CONTROLPARENT 상수"
  - "WS_EX_DLGMODALFRAME 상수"
  - "WS_EX_LEFT 상수"
  - "WS_EX_LEFTSCROLLBAR 상수"
  - "WS_EX_LTRREADING 상수"
  - "WS_EX_MDICHILD 상수"
  - "WS_EX_NOPARENTNOTIFY 상수"
  - "WS_EX_OVERLAPPEDWINDOW 상수"
  - "WS_EX_PALETTEWINDOW 상수"
  - "WS_EX_RIGHT 상수"
  - "WS_EX_RIGHTSCROLLBAR 상수"
  - "WS_EX_RTLREADING 상수"
  - "WS_EX_STATICEDGE constant"
  - "WS_EX_TOOLWINDOW 상수"
  - "WS_EX_TOPMOST 상수"
  - "WS_EX_TRANSPARENT 상수"
  - "WS_EX_WINDOWEDGE 상수"
ms.assetid: d18e6c69-0a01-49ed-b58a-55b3802b47c1
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# 확장 창 스타일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **WS\_EX\_ACCEPTFILES** 창이 끌어서 놓기를 허용하는 스타일로 만들어졌는지를 특정합니다.  
  
-   **WS\_EX\_APPWINDOW** 창이 표시되면 창을 작업 표시줄의 가장 위쪽으로 올립니다.  
  
-   **WS\_EX\_CLIENTEDGE** 창이 3차원 모양 — 즉, 오목 모서리와 테두리를 가지고 있는지 특정합니다.  
  
-   **WS\_EX\_CONTEXTHELP** 창 제목 표시줄의 물음표를 포함합니다.  사용자가 물음표를 클릭하면, 커서가 포인터가 붙은 물음표로 변경됩니다.  사용자가 자식 창을 클릭하면, 자식은 **WM\_HELP** 메시지를 받습니다.  
  
-   **WS\_EX\_CONTROLPARENT** TAB 키를 사용하여 창의 자식 창 사이를 이동할 수 있도록 허용합니다.  
  
-   **WS\_EX\_DLGMODALFRAME** `dwStyle` 매개 변수에서 **WS\_CAPTION** 스타일 플래그를 지정할 때 제목 표시줄을 이용하여 \(선택적으로\) 생성될 수 있는 이중 테두리가 있는 창을 지정합니다.  
  
-   **WS\_EX\_LAYERED** 창이 [계층화된 창](http://msdn.microsoft.com/library/ms632599\(v=vs.85\).aspx#layered")입니다.  이 스타일은 창이 **CS\_OWNDC** 또는 **CS\_CLASSDC**의 [클래스 스타일](http://msdn.microsoft.com/library/ms633574\(v=vs.85\).aspx#class_styles")을 가질 경우 사용될 수 없습니다.  하지만, [!INCLUDE[win8_first](../../mfc/reference/includes/win8_first_md.md)]는 이전 버전의 Windows가 최상위 레벨의 창에만 **WS\_EX\_LAYERED** 스타일을 지원했던 것과 달리 이를 자식 창에도 지원합니다.  
  
-   **WS\_EX\_LEFT** 창에 일반 왼쪽 맞춤 속성을 줍니다.  이 값이 기본값입니다.  
  
-   **WS\_EX\_LEFTSCROLLBAR** 세로 스크롤 막대를 클라이언트 영역의 왼쪽에 배치합니다.  
  
-   **WS\_EX\_LTRREADING** 창의 텍스트를 왼쪽에서부터 오른쪽 읽기 순서 속성을 사용하여 표시합니다.  이 값이 기본값입니다.  
  
-   **WS\_EX\_MDICHILD** MDI 자식 창을 만듭니다.  
  
-   **WS\_EX\_NOPARENTNOTIFY** 자식 창이 생성되거나 소멸될 때에 이 스타일로 생성된 자식 창이 `WM_PARENTNOTIFY` 메시지를 부모 창에게 전달하지 않도록 지정합니다.  
  
-   **WS\_EX\_OVERLAPPEDWINDOW WS\_EX\_CLIENTEDGE** 및 **WS\_EX\_WINDOWEDGE** 스타일을 결합합니다.  
  
-   **WS\_EX\_PALETTEWINDOW WS\_EX\_WINDOWEDGE** 및 **WS\_EX\_TOPMOST** 스타일을 결합합니다.  
  
-   **WS\_EX\_RIGHT** 창에 일반 오른쪽 맞춤 속성을 제공합니다.  이는 창 클래스에 의존적입니다.  
  
-   **WS\_EX\_RIGHTSCROLLBAR** 세로 스크롤 막대 \(있는 경우\) 를 클라이언트 영역 오른쪽에 배치합니다.  이 값이 기본값입니다.  
  
-   **WS\_EX\_RTLREADING** 창의 텍스트를 오른쪽에서부터 왼쪽 읽기 순서 속성을 사용하여 표시합니다.  
  
-   **WS\_EX\_STATICEDGE** 사용자 입력을 받지 않는 항목을 사용하는 3차원 테두리 스타일을 사용한 창을 생성합니다.  
  
-   **WS\_EX\_TOOLWINDOW** 창을 부유 도구 모음으로 사용할 수 있는 도구 창을 만듭니다.  도구 창은 일반 제목 표시줄보다 짧은 제목 표시줄을 가지며, 창 제목은 더 작은 글꼴을 사용하여 그려집니다.  사용자가 Alt\+Tab을 누를 때 나타나는 작업 표시줄이나 창에는 도구 창이 나타나지 않습니다.  
  
-   **WS\_EX\_TOPMOST** 이 스타일로 생성된 창이 모든 nontopmost 창 위에 존재하고 창이 비활성화되었을 때에도 그 위에 있어야 하는지를 지정합니다.  응용 프로그램은 이 속성을 추가하거나 제거하기 위하여 `SetWindowPos` 멤버 함수를 사용할 수 있습니다.  
  
-   **WS\_EX\_TRANSPARENT** 이 스타일을 사용하여 만든 창을 투명하게 지정합니다.  즉, 이 창 아래에 있는 모든 창은 이 창에 의해 가려지지 않습니다.  이 스타일을 사용하여 만든 창은 모든 형제 창이 업데이트된 후에 `WM_PAINT` 메시지를 받습니다.  
  
-   **WS\_EX\_WINDOWEDGE** 창에 올라가는 테두리가 포함되도록 지정합니다.  
  
## 참고 항목  
 [MFC에서 사용하는 스타일](../../mfc/reference/styles-used-by-mfc.md)   
 [CWnd::CreateEx](../Topic/CWnd::CreateEx.md)   
 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)