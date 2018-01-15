---
title: "연습: 도구 모음에 컨트롤 배치 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f991f8ebf87535de09dc7c3dce5e0f4ca2ee457b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>연습: 도구 모음에 컨트롤 배치
이 항목에서는 Windows 컨트롤을 포함하는 도구 모음 단추를 도구 모음에 추가하는 방법을 설명합니다. MFC 도구 모음 단추 이어야 합니다는 [CMFCToolBarButton 클래스](../mfc/reference/cmfctoolbarbutton-class.md)-예를 들어 파생 클래스를 [CMFCToolBarComboBoxButton 클래스](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), [CMFCToolBarEditBoxButton 클래스](../mfc/reference/cmfctoolbareditboxbutton-class.md), [CMFCDropDownToolbarButton 클래스](../mfc/reference/cmfcdropdowntoolbarbutton-class.md), 또는 [CMFCToolBarMenuButton 클래스](../mfc/reference/cmfctoolbarmenubutton-class.md)합니다.  
  
## <a name="adding-controls-to-toolbars"></a>도구 모음에 컨트롤 추가  
 도구 모음에 컨트롤을 추가 하려면 다음 단계를 따르십시오.  
  
1.  부모 도구 모음 리소스의 단추에 대한 더미 리소스 ID를 예약합니다. Visual Studio의 도구 모음 편집기를 사용 하 여 단추를 만드는 방법에 대 한 자세한 내용은 참조는 [도구 모음 편집기](../windows/toolbar-editor.md) 항목입니다.  
  
2.  부모 도구 모음에서 모든 비트맵의 단추에 대한 도구 모음 이미지(단추 아이콘)를 예약합니다.  
  
3.  `AFX_WM_RESETTOOLBAR` 메시지를 처리하는 메시지 처리기에서 다음을 수행합니다.  
  
    1.  `CMFCToolbarButton` 파생 클래스를 사용하여 단추 컨트롤을 생성합니다.  
  
    2.  더미 단추를 사용 하 여 새 컨트롤으로 바꾸기 [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton)합니다. `ReplaceButton`은 단추 개체를 복사하고 복사본을 유지하므로 스택에서 단추 개체를 생성할 수 있습니다.  
  
> [!NOTE]
>  사용 하 여 도구 모음을 다시 설정 해야 응용 프로그램에서 사용자 지정을 사용 하는 경우는 **재설정** 단추는 **도구 모음** 탭은 **사용자 지정** 보려면 대화 상자를는 다시 컴파일한 후 응용 프로그램에서 컨트롤을 업데이트 합니다. 도구 모음 상태는 Windows 레지스트리에 저장되며 레지스트리 정보는 응용 프로그램이 시작하는 동안 `ReplaceButton` 메서드가 실행된 후 로드됩니다.  
  
## <a name="toolbar-controls-and-customization"></a>도구 모음 컨트롤 및 사용자 지정  
 **명령을** 탭은 **사용자 지정** 대화 상자에 응용 프로그램에서 사용할 수 있는 명령 목록이 포함 되어 있습니다. 기본적으로는 **사용자 지정** 대화 상자는 응용 프로그램 메뉴를 처리 하 고 각 메뉴 범주의 표준 도구 모음 단추의 목록을 작성 합니다. 도구 모음 컨트롤에서 제공 하는 확장된 된 기능을 유지 하려면 표준 도구 모음 단추를 바꿔야 사용자 지정 컨트롤에는 **사용자 지정** 대화 상자.  
  
 만드는 사용자 지정을 사용 하도록 설정 하면는 **사용자 지정** 대화 상자 사용자 지정 처리기에서 `OnViewCustomize` 를 사용 하 여는 [CMFCToolBarsCustomizeDialog 클래스](../mfc/reference/cmfctoolbarscustomizedialog-class.md) 클래스입니다. 표시 하기 전에 **사용자 지정** 대화 상자를 호출 하 여 [CMFCToolBarsCustomizeDialog::Create](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create), 호출 [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) 바꾸려면 새 컨트롤 표준 단추입니다.  
  
## <a name="example-creating-a-find-combo-box"></a>예제: 찾기 콤보 상자 만들기  
 이 단원에서는 도구 모음에 나타나고 최근에 사용된 검색 문자열을 포함하는 `Find` 콤보 상자 컨트롤을 만드는 방법에 대해 설명합니다. 사용자는 컨트롤에 문자열을 입력한 다음 Enter 키를 눌러 문서를 검색하거나 Esc 키를 눌러 주 프레임에 포커스를 반환합니다. 이 예에서는 가정은 문서에 표시 되는 [CEditView 클래스](../mfc/reference/ceditview-class.md)-보기를 파생 합니다.  
  
### <a name="creating-the-find-control"></a>찾기 컨트롤 만들기  
 먼저 `Find` 콤보 상자 컨트롤을 만듭니다.  
  
1.  응용 프로그램 리소스에 단추와 해당 명령을 추가합니다.  
  
    1.  응용 프로그램 리소스에서 `ID_EDIT_FIND` 명령 ID로 응용 프로그램의 도구 모음이나 도구 모음과 연결된 모든 비트맵에 새 버튼을 추가합니다.  
  
    2.  ID_EDIT_FIND 명령 ID를 사용하여 새 메뉴 항목을 만듭니다.  
  
    3.  새로운 문자열 "텍스트 찾기\n찾기"를 문자열 테이블에 추가하고 `ID_EDIT_FIND_COMBO` 명령 ID를 할당합니다. 이 ID는 `Find` 콤보 상자 단추의 명령 ID로 사용됩니다.  
  
        > [!NOTE]
        >  `ID_EDIT_FIND`는 `CEditView`에 의해 처리되는 표준 명령이므로 이 명령을 위해 특수한 처리기를 구현하지 않아도 됩니다.  그러나 새 `ID_EDIT_FIND_COMBO` 명령에 대한 처리기를 구현해야 합니다.  
  
