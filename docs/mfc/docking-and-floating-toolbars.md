---
title: "도킹 및 부동 도구 모음 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CBRS_SIZE_DYNAMIC
- CBRS_SIZE_FIXED
dev_langs:
- C++
helpviewer_keywords:
- size [MFC], toolbars
- size
- frame windows [MFC], toolbar docking
- CBRS_ALIGN_ANY constant [MFC]
- palettes, floating
- toolbars [MFC], docking
- CBRS_SIZE_DYNAMIC constant [MFC]
- floating toolbars
- toolbars [MFC], size
- toolbars [MFC], floating
- fixed-size toolbars
- CBRS_SIZE_FIXED constant [MFC]
- toolbar controls [MFC], wrapping
- toolbars [MFC], wrapping
- floating palettes
ms.assetid: b7f9f9d4-f629-47d2-a3c4-2b33fa6b51e4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d6646fa33c0a78e8194faa5d511e107febca6d6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="docking-and-floating-toolbars"></a>도구 모음 고정 및 고정 해제
Microsoft Foundation Class 라이브러리는 도킹 가능한 도구 모음을 지원합니다. 도킹 가능한 도구 모음 연결 하거나 모든 면 해당 부모 창에 도킹할 수 또는 분리 하거나 자체 미니 프레임 창에서 이동할 수 있습니다. 이 문서에서는 응용 프로그램에서 도킹 가능한 도구 모음을 사용 하는 방법에 설명 합니다.  
  
 응용 프로그램의 기본 구조를 생성 하는 응용 프로그램 마법사를 사용 하 여 도킹 가능한 도구 모음을 선택 하 라는 메시지가 표시 됩니다. 기본적으로 응용 프로그램 마법사에서는 응용 프로그램에서 도킹 가능한 도구 모음을 배치 하는 데 필요한 세 가지 작업을 수행 하는 코드를 생성 합니다.  
  
