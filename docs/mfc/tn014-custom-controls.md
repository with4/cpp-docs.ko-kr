---
title: "TN014: 사용자 지정 컨트롤 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.controls"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "사용자 지정 컨트롤[MFC]"
  - "TN014"
ms.assetid: 1917a498-f643-457c-b570-9a0af7dbf7bb
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# TN014: 사용자 지정 컨트롤
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 노트는 사용자 지정과 자체 그리기 컨트롤에 대한 MFC 지원을 설명합니다.  또한 동적 하위 클래스를 설명하고 [CWnd](../mfc/reference/cwnd-class.md) 개체와 `HWND`들 사이의 관계를 설명하고 있습니다.  
  
 MFC 샘플 응용 프로그램 CTRLTEST은 다양한 사용자 지정 컨트롤을 사용하는 방법을 보여줍니다.  MFC 일반 샘플 [CTRLTEST](../top/visual-cpp-samples.md) 에 대한 소스 코드와 온라인 도움말을 참조하세요.  
  
## 소유자 그리기 컨트롤\/메뉴  
 Windows는 Windows 메시지를 사용 하 여 소유자 그리기 컨트롤 및 메뉴에 대한 지원을 제공 합니다.  메뉴 또는 컨트롤의 부모 창은 응답에서 이 메시지들과 호출 함수들을 받습니다.  메뉴 또는 소유자 그리기 컨트롤의 동작과 모양을 사용자 지정 하려면이 함수를 재정의할 수 있습니다.  
  
 MFC는 다음과 같은 함수들로 소유자 그리기를 지원합니다.  
  
-   [CWnd::OnDrawItem](../Topic/CWnd::OnDrawItem.md)  
  
-   [CWnd::OnMeasureItem](../Topic/CWnd::OnMeasureItem.md)  
  
-   [CWnd::OnCompareItem](../Topic/CWnd::OnCompareItem.md)  
  
-   [CWnd::OnDeleteItem](../Topic/CWnd::OnDeleteItem.md)  
  
 사용자는 사용자 지정 그리기 동작을 구현하기위해 사용자의 `CWnd` 파생 클래스에서 이 함수들을 오버라이드할 수 있습니다.  
  
 이 방법은 재사용 가능한 코드를 발생 하지 않습니다.  두 개의 다른 `CWnd` 클래스들에서 두 개의 비슷한 컨트롤들이 있는 경우 사용자는 두 위치에서 사용자 지정 컨트롤의 동작을 구현 해야 합니다.  MFC 지원 자체 그리기 컨트롤 아키텍처는 이 문제를 해결 합니다.  
  
## 셀프 그리기 컨트롤들 그리고 메뉴들  
 MFC는 표준 소유자 그리기 메시지를 위해서 기본 구현을 제공합니다\(`CWnd` 및 [CMenu](../mfc/reference/cmenu-class.md) 클래스에서\).  기본 구현은 소유자 그리기 매개 변수를 디코딩하고 메뉴 또는 컨트롤에 소유자 그리기 메시지를 위임 합니다.  이것은 그리기 코드가 컨트롤이나 메뉴의 클래스에 있기 때문에 소유자 창이 아닌 셀프 그리기라고 부릅니다.  
  
 셀프 그리기 컨트롤을 사용하여 사용자는 컨트롤을 표시하기위해 재사용 가능한 소유자 그리기 의미체계를 사용하는 컨트롤 클래스들을 빌드할 수 있습니다.  컨트롤을 드로잉하기 위한 코드는 그것의 부모가 아닌 컨트롤 클래스에 있습니다.  사용자 정의 컨트롤 프로그래밍에 개체 지향 접근 방식입니다.  사용자 자체 그리기 클래스들에 함수들의 다음과 같은 목록을 추가합니다.  
  
-   자체 그리기 버튼들을 위한:  
  
    ```  
    CButton:DrawItem(LPDRAWITEMSTRUCT);  
            // insert code to draw this button  
    ```  
  
-   자체 그리기 메뉴들을 위한:  
  
    ```  
    CMenu:MeasureItem(LPMEASUREITEMSTRUCT);  
            // insert code to measure the size of an item in this menu  
    CMenu:DrawItem(LPDRAWITEMSTRUCT);  
            // insert code to draw an item in this menu  
    ```  
  
