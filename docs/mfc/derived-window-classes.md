---
title: "파생된 창 클래스 | Microsoft Docs"
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
  - "클래스[C++], 파생"
  - "CWnd 클래스, 파생된 클래스"
  - "파생 클래스, 창 클래스"
  - "계층 구조, 창 클래스"
  - "창 클래스 계층 구조"
  - "창 클래스, 파생"
ms.assetid: 6f7e437e-fbde-4a06-bfab-72d9dbf05292
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 파생된 창 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 [CWnd](../mfc/reference/cwnd-class.md) 로 부터, WIndows에서 직접 만들 수 있습니다. 또는 `CWnd` 로부터 새 창 클래스를 파생 할 수 있습니다.  일반적으로 사용자 지정 창을 만드는 방법입니다.  그러나 프레임워크 프로그램에서 사용되는 대부분의 창은 `CWnd` 중 하나로 대신 만들어진 것입니다. \-MFC에서 제공 하는 프레임 창 클래스를 파생 합니다.  
  
## 프레임 창 클래스  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 단일 문서 및 뷰가 들어가는 SDI 프레임 창에 사용 됩니다.  모두 응용 프로그램의 주 프레임 창 및 현재 문서의 프레임 창입니다.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 MDI 응용 프로그램의 주 프레임 창으로 사용 됩니다.  주 프레임 창을 모든 MDI 문서 창의 컨테이너와 메뉴 표시줄을 공유합니다.  MDI 프레임 창은 바탕 화면에 표시 되는 최상위 창입니다.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 MDI 주 프레임 창에 열려 있는 각 문서에 사용 합니다.  각 문서와 뷰는 MDI 주 프레임 창에 의해 둘러 싸인 MDI 자식 프레임 창에 의해 둘러싸여있습니다.  MDI 자식 창은 일반 프레임 창과 유사 하지만 바탕 화면에 위치 하지 않고 MDI 프레임 창 안에 포함되어 있습니다.  그러나 MDI 자식 창에 대한 고유 메뉴 표시줄이 없고, 포함하고 있는 MDI 프레임 창의 메뉴 표시줄을 공유 해야 합니다.  
  
 자세한 내용은 [Frame Windows](../mfc/frame-windows.md) 도움말을 참조하십시오.  
  
## CWnd에서 파생 된 다른 창 클래스  
 게다가 프레임 창은, Windows의 다른 몇 가지 주요 범주에서 `CWnd` 로부터 파생됬습니다.  
  
 *뷰*  
 `CWnd` 를 사용하여 뷰는 만들어 집니다. \-파생 클래스 [CView](../mfc/reference/cview-class.md) \(또는 파생된 클래스 중 하나\).  뷰는 문서에 첨부 된 문서와 사용자 사이 중개 역할을 합니다.  뷰는 일반적으로 SDI 프레임 창이 나 MDI 자식 프레임 창 \(또는 도구 모음 및 상태 표시줄에서 다루지 않는 클라이언트 영역의 해당 부분\)의 클라이언트 영역을 채우는 자식 창 \(MDI 자식 없습니다\)입니다.  
  
 *대화 상자*  
 대화상자는 `CWnd` 를 사용하여 만들어졌습니다. \-파생 클래스 [CDialog](../mfc/reference/cdialog-class.md).  
  
 *폼*  
 대화 상자와 같은 대화 상자 템플릿 리소스를 기반으로 한 폼 뷰 클래스를 사용하여 만듭니다. [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), 또는 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md).  
  
 *컨트롤*  
 단추, 목록 상자 및 다른 클래스들을 사용하여 만들어진 콤보 상자 등의 컨트롤은 `CWnd` 로부터 도출되었습니다.  [컨트롤 항목](../mfc/controls-mfc.md)을 참조하십시오.  
  
 *컨트롤 막대*  
 컨트롤이 포함된 자식 창입니다.  도구 모음 및 상태 표시줄을 예로 들 수 있습니다.  [컨트롤 막대](../mfc/control-bars.md)를 참조하십시오.  
  
## 창 클래스 계층 구조  
 *MFC 참조*에 있는 [MFC 계층 구조 차트](../mfc/hierarchy-chart.md) 를 언급합니다.  뷰는 [문서\/뷰 아키텍처](../mfc/document-view-architecture.md)에서 설명됩니다.  대화 상자는 [대화 상자](../mfc/dialog-boxes.md)에서 설명됩니다.  
  
## 특수 창 클래스 만들기  
 클래스 라이브러리에서 제공 하는 창 클래스 외에도 특수 용도의 자식 창이 필요할 수 있습니다.  이러한 창을 만들기 위해, [CWnd](../mfc/reference/cwnd-class.md)를 만들었습니다.\-파생 클래스 및 자식 창 프레임이 나 뷰를 만듭니다.  프레임 워크는 문서 프레임 창의 클라이언트 영역 범위를 관리 하는 것을 염두에 두십시오.  클라이언트 영역 대부분은 뷰에의해 관리되어집니다. 그러나 사용자 지정 윈도우 혹은 컨트롤 막대와 같은 다른 창에서는 뷰의 공간을 공유할 수도 있습니다.  프레임 창의 클라이언트 영역에 자식 창을 배치 하기 위하여, [CView](../mfc/reference/cview-class.md) 와 [CControlBar](../mfc/reference/ccontrolbar-class.md) 는 클래스에서 메커니즘을 상호 작용 하도록 할 수 있습니다  
  
 [창 만들기](../mfc/creating-windows.md) 만들기 창 개체와 windows 관리 하는 방법에 대해 설명 합니다.  
  
## 참고 항목  
 [창 개체](../mfc/window-objects.md)