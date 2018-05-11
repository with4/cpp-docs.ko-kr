---
title: MFC 도구 모음 구현 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- toolbars [MFC], creating
- buttons [MFC], MFC toolbars
- toolbars [MFC], docking
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- floating toolbars [MFC]
- toolbars [MFC], floating
- docking toolbars [MFC]
- bitmaps [MFC], toolbar
- toolbar controls [MFC]
- CToolBarCtrl class [MFC], implementing toolbars
- tool tips [MFC], enabling
- toolbars [MFC]
- toolbars [MFC], implementing MFC toolbars
ms.assetid: af3319ad-c430-4f90-8361-e6a2c06fd084
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b0fd3a41d7574d627ebd374af170ce47801cd351
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-toolbar-implementation"></a>MFC 도구 모음 구현
도구 모음은입니다는 [컨트롤 막대](../mfc/control-bars.md) 컨트롤의 비트맵 이미지를 포함 하 합니다. 이러한 이미지는 누름 단추, 확인란 또는 라디오 단추 처럼 동작할 수 있습니다. MFC 클래스를 제공 [CToolbar](../mfc/reference/ctoolbar-class.md) 도구 모음을 관리할 수 있습니다.  
  
 사용 하면, MFC 도구 모음의 사용자가 창의 가장자리에 도킹 하거나 "이동" 응용 프로그램 창 안에 수 있습니다. MFC는 개발 환경에서와 같이 사용자 지정 가능한 도구 모음을 지원 하지 않습니다.  
  
 MFC에 도구 설명도 지원: 단추 위로 마우스를 배치할 때 도구 모음 단추의 용도 설명 하는 작은 팝업 창. 기본적으로 사용자가 도구 모음 단추를 누를 때 상태 문자열의 상태 표시줄에 나타납니다 (있는 경우). "즉석 에서" 상태에 누르지 않고 단추 위에 마우스를 놓을 때 상태 문자열을 표시 하도록 업데이트 표시줄을 활성화할 수 있습니다.  
  
> [!NOTE]
>  MFC 버전 4.0부터 도구 모음 및 도구 설명 구현 MFC에 특정 이전 구현 하는 대신 Windows 95 및 이상의 기능을 사용 하 여 합니다.  
  
 이전 버전과 호환성에 대 한 MFC 유지 클래스에서 이전 도구 모음 구현 **COldToolBar**합니다. 이전 버전의 MFC에 대 한 문서 설명 **COldToolBar** 아래 `CToolBar`합니다.  
  
 응용 프로그램 마법사에서 도구 모음 옵션을 선택 하 여 프로그램의 첫 번째 도구 모음을 만듭니다. 추가 도구 모음을 만들 수도 있습니다.  
  
 다음 사항이이 문서의 되었습니다.  
  
