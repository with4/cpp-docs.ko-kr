---
title: "컨트롤 막대 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.control
dev_langs:
- C++
helpviewer_keywords:
- control bars [MFC], classes
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 44fcecbf1d7ddb6c46469f25349d972c8b317809
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="control-bar-classes"></a>컨트롤 막대 클래스
컨트롤 막대 프레임 창에 연결 됩니다. 단추, 상태 창 또는 대화 상자 템플릿을 포함 합니다. 자유 부동 컨트롤 막대, 라고도 함 도구 팔레트에 연결 하 여 구현 됩니다는 [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md) 개체입니다.  
  
## <a name="framework-control-bars"></a>프레임 워크 컨트롤 막대  
 이러한 컨트롤 막대는 MFC 프레임 워크의 필수적인 부분입니다. 사용 하기 쉽게 프레임 워크와 통합 되어 있으므로 Windows 컨트롤 막대 보다 더 강력 합니다. 대부분의 MFC 응용 프로그램 Windows 컨트롤 막대 보다는 이러한 컨트롤 막대를 사용합니다.  
  
 [CControlBar](../mfc/reference/ccontrolbar-class.md)  
 이 섹션에 나열 된 MFC 컨트롤 막대에 대 한 기본 클래스입니다. 컨트롤 막대는 창 프레임 창의 가장자리에 따라 정렬 합니다. 컨트롤 막대를 포함 하거나 `HWND`-기반 자식 컨트롤 또는 컨트롤에 기반을 두지는 `HWND`, 도구 모음 단추와 같이 합니다.  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 대화 상자 템플릿을 기반으로 하는 컨트롤 막대입니다.  
  
 [CReBar](../mfc/reference/crebar-class.md)  
 컨트롤 형식으로 추가 자식 창을 포함할 수 있는 도구 모음을 지원 합니다.  
  
 [CToolBar](../mfc/reference/ctoolbar-class.md)  
 하지 비트맵 명령 단추를 포함 하는 도구 모음 컨트롤 창 기반으로 한 `HWND`합니다. 이 클래스를 사용 하는 대부분의 MFC 응용 프로그램 보다는 `CToolBarCtrl`합니다.  
  
 [CStatusBar](../mfc/reference/cstatusbar-class.md)  
 상태 표시줄 컨트롤 창에 대 한 기본 클래스입니다. 이 클래스를 사용 하는 대부분의 MFC 응용 프로그램 보다는 `CStatusBarCtrl`합니다.  
  
## <a name="windows-control-bars"></a>Windows 컨트롤 막대  
 이러한 컨트롤 막대에 해당 하는 Windows 컨트롤에 대 한 씬 래퍼는입니다. 되기 때문에 프레임 워크와 통합 되지 않은, 더 어려워지므로 앞에 나열 된 컨트롤 막대 보다 사용 합니다. 대부분의 MFC 응용 프로그램 앞에 나열 된 컨트롤 막대를 사용 합니다.  
  
 [CRebarCtrl](../mfc/reference/crebarctrl-class.md)  
 내부 제어를 구현 하는 `CRebar` 개체입니다.  
  
 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
 가로 창 일반적으로 응용 프로그램 상태 정보를 표시할 수 있는 창으로 구분 합니다.  
  
 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
 Windows의 도구 모음 공용 컨트롤의 기능을 제공합니다.  
  
## <a name="related-classes"></a>관련된 클래스  
 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)  
 응용 프로그램 도구의 용도 설명 하는 텍스트 한 줄을 표시 하는 작은 팝업 창입니다.  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 도킹 컨트롤 막대에 대 한 상태 데이터의 영구 저장소를 처리 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

