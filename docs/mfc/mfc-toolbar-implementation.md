---
title: "MFC 도구 모음 구현 | Microsoft Docs"
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
  - "비트맵[C++], 도구 모음"
  - "단추[C++], MFC 도구 모음"
  - "CToolBar 클래스, 도구 모음 만들기"
  - "CToolBarCtrl 클래스, 도구 모음 구현"
  - "도킹 도구 모음"
  - "부동 도구 모음"
  - "MFC 도구 모음"
  - "도구 설명[C++], 사용"
  - "도구 모음 컨트롤[MFC]"
  - "도구 모음[C++]"
  - "도구 모음[C++], 만들기"
  - "도구 모음[C++], 도킹"
  - "도구 모음[C++], 부동"
  - "도구 모음[C++], MFC 도구 모음 구현"
ms.assetid: af3319ad-c430-4f90-8361-e6a2c06fd084
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC 도구 모음 구현
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

도구 모음은 컨트롤의 비트맵 이미지를 포함하는 [컨트롤 막대](../mfc/control-bars.md)입니다.  이러한 이미지는 누름 단추, 확인란 또는 라디오 단추와 같이 작동할 수 있습니다.  MFC 클래스는 [CToolbar](../mfc/reference/ctoolbar-class.md) 도구 모음의 관리를 지원합니다.  
  
 이를 적용하면, MFC 도구 모음 사용자는 도구 모음을 창 가장자리에 도킹 하거나 응용 프로그램 창 내의 어떤 곳에도 "띄울" 수 있습니다.  MFC는 개발 환경에서와 같은 사용자 지정이 가능한 도구 모음을 지원하지 않습니다.  
  
 MFC는 또한 도구 설명을 지원합니다: 마우스를 단추 위에 올릴 경우 도구 모음 단추의 목적을 설명하는 작은 팝업 창을 띄웁니다.  기본적으로 사용자가 도구 모음 단추를 누르면, 상태 표시줄에 상태 문자열이 나타납니다 \(있는 경우\).  단추를 누르지 않은 채로 마우스를 단추 위에 올려놓을 때 상태 문자열을 표시하도록 업데이트함으로써 "fly by" 상태 표시줄을 활성화할 수 있습니다.  
  
> [!NOTE]
>  도구 모음 및 도구 설명은 MFC에 특정된 이전 방식의 구현 대신 Windows 95와 그 이후 버전에서는 기능적으로 구현됩니다.  
  
 이전 버전과의 호환성을 위해 MFC는 이전 도구 모음을 **COldToolBar** 클래스에서 에서 구현하여 유지하였습니다.  이전 버전의 MFC 문서는 **COldToolBar**의  `CToolBar` 를 설명합니다.  
  
 응용 프로그램 마법사에서 도구 모음 옵션을 선택하면 프로그램의 첫 번째 도구 모음을 만듭니다.  추가 도구 모음을 만들 수도 있습니다.  
  
 다음은 이 문서에 소개 된 것입니다.  
  
