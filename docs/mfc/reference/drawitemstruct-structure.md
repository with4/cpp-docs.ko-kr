---
title: "DRAWITEMSTRUCT 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DRAWITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- DRAWITEMSTRUCT structure [MFC]
ms.assetid: ba9ef1d4-aebb-45e9-b956-4b81a02e50f7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 438d698b486b455d7898a836d510aa5ec1c6e454
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="drawitemstruct-structure"></a>DRAWITEMSTRUCT 구조체
`DRAWITEMSTRUCT` 구조체는 소유자 창에서 소유자가 그린 컨트롤 또는 메뉴 항목을 그리는 방법을 결정하는 데 필요한 정보를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagDRAWITEMSTRUCT {  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    UINT itemAction;  
    UINT itemState;  
    HWND hwndItem;  
    HDC hDC;  
    RECT rcItem;  
    DWORD itemData;  
} DRAWITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `CtlType`  
 컨트롤 형식입니다. 컨트롤 형식의 값은 다음과 같습니다.  
  
- **ODT_BUTTON** 소유자가 그린 단추  
  
- **ODT_COMBOBOX** 소유자가 그린 콤보 상자  
  
- **ODT_LISTBOX** 소유자가 그린 목록 상자  
  
- **ODT_MENU** 소유자가 그린 메뉴  
  
- **ODT_LISTVIEW** 목록 뷰 컨트롤  
  
- **ODT_STATIC** 소유자가 그린 정적 컨트롤  
  
- **ODT_TAB** 탭 컨트롤  
  
 `CtlID`  
 콤보 상자, 목록 상자 또는 단추에 대한 컨트롤 ID입니다. 이 멤버는 메뉴에 사용되지 않습니다.  
  
 `itemID`  
 메뉴에 대한 메뉴 항목 ID 또는 목록 상자나 콤보 상자에 있는 항목의 인덱스입니다. 빈 목록 상자 또는 콤보 상자의 경우 이 멤버가 음수 값이므로 컨트롤에 항목이 없는 경우에도 응용 프로그램이 **rcItem** 멤버에 의해 지정된 좌표에 포커스 사각형만 그릴 수 있습니다. 따라서 목록 상자 또는 콤보 상자에 입력 포커스가 있는지 여부를 사용자에게 표시할 수 있습니다. **itemAction** 멤버의 비트 설정은 목록 상자 또는 콤보 상자에 입력 포커스가 있는 것처럼 사각형을 그릴지 여부를 결정합니다.  
  
 `itemAction`  
 그리기 작업을 필수로 정의합니다. 다음 비트 중 하나 이상이 됩니다.  
  
- **ODA_DRAWENTIRE** 이 비트는 전체 컨트롤을 그려야 할 때 설정됩니다.  
  
- **ODA_FOCUS** 이 비트는 컨트롤이 입력 포커스를 얻거나 잃을 때 설정됩니다. **itemState** 멤버를 선택하여 컨트롤에 포커스가 있는지 여부를 결정해야 합니다.  
  
- **ODA_SELECT** 이 비트는 선택 상태만 변경된 경우에 설정됩니다. **itemState** 멤버를 선택하여 새 선택 상태를 결정해야 합니다.  
  
 *itemState*  
 현재 그리기 작업이 발생한 후 항목의 시각적 상태를 지정합니다. 즉, 메뉴 항목이 흐리게 표시되어야 하는 경우 상태 플래그 **ODS_GRAYED** 를 설정합니다. 상태 플래그는 다음과 같습니다.  
  
- **ODS_CHECKED** 이 비트는 메뉴 항목을 선택해야 하는 경우에 설정됩니다. 이 비트는 메뉴에서만 사용됩니다.  
  
- **ODS_DISABLED** 이 비트는 항목을 사용 안 함으로 그려야 하는 경우에 설정됩니다.  
  
- **ODS_FOCUS** 이 비트는 항목에 입력 포커스가 있는 경우에 설정됩니다.  
  
- **ODS_GRAYED** 이 비트는 항목을 흐리게 표시해야 하는 경우에 설정됩니다. 이 비트는 메뉴에서만 사용됩니다.  
  
- **ODS_SELECTED** 이 비트는 항목의 상태가 선택됨인 경우에 설정됩니다.  
  
- **ODS_COMBOBOXEDIT** 소유자가 그린 콤보 상자의 선택 필드(편집 컨트롤)에서 그리기가 수행됩니다.  
  
- **ODS_DEFAULT** 항목이 기본 항목입니다.  
  
 `hwndItem`  
 콤보 상자, 목록 상자 및 단추에 대한 컨트롤의 창 핸들을 지정합니다. 메뉴 항목이 포함된 메뉴(`HMENU`)의 핸들을 지정합니다.  
  
 `hDC`  
 장치 컨텍스트를 식별합니다. 이 장치 컨텍스트는 컨트롤에서 그리기 작업을 수행할 때 사용해야 합니다.  
  
 *rcItem*  
 그릴 컨트롤의 경계를 정의하는 `hDC` 멤버에 의해 지정된 장치 컨텍스트의 사각형입니다. Windows에서는 콤보 상자, 목록 상자 및 단추에 대한 장치 컨텍스트에서 소유자가 그리는 모든 항목이 자동으로 잘리지만 메뉴 항목은 잘리지 않습니다. 소유자는 메뉴 항목을 그릴 때 **rcItem** 멤버에 의해 정의된 사각형의 경계 외부에 그리면 안 됩니다.  
  
 `itemData`  
 콤보 상자 또는 목록 상자의 경우 이 멤버는 다음 중 하나에 의해 목록 상자에 전달된 값을 포함합니다.  
  
- [CComboBox::AddString](../../mfc/reference/ccombobox-class.md#addstring)  
  
- [CComboBox::InsertString](../../mfc/reference/ccombobox-class.md#insertstring)  
  
- [CListBox::AddString](../../mfc/reference/clistbox-class.md#addstring)  
  
- [CListBox::InsertString](../../mfc/reference/clistbox-class.md#insertstring)  
  
 메뉴의 경우 이 멤버는 다음 중 하나에 의해 메뉴에 전달된 값을 포함합니다.  
  
- [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)  
  
- [CMenu::InsertMenu](../../mfc/reference/cmenu-class.md#insertmenu)  
  
- [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu)  
  
## <a name="remarks"></a>설명  
 소유자가 그린 컨트롤 또는 메뉴 항목의 소유자 창은 이 구조에 대한 포인터를 `lParam` 메시지의 `WM_DRAWITEM` 매개 변수로 받습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winuser.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)

