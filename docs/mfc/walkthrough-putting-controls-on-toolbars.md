---
title: "연습: 도구 모음에 컨트롤 배치 | Microsoft Docs"
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
  - "사용자 지정 대화 상자, 컨트롤 추가"
  - "도구 모음, 컨트롤 추가"
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# 연습: 도구 모음에 컨트롤 배치
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목은 Windows 컨트롤을 포함하는 도구 모음 단추를 도구 모음에 추가하는 방법을 설명합니다.  MFC에서, 도구 모음 단추는 [CMFCToolBarButton Class](../mfc/reference/cmfctoolbarbutton-class.md) 파생 클래스여야 합니다. [CMFCToolBarComboBoxButton Class](../mfc/reference/cmfctoolbarcomboboxbutton-class.md), [CMFCToolBarEditBoxButton Class](../mfc/reference/cmfctoolbareditboxbutton-class.md), [CMFCDropDownToolbarButton Class](../mfc/reference/cmfcdropdowntoolbarbutton-class.md), 또는 [CMFCToolBarMenuButton Class](../mfc/reference/cmfctoolbarmenubutton-class.md)를 예로 들 수 있습니다.  
  
## 도구 모음에 컨트롤 추가  
 도구 모음에 컨트롤을 추가 하려면, 다음과 단계를 따르십시오:  
  
1.  부모 리소스 도구 모음 단추에 더미 리소스 ID를 예약합니다.  Visual Studio 도구 모음 편집기를 사용하여 단추를 만드는 방법에 대한 자세한 내용은 [Toolbar Editor](../mfc/toolbar-editor.md) 항목을 참조하십시오.  
  
2.  상위 도구 모음의 단추에 대한 모든 비트맵을 위한 도구 모음 이미지 \(버튼 아이콘\)를 예약합니다.  
  
3.  `AFX_WM_RESETTOOLBAR` 메시지를 처리하는 메시지 처리기는 다음을 수행하십시오:  
  
    1.  `CMFCToolbarButton`\-파생 클래스를 사용하여 단추 컨트롤을 생성하십시오.  
  
    2.  더미 단추를 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)을 사용하여 새 컨트롤을 대체하십시오.  `ReplaceButton`은 단추 개체를 복사하고 복사본을 유지하기 때문에, 쌓기에서 단추 개체를 생성할 수 있습니다.  
  
> [!NOTE]
>  응용 프로그램에서 사용자 지정을 적용할 경우, 다시 컴파일된 이후의 응용 프로그램 내 업데이트된 컨트롤을 보려면 **사용자 지정** 대화 상자에서 **도구 모음** 탭의 **재설정** 단추를 사용하여 도구 모음을 재설정해야 할 수 있습니다.  도구 모음 상태는 Windows 레지스트리에 저장되며, 레지스트리 정보는 응용 프로그램 시작시 `ReplaceButton` 메서드가 실행된 이후에 로드됩니다.  
  
## 도구 모음 컨트롤 및 사용자 지정  
 **사용자 지정** 대화 상자의 **명령** 탭은 응용 프로그램에서 사용할 수 있는 명령 목록이 포함되어 있습니다.  기본적으로, **사용자 지정** 대화 상자는 응용 프로그램 메뉴를 처리하고 각 메뉴 범주의 표준 도구 모음 단추의 목록을 만듭니다.  도구 모음 컨트롤이 제공하는 확장된 기능을 유지하려면 표준 도구 모음 단추를 **사용자 지정** 대화 상자에서 사용자 지정 컨트롤로 교체해야 합니다.  
  
 사용자 지정을 적용하려면, [CMFCToolBarsCustomizeDialog Class](../mfc/reference/cmfctoolbarscustomizedialog-class.md) 클래스를 사용하여 **사용자 지정** 대화 상자에서 사용자 지정 처리기 `OnViewCustomize`를 생성해야 합니다.  [CMFCToolBarsCustomizeDialog::Create](../Topic/CMFCToolBarsCustomizeDialog::Create.md)를 호출하여 **사용자 지정** 대화 상자를 표시하기 전에, [CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md)를 호출하여 표준 단추를 새 컨트롤로 교체하십시오.  
  
## 예: 찾기 콤보 상자 만들기  
 이 부분은 최근에 사용된 검색 문자열을 포함하는 도구 모음에 `Find` 콤보 상자 컨트롤을 만드는 방법에 대해 설명합니다.  사용자는 문서를 검색 하기 위해 컨트롤에 문자열을 입력한 다음 엔터 키를 누르거나 주 프레임으로 돌아가기 위해 ESC 키를 누를 수 있습니다.  이 예제는 문서가 [CEditView Class](../mfc/reference/ceditview-class.md)\-파생 뷰에 표시되는 것을 가정합니다.  
  
### 찾기 컨트롤 만들기  
 먼저, `Find` 콤보 상자 컨트롤을 만듭니다:  
  
1.  응용 프로그램 리소스에 단추와 그 명령을 추가합니다:  
  
    1.  응용 프로그램 리소스에서, `ID_EDIT_FIND` 명령 ID로 응용 프로그램의 도구 모음이나 도구 모음과 관련된 모든 비트맵에 새 버튼을 추가합니다.  
  
    2.  ID\_EDIT\_FIND 명령 ID를 사용하여 새 메뉴 항목을 만듭니다.  
  
    3.  새로운 문자열 "텍스트 찾기\\nFind"을 문자열 테이블에 추가하고 `ID_EDIT_FIND_COMBO` 명령 ID를 할당합니다.  이 ID는 `Find` 콤보 상자 단추의 명령 ID로 사용될 것입니다.  
  
        > [!NOTE]
        >  `ID_EDIT_FIND`는 `CEditView`에 의해 처리되는 표준 명령이기 때문에, 이 명령을 위해 특수한 처리기를 구현하지 않아도 됩니다.  하지만 새 `ID_EDIT_FIND_COMBO` 명령에 대한 처리기를 구현해야 합니다.  
  
