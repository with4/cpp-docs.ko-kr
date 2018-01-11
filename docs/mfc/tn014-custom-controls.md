---
title: "TN014: 사용자 지정 컨트롤 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.controls
dev_langs: C++
helpviewer_keywords:
- TN014
- custom controls [MFC]
ms.assetid: 1917a498-f643-457c-b570-9a0af7dbf7bb
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b4ffc4f26ed365673cdfb525c2bf3653827cc4ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tn014-custom-controls"></a>TN014: 사용자 지정 컨트롤
이 노트는 사용자 지정과 자체 그리기 컨트롤에 대한 MFC 지원을 설명합니다. 또한 동적 서브클래싱을 설명 하 고 간의 관계를 설명 [CWnd](../mfc/reference/cwnd-class.md) 개체 및 `HWND`s입니다.  
  
 MFC 샘플 응용 프로그램 CTRLTEST는 여러 사용자 지정 컨트롤을 사용하는 방법을 보여줍니다. MFC 일반 샘플에 대 한 소스 코드 참조 [CTRLTEST](../visual-cpp-samples.md) 및 온라인 도움말입니다.  
  
## <a name="owner-draw-controlsmenus"></a>소유자 그리기 컨트롤/메뉴  
 Windows는 Windows 메시지를 사용하여 소유자 그리기 컨트롤 및 메뉴에 대한 지원을 제공합니다. 모든 컨트롤 또는 메뉴의 부모 창은 이러한 메시지를 수신하고 그에 대한 응답으로 함수를 호출합니다. 이러한 함수를 재정의하여 소유자 그리기 컨트롤 또는 메뉴의 시각적 모양과 동작을 사용자 지정할 수 있습니다.  
  
 MFC는 다음과 같은 함수로 소유자 그리기를 직접 지원합니다.  
  
