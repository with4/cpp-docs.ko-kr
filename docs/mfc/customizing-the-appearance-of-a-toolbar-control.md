---
title: 도구 모음 컨트롤의 모양 사용자 지정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TBSTYLE_
dev_langs:
- C++
helpviewer_keywords:
- flat toolbars
- CToolBar class [MFC], styles
- transparent toolbars
- TBSTYLE_ styles [MFC]
- CToolBarCtrl class [MFC], object styles
- toolbar controls [MFC], style
ms.assetid: fd0a73db-7ad1-4fe4-889b-02c3980f49e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 96ec459e1c956c805991f2e37d22b8260f0ffdf2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343696"
---
# <a name="customizing-the-appearance-of-a-toolbar-control"></a>도구 모음 컨트롤의 모양 사용자 지정
클래스 `CToolBarCtrl` 모양을 (및 경우에 따라서는 동작)의 도구 모음 개체에 영향을 주는 많은 스타일을 제공 합니다. 도구 모음 개체를 설정 하 여 수정는 `dwCtrlStyle` 의 매개 변수는 `CToolBarCtrl::Create` (또는 `CToolBar::CreateEx`) 도구 모음 컨트롤을 처음 만들 때 멤버 함수입니다.  
  
 다음과 같은 스타일 도구 모음 단추 "3D" 모양 및 단추 텍스트의 배치에 영향을 줍니다.  
  
-   **TBSTYLE_FLAT** 도구 모음 및 단추 모두 투명 하 게 있는 플랫 도구 모음을 만듭니다. 단추 텍스트 단추 비트맵 아래에 나타납니다. 이 스타일은 사용 커서 아래에 있는 단추는 자동으로 강조 표시 됩니다.  
  
-   **TBSTYLE_TRANSPARENT** 투명 한 도구 모음을 만듭니다. 투명 한 도구 모음에서 도구 모음을 투명 하 게 되지만 단추는 되지 않습니다. 단추 텍스트 단추 비트맵 아래에 나타납니다.  
  
-   **TBSTYLE_LIST** 장소 단추 단추 비트맵의 오른쪽에는 텍스트입니다.  
  
> [!NOTE]
>  다시 그리기 문제를 방지 하려면는 **TBSTYLE_FLAT** 및 **TBSTYLE_TRANSPARENT** 스타일 도구 모음 개체를 표시 하기 전에 설정 해야 합니다.  
  
 다음과 같은 스타일 도구 모음을 끌어서를 사용 하 여 도구 모음 개체 내에서 개별 단추 위치를 변경 및 삭제할 사용자 있습니다를 결정 합니다.  
  
-   **TBSTYLE_ALTDRAG** alt 키를 누른 상태로 끌거나 도구 모음 단추의 위치를 변경할 수 있습니다. 이 스타일을 지정 하지 않으면 사용자는 키를 누른 채 단추 끌기를 유효 해야 합니다.  
  
    > [!NOTE]
    >  `CCS_ADJUSTABLE` 스타일 도구 모음 단추를 끌어다 놓을 수 있도록 지정 해야 합니다.  
  
-   **TBSTYLE_REGISTERDROP** 생성 **TBN_GETOBJECT** 알림 메시지를 요청 하려면 도구 모음 단추 위로 마우스 포인터를 이동할 때 대상 개체를 삭제 합니다.  
  
 나머지 스타일 도구 모음 개체의 시각적 및 표시 되지 않는 측면을 영향을 줍니다.  
  
-   `TBSTYLE_WRAPABLE` 여러 줄의 단추를 가질 수 있는 도구 모음을 만듭니다. 도구 모음 단추 "바꿈하여" 다음 줄으로 도구 모음 같은 줄에서 모든 단추를 포함 하는 범위가 너무 좁으면 해지면 합니다. 분리 및 바꿈은 경계에서 발생 합니다.  
  
-   **TBSTYLE_CUSTOMERASE** 생성 **NM_CUSTOMDRAW** 알림 메시지를 처리할 때 `WM_ERASEBKGND` 메시지입니다.  
  
-   `TBSTYLE_TOOLTIPS` 응용 프로그램 도구 모음에서 단추에 대 한 설명 텍스트를 표시 하는 데 사용할 수 있는 도구 설명 컨트롤을 만듭니다.  
  
 도구 모음 스타일과 확장 된 스타일의 전체 목록을 보려면 [도구 모음 컨트롤과 단추 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760439) 및 [확장 스타일 도구 모음](http://msdn.microsoft.com/library/windows/desktop/bb760430) Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