-   [도구 모음 단추](#_core_toolbar_buttons)  
  
-   [도구 모음 고정 및 고정 해제](#_core_docking_and_floating_toolbars)  
  
-   [도구 모음 및 도구 설명](#_core_toolbars_and_tool_tips)  
  
-   [CToolBar 및 CToolBarCtrl 클래스](#_core_the_ctoolbar_and_ctoolbarctrl_classes)  
  
-   [도구 모음 비트맵](#_core_the_toolbar_bitmap)  
  
##  <a name="_core_toolbar_buttons"></a> 도구 모음 단추  
 도구 모음의 단추는 메뉴의 항목과 유사합니다.  두 종류의 사용자 인터페이스 개체는 명령을 생성하며, 프로그램은 처리기 함수를 제공하여 이 명령을 처리합니다.  종종 도구 모음 단추는 메뉴 명령을 기능적으로 복제하여 같은 기능을 하는 대체 사용자 인터페이스를 제공합니다.  단추와 메뉴 항목에게 같은 ID를 부여하는 것으로 간단하게 그러한 복제가 수행됩니다.  
  
 누름 단추, 확인란 혹은 라디오 단추처럼 나타나고 작동하는 단추를 도구 모음에 만들 수 있습니다.  자세한 내용은 [CToolBar](../mfc/reference/ctoolbar-class.md) 클래스를 참조하십시오.  
  
##  <a name="_core_docking_and_floating_toolbars"></a> 도구 모음 고정 및 고정 해제  
 MFC 도구 모음은 다음을 수행할 수 있습니다:  
  
-   부모 창의 한쪽에 고정 되어 있기  
  
-   드래그거나 "도킹", 또는 부모 창의 사용자가 지정하는 면에 부착되는 것  
  
-   "띄워져" 있거나 프레임 창으로부터 탈착된 채로 자체의 미니 프레임 창에 있어서 사용자가 원하는 편리한 위치로 이동이 가능  
  
-   떠 있을 때 크기를 조정 가능  
  
 자세한 내용은 [도킹 및 부유 도구 모음](../mfc/docking-and-floating-toolbars.md) 문서를 참조하십시오.  
  
##  <a name="_core_toolbars_and_tool_tips"></a> 도구 모음 및 도구 설명  
 MFC 도구 모음은 "도구 설명"을 표시하기 위해서 만들 수도 있습니다 — 작은 팝업 창은 도구 모은 단추의 용도에 대한 간단한 텍스트 설명을 포함합니다.  사용자가 도구 모음 단추 위로 마우스를 이동하면, 도구 설명 창이 팝업 힌트를 제공합니다.  자세한 내용은 [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md) 문서를 참조하십시오.  
  
##  <a name="_core_the_ctoolbar_and_ctoolbarctrl_classes"></a> CToolBar 및 CToolBarCtrl 클래스  
 [CToolBar](../mfc/reference/ctoolbar-class.md) 클래스를 통해 응용 프로그램의 도구 모음을 관리할 수 있습니다.  MFC 버전 4.0 기준으로 `CToolBar`는 Windows 95 혹은 그 이후 버전과 Windows NT 3.51 이상의 버전에서 이용 가능한 도구 모음 공용 컨트롤을 사용하기 위해서 재구현되었습니다.  
  
 MFC가 운영 체제의 지원을 받기 때문에, 이 재구현은 도구 모음을 위한 MFC 코드를 줄여줍니다.  이 재구현은 또한 기능을 향상시킵니다.  도구 모음을 조작하기 위해 `CToolBar`의 멤버 함수를 사용하거나 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 개체에 대한 참조를 얻고 도구 모음 사용자 정의와 추가적인 기능을 위해 그 멤버 함수를 호출할 수 있습니다.  
  
> [!TIP]
>  기존 MFC의 `CToolBar` 구현에 많은 투자를 하였다면, 그러한 지원은 여전히 사용 가능합니다.  [이전 도구 모음을 사용하기](../mfc/using-your-old-toolbars.md) 문서를 참조하십시오.  
  
 또한 MFC 일반 샘플 [DOCKTOOL](../top/visual-cpp-samples.md)을 참조 하십시오.  
  
##  <a name="_core_the_toolbar_bitmap"></a> 도구 모음 비트맵  
 `CToolBar` 개체가 생성되면, 각 단추 마다 이미지가 하나씩 포함된 단일 비트맵을 로드하여 도구 모음 이미지를 만든다.  응용 프로그램 마법사는 Visual C\+\+ [도구 모음 편집기](../mfc/toolbar-editor.md)를 사용하여 사용자 지정할 수 있는 표준 도구 모음 비트맵을 생성합니다.  
  
### 추가 정보  
  
-   [도구 모음 기본 사항](../mfc/toolbar-fundamentals.md)  
  
-   [도구 모음 고정 및 고정 해제](../mfc/docking-and-floating-toolbars.md)  
  
-   [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md)  
  
-   [ToolBar 컨트롤 사용](../mfc/working-with-the-toolbar-control.md)  
  
-   [이전 도구 모음 사용](../mfc/using-your-old-toolbars.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md) 및 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 클래스  
  
## 참고 항목  
 [도구 모음](../mfc/toolbars.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)