-   자체 그리기 리스트 박스들을 위한:  
  
    ```  
    CListBox:MeasureItem(LPMEASUREITEMSTRUCT);  
            // insert code to measure the size of an item in this list box  
    CListBox:DrawItem(LPDRAWITEMSTRUCT);  
            // insert code to draw an item in this list box  
  
    CListBox:CompareItem(LPCOMPAREITEMSTRUCT);  
            // insert code to compare two items in this list box if LBS_SORT  
    CListBox:DeleteItem(LPDELETEITEMSTRUCT);  
            // insert code to delete an item from this list box  
    ```  
  
-   자체 그리기 콤보 박스들을 위한:  
  
    ```  
    CComboBox:MeasureItem(LPMEASUREITEMSTRUCT);  
            // insert code to measure the size of an item in this combo box  
    CComboBox:DrawItem(LPDRAWITEMSTRUCT);  
            // insert code to draw an item in this combo box  
  
    CComboBox:CompareItem(LPCOMPAREITEMSTRUCT);  
            // insert code to compare two items in this combo box if CBS_SORT  
    CComboBox:DeleteItem(LPDELETEITEMSTRUCT);  
            // insert code to delete an item from this combo box  
    ```  
  
 소유자 그리기 구조에 대 한 자세한 내용은 \([DRAWITEMSTRUCT](../mfc/reference/drawitemstruct-structure.md),  [MEASUREITEMSTRUCT](../mfc/reference/measureitemstruct-structure.md),  [COMPAREITEMSTRUCT](../mfc/reference/compareitemstruct-structure.md), 및  [DELETEITEMSTRUCT](../mfc/reference/deleteitemstruct-structure.md)\) `CWnd::OnDrawItem`, `CWnd::OnMeasureItem`,  `CWnd::OnCompareItem`, 및 `CWnd::OnDeleteItem` 에 대한 MFC 문서를 참조하세요.  
  
## 자체 그리기 컨트롤들과 메뉴들을 사용  
 자체 그리기 메뉴에서 사용자는 `OnMeasureItem` 와 `OnDrawItem` 메서드를 모두 재정의 해야합니다.  
  
 자체 그리기 목록 상자와 콤보 상자에 대해서 사용자는 `OnMeasureItem` 와 `OnDrawItem`를 재정의 해야합니다.  사용자는 대화상자 탬플릿에 목록 상자에 대한 `LBS_OWNERDRAWVARIABLE`스타일 또는 콤보 박스를 위한 `CBS_OWNERDRAWVARIABLE` 스타일을 지정해야합니다.  `OWNERDRAWFIXED` 스타일은 자체 그리기 아이템과는 작동하지 않습니다. 고정된 아이템 높이가 자체 그리기 컨트롤들이 리스트 박스에 연결되기 전에 결정되기 때문입니다. \(사용자는 이 제한을 극복 하기 위해 [CListBox::SetItemHeight](../Topic/CListBox::SetItemHeight.md) 와 [CComboBox::SetItemHeight](../Topic/CComboBox::SetItemHeight.md) 메서드들을 사용할 수 있습니다.\)  
  
 `OWNERDRAWVARIABLE` 스타일로 전환하는 것은 컨트롤에 `NOINTEGRALHEIGHT`적용하도록 할 것입니다.  그 컨트롤은 정수 높이로 계산될 수 없기 때문에 `INTEGRALHEIGHT`의 기본 스타일은 무시되고 그 컨트롤은 항상 `NOINTEGRALHEIGHT`입니다.  만약 사용자의 항목이 고정된 높이이면 사용자는 컨트롤 사이즈를 아이템 사이즈의 정수 승수로 지정함으로써 그려지도록 하는 것으로 부터의 일부 항목을 방지할 수 있습니다.  
  
 `LBS_SORT` 또는 `CBS_SORT`스타일에서 자체 그리기 리스트 박스와 콤보박스에 대하여 사용자는 `OnCompareItem` 메서드를 재정의하여야 합니다.  
  
 자체 그리기 리스트 박스와 콤보박스에 대해 `OnDeleteItem` 는 일반적으로 재정의 되지 않습니다.  사용자가 어떤 특수한 처리를 하려고 하는 경우 `OnDeleteItem` 를 재정의 할 수 있습니다.  이것이 적용되는 것은 추가적인 메모리나 다른 리소스들이 각각의 리스트 박스 또는 콤보 박스 아이템과 저장될 때 입니다.  
  