2.  새 클래스를 만든 `CFindComboBox`에서 파생 된 [CComboBox 클래스](../mfc/reference/ccombobox-class.md)합니다.  
  
3.  `CFindComboBox` 클래스에서 `PreTranslateMessage` 가상 메서드를 재정의합니다. 이 메서드를 처리할 콤보 상자가 하면는 [WM_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280) 메시지입니다. 사용자가 Esc 키를 누르면(`VK_ESCAPE`) 주 프레임 창으로 포커스를 반환합니다. 사용자가 Enter 키를 누르면(`VK_ENTER`) `WM_COMMAND` 명령 ID를 포함하는 `ID_EDIT_FIND_COMBO` 메시지를 주 프레임 창에 게시합니다.  
  
4.  에 대 한 클래스를 만들기는 `Find` 에서 파생 되는 콤보 상자 단추 [CMFCToolBarComboBoxButton 클래스](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)합니다. 이 예제에서는 `CFindComboButton`이라는 이름으로 지정됩니다.  
  
5.  `CMFCToolbarComboBoxButton`의 생성자에는 세 개의 매개 변수(단추의 명령 ID, 단추 이미지 인덱스 및 콤보 상자의 스타일)가 있습니다. 이러한 매개 변수를 다음과 같이 설정합니다.  
  
    1.  `ID_EDIT_FIND_COMBO`를 명령 ID로 전달합니다.  
  
    2.  사용 하 여 [CCommandManager::GetCmdImage](http://msdn.microsoft.com/en-us/4094d08e-de74-4398-a483-76d27a742dca) 와 `ID_EDIT_FIND` 이미지 인덱스를 가져옵니다.  
  
    3.  목록이 사용 가능한 콤보 상자 스타일에 대 한 참조 [콤보 상자 스타일](../mfc/reference/styles-used-by-mfc.md#combo-box-styles)합니다.  
  
6.  `CFindComboButton` 클래스에서 `CMFCToolbarComboBoxButton::CreateCombo` 메서드를 재정의합니다. 여기서 `CFindComboButton` 개체를 만들고 해당 개체에 대한 포인터를 반환해야 합니다.  
  
7.  사용 하 여는 [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) 매크로 영구 콤보 단추 수 있도록 합니다. 작업 영역 관리자가 Windows 레지스트리에서 단추의 상태를 자동으로 로드 및 저장합니다.  
  
8.  문서 뷰에서 `ID_EDIT_FIND_COMBO` 처리기를 구현합니다. 사용 하 여 [CMFCToolBar::GetCommandButtons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons) 와 `ID_EDIT_FIND_COMBO` 모두 검색 하려면 `Find` 콤보 상자 단추입니다. 사용자 지정으로 인해 명령 ID가 동일한 단추의 복사본이 여러 개 있을 수 있습니다.  
  
9. ID_EDIT_FIND 메시지 처리기에서 `OnFind`를 사용 하 여 [CMFCToolBar::IsLastCommandFromButton](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton) 찾기 명령에서 보냈는지 여부를 결정 하는 `Find` 콤보 상자 단추입니다. 명령을 보낸 경우 텍스트를 찾고 콤보 상자에 검색 문자열을 추가합니다.  
  
### <a name="adding-the-find-control-to-the-main-toolbar"></a>주 도구 모음에 찾기 컨트롤 추가  
 도구 모음에 콤보 상자 단추를 추가하려면 다음 단계를 따르십시오.  
  
1.  주 프레임 창의 `AFX_WM_RESETTOOLBAR` 메시지 처리기 `OnToolbarReset`을 구현합니다.  
  
    > [!NOTE]
    >  응용 프로그램이 시작하는 동안 도구 모음이 초기화되는 경우 또는 도구 모음이 사용자 지정 동안 다시 설정되는 경우 프레임워크는 이 메시지를 주 프레임 창으로 보냅니다. 두 경우 모두 표준 도구 모음 단추를 사용자 지정 `Find` 콤보 상자 단추로 대체해야 합니다.  
  
2.  `AFX_WM_RESETTOOLBAR` 처리기에서 도구 모음 ID, 즉 `WPARAM` 메시지의 `AFX_WM_RESETTOOLBAR`을 검사합니다. 도구 모음 ID가 포함 된 도구 모음에서와 같은 경우는 `Find` 콤보 상자 단추, 호출 [CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton) 바꾸려면는 `Find` 단추 (명령 ID 사용 하 여 단추, 즉 `ID_EDIT_FIND)` 으로 `CFindComboButton` 개체입니다.  
  
    > [!NOTE]
    >  `CFindComboBox`이 단추 개체를 복사하고 복사본을 유지하므로 스택에서 `ReplaceButton`를 생성할 수 있습니다.  
  
### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>사용자 지정 대화 상자에 찾기 컨트롤 추가  
 사용자 지정 처리기에서 `OnViewCustomize`, 호출 [CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) 바꾸려면는 `Find` 단추 (명령 ID 사용 하 여 단추, 즉 `ID_EDIT_FIND)` 와 `CFindComboButton` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../mfc/hierarchy-chart.md)   
 [클래스](../mfc/reference/mfc-classes.md)   
 [CMFCToolBar 클래스](../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton 클래스](../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton 클래스](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCToolBarsCustomizeDialog 클래스](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