- [CWnd::OnDrawItem](../mfc/reference/cwnd-class.md#ondrawitem)  
  
- [CWnd::OnMeasureItem](../mfc/reference/cwnd-class.md#onmeasureitem)  
  
- [CWnd::OnCompareItem](../mfc/reference/cwnd-class.md#oncompareitem)  
  
- [CWnd::OnDeleteItem](../mfc/reference/cwnd-class.md#ondeleteitem)  
  
 `CWnd` 파생 클래스에서 이러한 함수를 재정의하여 사용자 지정 그리기 동작을 구현할 수 있습니다.  
  
 이 방법은 재사용 가능한 코드를 일으키지 않습니다. 두 개의 다른 `CWnd` 클래스에 두 개의 비슷한 컨트롤이 있으면 두 위치에서 사용자 지정 컨트롤 동작을 구현해야 합니다. MFC로 지원되는 자체 그리기 컨트롤 아키텍처는 이 문제를 해결합니다.  
  
## <a name="self-draw-controls-and-menus"></a>자체 그리기 컨트롤 및 메뉴  
 MFC 기본 구현을 제공 (에 `CWnd` 및 [CMenu](../mfc/reference/cmenu-class.md) 클래스) 표준 소유자 그리기 메시지에 대 한 합니다. 이러한 기본 구현은 소유자 그리기 매개 변수를 디코딩하고 소유자 그리기 메시지를 컨트롤 또는 메뉴에 위임합니다. 자체 그리기라고 부르는 이유는 그리기 코드가 소유자 창이 아닌 컨트롤 또는 메뉴의 클래스에 있기 때문입니다.  
  
 자체 그리기 컨트롤을 사용하면 소유자 그리기 의미 체계를 사용해서 컨트롤을 표시하는 재사용 가능한 컨트롤 클래스를 빌드할 수 있습니다. 컨트롤 그리기에 대한 코드는 해당 부모가 아닌 컨트롤 클래스에 있습니다. 이러한 방식은 사용자 지정 컨트롤 프로그래밍에 대한 개체 지향 접근 방식입니다. 다음 함수 목록을 자체 그리기 클래스에 추가합니다.  
  
-   자체 그리기 단추:  
  
 ```  
    CButton:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw this button  
 ```  
  
-   자체 그리기 메뉴:  
  
 ```  
    CMenu:MeasureItem(LPMEASUREITEMSTRUCT);
*// insert code to measure the size of an item in this menu  
    CMenu:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw an item in this menu  
 ```  
  
-   자체 그리기 목록 상자:  
  
 ```  
    CListBox:MeasureItem(LPMEASUREITEMSTRUCT);
*// insert code to measure the size of an item in this list box  
    CListBox:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw an item in this list box  
 
    CListBox:CompareItem(LPCOMPAREITEMSTRUCT);
*// insert code to compare two items in this list box if LBS_SORT  
    CListBox:DeleteItem(LPDELETEITEMSTRUCT);
*// insert code to delete an item from this list box  
 ```  
  
-   자체 그리기 콤보 상자:  
  
 ```  
    CComboBox:MeasureItem(LPMEASUREITEMSTRUCT);
*// insert code to measure the size of an item in this combo box  
    CComboBox:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw an item in this combo box  
 
    CComboBox:CompareItem(LPCOMPAREITEMSTRUCT);
*// insert code to compare two items in this combo box if CBS_SORT  
    CComboBox:DeleteItem(LPDELETEITEMSTRUCT);
*// insert code to delete an item from this combo box  
 ```  
  
 소유자 그리기 구조에 대 한 자세한 내용은 ([DRAWITEMSTRUCT](../mfc/reference/drawitemstruct-structure.md), [MEASUREITEMSTRUCT](../mfc/reference/measureitemstruct-structure.md), [COMPAREITEMSTRUCT](../mfc/reference/compareitemstruct-structure.md), 및 [DELETEITEMSTRUCT](../mfc/reference/deleteitemstruct-structure.md))에 대 한 MFC 설명서를 참조 `CWnd::OnDrawItem`, `CWnd::OnMeasureItem`, `CWnd::OnCompareItem`, 및 `CWnd::OnDeleteItem` 각각.  
  
## <a name="using-self-draw-controls-and-menus"></a>자체 그리기 컨트롤 및 메뉴 사용  
 자체 그리기 메뉴에 대해서는 `OnMeasureItem` 및 `OnDrawItem` 메서드를 모두 재정의해야 합니다.  
  
 자체 그리기 목록 상자 및 콤보 상자에 대해서는 `OnMeasureItem` 및 `OnDrawItem`을 재정의해야 합니다. 목록 상자에 대해 `LBS_OWNERDRAWVARIABLE` 스타일을 지정하거나 대화 상자 템플릿의 콤보 상자에 대해 `CBS_OWNERDRAWVARIABLE` 스타일을 지정해야 합니다. 자체 그리기 컨트롤이 목록 상자에 연결되기 전에 고정된 항목 높이가 결정되기 때문에 `OWNERDRAWFIXED` 스타일은 자체 그리기 항목에서 작동하지 않습니다. (메서드를 사용할 수 [CListBox::SetItemHeight](../mfc/reference/clistbox-class.md#setitemheight) 및 [CComboBox::SetItemHeight](../mfc/reference/ccombobox-class.md#setitemheight) 이 제한을 극복할.)  
  
 `OWNERDRAWVARIABLE` 스타일로 전환하면 시스템에서 `NOINTEGRALHEIGHT` 스타일이 컨트롤에 강제로 적용됩니다. 컨트롤이 변수 크기의 항목에서 정수 높이를 계산할 수 없기 때문에 `INTEGRALHEIGHT`의 기본 스타일이 무시되고 컨트롤이 항상 `NOINTEGRALHEIGHT`입니다. 항목이 고정된 높이인 경우 컨트롤 크기를 항목 크기의 정수 배율로 지정하여 항목이 일부만 그려지지 않도록 방지할 수 있습니다.  
  
 `LBS_SORT` 또는 `CBS_SORT` 스타일의 자체 그리기 목록 상자 및 콤보 상자의 경우 `OnCompareItem` 메서드를 재정의해야 합니다.  
  
 자체 그리기 목록 상자 및 콤보 상자의 경우 `OnDeleteItem`은 일반적으로 재정의되지 않습니다. 특수 처리를 수행하려는 경우에는 `OnDeleteItem`을 재정의할 수 있습니다. 이러한 경우를 적용할 수 있는 한 가지 사례는 추가 메모리 또는 기타 리소스가 각 목록 상자 또는 콤보 상자 항목에 저장되어 있는 경우입니다.  
  
## <a name="examples-of-self-drawing-controls-and-menus"></a>자체 그리기 컨트롤 및 메뉴의 예제  
 MFC 일반 샘플 [CTRLTEST](../visual-cpp-samples.md) 자체 그리기 메뉴 및 자체 그리기 목록 상자의 샘플을 제공 합니다.  
  
 자체 그리기 단추의 가장 일반적인 예는 비트맵 단추입니다. 비트맵 단추는 서로 다른 상태의 비트맵 이미지를 1~3개 보여주는 단추입니다. MFC 클래스에서이 예제를 보려면 [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)합니다.  
  
## <a name="dynamic-subclassing"></a>동적 서브클래싱  
 일부 경우에는 이미 존재하는 개체의 기능을 변경해야 할 수 있습니다. 이전 예제에서는 컨트롤이 생성되기 전에 사용자가 컨트롤을 사용자 지정해야 했습니다. 동적 서브클래싱은 사용자가 이미 생성된 컨트롤을 사용자 지정할 수 있게 해줍니다.  
  
 서브클래싱은 대체 하기 위해 Windows 용어는 [WndProc](http://msdn.microsoft.com/en-us/94ba8ffa-3c36-46d4-ac74-9bd10b1ffd26) 를 사용자 지정 된 창의 `WndProc` 호출 하는 `WndProc` 기본 기능에 대 한 합니다.  
  
 이 용어를 C++ 클래스 파생과 혼동해서는 안됩니다. 설명 하자면 c + + 용어인 *기본 클래스* 및 *파생 클래스* 유사 *superclass* 및 *하위 클래스* 창에 개체 모델입니다. MFC의 C++ 파생과 Windows의 서브클래싱은 기능적으로 비슷하지만 C++의 경우 동적 서브클래싱이 지원되지 않습니다.  
  
 `CWnd` 클래스는 C++ 개체(`CWnd`에서 파생)와 Windows의 창 개체(`HWND`) 사이의 연결을 제공합니다.  
  
 이러한 연결에는 세 가지 일반적인 특성이 존재합니다.  
  
- `CWnd`는 `HWND`를 만듭니다. `CWnd`에서 파생된 클래스를 만들어서 파생 클래스의 동작을 수정할 수 있습니다. `HWND` 응용 프로그램 호출 때 만들어지는 [CWnd::Create](../mfc/reference/cwnd-class.md#create)합니다.  
  
-   이 응용 프로그램은 `CWnd`를 기존 `HWND`에 연결합니다. 기존 창의 동작은 수정되지 않습니다. 경우 위임의 이며 호출 함으로써 [CWnd::Attach](../mfc/reference/cwnd-class.md#attach) 기존의 별칭 `HWND` 에 `CWnd` 개체입니다.  
  
- `CWnd`가 기존 `HWND`에 연결되고 파생 클래스의 동작을 수정할 수 있습니다. 런타임에 Windows 개체의 동작을 바꾸고, 따라서 클래스도 바꾸기 때문에 이를 동적 서브클래싱이라고 부릅니다.  
  
 메서드를 사용 하 여 동적 서브클래싱을 얻을 수 있는 [CWnd::SubclassWindow](../mfc/reference/cwnd-class.md#subclasswindow) 및[CWnd::SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem)합니다.  
  
 두 루틴은 모두 `CWnd` 개체를 기존 `HWND`에 연결합니다. `SubclassWindow`는 `HWND`를 직접 사용합니다. `SubclassDlgItem`은 컨트롤 ID 및 부모 창을 사용하는 도우미 함수입니다. `SubclassDlgItem`은 대화 상자 템플릿에서 생성된 대화 상자 컨트롤에 C++ 개체를 연결하기 위해 설계되었습니다.  
  
 참조는 [CTRLTEST](../visual-cpp-samples.md) 사용 하는 경우 여러 가지 예는 예제 `SubclassWindow` 및 `SubclassDlgItem`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