## 자체 그리기 컨트롤과 메뉴의 예제  
 MFC 일반 샘플  [CTRLTEST](../top/visual-cpp-samples.md) 은 자체 그리기 메뉴와 자체 그리기 리스트 박스의 샘플들을 제공합니다.  
  
 자체 그리기 버튼의 가장 대표적인 예는 비트맵 버튼입니다.  비트맵 버튼은 다른 상태에 대한 1,2,3비트맵 이미지들을 보여주는 버튼입니다.  이 예제는 MFC 클래스 [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)에서 제공됩니다.  
  
## 동적 하위 클래스  
 때때로 사용자는 이미 존재하는 개체의 기능을 변경하고자 합니다.  앞의 예제들은 생성되기 전에 컨트롤을 사용자지정하도록 요구됩니다.  동적 하위 클래스는 이미 생성되었었던 컨트롤을 사용자지정할 수 있도록 합니다.  
  
 하위 클래스는 사용자 지정된 `WndProc`과 창의 [WndProc](http://msdn.microsoft.com/ko-kr/94ba8ffa-3c36-46d4-ac74-9bd10b1ffd26)을 교체하는 것과 기본 기능에 대해 이 전의  `WndProc` 호출에 대한 윈도우즈 용어 입니다.  
  
 이것은 C\+\+ 클래스 파생과 혼동하면 안됩니다.  명확하게 C\+\+용어 *기본 클래스* 와 *파생 클래스*는 윈도우즈 개체 모델에서 *슈퍼 클래스* 와 *서브 클래스*와 유사합니다.  MFC의 c\+\+ 파생과 윈도우즈 서브 클래싱은 C\+\+이 동적 서브클래싱을 지원하지 않는다는 것 이외에는 기능적으로 유사합니다.  
  
 `CWnd`클래스는 C\+\+개체 \(`CWnd`에서 파생된\)와 Windows 창 개체 \(`HWND`라고 알려진\)사이의 연결을 제공합니다.  
  
 연관된 세 가지 일반적인 방법이 있습니다:  
  
-   `CWnd` 는 `HWND`를 만듭니다.  사용자는 `CWnd`에서 파생된 클래스를 생성함으로써 파생 클래스에서 동작을 수정할 수 있습니다.  `HWND`는 사용자의 응용프로그램이 [CWnd::Create](../Topic/CWnd::Create.md)을 호출할 때 생성됩니다.  
  
-   응용 프로그램은 기존 `HWND`에 `CWnd`을 연결합니다.   기존 윈도우의 동작은 수정되지 않습니다.  이것은 위임의 한 경우이고  `CWnd` 개체에 기존 `HWND`을 별칭하기 위한 [CWnd::Attach](../Topic/CWnd::Attach.md)을 호출함으로써 가능하게 합니다.  
  
-   `CWnd`는 기존의 `HWND`에 연결되고 사용자는 파생 클래스에서 동작을 수정할 수 있습니다.  우리가 동작을 수정하고 있기 때문에 이것은 동작 서브 클래싱이라 불립니다.  
  
 사용자는 [CWnd::SubclassWindow](../Topic/CWnd::SubclassWindow.md) 와 `` [CWnd::SubclassDlgItem](../Topic/CWnd::SubclassDlgItem.md)메서드들을 사용하여 동적 서브클래싱을 할 수 있습니다.  
  
 두 루틴 모두 `CWnd`개체를 존재하는 `HWND`에 연결합니다.  `SubclassWindow`은 `HWND`를 직접 사용합니다.  `SubclassDlgItem` 는 컨트롤 ID와 부모 창을 사용하는 도우미 함수입니다.  `SubclassDlgItem`는 대화상자 템플릿으로부터 생성된 대화상자 컨트롤에 C\+\+ 개체를 연결하는 것에 대해 설계되었습니다.  
  
 `SubclassWindow` 및 `SubclassDlgItem`를 사용할 때의 여러가지 예에 대한 [CTRLTEST](../top/visual-cpp-samples.md) 예제를 참조하십시오.  
  
## 참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)