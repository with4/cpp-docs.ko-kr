---
title: "컨트롤 막대 클래스 | Microsoft Docs"
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
  - "vc.classes.control"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "컨트롤 막대, 클래스"
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 컨트롤 막대 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컨트롤 막대는 프레임 창에 연결 됩니다.  단추, 상태 창 또는 대화 상자 템플릿을 포함합니다.  또한 도구 팔레트 막대라고도 명명된 부동성 컨트롤 막대는 그들을 [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md) 개체로 연결하는 것에 의해 구현됩니다.  
  
## Framework 컨트롤 막대  
 이러한 컨트롤 막대는 MFC framework의 구성 요소입니다.  그들은 framework와 통합되었기 때문에, Windows 컨트롤 막대보다 더 사용하기 쉽고 좀 더 강력합니다.  대부분의 MFC 응용 프로그램은 Windows 컨트롤 막대보다는 이러한 컨트롤 막대를 사용합니다.  
  
 [CControlBar](../mfc/reference/ccontrolbar-class.md)  
 MFC 컨트롤 막대에 대한 기본 클래스가 이곳에 나열됩니다.  컨트롤 막대는 프레임 창의 가장자리에 정렬된 창입니다.  컨트롤 막대는 자식 컨트롤에 기반을 둔 `HWND` 또는 도구 모음 단추와 같이 `HWND`에 기반을 두지 않은 컨트롤 중 하나를 포함합니다.  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 대화 상자 템플릿을 기반으로 하는 컨트롤 막대입니다.  
  
 [CReBar](../mfc/reference/crebar-class.md)  
 컨트롤 양식에서 추가 자식 창을 포함할 수 있는 도구 모음을 지원합니다.  
  
 [CToolBar](../mfc/reference/ctoolbar-class.md)  
 비트맵 명령 단추를 포함하는 도구 모음 컨트롤 창은 `HWND`에 기반하지 않습니다.  대부분의 MFC 응용 프로그램은 `CToolBarCtrl`보다는 이 클래스를 사용합니다.  
  
 [CStatusBar](../mfc/reference/cstatusbar-class.md)  
 상태 표시줄 컨트롤 창에 대한 기본 클래스입니다.  대부분의 MFC 응용 프로그램은 `CStatusBarCtrl`보다는 이 클래스를 사용합니다.  
  
## Windows 컨트롤 막대  
 이러한 컨트롤 막대는 Windows 컨트롤에 해당하는 씬 래퍼입니다.  framework와 통합되지 않았기 때문에, 그들은 앞에 나열된 컨트롤 막대보다 사용하기 어렵습니다.  대부분의 MFC 응용 프로그램은 앞에 나열된 컨트롤 막대를 사용합니다.  
  
 [CRebarCtrl](../mfc/reference/crebarctrl-class.md)  
 `CRebar` 개체의 내부 제어를 구현합니다.  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 수평 창은 일반적으로 응용 프로그램이 상태 정보를 표시할 수 있는 창으로 분할됩니다.  
  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Windows의 도구 모음 공용 컨트롤의 기능을 제공합니다.  
  
## 관련 클래스  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 응용 프로그램 도구의 용도를 설명하는 텍스트 한 줄을 표시하는 작은 팝업 창인 "도구 설명 컨트롤"입니다.  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 컨트롤 막대에 대한 상태 데이터를 도킹하는 영구 저장소를 처리합니다.  
  
## 참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)