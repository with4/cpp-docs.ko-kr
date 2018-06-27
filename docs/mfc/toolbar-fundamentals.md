---
title: 도구 모음 기본 사항 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- RT_TOOLBAR
dev_langs:
- C++
helpviewer_keywords:
- embedding toolbar in frame window class [MFC]
- application wizards [MFC], installing default application toolbars
- toolbars [MFC], creating
- resources [MFC], toolbar
- toolbar controls [MFC], toolbars created using Application Wizard
- toolbar controls [MFC], command ID
- RT_TOOLBAR resource [MFC]
- toolbars [MFC], adding default using Application Wizard
- LoadBitmap method [MFC], toolbars
- Toolbar editor [MFC], Application Wizard
- command IDs [MFC], toolbar buttons
- SetButtons method [MFC]
- CToolBar class [MFC], default toolbars in Application Wizard
- frame window classes [MFC], toolbar embedded in
- LoadToolBar method [MFC]
ms.assetid: cc00aaff-8a56-433b-b0c0-b857d76b4ffd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5240cf50b35b2e1a300071ccb6cc15a065ac364e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951639"
---
# <a name="toolbar-fundamentals"></a>도구 모음 기본 사항
이 문서에서는 응용 프로그램 마법사에서 옵션을 선택 하 여 응용 프로그램에 기본 도구 모음을 추가할 수 있는 기본 MFC 구현을 설명 합니다. 다루는 항목은 다음과 같습니다.  
  
