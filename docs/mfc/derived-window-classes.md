---
title: 파생 된 창 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window class hierarchy
- hierarchies, window classes
- classes [MFC], derived
- CWnd class [MFC], classes derived from
- derived classes [MFC], window classes
- window classes [MFC], derived
ms.assetid: 6f7e437e-fbde-4a06-bfab-72d9dbf05292
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eddc6c59190856d09eae75c6f4314c902740092f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="derived-window-classes"></a>파생된 창 클래스
Windows에서 직접 만들 수 있습니다 [CWnd](../mfc/reference/cwnd-class.md)에서 새 창 클래스를 파생 하거나 `CWnd`합니다. 일반적으로 사용자 지정 창을 만드는 방법입니다. 하지만 대부분의 프레임 워크 프로그램에 사용 되는 창을 대신 중 하나에서 생성 된 `CWnd`-MFC에서 제공 하는 프레임 창 클래스를 파생 합니다.  
  
## <a name="frame-window-classes"></a>프레임 창 클래스  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 단일 문서와 해당 뷰 SDI 프레임 창에 사용 합니다. 프레임 창에는 응용 프로그램에 대 한 주 프레임 창 하면서 현재 문서에 대 한 프레임 창 있습니다.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 MDI 응용 프로그램에 대 한 주 프레임 창으로 사용 합니다. 주 프레임 창은 MDI 문서 창 모두에 대 한 컨테이너와 해당 메뉴 모음을 공유 합니다. MDI 프레임 창은 바탕 화면에 나타나는 최상위 창.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 MDI 주 프레임 창에서 열린 개별 문서에 사용 합니다. MDI 주 프레임 창에 포함 된 MDI 자식 프레임 창에서 각 문서와 뷰 묶여 있습니다. MDI 자식 창에 일반적인 프레임 창을 유사 하지만 바탕 화면에 위치 하지 않고 MDI 프레임 창 내에 포함. 그러나 MDI 자식 창에 게 없는 경우 자체의 메뉴 모음 및 포함 된 MDI 프레임 창의 메뉴 모음을 공유 해야 합니다.  
  
 자세한 내용은 참조 [프레임 창](../mfc/frame-windows.md)합니다.  
  
## <a name="other-window-classes-derived-from-cwnd"></a>CWnd에서 파생 된 다른 창 클래스  
 프레임 창 뿐만 아니라 windows의 다른 몇 가지 주요 범주에서 파생 된 `CWnd`:  
  
 *뷰*  
 사용 하 여 생성 하는 `CWnd`-파생 클래스 [CView](../mfc/reference/cview-class.md) (또는 파생된 클래스 중 하나). 뷰는 문서에 연결 하 고 문서와 사용자 간의 중개자로 작동 합니다. 뷰는 일반적으로 SDI 프레임 창 또는 MDI 자식 프레임 창 (또는 도구 모음 및/또는 상태 표시줄에서 포함 하지 않는 클라이언트 영역의 해당 부분)의 클라이언트 영역을 채우는 자식 창 (MDI 자식 하지 함).  
  
 *대화 상자*  
 대화 상자를 사용 하 여 만드는 `CWnd`-파생 클래스 [CDialog](../mfc/reference/cdialog-class.md)합니다.  
  
 *양식*  
 대화 상자와 같은 대화 상자 템플릿 리소스에 따라 폼 뷰 클래스를 사용 하 여 만들어집니다. [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), 또는 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)합니다.  
  
 *컨트롤*  
 단추, 목록 상자 및 콤보 상자 등의 컨트롤에서 파생 된 다른 클래스를 사용 하 여 만들어집니다. `CWnd`합니다. 참조 [항목 제어](../mfc/controls-mfc.md)합니다.  
  
 *컨트롤 막대*  
 컨트롤을 포함 하는 자식 창 도구 모음 및 상태 표시줄을 예로 들 수 있습니다. 참조 [컨트롤 막대](../mfc/control-bars.md)합니다.  
  
## <a name="window-class-hierarchy"></a>창 클래스 계층 구조  
 참조는 [MFC 계층 구조 차트](../mfc/hierarchy-chart.md) 에 *MFC 참조*합니다. 보기 설명 [문서/뷰 아키텍처](../mfc/document-view-architecture.md)합니다. 대화 상자에 설명 되어 [대화 상자](../mfc/dialog-boxes.md)합니다.  
  
## <a name="creating-your-own-special-purpose-window-classes"></a>특수 한 용도의 창 클래스 만들기  
 클래스 라이브러리에서 제공 하는 창 클래스 뿐 아니라 특수 한 용도의 자식 창 할 수 있습니다. 이러한 창을 만들기 위해 나만의 사이트 생성 [CWnd](../mfc/reference/cwnd-class.md)-클래스를 파생 하 고 프레임 또는 뷰의 자식 창으로 만듭니다. 프레임 워크 범위는 문서 프레임 창의 클라이언트 영역을 관리 하는 것을 염두에 두십시오. 대부분의 클라이언트 영역을 볼 수 있지만 다른 창에서 관리 하는, 예: 컨트롤 막대 또는 사용자 고유의 사용자 지정 windows와 공유할 수 있습니다는 공간 보기입니다. 클래스의 메커니즘와 상호 작용 해야 할 수 있습니다 [CView](../mfc/reference/cview-class.md) 및 [CControlBar](../mfc/reference/ccontrolbar-class.md) 프레임 창의 클라이언트 영역에서 자식 창의 위치를 지정 합니다.  
  
 [창 만들기](../mfc/creating-windows.md) 창 개체 및 관리 하는 windows의 생성에 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [창 개체](../mfc/window-objects.md)