-   [도구 모음 단추](#_core_toolbar_buttons)  
  
-   [도킹 및 부동 도구 모음](#_core_docking_and_floating_toolbars)  
  
-   [도구 모음 및 도구 설명](#_core_toolbars_and_tool_tips)  
  
-   [CToolBar 및 CToolBarCtrl 클래스](#_core_the_ctoolbar_and_ctoolbarctrl_classes)  
  
-   [도구 모음 비트맵](#_core_the_toolbar_bitmap)  
  
##  <a name="_core_toolbar_buttons"></a> 도구 모음 단추  
 도구 모음에서 단추는 메뉴에서 항목과 유사 합니다. 두 종류의 사용자 인터페이스 개체 처리기 함수를 제공 하 여 프로그램을 처리 하는 명령을 생성 합니다. 도구 모음 단추 종종 동일한 기능에 대 한 대체 사용자 인터페이스를 제공 하는 메뉴 명령의 기능을 중복 되었습니다. 단추와 메뉴 항목에 같은 ID를 전달 하면 명령이 복제 됩니다.  
  
 도구 모음에서 단추 누름 단추, 확인란 또는 라디오 단추 기호로 표시 및 동작을 만들 수 있습니다. 자세한 내용은 클래스를 참조 하십시오. [CToolBar](../mfc/reference/ctoolbar-class.md)합니다.  
  
##  <a name="_core_docking_and_floating_toolbars"></a> 도킹 및 부동 도구 모음  
 MFC 도구 모음을 수행할 수 있습니다.  
  
-   부모 창의 한쪽 고정 되어 있습니다.  
  
-   놓 및 "고정" 또는 지정한 부모 창의 원하는 쪽에 사용자가 연결 합니다.  
  
-   "부동" 또는 사용자를 편리 하 게 어느 방향으로든 것으로 이동할 수 있도록 자체 미니 프레임 창에는 프레임 창에서 분리 되어야 합니다.  
  
-   부동 하는 동안 크기를 조정할 수 있습니다.  
  
 자세한 내용은 문서 참조 [도킹 및 부동 도구 모음](../mfc/docking-and-floating-toolbars.md)합니다.  
  
##  <a name="_core_toolbars_and_tool_tips"></a> 도구 모음 및 도구 설명  
 MFC 도구 모음 표시 "도구 설명"을 만들 수도 있습니다-도구 모음 단추의 용도에 대 한 간단한 텍스트 설명을 포함 하는 작은 팝업 창. 도구 모음 단추 위로 마우스를 이동할 때 도구 설명 창이 힌트를 제공 하 여 표시 합니다. 자세한 내용은 문서 참조 [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md)합니다.  
  
##  <a name="_core_the_ctoolbar_and_ctoolbarctrl_classes"></a> CToolBar 및 CToolBarCtrl 클래스  
 클래스를 통해 응용 프로그램의 도구 모음을 관리할 [CToolBar](../mfc/reference/ctoolbar-class.md)합니다. MFC 버전 4.0 기준으로 `CToolBar` 이상 Windows 95에서 사용할 수 도구 모음 공용 컨트롤 및 Windows NT 버전 3.51 이상 사용 하 여 구현 합니다.  
  
 MFC를 사용 하기 때문에이 다시 구현 밖에 도구 모음, 더 적은 MFC 코드에는 운영 체제 지원의 사용 합니다. 다시 구현에는 기능이 향상 됩니다. 사용할 수 있습니다 `CToolBar` 도구 모음 또는 있습니다를 조작 하는 멤버 함수는 기본에 대 한 참조를 가져올 수 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 개체와 도구 모음 사용자 지정 및 추가 기능에 대 한 멤버의 멤버 함수를 호출 합니다.  
  
> [!TIP]
>  경우 하면 과도 하 게에 투자의 이전 버전의 MFC 구현 `CToolBar`, 지지도 계속 사용할 수입니다. 문서 참조 [이전 도구 모음 사용 하 여](../mfc/using-your-old-toolbars.md)합니다.  
  
 MFC 일반 샘플도 참조 [DOCKTOOL](../visual-cpp-samples.md)합니다.  
  
##  <a name="_core_the_toolbar_bitmap"></a> 도구 모음 비트맵  
 한 번 생성 한 `CToolBar` 개체 각 단추에 대 한 이미지가 포함 된 단일 비트맵을 로드 하 여 도구 모음 이미지를 만듭니다. 응용 프로그램 마법사는 Visual c + + 사용자 지정할 수 있는 표준 도구 모음 비트맵을 만듭니다 [도구 모음 편집기](../windows/toolbar-editor.md)합니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
  
-   [도구 모음 기본 사항](../mfc/toolbar-fundamentals.md)  
  
-   [도킹 및 부동 도구 모음](../mfc/docking-and-floating-toolbars.md)  
  
-   [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md)  
  
-   [ToolBar 컨트롤 사용](../mfc/working-with-the-toolbar-control.md)  
  
-   [이전 도구 모음 사용](../mfc/using-your-old-toolbars.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md) 및 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 클래스  
  
## <a name="see-also"></a>참고 항목  
 [도구 모음](../mfc/toolbars.md)   
 [도구 모음 편집기](../windows/toolbar-editor.md)