-   [응용 프로그램 마법사 도구 모음 옵션](#_core_the_appwizard_toolbar_option)  
  
-   [코드에서 도구 모음](#_core_the_toolbar_in_code)  
  
-   [도구 모음 리소스 편집](#_core_editing_the_toolbar_resource)  
  
-   [여러 도구 모음](#_core_multiple_toolbars)  
  
##  <a name="_core_the_appwizard_toolbar_option"></a> 응용 프로그램 마법사 도구 모음 옵션  
 기본 단추가 포함 된 단일 도구 모음을 가져오려면 사용자 인터페이스 기능 페이지에서 표준 도킹 도구 모음 옵션을 선택 합니다. 그러면 응용 프로그램에 코드를 추가 하는:  
  
-   도구 모음 개체를 만듭니다.  
  
-   도킹 또는 고정 해제 하는 기능을 포함 하 여 도구 모음을 관리 합니다.  
  
##  <a name="_core_the_toolbar_in_code"></a> 코드에서 도구 모음  
 도구 모음을 한 [CToolBar](../mfc/reference/ctoolbar-class.md) 개체가 응용 프로그램의 데이터 멤버로 선언 `CMainFrame` 클래스입니다. 즉, 도구 모음 개체 주 프레임 창 개체에 포함 됩니다. 즉, 프레임 창을 만들고 프레임 창을 제거 하는 경우 도구 모음을 삭제 하는 경우 MFC 도구 모음을 만듭니다. 여러 문서 MDI (인터페이스) 응용 프로그램의 경우 다음의 partial 클래스 선언 포함된 된 도구 모음 및 포함 된 상태 표시줄에 대 한 데이터 멤버를 보여 줍니다. 또한 재정의 표시는 `OnCreate` 멤버 함수입니다.  
  
 [!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]  
  
 도구 모음 만들기가 수행 `CMainFrame::OnCreate`합니다. MFC 호출 [OnCreate](../mfc/reference/cwnd-class.md#oncreate) 창 프레임에 대 한 하지만 표시 되기 전에 만든 후 합니다. 기본 `OnCreate` 다음 도구 모음 작업을 수행 하는 응용 프로그램 마법사가 생성 하 합니다.  
  
1.  호출 된 `CToolBar` 개체의 [만들기](../mfc/reference/ctoolbar-class.md#create) 멤버 함수를 만드는 기본 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 개체입니다.  
  
2.  호출 [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) 도구 모음 리소스 정보를 로드 합니다.  
  
3.  도킹, 부동 및 도구 설명을 활성화 하는 함수를 호출 합니다. 이 함수를이 호출 하는 방법에 대 한 자세한 문서를 참조 [도킹 및 부동 도구 모음](../mfc/docking-and-floating-toolbars.md)합니다.  
  
> [!NOTE]
>  MFC 일반 샘플 [DOCKTOOL](../visual-cpp-samples.md) 일러스트레이션와 새 MFC 도구 모음을 포함 합니다. 사용 하는 도구 모음 `COldToolbar` 2 단계에서 호출이 필요 `LoadBitmap` (대신 `LoadToolBar`) 및 `SetButtons`합니다. 새 도구 모음에 대 한 호출을 필요한 `LoadToolBar`합니다.  
  
 도킹, 부동 및 도구 설명 호출은 선택적입니다. 해당 행을 제거할 수 있습니다 `OnCreate` 하려는 경우. 고정 하거나 다시 도킹할 수 없습니다 및 도구 설명을 표시할 수 없습니다 상태를 유지 하는 도구 모음이 만들어집니다.  
  
##  <a name="_core_editing_the_toolbar_resource"></a> 도구 모음 리소스 편집  
 기반 응용 프로그램 마법사로 가져오는 기본 도구는 **RT_TOOLBAR** MFC 버전 4.0에서에서 도입 하는 사용자 지정 리소스입니다. 로이 리소스를 편집할 수는 [도구 모음 편집기](../windows/toolbar-editor.md)합니다. 편집기를 사용 하면 쉽게 추가, 삭제 및 단추를 다시 정렬할 수 있습니다. Visual c + +에서 일반 그래픽 편집기와 매우 비슷한 단추에 대 한 그래픽 편집기를 포함 합니다. 이전 버전의 Visual c + + 도구 모음을 편집한 경우 있습니다 작업이 훨씬 더 쉽게 이제 합니다.  
  
 도구 모음 단추를 명령에 연결 하려면 하면 단추 명령 ID와 같은 `ID_MYCOMMAND`합니다. 속성 페이지의 도구 모음 편집기에서 단추의 명령 ID를 지정 합니다. 그런 다음 명령에 대 한 처리기 함수를 만듭니다 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md) 자세한 정보에 대 한).  
  
 새 [CToolBar](../mfc/reference/ctoolbar-class.md) 멤버 함수를 사용할는 **RT_TOOLBAR** 리소스입니다. [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) 대신 더 길어진 [LoadBitmap](../mfc/reference/ctoolbar-class.md#loadbitmap) 도구 모음 단추 이미지의 비트맵을 로드 하 고 [SetButtons](../mfc/reference/ctoolbar-class.md#setbuttons) 단추 스타일을 설정 하 고 단추 비트맵 이미지를 사용 하 여 연결을 합니다.  
  
 도구 모음 편집기를 사용 하는 방법에 대 한 세부 정보를 참조 하십시오. [도구 모음 편집기](../windows/toolbar-editor.md)합니다.  
  
##  <a name="_core_multiple_toolbars"></a> 여러 도구 모음  
 응용 프로그램 마법사 하나의 기본 도구 모음을 제공합니다. 응용 프로그램에 둘 이상의 도구 모음을 필요한 경우에 기본 도구 모음에 대 한 마법사에서 생성 된 코드에 따라 추가 도구 모음에 대 한 코드를 모델링할 수 있습니다.  
  
 명령의 결과로 도구 모음을 표시 하려는 경우 해야 합니다.  
  
-   새 도구 모음 리소스 도구 모음 편집기 만들고 로드에서 `OnCreate` 와 [LoadToolbar](../mfc/reference/ctoolbar-class.md#loadtoolbar) 멤버 함수입니다.  
  
-   새 포함 [CToolBar](../mfc/reference/ctoolbar-class.md) 주 프레임 창 클래스에는 개체입니다.  
  
-   적절 한 함수를 호출 하는 확인 `OnCreate` 를 도킹 하거나 부동 도구 모음의 스타일을 설정 합니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
  
-   [MFC 도구 모음 구현 (도구 모음에 대 한 개요 정보)](../mfc/mfc-toolbar-implementation.md)  
  
-   [도킹 및 부동 도구 모음](../mfc/docking-and-floating-toolbars.md)  
  
-   [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md) 및 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 클래스  
  
-   [도구 모음 컨트롤](../mfc/working-with-the-toolbar-control.md)  
  
-   [이전 도구 모음을 사용 하 여](../mfc/using-your-old-toolbars.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC 도구 모음 구현](../mfc/mfc-toolbar-implementation.md)