-   [프레임 창에서 도킹 기능을 활성화](#_core_enabling_docking_in_a_frame_window)합니다.  
  
-   [도킹 도구 모음에 대 한 기능을 활성화](#_core_enabling_docking_for_a_toolbar)합니다.  
  
-   [(프레임 창)에 도구 모음을 도킹](#_core_docking_the_toolbar)합니다.  
  
 다음이 단계 중 하나라도 없으면 응용 프로그램에 표준 도구 모음이 표시 됩니다. 응용 프로그램에서 각 도킹 가능한 도구 모음에 대 한 마지막 두 단계를 수행 해야 합니다.  
  
 이 문서에서 다루는 다른 항목은 다음과 같습니다.  
  
-   [부동 도구 모음](#_core_floating_the_toolbar)  
  
-   [동적으로 도구 모음을 크기 조정](#_core_dynamically_resizing_the_toolbar)  
  
-   [고정 스타일 도구 모음에 대 한 줄 바꿈 위치 설정](#_core_setting_wrap_positions_for_a_fixed_style_toolbar)  
  
 MFC 일반 샘플 [DOCKTOOL](../visual-cpp-samples.md) 예입니다.  
  
##  <a name="_core_enabling_docking_in_a_frame_window"></a>프레임 창에서 도킹 활성화  
 프레임 창에 도구 모음을 고정 하려면 프레임 창 (또는 대상) 도킹을 허용 하도록 활성화 되어야 합니다. 이렇게 사용 하 여는 [CFrameWnd::EnableDocking](../mfc/reference/cframewnd-class.md#enabledocking) 하나를 사용 하는 함수를 `DWORD` 스타일의 집합이 매개 변수에서는 도킹 프레임 창 중 어느 쪽을 허용할 나타내는 비트입니다. 도구 모음을 도킹할 수 되려고 하 고 여러 측면에 도킹 될 수 있는 인에서 지정 된 측면은 전달 된 매개 변수가 `EnableDocking` 다음과 같은 순서로 사용: 위쪽, 아래쪽, 왼쪽, 오른쪽입니다. 도킹 컨트롤 막대를 모든, 전달할 수 있게 되기를 원하는 경우 `CBRS_ALIGN_ANY` 를 `EnableDocking`합니다.  
  
##  <a name="_core_enabling_docking_for_a_toolbar"></a>도킹 도구 모음에 대 한 활성화  
 도킹 대상의 준비 하는 다음 유사한 방식으로 도구 모음 (또는 원본)를 준비 해야 합니다. 호출 [CControlBar::EnableDocking](../mfc/reference/ccontrolbar-class.md#enabledocking) 도킹 하려면 각 도구 모음에 대 한 도구 모음 도킹 해야를 면 대상 지정 합니다. 에 대 한 호출에 지정 된 면 없으면 `CControlBar::EnableDocking` 프레임 창에서 도킹 가능한 면 일치 하며, 도구 모음 도킹 수 없습니다-이동 수 있습니다. 된 면 부동 도구 모음, 프레임 창으로 도킹 될 수 없습니다 유지 됩니다.  
  
 원하는 효과 영구적으로 부동 도구 모음 이면 호출 `EnableDocking` 0 매개 변수를 사용 합니다. 그런 다음 호출 [CFrameWnd::FloatControlBar](../mfc/reference/cframewnd-class.md#floatcontrolbar)합니다. 도구 모음에는 부동, 도킹 될 수 없습니다 영구적으로 유지 됩니다.  
  
##  <a name="_core_docking_the_toolbar"></a>도구 모음 도킹  
 프레임 워크를 호출 하 여 [CFrameWnd::DockControlBar](../mfc/reference/cframewnd-class.md#dockcontrolbar) 사용자가 도킹 수 있는 프레임 창의 가장자리에 도구 모음을 삭제 하려고 할 때입니다.  
  
 또한 언제 든 지 컨트롤 막대 프레임 창에 고정 합니다.이 함수를 호출할 수 있습니다. 이 초기화 하는 동안 정상적으로 수행 됩니다. 프레임 창의 특정 측면에 둘 이상의 도구 모음을 도킹할 수 있는 합니다.  
  
##  <a name="_core_floating_the_toolbar"></a>부동 도구 모음  
 프레임 창에서 도킹 가능한 도구 모음을 분리 부동 도구 모음에서 호출 됩니다. 호출 [CFrameWnd::FloatControlBar](../mfc/reference/cframewnd-class.md#floatcontrolbar) 에이 작업을 수행 합니다. 도구 모음의 놓을지, 것를 배치할 위치, 지점 및 부동 도구 모음이 가로 또는 세로 인지를 확인 하는 맞춤 스타일을 지정 합니다.  
  
 프레임 워크는 사용자가을 도구 모음 도킹 해제 끌 도킹 해제 되어 없는 위치에 놓습니다 하는 경우이 함수를 호출 합니다. 프레임 창 외부 아무 곳 이나 수 있습니다. 와 마찬가지로 `DockControlBar`을 초기화 하는 동안이 함수를 호출할 수도 있습니다.  
  
 도킹 가능한 도구 모음의 MFC 구현 도킹 가능한 도구 모음을 지원 되는 일부 응용 프로그램에 있는 확장 된 기능 중 일부를 제공 하지 않습니다. 사용자 지정 가능한 도구 모음 같은 기능을 제공 되지 않습니다.  
  
##  <a name="_core_dynamically_resizing_the_toolbar"></a>동적으로 도구 모음을 크기 조정  
 Visual c + + 버전 4.0부터 만들 수 있습니다 수 동적으로 부동 도구 모음을 크기 조정 하도록 응용 프로그램의 사용자에 대 한 합니다. 일반적으로 도구 모음에 가로로 표시 되 긴 막대 모양입니다. 하지만 도구 모음의 방향 및 모양을 변경할 수 있습니다. 예를 들어 사용자 도킹 프레임 창의 세로 측면 중 하나에 대 한 도구 모음, 셰이프 세로 레이아웃으로 변경 됩니다. 도구 모음 단추 행이 여러 개 있는 사각형으로 모양을 변경도 가능 합니다.  
  
 다음과 같은 작업을 수행할 수 있습니다.  
  
-   동적 크기 조정 도구 모음 특징으로 지정 합니다.  
  
-   도구 모음 특징으로 고정된 크기 조정을 지정 합니다.  
  
 이 지원 하기는 두 가지 새 도구 모음 스타일에 대 한 호출에서 사용 하기 위해는 [CToolBar::Create](../mfc/reference/ctoolbar-class.md#create) 멤버 함수입니다. 다음 창이 여기에 포함됩니다.  
  
-   **CBRS_SIZE_DYNAMIC** 동적 컨트롤 막대입니다.  
  
-   **CBRS_SIZE_FIXED** 컨트롤 막대 고정 됩니다.  
  
 동적 크기 스타일을 사용 하면, 부동 하는 동안 하지만 하지 도킹 하는 동안 도구 모음에서 크기를 조정 합니다. 도구 모음에서 "래핑" 가장자리를 끌 때 모양을 변경 해야 하는 경우.  
  
 고정 크기 스타일에는 각 열에 있는 단추 위치를 수정 하는 도구 모음, 줄 바꿈 상태가 유지 합니다. 응용 프로그램의 사용자는 도구 모음의 모양을 변경할 수 없습니다. 도구 모음에서 단추 사이의 구분선의 위치와 같은 지정 된 위치에서 래핑합니다. 도구 모음 도킹 됨 또는 부동 소수점 인지이 모양을 유지 합니다. 단추의 여러 열을 고정된 색상표 같습니다.  
  
 사용할 수도 있습니다 [CToolBar::GetButtonStyle](../mfc/reference/ctoolbar-class.md#getbuttonstyle) 도구 모음에 상태 및 단추에 대 한 스타일을 반환 하려면. 단추의 스타일 단추가 표시 되는 방식 및 사용자 입력;에 응답 하기를 결정 합니다. 상태 래핑된에서 단추 인지 여부를 알려 줍니다.  
  
##  <a name="_core_setting_wrap_positions_for_a_fixed_style_toolbar"></a>고정 스타일 도구 모음에 대 한 줄 바꿈 위치 설정  
 스타일 고정 크기 도구 모음에 대 한 도구 모음 단추 인덱스는 도구 모음이 다른 줄을 지정 합니다. 다음 코드에서는 주 프레임 창에서이 작업을 수행 하는 방법을 보여 줍니다. `OnCreate` 재정의:  
  
 [!code-cpp[NVC_MFCDocViewSDI#10](../mfc/codesnippet/cpp/docking-and-floating-toolbars_1.cpp)]  
  
 MFC 일반 샘플 [DOCKTOOL](../visual-cpp-samples.md) 클래스의 멤버 함수를 사용 하는 방법을 보여 줍니다. [CControlBar](../mfc/reference/ccontrolbar-class.md) 및 [CToolBar](../mfc/reference/ctoolbar-class.md) 동적 레이아웃 도구 모음을 관리할 수 있습니다. EDITBAR 파일을 참조 하십시오. CPP 파일을 참조 합니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [도구 모음 기본 사항](../mfc/toolbar-fundamentals.md)  
  
-   [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md)  
  
-   [이전 도구 모음을 사용 하 여](../mfc/using-your-old-toolbars.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC 도구 모음 구현](../mfc/mfc-toolbar-implementation.md)

