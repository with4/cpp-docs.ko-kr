---
title: "도구 모음 도구 설명 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], activating
- CBRS_TOOLTIPS constant [MFC]
- tool tips [MFC], adding text
- updates [MFC]
- CBRS_FLYBY constant [MFC]
- tool tips [MFC]
- updating status bar messages
- updates, status bar messages
- status bars [MFC], tool tips
- flyby status bar updates
ms.assetid: d1696305-b604-4fad-9f09-638878371412
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 248c975c51a2f44f6c9b17094d6b05082a9016a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="toolbar-tool-tips"></a>도구 모음 도구 설명
도구 설명은 일정 시간 동안에 대 한 단추 위로 마우스를 배치할 때 도구 모음 단추의 용도에 대해 간략히 설명을 제공 하는 작은 팝업 창. 도구 모음에 있는 응용 프로그램 마법사로 응용 프로그램을 만들 때 도구 설명 지원 하기 위해 제공 됩니다. 이 문서는 모두 도구 설명 지원을 응용 프로그램에 도구 설명 지원을 추가 하는 방법 및 응용 프로그램 마법사에서 만든를 설명 합니다.  
  
 이 문서에서는 다룹니다.  
  
-   [도구 설명 활성화](#_core_activating_tool_tips)  
  
-   [Flyby 상태 표시줄 업데이트](#_core_fly_by_status_bar_updates)  
  
##  <a name="_core_activating_tool_tips"></a>도구 설명 활성화  
 응용 프로그램에서 도구 설명을 활성화 하려면 다음 두 가지를 수행 해야 합니다.  
  
-   추가 `CBRS_TOOLTIPS` 다른 스타일을 스타일 (같은 **WS_CHILD**, **WS_VISIBLE**, 및 기타 **CBRS_** 스타일) 변수로 전달 되는 `dwStyle` 매개 변수는 를[ CToolBar::Create](../mfc/reference/ctoolbar-class.md#create) 함수 또는 [SetBarStyle](../mfc/reference/ccontrolbar-class.md#setbarstyle)합니다.  
  
-   아래 절차에 따라, 도구 모음 명령에 대 한 명령줄 프롬프트를 포함 하는 문자열 리소스를 줄 바꿈 문자 ('\n') 구분 된 도구 설명 텍스트를 추가 합니다. 도구 모음 단추의 ID를 공유 하는 문자열 리소스.  
  
#### <a name="to-add-the-tool-tip-text"></a>도구 설명 텍스트를 추가 하려면  
  
1.  도구 모음 편집기에서 도구 모음을 편집 하는 동안 열은 **도구 모음 단추 속성** 지정된 단추에 대 한 창.  
  
2.  에 **프롬프트** 상자 해당 단추의 도구 설명에 표시할 텍스트를 지정 합니다.  
  
> [!NOTE]
>  문자열 리소스를 편집를 열고 도구 모음 편집기에서 단추 속성에 해야 했던 이전 프로시저를 대체 하는 대로 텍스트를 설정 합니다.  
  
 도구 설명이 활성화 컨트롤 막대에 배치 된 자식 컨트롤을 다음 조건을 충족으로 컨트롤 막대 컨트롤 막대에 있는 모든 자식 컨트롤에 대 한 도구 설명을 표시 합니다.  
  
-   컨트롤의 ID는 1-되지 않습니다.  
  
-   리소스 파일의 자식 컨트롤로 동일한 ID 가진 문자열 테이블 항목에 도구 설명 문자열이 있습니다.  
  
##  <a name="_core_fly_by_status_bar_updates"></a>Flyby 상태 표시줄 업데이트  
 도구 설명에 관련 된 기능은 "flyby" 상태 표시줄 업데이트입니다. 기본적으로 상태 표시줄에 메시지가 단추가 활성화 될 때만 특정 도구 모음 단추를 설명 합니다. 포함 하 여 `CBRS_FLYBY` 스타일에 전달 된 프로그램 목록에서 `CToolBar::Create`, 업데이트 실제로 단추를 활성화 하지 않고 도구 모음 위로 마우스 커서를 이동할 때 이러한 메시지를 포함할 수 있습니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [MFC 도구 모음 구현 (도구 모음에 대 한 개요 정보)](../mfc/mfc-toolbar-implementation.md)  
  
-   [도킹 및 부동 도구 모음](../mfc/docking-and-floating-toolbars.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md) 및 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 클래스  
  
-   [도구 모음 컨트롤](../mfc/working-with-the-toolbar-control.md)  
  
-   [이전 도구 모음을 사용 하 여](../mfc/using-your-old-toolbars.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC 도구 모음 구현](../mfc/mfc-toolbar-implementation.md)