2.  [CComboBox Class](../mfc/reference/ccombobox-class.md)에서 파생된 새 `CFindComboBox` 클래스를 만듭니다.  
  
3.  `CFindComboBox` 클레스에서, `PreTranslateMessage` 가상 메서드를 재정의합니다.  이 메서드는 콤보 상자가 [WM\_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280) 메시지를 처리할 수 있도록 합니다.  사용자가 ESC 키를 누르면 \(`VK_ESCAPE`\), 주 프레임 창으로 포커스를 반환합니다.  사용자가 엔터 키를 누르면 \(`VK_ENTER`\), `ID_EDIT_FIND_COMBO` 명령 ID를 포함하는 `WM_COMMAND` 메시지를 주 프레임 창에 보냅니다.  
  
4.  [CMFCToolBarComboBoxButton Class](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)에서 파생되는 `Find` 콤보 상자 단추에 대한 클래스를 만드십시오.  이 예제에서는 `CFindComboButton`라는 이름을 지정합니다.  
  
5.  `CMFCToolbarComboBoxButton`의 생성자는 세 개의 매개 변수를 취합니다: 단추의 명령 ID, 단추의 이미지 색인, 그리고 콤보 상자의 스타일입니다.  이러한 매개 변수를 다음과 같이 설정합니다.  
  
    1.  `ID_EDIT_FIND_COMBO`를 명령 ID로 전달합니다.  
  
    2.  [CCommandManager::GetCmdImage](http://msdn.microsoft.com/ko-kr/4094d08e-de74-4398-a483-76d27a742dca)와 `ID_EDIT_FIND`를 사용하여 이미지 색인을 가져옵니다.  
  
    3.  사용 가능한 콤보 상자 스타일의 목록을 보기 위해서는 [콤보 상자 스타일](../mfc/reference/combo-box-styles.md)를 참조하십시오.  
  
6.  `CFindComboButton` 클래스에서 `CMFCToolbarComboBoxButton::CreateCombo` 메서드를 재정의합니다.  여기서 `CFindComboButton` 개체를 만들고 그에 대한 포인터를 반환해야 합니다.  
  
7.  콤보 단추를 영구적으로 만들기 위해 [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) 매크로를 사용하십시오.  작업 영역 관리자가 버튼의 상태를 Windows 레지스트리에서 자동으로 불러오고 저장합니다.  
  
8.  문서 뷰에서 `ID_EDIT_FIND_COMBO` 처리기를 구현합니다.  모든 `Find` 콤보 상자 단추를 검색하기 위해 [CMFCToolBar::GetCommandButtons](../Topic/CMFCToolBar::GetCommandButtons.md)와 `ID_EDIT_FIND_COMBO`를 사용하십시오.  사용자 지정으로 인해 명령 ID가 동일한 단추의 복사본이 여러 개 있을 수 있습니다.  
  
9. `Find` 콤보 상자 단추에서 찾기 명령이 보내졌는지 여부를 알기 위해서는 ID\_EDIT\_FIND의 `OnFind` 메시지 처리기에서 [CMFCToolBar::IsLastCommandFromButton](../Topic/CMFCToolBar::IsLastCommandFromButton.md)를 사용하십시오.  그렇다면, 텍스트를 찾고 콤보 상자에 검색 문자열을 추가합니다.  
  
### 주 도구 모음에 찾기 컨트롤 추가  
 도구 모음에 콤보 상자 단추를 추가 하려면 다음 단계를 따르십시오:  
  
1.  주 프레임 창의 `AFX_WM_RESETTOOLBAR` 메시지 처리기 `OnToolbarReset`를 구현하십시오.  
  
    > [!NOTE]
    >  응용 프로그램이 시작시 도구 모음이 초기화되는 동안이나 도구 모음이 사용자 지정에 의해 재설정되는 동안 프레임워크는 이 메시지를 주 프레임 창으로 보냅니다.  두 경우 모두, 표준 도구 모음 단추를 사용자 지정 `Find` 콤보 상자 단추로 변경해야 합니다.  
  
2.  `AFX_WM_RESETTOOLBAR` 처리기에서 도구 모음 ID를 검사하십시오. 그것은, `WPARAM`의 `AFX_WM_RESETTOOLBAR` 메시지입니다.  `Find` 콤보 상자 단추를 포함하는 도구 모음과 도구 모음 ID가 같은 경우, [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)를 호출하여 `Find` 단추 \(`CFindComboButton` 개체와 `ID_EDIT_FIND)` 명령 ID의 단추\) 를 바꾸십시오.  
  
    > [!NOTE]
    >  `ReplaceButton`은 단추 개체를 복사하고 복사본을 유지하기 때문에, 쌓기에서 `CFindComboBox`를 생성할 수 있습니다.  
  
### 사용자 지정 대화 상자에 찾기 컨트롤 추가  
 `OnViewCustomize` 사용자 지정 처리기에서, [CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md)를 호출하여 `Find` 단추 \(`CFindComboButton` 개체와 `ID_EDIT_FIND)` 명령 ID의 단추\) 를 바꾸십시오.  
  
## 참고 항목  
 [계층 구조 차트](../mfc/hierarchy-chart.md)   
 [클래스](../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton Class](../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton Class](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCToolBarsCustomizeDialog Class](../mfc/reference/cmfctoolbarscustomizedialog-class.md)