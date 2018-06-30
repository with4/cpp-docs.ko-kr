---
title: DRAWITEMSTRUCT 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DRAWITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- DRAWITEMSTRUCT structure [MFC]
ms.assetid: ba9ef1d4-aebb-45e9-b956-4b81a02e50f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff4596a52170d0c6d197a0bda431963b5f0e9344
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120941"
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
 *CtlType*  
 컨트롤 형식입니다. 컨트롤 형식의 값은 다음과 같습니다.  
  
- ODT_BUTTON 소유자가 그린 단추  
  
- ODT_COMBOBOX 소유자가 그린 콤보 상자  
  
- ODT_LISTBOX 소유자가 그린 목록 상자  
  
- ODT_MENU 소유자가 그린 메뉴  
  
- ODT_LISTVIEW 목록 뷰 컨트롤  
  
- ODT_STATIC 소유자가 그린 정적 컨트롤  
  
- ODT_TAB 탭 컨트롤  
  
 *CtlID*  
 콤보 상자, 목록 상자 또는 단추에 대한 컨트롤 ID입니다. 이 멤버는 메뉴에 사용되지 않습니다.  
  
 *itemID*  
 메뉴에 대한 메뉴 항목 ID 또는 목록 상자나 콤보 상자에 있는 항목의 인덱스입니다. 빈 목록 상자 또는 콤보 상자의 경우이 멤버는 응용 프로그램에 의해 지정 된 좌표에 포커스 사각형만 그릴 수 있는 음수 값은 `rcItem` 컨트롤에 항목이 없는 경우에 멤버입니다. 따라서 목록 상자 또는 콤보 상자에 입력 포커스가 있는지 여부를 사용자에게 표시할 수 있습니다. 비트 설정은 `itemAction` 멤버 목록 상자나 콤보 상자에 입력 포커스가 처럼 그릴 사각형 인지를 확인 합니다.  
  
 *ItemAction*  
 그리기 작업을 필수로 정의합니다. 다음 비트 중 하나 이상이 됩니다.  
  
- ODA_DRAWENTIRE이이 비트는 전체 컨트롤을 그려야 할 때 설정 됩니다.  
  
- ODA_FOCUS이이 비트는 컨트롤이 얻거나 입력된 포커스를 잃을 때 설정 됩니다. `itemState` 컨트롤에 포커스가 있는지 여부를 확인 하려면 멤버를 선택 해야 합니다.  
  
- ODA_SELECT이이 비트는 선택 상태만 변경 될 때 설정 됩니다. `itemState` 멤버를 선택 하 여 새 선택 상태를 결정 해야 합니다.  
  
 *itemState*  
 현재 그리기 작업이 발생한 후 항목의 시각적 상태를 지정합니다. 즉, 메뉴 항목이 흐리게 표시 해야 하 이면 상태 플래그 ODS_GRAYED 설정 됩니다. 상태 플래그는 다음과 같습니다.  
  
- ODS_CHECKED이이 비트는 항목 인지 여부를 검사할 경우 설정 됩니다. 이 비트는 메뉴에서만 사용됩니다.  
  
- ODS_DISABLED이이 비트는 항목 사용 안 함으로 그려야 하는 경우 설정 됩니다.  
  
- ODS_FOCUS이이 비트는 항목에 입력 포커스가 있는 경우 설정 됩니다.  
  
- ODS_GRAYED이이 비트는 항목 흐리게 표시 해야 하는 경우 설정 됩니다. 이 비트는 메뉴에서만 사용됩니다.  
  
- ODS_SELECTED이이 비트는 항목의 상태가 선택 되어 있으면 설정 됩니다.  
  
- ODS_COMBOBOXEDIT 그리기 소유자 콤보 상자의 선택 필드 (편집 컨트롤)에서 수행이 됩니다.  
  
- ODS_DEFAULT 항목이 기본 항목입니다.  
  
 *hwndItem*  
 콤보 상자, 목록 상자 및 단추에 대한 컨트롤의 창 핸들을 지정합니다. 메뉴 항목이 포함 된 메뉴 (HMENU)의 핸들을 지정 합니다.  
  
 *hDC*  
 장치 컨텍스트를 식별합니다. 이 장치 컨텍스트는 컨트롤에서 그리기 작업을 수행할 때 사용해야 합니다.  
  
 *rcItem*  
 로 지정 된 장치 컨텍스트의 사각형은 *hDC* 그릴 컨트롤의 경계를 정의 하는 멤버입니다. Windows에서는 콤보 상자, 목록 상자 및 단추에 대한 장치 컨텍스트에서 소유자가 그리는 모든 항목이 자동으로 잘리지만 메뉴 항목은 잘리지 않습니다. 메뉴 항목을 그릴 때 소유자 외부에 그리면 안 정의 된 사각형의 경계는 `rcItem` 멤버입니다.  
  
 *itemData*  
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
 소유자가 그린 컨트롤 또는 메뉴 항목의 소유자 창은이 구조에 대 한 포인터를 받는 *lParam* WM_DRAWITEM 메시지의 매개 변수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winuser.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)

