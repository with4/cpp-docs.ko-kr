---
title: "CMenu 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMenu
- AFXWIN/CMenu
- AFXWIN/CMenu::CMenu
- AFXWIN/CMenu::AppendMenu
- AFXWIN/CMenu::Attach
- AFXWIN/CMenu::CheckMenuItem
- AFXWIN/CMenu::CheckMenuRadioItem
- AFXWIN/CMenu::CreateMenu
- AFXWIN/CMenu::CreatePopupMenu
- AFXWIN/CMenu::DeleteMenu
- AFXWIN/CMenu::DeleteTempMap
- AFXWIN/CMenu::DestroyMenu
- AFXWIN/CMenu::Detach
- AFXWIN/CMenu::DrawItem
- AFXWIN/CMenu::EnableMenuItem
- AFXWIN/CMenu::FromHandle
- AFXWIN/CMenu::GetDefaultItem
- AFXWIN/CMenu::GetMenuContextHelpId
- AFXWIN/CMenu::GetMenuInfo
- AFXWIN/CMenu::GetMenuItemCount
- AFXWIN/CMenu::GetMenuItemID
- AFXWIN/CMenu::GetMenuItemInfo
- AFXWIN/CMenu::GetMenuState
- AFXWIN/CMenu::GetMenuString
- AFXWIN/CMenu::GetSafeHmenu
- AFXWIN/CMenu::GetSubMenu
- AFXWIN/CMenu::InsertMenu
- AFXWIN/CMenu::InsertMenuItem
- AFXWIN/CMenu::LoadMenu
- AFXWIN/CMenu::LoadMenuIndirect
- AFXWIN/CMenu::MeasureItem
- AFXWIN/CMenu::ModifyMenu
- AFXWIN/CMenu::RemoveMenu
- AFXWIN/CMenu::SetDefaultItem
- AFXWIN/CMenu::SetMenuContextHelpId
- AFXWIN/CMenu::SetMenuInfo
- AFXWIN/CMenu::SetMenuItemBitmaps
- AFXWIN/CMenu::SetMenuItemInfo
- AFXWIN/CMenu::TrackPopupMenu
- AFXWIN/CMenu::TrackPopupMenuEx
- AFXWIN/CMenu::m_hMenu
dev_langs:
- C++
helpviewer_keywords:
- HMENU
- menus, class
- menus, base class
- menus, creating
- menus, managing
- CMenu class
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: dcd353bf0be5d23c1782347f54b16a875ed190ed
ms.lasthandoff: 02/24/2017

---
# <a name="cmenu-class"></a>CMenu 클래스
Windows `HMENU`의 캡슐화입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMenu : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMenu::CMenu](#cmenu)|`CMenu` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMenu::AppendMenu](#appendmenu)|이 메뉴의 끝에 새 항목을 추가합니다.|  
|[CMenu::Attach](#attach)|연결에 대 한 창 핸들 메뉴는 `CMenu` 개체입니다.|  
|[CMenu::CheckMenuItem](#checkmenuitem)|옆에 확인 표시를 삽입 하거나 팝업 메뉴에서 메뉴 항목에서 확인 표시를 제거 합니다.|  
|[CMenu::CheckMenuRadioItem](#checkmenuradioitem)|메뉴 항목 옆에 있는 라디오 단추를 배치 하 고 라디오 단추 그룹의 다른 메뉴 항목을 모두 제거 합니다.|  
|[CMenu::CreateMenu](#createmenu)|빈 메뉴를 만들고 연결 하는 `CMenu` 개체입니다.|  
|[CMenu::CreatePopupMenu](#createpopupmenu)|빈 팝업 메뉴를 만들고 연결 하는 `CMenu` 개체입니다.|  
|[CMenu::DeleteMenu](#deletemenu)|메뉴에서 지정된 된 항목을 삭제합니다. 메뉴 항목에는 연결 된 팝업 메뉴를 팝업 메뉴에 대 한 핸들을 삭제 하 고 메서드에서 사용 된 메모리를 해제 합니다.|  
|[CMenu::DeleteTempMap](#deletetempmap)|모든 임시 삭제 `CMenu` 가 만든 개체는 `FromHandle` 멤버 함수입니다.|  
|[CMenu::DestroyMenu](#destroymenu)|에 연결 된 메뉴를 소멸는 `CMenu` 개체를 메뉴에 사용 되는 메모리를 해제 합니다.|  
|[CMenu::Detach](#detach)|Windows 메뉴 핸들을 분리 한 `CMenu` 개체 핸들을 반환 합니다.|  
|[CMenu::DrawItem](#drawitem)|소유자가 그린 메뉴 변경의 시각적 측면이 때 프레임 워크에 의해 호출 됩니다.|  
|[CMenu::EnableMenuItem](#enablemenuitem)|사용, 사용 하지 않도록 설정, 또는 (회색) 흐리게 표시 된 메뉴 항목입니다.|  
|[CMenu::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CMenu` Windows 메뉴 핸들을 지정 된 개체입니다.|  
|[CMenu::GetDefaultItem](#getdefaultitem)|지정 된 메뉴 항목이 기본 메뉴 항목을 결정합니다.|  
|[CMenu::GetMenuContextHelpId](#getmenucontexthelpid)|메뉴와 연결 된 도움말 컨텍스트 ID를 검색 합니다.|  
|[CMenu::GetMenuInfo](#getmenuinfo)|특정 메뉴에 대 한 정보를 검색합니다.|  
|[CMenu::GetMenuItemCount](#getmenuitemcount)|팝업 또는 최상위 메뉴에서 항목의 수를 결정 합니다.|  
|[CMenu::GetMenuItemID](#getmenuitemid)|지정된 된 위치에 있는 메뉴 항목에 대 한 메뉴 항목 식별자를 가져옵니다.|  
|[CMenu::GetMenuItemInfo](#getmenuiteminfo)|메뉴 항목에 대 한 정보를 검색합니다.|  
|[CMenu::GetMenuState](#getmenustate)|팝업 메뉴에서 항목의 수 또는 지정 된 메뉴 항목의 상태를 반환합니다.|  
|[CMenu::GetMenuString](#getmenustring)|지정 된 메뉴 항목의 레이블을 검색합니다.|  
|[CMenu::GetSafeHmenu](#getsafehmenu)|반환 된 `m_hMenu` 이 래핑됩니다 `CMenu` 개체입니다.|  
|[CMenu::GetSubMenu](#getsubmenu)|팝업 메뉴에 대 한 포인터를 검색합니다.|  
|[CMenu::InsertMenu](#insertmenu)|다른 항목의 메뉴 내려가면서 지정된 된 위치에 새 메뉴 항목을 삽입 합니다.|  
|[CMenu::InsertMenuItem](#insertmenuitem)|메뉴에 지정된 된 위치에 새 메뉴 항목을 삽입합니다.|  
|[CMenu::LoadMenu](#loadmenu)|실행 파일에서 메뉴 리소스를 로드 하 고 연결 하는 `CMenu` 개체입니다.|  
|[CMenu::LoadMenuIndirect](#loadmenuindirect)|메모리에 서식 파일 메뉴에서에서 메뉴를 로드 하 고 연결 하는 `CMenu` 개체입니다.|  
|[CMenu::MeasureItem](#measureitem)|소유자가 그린 메뉴를 만들 때 메뉴 크기를 결정 하는 프레임 워크에서 호출 됩니다.|  
|[CMenu::ModifyMenu](#modifymenu)|지정된 된 위치에 기존 메뉴 항목을 변경합니다.|  
|[CMenu::RemoveMenu](#removemenu)|지정 된 메뉴에서 연결 된 팝업 메뉴는 메뉴 항목을 삭제합니다.|  
|[CMenu::SetDefaultItem](#setdefaultitem)|지정 된 메뉴 항목이 기본 메뉴 항목을 설정합니다.|  
|[CMenu::SetMenuContextHelpId](#setmenucontexthelpid)|메뉴와 연결 되도록 도움말 컨텍스트 ID를 설정 합니다.|  
|[CMenu::SetMenuInfo](#setmenuinfo)|특정 메뉴에서 정보를 설정합니다.|  
|[CMenu::SetMenuItemBitmaps](#setmenuitembitmaps)|지정 된 확인 표시 비트맵 메뉴 항목과 연결합니다.|  
|[CMenu::SetMenuItemInfo](#setmenuiteminfo)|메뉴 항목에 대 한 정보를 변경합니다.|  
|[CMenu::TrackPopupMenu](#trackpopupmenu)|지정된 된 위치에 부동 팝업 메뉴를 표시 하 고 팝업 메뉴에서 항목의 선택 집합을 추적 합니다.|  
|[CMenu::TrackPopupMenuEx](#trackpopupmenuex)|지정된 된 위치에 부동 팝업 메뉴를 표시 하 고 팝업 메뉴에서 항목의 선택 집합을 추적 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CMenu::operator HMENU](#operator_hmenu)|메뉴 개체의 핸들을 검색합니다.|  
|[CMenu::operator! =](#operator_neq)|메뉴의 두 개체가 같지 않은지 확인 합니다.|  
|[CMenu::operator = =](#operator_eq_eq)|메뉴의 두 개체가 같은지 여부를 결정 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMenu::m_hMenu](#m_hmenu)|에 연결 된 Windows 메뉴에 대 한 핸들을 지정 된 `CMenu` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 만들기, 추적, 업데이트 및 삭제 메뉴에 대 한 멤버 함수를 제공 합니다.  
  
 만들기는 `CMenu` 개체에는 로컬 스택 프레임을 호출 `CMenu`의 필요에 따라 새 메뉴를 조작 하는 멤버 함수입니다. 그런 다음, 호출 [CWnd::SetMenu](../../mfc/reference/cwnd-class.md#setmenu) 창 메뉴를 설정 하려면에 대 한 호출 바로 뒤의 `CMenu` 개체의 [분리](#detach) 멤버 함수입니다. `CWnd::SetMenu` 멤버 함수 새로 만들기 메뉴에 창의 메뉴를 설정 하면 창 메뉴 변경 내용을 적용 하려면 다시 그려져 야 하 고 창에는 메뉴의 소유권을 전달 합니다. 에 대 한 호출 **분리** 분리는 `HMENU` 에서 `CMenu` 하므로 개체는 로컬 `CMenu` 변수 범위를 벗어난 전달는 `CMenu` 개체 소멸자가 더 이상 소유 하 고 메뉴를 제거 하려고 시도 하지 않습니다. 메뉴 자체 창이 소멸 될 때 자동으로 삭제 됩니다.  
  
 사용할 수는 [LoadMenuIndirect](#loadmenuindirect) 멤버 함수를 호출 하 여 리소스에서 만든 메뉴 제외 하 고 메모리에서 서식 파일에서 메뉴를 만드는 [LoadMenu](#loadmenu) 관리가 더 쉬워집니다 및 메뉴 리소스를 만들고 메뉴 편집기에서 수정할 수 있습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenu`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="appendmenu"></a>CMenu::AppendMenu  
 메뉴의 끝에 새 항목을 추가 합니다.  
  
```  
BOOL AppendMenu(
    UINT nFlags,  
    UINT_PTR nIDNewItem = 0,  
    LPCTSTR lpszNewItem = NULL);

 
BOOL AppendMenu(
    UINT nFlags,  
    UINT_PTR nIDNewItem,  
    const CBitmap* pBmp);
```  
  
### <a name="parameters"></a>매개 변수  
 `nFlags`  
 메뉴에 추가 될 때 새 메뉴 항목의 상태에 대 한 정보를 지정 합니다. 주의 섹션에 나열 된 값 중 하나 이상이 구성 됩니다.  
  
 `nIDNewItem`  
 새 메뉴 항목의 명령 ID를 지정 또는 `nFlags` 로 설정 된 **MF_POPUP**, 메뉴 핸들 ( `HMENU`) 팝업 메뉴의 합니다. `nIDNewItem` 매개 변수가 무시 됩니다 (필요 하지 않습니다) `nFlags` 로 설정 된 **MF_SEPARATOR**합니다.  
  
 `lpszNewItem`  
 새 메뉴 항목의 내용을 지정합니다. `nFlags` 매개 변수를 해석 하는 `lpszNewItem` 다음과 같은 방식으로:  
  
|nFlags|LpszNewItem의 해석|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|응용 프로그램 메뉴 항목과 연결 된 추가 데이터를 유지 관리 하는 데 사용할 수 있는 응용 프로그램에서 제공한 32 비트 값을 포함 합니다. 이 32 비트 값은 처리 하는 경우 응용 프로그램에 사용할 수 있는 `WM_MEASUREITEM` 및 `WM_DRAWITEM` 메시지입니다. 값에 저장 되는 **itemData** 해당 메시지와 함께 제공 되는 구조체의 멤버입니다.|  
|**MF_STRING**|Null로 끝나는 문자열에 대 한 포인터를 포함합니다. 이 기본 해석 합니다.|  
|**MF_SEPARATOR**|`lpszNewItem` (필요 없음) 매개 변수가 무시 됩니다.|  
  
 *pBmp*  
 가리키는 `CBitmap` 메뉴 항목으로 사용할 수 있는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 응용 프로그램에서 값을 설정 하 여 메뉴 항목의 상태를 지정할 수 `nFlags`합니다. 때 `nIDNewItem` 지정 팝업 메뉴에서 추가 되는 메뉴의 일부가 됩니다. 해당 메뉴 손상 된 경우에 추가 된 메뉴가 제거 됩니다. 추가 된 메뉴가에서 분리 해야는 `CMenu` 충돌을 피하기 위해 개체입니다. **MF_STRING** 및 `MF_OWNERDRAW` 의 비트맵 버전에 대해 올바르지 않은 `AppendMenu`합니다.  
  
 다음 목록에서 설정할 수 있는 플래그에 설명 `nFlags`:  
  
- **MF_CHECKED** 와 토글으로 작동 **MF_UNCHECKED** 항목 옆에 있는 기본 확인 표시를 합니다. 응용 프로그램이 확인 표시 비트맵을 제공 하는 경우 (참조는 [SetMenuItemBitmaps](#setmenuitembitmaps) 멤버 함수), "에 확인 표시가" 비트맵 표시 됩니다.  
  
- **MF_UNCHECKED** 와 토글으로 작동 **MF_CHECKED** 항목 옆에 있는 확인 표시를 제거 합니다. 응용 프로그램이 확인 표시 비트맵을 제공 하는 경우 (참조는 `SetMenuItemBitmaps` 멤버 함수)를 "해제 확인 표시가" 비트맵 표시 됩니다.  
  
- **MF_DISABLED** 를 선택할 수 없는 하지만 dim 하지 않는 메뉴 항목을 사용 하지 않도록 설정 합니다.  
  
- `MF_ENABLED`흐리게 표시 된 상태에서 복원 하 고 선택할 수 있도록 메뉴 항목을 사용할 수 있습니다.  
  
- **MF_GRAYED** 하 고 선택할 수 없는 것을 흐리게 표시 메뉴 항목을 사용 하지 않도록 설정 합니다.  
  
- **MF_MENUBARBREAK** 정적 메뉴 또는 팝업 메뉴에 새 열에 새 줄에는 항목을 배치 합니다. 새 팝업 메뉴 열 구분 세로선으로 기존 열에서 분리 됩니다.  
  
- **MF_MENUBREAK** 정적 메뉴 또는 팝업 메뉴에 새 열에 새 줄에는 항목을 배치 합니다. 열 사이의 구분선 없습니다 배치 됩니다.  
  
- `MF_OWNERDRAW`항목 소유자 그리기 항목 임을 지정 합니다. 메뉴를 소유 하는 창 수신 메뉴는 처음으로 표시 되 면는 `WM_MEASUREITEM` 메뉴 항목의 너비와 높이 검색 하는 메시지입니다. `WM_DRAWITEM` 메시지는 보낸 때마다 소유자는 메뉴 항목의 시각적 모양을 업데이트 해야 합니다. 이 옵션 최상위 메뉴 항목에 대해 올바르지 않습니다.  
  
- **MF_POPUP** 메뉴 항목에 연결 된 팝업 메뉴가 포함 되도록 지정 합니다. ID 매개 변수는 항목에 연결할 수 있는 팝업 메뉴에 대 한 핸들을 지정 합니다. 이 팝업 메뉴 항목에는 최상위 팝업 메뉴 또는 팝업 메뉴 계층 구조를 추가 하는 데 사용 됩니다.  
  
- **MF_SEPARATOR** 가로 구분선을 그립니다. 팝업 메뉴에만 사용할 수 있습니다. 이 줄 흐리게 표시 비활성화 하거나 강조 표시 될 수 없습니다. 다른 매개 변수는 무시 됩니다.  
  
- **MF_STRING** 메뉴 항목 문자열 임을 지정 합니다.  
  
 다음 그룹의 각 상호 배타적인와 함께 사용할 수 있는 플래그를 나열 합니다.  
  
- **MF_DISABLED**, `MF_ENABLED`, 및 **MF_GRAYED**  
  
- **MF_STRING**, `MF_OWNERDRAW`, **MF_SEPARATOR**, 및 비트맵 버전  
  
- **MF_MENUBARBREAK** 및 **MF_MENUBREAK**  
  
- **MF_CHECKED** 및 **MF_UNCHECKED**  
  
 (여부 창이 표시 됩니다) 창이 변경 되, 응용 프로그램에 상주 하는 메뉴 때마다 [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMenu::CreateMenu](#createmenu)합니다.  
  
##  <a name="attach"></a>CMenu::Attach  
 기존 Windows 메뉴에 연결 된 `CMenu` 개체입니다.  
  
```  
BOOL Attach(HMENU hMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 `hMenu`  
 창 메뉴에 대 한 핸들을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 작업에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 메뉴에 이미 연결 되어 있으면이 함수를 호출 하지 않아야는 `CMenu` 개체입니다. 메뉴 핸들에 저장 되는 `m_hMenu` 데이터 멤버입니다.  
  
 조작 하려는 메뉴와 이미 연결 되어 창, 하는 경우 사용할 수 있습니다는 [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu) 함수 메뉴에 대 한 핸들입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&21;](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]  
  
##  <a name="checkmenuitem"></a>CMenu::CheckMenuItem  
 확인 표시를 추가 하거나 팝업 메뉴에서 메뉴 항목에서 확인 표시를 지웁니다.  
  
```  
UINT CheckMenuItem(
    UINT nIDCheckItem,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDCheckItem`  
 메뉴 항목을 확인할 수를 기준으로 지정 `nCheck`합니다.  
  
 `nCheck`  
 메뉴 항목을 확인 하는 방법 및 메뉴에서 항목의 위치를 결정 하는 방법을 지정 합니다. `nCheck` 매개 변수 조합의 수 **MF_CHECKED** 또는 **MF_UNCHECKED** 와 **MF_BYPOSITION** 또는 **MF_BYCOMMAND** 플래그입니다. 비트 OR 연산자를 사용 하 여 이러한 플래그를 결합할 수 있습니다. 다음과 같은 의미가 있습니다.  
  
- **MF_BYCOMMAND** 지정 매개 변수는 기존 메뉴 항목의 명령 ID를 제공 합니다. 이 값이 기본값입니다.  
  
- **MF_BYPOSITION** 지정 매개 변수는 기존 메뉴 항목의 위치를 제공 합니다. 첫 번째 항목이 위치 0에 표시 됩니다.  
  
- **MF_CHECKED** 와 토글으로 작동 **MF_UNCHECKED** 항목 옆에 있는 기본 확인 표시를 합니다.  
  
- **MF_UNCHECKED** 와 토글으로 작동 **MF_CHECKED** 항목 옆에 있는 확인 표시를 제거 합니다.  
  
### <a name="return-value"></a>반환 값  
 항목의 이전 상태: **MF_CHECKED** 또는 **MF_UNCHECKED**, 또는 0xFFFFFFFF 메뉴 항목이 없는 경우.  
  
### <a name="remarks"></a>주의  
 `nIDCheckItem` 매개 변수를 수정할 수는 항목을 지정 합니다.  
  
 `nIDCheckItem` 매개 변수는 메뉴 항목 뿐만 아니라 팝업 메뉴 항목을 식별할 수 있습니다. 특별 한 단계 없이 팝업 메뉴 항목을 확인 해야 합니다. 최상위 메뉴 항목을 확인할 수 없습니다. 연결 된 메뉴 항목 식별자를 없기 때문 위치별 팝업 메뉴 항목을 선택 해야.  
  
### <a name="example"></a>예제  
  예를 참조 [CMenu::GetMenuState](#getmenustate)합니다.  
  
##  <a name="checkmenuradioitem"></a>CMenu::CheckMenuRadioItem  
 지정 된 메뉴 항목을 확인 하 고 라디오 항목을 사용 하면 키를 누릅니다.  
  
```  
BOOL CheckMenuRadioItem(
    UINT nIDFirst,  
    UINT nIDLast,  
    UINT nIDItem,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDFirst`  
 지정 (ID 또는 값에 따라 오프셋으로 `nFlags`) 라디오 단추 그룹의 첫 번째 메뉴 항목입니다.  
  
 `nIDLast`  
 지정 (ID 또는 값에 따라 오프셋으로 `nFlags`) 라디오 단추 그룹의 마지막 메뉴 항목입니다.  
  
 `nIDItem`  
 지정 (ID 또는 값에 따라 오프셋으로 `nFlags`) 라디오 단추와 확인 되는 그룹에 있는 항목입니다.  
  
 `nFlags`  
 해석을 지정 `nIDFirst`, `nIDLast`, 및 `nIDItem` 다음과 같은 방식으로:  
  
|nFlags|해석|  
|------------|--------------------|  
|**MF_BYCOMMAND**|매개 변수가 제공 기존 메뉴 항목의 명령 ID를 지정 합니다. 모두 이것이 기본값 **MF_BYCOMMAND** 나 **MF_BYPOSITION** 설정 됩니다.|  
|**MF_BYPOSITION**|매개 변수가 제공 기존 메뉴 항목의 위치를 지정 합니다. 첫 번째 항목이 위치 0에 표시 됩니다.|  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0  
  
### <a name="remarks"></a>주의  
 같은 시간에이 함수는 다른 모든 메뉴 항목에 연결 된 그룹을 선택 하거나 선택 취소 하며 해당 항목에 대 한 라디오 항목 유형 플래그를 지웁니다. 선택한 항목이 확인 표시 비트맵 대신 라디오 단추 (또는 글머리 기호) 비트맵을 사용 하 여 표시 됩니다.  
  
### <a name="example"></a>예제  
  예를 참조 [ON_COMMAND_RANGE](http://msdn.microsoft.com/library/c52719fc-dd6e-48c9-af79-383f48d608e0)합니다.  
  
##  <a name="cmenu"></a>CMenu::CMenu  
 빈 메뉴를 만들고 연결 하는 `CMenu` 개체입니다.  
  
```  
CMenu();
```  
  
### <a name="remarks"></a>주의  
 메뉴의 만들기 또는 부하 멤버 함수 중 하나를 호출할 때까지 만들어지지 않습니다 **CMenu:**  
  
- [CreateMenu](#createmenu)  
  
- [CreatePopupMenu](#createpopupmenu)  
  
- [LoadMenu](#loadmenu)  
  
- [LoadMenuIndirect](#loadmenuindirect)  
  
- [Attach](#attach)  
  
##  <a name="createmenu"></a>CMenu::CreateMenu  
 메뉴를 만들고 연결 하는 `CMenu` 개체입니다.  
  
```  
BOOL CreateMenu();
```  
  
### <a name="return-value"></a>반환 값  
 메뉴 성공적으로 만들어진 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 메뉴는 처음에 비어 있습니다. 사용 하 여 메뉴 항목을 추가할 수는 `AppendMenu` 또는 `InsertMenu` 멤버 함수입니다.  
  
 창에 할당 되는 메뉴의 경우 창이 소멸 될 때 자동으로 소멸 됩니다 것입니다.  
  
 종료 하기 전에 응용 프로그램의 메뉴 창에 할당 되지 않은 경우에 메뉴와 연결 된 시스템 리소스를 해제 해야 합니다. 응용 프로그램 메뉴를 호출 하 여 해제 된 [DestroyMenu](#destroymenu) 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&22;](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]  
  
##  <a name="createpopupmenu"></a>CMenu::CreatePopupMenu  
 팝업 메뉴를 만들고 연결 하는 `CMenu` 개체입니다.  
  
```  
BOOL CreatePopupMenu();
```  
  
### <a name="return-value"></a>반환 값  
 팝업 메뉴 만들었습니다; 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 메뉴는 처음에 비어 있습니다. 사용 하 여 메뉴 항목을 추가할 수는 `AppendMenu` 또는 `InsertMenu` 멤버 함수입니다. 응용 프로그램 기존 메뉴 또는 팝업 메뉴에 팝업 메뉴를 추가할 수 있습니다. `TrackPopupMenu` 부동 팝업 메뉴로이 메뉴를 표시 하 고 팝업 메뉴 선택 항목을 추적 하기 위해 멤버 함수를 사용할 수 있습니다.  
  
 창에 할당 되는 메뉴의 경우 창이 소멸 될 때 자동으로 소멸 됩니다 것입니다. 메뉴 기존 메뉴에 추가 되는 경우 해당 메뉴 소멸 될 때 자동으로 소멸 됩니다 것입니다.  
  
 종료 하기 전에 응용 프로그램의 메뉴 창에 할당 되지 않은 경우 팝업 메뉴와 연결 된 시스템 리소스를 해제 해야 합니다. 응용 프로그램 메뉴를 호출 하 여 해제 된 [DestroyMenu](#destroymenu) 멤버 함수입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMenu::CreateMenu](#createmenu)합니다.  
  
##  <a name="deletemenu"></a>CMenu::DeleteMenu  
 메뉴에서 항목을 삭제 합니다.  
  
```  
BOOL DeleteMenu(
    UINT nPosition,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPosition`  
 메뉴 항목을 기준으로 삭제 하는 것을 지정 `nFlags`합니다.  
  
 `nFlags`  
 해석 하는 데 사용 됩니다 `nPosition` 다음과 같은 방식으로:  
  
|nFlags|NPosition의 해석|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|매개 변수가 제공 기존 메뉴 항목의 명령 ID를 지정 합니다. 모두 이것이 기본값 **MF_BYCOMMAND** 나 **MF_BYPOSITION** 설정 됩니다.|  
|**MF_BYPOSITION**|매개 변수가 제공 기존 메뉴 항목의 위치를 지정 합니다. 첫 번째 항목이 위치 0에 표시 됩니다.|  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 메뉴 항목에 있는 경우 연결 된 팝업 메뉴에서 `DeleteMenu` 팝업 메뉴에 대 한 핸들을 제거 하 고 팝업 메뉴에서 사용 하는 메모리를 해제 합니다.  
  
 (여부 창이 표시 됩니다) 창이 변경, 호출 하는 응용 프로그램에 상주 하는 메뉴 때마다 [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu)합니다.  
  
##  <a name="deletetempmap"></a>CMenu::DeleteTempMap  
 자동으로 호출는 `CWinApp` 유휴 시간 처리기는 모든 임시 삭제 `CMenu` 가 만든 개체는 [FromHandle](#fromhandle) 멤버 함수입니다.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>주의  
 `DeleteTempMap`임시에 연결 하는 Windows 메뉴 개체를 분리 `CMenu` 개체를 삭제 하기 전에 `CMenu` 개체입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing&23;](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]  
  
##  <a name="destroymenu"></a>CMenu::DestroyMenu  
 메뉴 및 사용 된 모든 Windows 리소스를 삭제 합니다.  
  
```  
BOOL DestroyMenu();
```  
  
### <a name="return-value"></a>반환 값  
 메뉴 소멸 되 고, 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 메뉴에서 분리 되는 `CMenu` 소멸 되기 전에 개체입니다. Windows `DestroyMenu` 함수에서 자동으로 호출 되는 `CMenu` 소멸자입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMenu::CreateMenu](#createmenu)합니다.  
  
##  <a name="detach"></a>CMenu::Detach  
 Windows 메뉴를 분리 한 `CMenu` 개체 핸들을 반환 합니다.  
  
```  
HMENU Detach();
```  
  
### <a name="return-value"></a>반환 값  
 형식의 핸들을 `HMENU`, 성공 하 고 그렇지 않으면 Windows 메뉴에 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 `m_hMenu` 데이터 멤버가로 설정 된 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&21;](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]  
  
##  <a name="drawitem"></a>CMenu::DrawItem  
 소유자가 그린 메뉴 변경의 시각적 측면이 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpDrawItemStruct`  
 에 대 한 포인터는 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) 필요한 드로잉의 종류에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="remarks"></a>주의  
 `itemAction` 의 멤버는 `DRAWITEMSTRUCT` 구조 수행 되는 그리기 작업을 정의 합니다. 소유자 그리기에 대 한 그리기를 구현 하려면이 멤버 함수 재정의 `CMenu` 개체입니다. 응용 프로그램에 제공 된 디스플레이 컨텍스트에 대해 선택한 모든 그래픽 장치 인터페이스 (GDI) 개체를 복원 해야 `lpDrawItemStruct` 이 멤버 함수를 종료 하기 전에 합니다.  
  
 참조 [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) 에 대 한 설명은 `DRAWITEMSTRUCT` 구조입니다.  
  
### <a name="example"></a>예제  
 다음 코드는 MFC에서 [CTRLTEST](../../visual-cpp-samples.md) 샘플:  
  
 [!code-cpp[NVC_MFCWindowing #&24;](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]  
  
##  <a name="enablemenuitem"></a>CMenu::EnableMenuItem  
 사용 하지 않도록 설정, 사용 하거나 메뉴 항목이 흐리게 표시 합니다.  
  
```  
UINT EnableMenuItem(
    UINT nIDEnableItem,  
    UINT nEnable);
```  
  
### <a name="parameters"></a>매개 변수  
 *nIDEnableItem*  
 기준으로 메뉴 항목 사용 가능 하도록 지정 `nEnable`합니다. 이 매개 변수는 팝업 메뉴 항목 뿐 아니라 표준 메뉴 항목에 지정할 수 있습니다.  
  
 `nEnable`  
 수행할 동작을 지정 합니다. 조합 수 **MF_DISABLED**, `MF_ENABLED`, 또는 **MF_GRAYED**와 **MF_BYCOMMAND** 또는 **MF_BYPOSITION**합니다. 비트 OR 연산자를 사용 하 여 이러한 값을 결합할 수 있습니다. 이러한 값에는 다음과 같은 의미가 있습니다.  
  
- **MF_BYCOMMAND** 지정 매개 변수는 기존 메뉴 항목의 명령 ID를 제공 합니다. 이 값이 기본값입니다.  
  
- **MF_BYPOSITION** 지정 매개 변수는 기존 메뉴 항목의 위치를 제공 합니다. 첫 번째 항목이 위치 0에 표시 됩니다.  
  
- **MF_DISABLED** 를 선택할 수 없는 하지만 dim 하지 않는 메뉴 항목을 사용 하지 않도록 설정 합니다.  
  
- `MF_ENABLED`흐리게 표시 된 상태에서 복원 하 고 선택할 수 있도록 메뉴 항목을 사용할 수 있습니다.  
  
- **MF_GRAYED** 하 고 선택할 수 없는 것을 흐리게 표시 메뉴 항목을 사용 하지 않도록 설정 합니다.  
  
### <a name="return-value"></a>반환 값  
 이전 상태 ( **MF_DISABLED**, `MF_ENABLED`, 또는 **MF_GRAYED**) 또는 유효 하지 않은 경우-1입니다.  
  
### <a name="remarks"></a>주의  
 [CreateMenu](#createmenu), [InsertMenu](#insertmenu), [ModifyMenu](#modifymenu), 및 [LoadMenuIndirect](#loadmenuindirect) 멤버 함수는 메뉴 항목의 상태 (설정, 해제 또는 흐리게 표시)을 설정할 수도 있습니다.  
  
 사용 하는 **MF_BYPOSITION** 값에 올바른 사용 하도록 응용 프로그램 필요 `CMenu`합니다. 하는 경우는 `CMenu` 메뉴 모음을 사용 하는 경우 최상위 메뉴 항목 (메뉴 모음에서 항목)에 영향을 받습니다. 위치별 팝업 또는 중첩 된 팝업 메뉴에 있는 항목의 상태를 설정 하려면 응용 프로그램을 지정 해야는 `CMenu` 팝업 메뉴입니다.  
  
 응용 프로그램을 지정는 **MF_BYCOMMAND** 플래그를 Windows에 종속 된 모든 팝업 메뉴 항목을 확인는 `CMenu`; 따라서 존재 하지 않는 메뉴 항목이 중복을 사용 하는 `CMenu` 메뉴 표시줄은 충분 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&25;](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]  
  
##  <a name="fromhandle"></a>CMenu::FromHandle  
 에 대 한 포인터를 반환 합니다.는 `CMenu` 메뉴에 대 한 창 핸들을 지정 된 개체입니다.  
  
```  
static CMenu* PASCAL FromHandle(HMENU hMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 `hMenu`  
 메뉴에 대 한 창 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CMenu` 일시적 또는 영구적 있을 수 있습니다.  
  
### <a name="remarks"></a>주의  
 하는 경우는 `CMenu` Windows 메뉴 개체는 임시 개체가 이미 연결 되지 않은 `CMenu` 개체를 만들어 연결 합니다.  
  
 이 임시 `CMenu` 개체는 응용 프로그램에는 모든 임시 개체는 삭제 되는 시간에 해당 이벤트 루프에서 유휴 시간 전 까지는 유효 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMenu::CreateMenu](#createmenu)합니다.  
  
##  <a name="getdefaultitem"></a>CMenu::GetDefaultItem  
 지정 된 메뉴 항목이 기본 메뉴 항목을 결정합니다.  
  
```  
UINT GetDefaultItem(
    UINT gmdiFlags,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 *gmdiFlags*  
 메뉴 항목에 대 한 함수가 검색 하는 방법을 지정 하는 값입니다. 이 매개 변수 없음,&1; 또는 다음 값의 조합 될 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|**GMDI_GOINTOPOPUPS**|를 기본 항목에 하위 메뉴가 열리면 하나인 경우 함수는 해당 하위 메뉴 재귀적으로 검색 하려면 지정 합니다. 하위 메뉴에 있는 기본 항목이 없는 경우 반환 값의 하위 메뉴를 열고 항목을 식별 합니다.<br /><br /> 기본적으로 함수는 하위 메뉴를 열고 하는 항목 인지에 관계 없이 지정 된 메뉴에서 첫 번째 기본 항목을 반환 합니다.|  
|**GMDI_USEDISABLED**|비활성화 된 경우에 기본 항목을 반환 하는 함수 임을 지정 합니다.<br /><br /> 함수는 기본적으로 사용 안 함 또는 회색으로 표시 된 항목을 건너뜁니다.|  
  
 `fByPos`  
 위치 또는 메뉴 항목의 식별자를 검색할 것인지를 지정 하는 값입니다. 이 매개 변수가 **FALSE**, 반환 됩니다. 그렇지 않으면 위치가 반환 됩니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 반환 값은 식별자 또는 메뉴 항목의 위치입니다. 함수가 실패 한 경우 반환 값은-1입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 함수의 동작을 구현 [GetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647976)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMenu::InsertMenu](#insertmenu)합니다.  
  
##  <a name="getmenucontexthelpid"></a>CMenu::GetMenuContextHelpId  
 ID와 관련 된 상황에 맞는 도움말 검색 `CMenu`합니다.  
  
```  
DWORD GetMenuContextHelpId() const;  
```  
  
### <a name="return-value"></a>반환 값  
 ID가 현재 연결 된 상황에 맞는 도움말 `CMenu` 있으면; 그렇지 않으면&0;입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMenu::InsertMenu](#insertmenu)합니다.  
  
##  <a name="getmenuinfo"></a>CMenu::GetMenuInfo  
 메뉴에 대 한 정보를 검색합니다.  
  
```  
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpcmi`  
 에 대 한 포인터는 [MENUINFO](http://msdn.microsoft.com/library/windows/desktop/ms647575) 메뉴에 대 한 정보가 포함 된 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 반환 값은&0;이 아닌 값입니다. 그렇지 않으면 반환 값은&0;입니다.  
  
### <a name="remarks"></a>주의  
 메뉴에 대 한 정보를 검색 하려면이 함수를 호출 합니다.  
  
##  <a name="getmenuitemcount"></a>CMenu::GetMenuItemCount  
 팝업 또는 최상위 메뉴에서 항목의 수를 결정 합니다.  
  
```  
UINT GetMenuItemCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 메뉴의 항목 수 그렇지 않으면-1입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu)합니다.  
  
##  <a name="getmenuitemid"></a>CMenu::GetMenuItemID  
 에 정의 된 위치에 있는 메뉴 항목에 대 한 메뉴 항목 식별자 `nPos`합니다.  
  
```  
UINT GetMenuItemID(int nPos) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 위치 (0부터 시작) 메뉴 항목의 ID를 검색 하는 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 팝업 메뉴에서 지정된 된 항목에 대 한 항목 ID입니다. 지정된 된 항목 (팝업 메뉴에 있는 항목)가 아니라 팝업 메뉴 이면 반환 값은-1입니다. 경우 `nPos` 에 해당 하는 **구분 기호** 메뉴 항목을 반환 값은 0입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMenu::InsertMenu](#insertmenu)합니다.  
  
##  <a name="getmenuiteminfo"></a>CMenu::GetMenuItemInfo  
 메뉴 항목에 대 한 정보를 검색합니다.  
  
```  
BOOL GetMenuItemInfo(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `uItem`  
 식별자 또는 대 한 정보를 얻을 수 있는 메뉴 항목의 위치입니다. 이 매개 변수의 의미의 값에 따라 달라 집니다 `ByPos`합니다.  
  
 `lpMenuItemInfo`  
 에 대 한 포인터는 [MENUITEMINFO](http://msdn.microsoft.com/library/windows/desktop/ms647578)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], 메뉴에 대 한 정보가 들어 있는 합니다.  
  
 `fByPos`  
 의미를 지정 하는 값 `nIDItem`합니다. 기본적으로 `ByPos` 는 **FALSE**, 메뉴 항목 식별자가 표시 되어 해당 uItem 나타냅니다. 경우 `ByPos` 로 설정 되지 않은 **FALSE**, 메뉴 항목 위치를 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 반환 값은&0;이 아닌 값입니다. 함수가 실패하면 반환 값은&0;입니다. 확장 정보를 가져오려면 오류, Win32 함수를 사용 하 여 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 동작을 구현 하는이 멤버 함수는 Win32 함수의 [GetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms647980)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. MFC 구현에서 `GetMenuItemInfo`, 메뉴에 대 한 핸들을 사용 하지 마십시오.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&26;](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]  
  
##  <a name="getmenustate"></a>CMenu::GetMenuState  
 팝업 메뉴에서 항목의 수 또는 지정 된 메뉴 항목의 상태를 반환합니다.  
  
```  
UINT GetMenuState(
    UINT nID,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nID`  
 메뉴 항목 ID를 기준으로 지정 `nFlags`합니다.  
  
 `nFlags`  
 특성을 지정 `nID`합니다. 다음 값 중 하나일 수 있습니다.  
  
- **MF_BYCOMMAND** 지정 매개 변수는 기존 메뉴 항목의 명령 ID를 제공 합니다. 이 값이 기본값입니다.  
  
- **MF_BYPOSITION** 지정 매개 변수는 기존 메뉴 항목의 위치를 제공 합니다. 첫 번째 항목이 위치 0에 표시 됩니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 항목이 존재 하지 않는 경우에 0xFFFFFFFF 값입니다. 경우 *nId* 팝업 메뉴에서 식별의 상위 바이트 팝업 메뉴에 있는 항목의 수를 포함 하 고 팝업 메뉴와 연결 된 메뉴 플래그를 포함 하는 하위 바이트입니다. 그렇지 않으면 반환 값입니다 (Boolean 또는) 마스크 다음 목록에서 값 (이 마스크는 메뉴의 상태를 설명 하는 항목 *nId* 식별):  
  
- **MF_CHECKED** 와 토글으로 작동 **MF_UNCHECKED** 항목 옆에 있는 기본 확인 표시를 합니다. 응용 프로그램이 확인 표시 비트맵을 제공 하는 경우 (참조는 `SetMenuItemBitmaps` 멤버 함수), "에 확인 표시가" 비트맵 표시 됩니다.  
  
- **MF_DISABLED** 를 선택할 수 없는 하지만 dim 하지 않는 메뉴 항목을 사용 하지 않도록 설정 합니다.  
  
- `MF_ENABLED`흐리게 표시 된 상태에서 복원 하 고 선택할 수 있도록 메뉴 항목을 사용할 수 있습니다. 이 상수의 값 0; 인지 note 이 값을 사용 하는 경우에 실패에 대 한 0에 대 한 응용 프로그램 테스트 하지 해야 합니다.  
  
- **MF_GRAYED** 하 고 선택할 수 없는 것을 흐리게 표시 메뉴 항목을 사용 하지 않도록 설정 합니다.  
  
- **MF_MENUBARBREAK** 정적 메뉴 또는 팝업 메뉴에 새 열에 새 줄에는 항목을 배치 합니다. 새 팝업 메뉴 열 구분 세로선으로 기존 열에서 분리 됩니다.  
  
- **MF_MENUBREAK** 정적 메뉴 또는 팝업 메뉴에 새 열에 새 줄에는 항목을 배치 합니다. 열 사이의 구분선 없습니다 배치 됩니다.  
  
- **MF_SEPARATOR** 가로 구분선을 그립니다. 팝업 메뉴에만 사용할 수 있습니다. 이 줄 흐리게 표시 비활성화 하거나 강조 표시 될 수 없습니다. 다른 매개 변수는 무시 됩니다.  
  
- **MF_UNCHECKED** 와 토글으로 작동 **MF_CHECKED** 항목 옆에 있는 확인 표시를 제거 합니다. 응용 프로그램이 확인 표시 비트맵을 제공 하는 경우 (참조는 `SetMenuItemBitmaps` 멤버 함수)를 "해제 확인 표시가" 비트맵 표시 됩니다. 이 상수의 값 0; 인지 note 이 값을 사용 하는 경우에 실패에 대 한 0에 대 한 응용 프로그램 테스트 하지 해야 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&27;](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]  
  
##  <a name="getmenustring"></a>CMenu::GetMenuString  
 지정 된 메뉴 항목의 레이블이 지정된 된 버퍼에 복사합니다.  
  
```  
int GetMenuString(
    UINT nIDItem,  
    LPTSTR lpString,  
    int nMaxCount,  
    UINT nFlags) const;  
  
int GetMenuString(
    UINT nIDItem,  
    CString& rString,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDItem`  
 값에 따라 메뉴에서 메뉴 항목의 정수 id 또는 메뉴 항목의 오프셋을 지정 `nFlags`합니다.  
  
 `lpString`  
 레이블을 수신 하는 버퍼를 가리킵니다.  
  
 `rString`  
 에 대 한 참조는 `CString` 복사한 메뉴 문자열을 수신 하는 개체입니다.  
  
 `nMaxCount`  
 복사할 레이블의 최대 길이 (문자)에 지정 합니다. 레이블이에 지정 된 최대값 보다 긴 경우 `nMaxCount`, 나머지 문자는 잘립니다.  
  
 `nFlags`  
 해석은 지정 된 `nIDItem` 매개 변수입니다. 다음 값 중 하나일 수 있습니다.  
  
|nFlags|NIDItem의 해석|  
|------------|-------------------------------|  
|**MF_BYCOMMAND**|매개 변수가 제공 기존 메뉴 항목의 명령 ID를 지정 합니다. 모두 이것이 기본값 **MF_BYCOMMAND** 나 **MF_BYPOSITION** 설정 됩니다.|  
|**MF_BYPOSITION**|매개 변수가 제공 기존 메뉴 항목의 위치를 지정 합니다. 첫 번째 항목이 위치 0에 표시 됩니다.|  
  
### <a name="return-value"></a>반환 값  
 실제 null 종결자를 포함 하지 않고는 버퍼에 복사 하는 문자 수를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 `nMaxCount` 문자열 종료 null 문자를 수용 하기 위해 레이블의 문자 수가 보다 하나 더 큰 매개 변수 이어야 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMenu::InsertMenu](#insertmenu)합니다.  
  
##  <a name="getsafehmenu"></a>CMenu::GetSafeHmenu  
 반환 된 `HMENU` 이 래핑됩니다 `CMenu` 개체 또는 **NULL** `CMenu` 포인터.  
  
```  
HMENU GetSafeHmenu() const;  
```  
  
### <a name="example"></a>예제  
  예를 참조 [CMenu::LoadMenu](#loadmenu)합니다.  
  
##  <a name="getsubmenu"></a>CMenu::GetSubMenu  
 검색 된 `CMenu` 팝업 메뉴의 개체입니다.  
  
```  
CMenu* GetSubMenu(int nPos) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 메뉴에 포함 된 팝업 메뉴의 위치를 지정 합니다. 위치 값이 첫 번째 메뉴 항목의 0부터 시작합니다. 이 함수에 팝업 메뉴의 식별자를 사용할 수 없습니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CMenu` 개체 `m_hMenu` 멤버; 지정된 된 위치에 있을 때 팝업 메뉴 팝업 메뉴에 대 한 핸들을 포함 그렇지 않으면 **NULL**합니다. 경우에 `CMenu` 개체가 존재 하지 않는 다음 임시 생성 됩니다. `CMenu` 반환 된 포인터를 저장 해야 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMenu::TrackPopupMenu](#trackpopupmenu)합니다.  
  
##  <a name="insertmenu"></a>CMenu::InsertMenu  
 에 지정 된 위치에 새 메뉴 항목을 삽입 `nPosition` 메뉴 다른 항목으로 이동 합니다.  
  
```  
BOOL InsertMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem = 0,  
    LPCTSTR lpszNewItem = NULL);

 
BOOL InsertMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem,  
    const CBitmap* pBmp);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPosition`  
 삽입할 새 메뉴 항목은 앞의 메뉴 항목을 지정 합니다. `nFlags` 매개 변수를 해석 하는 것 `nPosition` 다음과 같은 방법으로:  
  
|nFlags|NPosition의 해석|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|매개 변수가 제공 기존 메뉴 항목의 명령 ID를 지정 합니다. 모두 이것이 기본값 **MF_BYCOMMAND** 나 **MF_BYPOSITION** 설정 됩니다.|  
|**MF_BYPOSITION**|매개 변수가 제공 기존 메뉴 항목의 위치를 지정 합니다. 첫 번째 항목이 위치 0에 표시 됩니다. 경우 `nPosition` –&1;은 새 메뉴 항목이 메뉴의 끝에 추가 됩니다.|  
  
 `nFlags`  
 지정 방법을 `nPosition` 해석 되 고 메뉴에 추가 될 때 새 메뉴 항목의 상태에 대 한 정보를 지정 합니다. 으로 설정할 수 있는 플래그는 목록에 대 한 참조는 [AppendMenu](#appendmenu) 멤버 함수입니다. 둘 이상의 값을 지정 하려면 비트 OR 연산자를 사용 하 여 결합 하 여 사용 하 여는 **MF_BYCOMMAND** 또는 **MF_BYPOSITION** 플래그입니다.  
  
 `nIDNewItem`  
 새 메뉴 항목의 명령 ID를 지정 또는 `nFlags` 로 설정 된 **MF_POPUP**, 메뉴 핸들 ( `HMENU`)의 팝업 메뉴. `nIDNewItem` 매개 변수가 무시 됩니다 (필요 하지 않습니다) `nFlags` 로 설정 된 **MF_SEPARATOR**합니다.  
  
 `lpszNewItem`  
 새 메뉴 항목의 내용을 지정합니다. `nFlags`해석 하는 데 사용 될 `lpszNewItem` 다음과 같은 방법으로:  
  
|nFlags|LpszNewItem의 해석|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|응용 프로그램 메뉴 항목과 연결 된 추가 데이터를 유지 관리 하는 데 사용할 수 있는 응용 프로그램에서 제공한 32 비트 값을 포함 합니다. 이 32 비트 값은 응용 프로그램에 사용할 수는 **itemData** 에서 제공 하는 구조체의 멤버는 [WM_MEASUREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775925) 및 [WM_DRAWITEM](http://msdn.microsoft.com/library/windows/desktop/bb775923) 메시지입니다. 이러한 메시지는 메뉴 항목이 처음 표시 되거나 변경 될 때 전송 됩니다.|  
|**MF_STRING**|Null로 끝나는 문자열에 대 한 긴 포인터를 포함합니다. 이 기본 해석 합니다.|  
|**MF_SEPARATOR**|`lpszNewItem` (필요 없음) 매개 변수가 무시 됩니다.|  
  
 *pBmp*  
 가리키는 `CBitmap` 메뉴 항목으로 사용할 수 있는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 응용 프로그램에서 값을 설정 하 여 메뉴 항목의 상태를 지정할 수 `nFlags`합니다.  
  
 (여부 창이 표시 됩니다) 창이 변경 되, 응용 프로그램에 상주 하는 메뉴 때마다 `CWnd::DrawMenuBar`합니다.  
  
 때 `nIDNewItem` 지정 팝업 메뉴에서 삽입 되는 메뉴의 일부가 됩니다. 해당 메뉴 손상 된 경우에 삽입 된 메뉴 소멸 됩니다. 디스크 삽입된 메뉴를 분리 해야는 `CMenu` 충돌을 피하기 위해 개체입니다.  
  
 활성 다중 문서 MDI (인터페이스) 자식 창 최대화 되 고 응용 프로그램을 삽입 하면 팝업 메뉴가 MDI 응용 프로그램의 메뉴에이 함수를 호출 하 고 지정 하 여는 **MF_BYPOSITION** 플래그를 메뉴는 예상 보다 더 멀리 남아 있는 한 위치를 삽입 합니다. 이 컨트롤 메뉴 활성 MDI 자식 창의 MDI 프레임 창의 메뉴 표시줄의 첫 번째 위치에 삽입 됩니다 때문에 발생 합니다. 메뉴를 올바르게 배치 하려면 응용 프로그램 그렇지 않은 경우에 사용 되는 위치 값에 1을 추가 해야 합니다. 응용 프로그램이 사용할 수는 **WM_MDIGETACTIVE** 현재 활성 자식 창 최대화 되었는지 여부를 결정 하는 메시지입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&28;](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]  
  
##  <a name="insertmenuitem"></a>CMenu::InsertMenuItem  
 메뉴에 지정된 된 위치에 새 메뉴 항목을 삽입합니다.  
  
```  
BOOL InsertMenuItem(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `uItem`  
 설명을 참조 `uItem` 에서 [InsertMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647988) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `lpMenuItemInfo`  
 설명을 참조 `lpmii` 에서 **InsertMenuItem** 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `fByPos`  
 설명을 참조 `fByPosition` 에서 **InsertMenuItem** 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 [InsertMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647988)에서 설명 된 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="loadmenu"></a>CMenu::LoadMenu  
 응용 프로그램의 실행 파일에서 메뉴 리소스를 로드 하 고 연결 하는 `CMenu` 개체입니다.  
  
```  
BOOL LoadMenu(LPCTSTR lpszResourceName);  
BOOL LoadMenu(UINT nIDResource);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszResourceName`  
 로드 하는 메뉴 리소스의 이름을 포함 하는 null로 끝나는 문자열을 가리킵니다.  
  
 `nIDResource`  
 로드 하는 메뉴 리소스의 메뉴 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 메뉴 리소스를 성공적으로 로드 한 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 종료 하기 전에 응용 프로그램의 메뉴 창에 할당 되지 않은 경우에 메뉴와 연결 된 시스템 리소스를 해제 해야 합니다. 응용 프로그램 메뉴를 호출 하 여 해제 된 [DestroyMenu](#destroymenu) 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&29;](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]  
  
##  <a name="loadmenuindirect"></a>CMenu::LoadMenuIndirect  
 메모리에 메뉴 서식 파일에서 리소스를 로드 하 고 연결 하는 `CMenu` 개체입니다.  
  
```  
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpMenuTemplate*  
 메뉴 서식 파일을 가리키는 (단일은 [MENUITEMTEMPLATEHEADER](http://msdn.microsoft.com/library/windows/desktop/ms647583) 구조와 하나 이상의 컬렉션 [MENUITEMTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms647581) 구조). 이러한 두 구조에 대 한 자세한 내용은 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 메뉴 리소스를 성공적으로 로드 한 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 메뉴 서식 파일에는 헤더와 하나 이상의 컬렉션은 [MENUITEMTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms647581) 구조에는 각각 하나 이상의 메뉴 항목 및 팝업 메뉴를 포함할 수 있습니다.  
  
 버전 번호는 0 이어야 합니다.  
  
 **mtOption** 플래그를 포함 해야 **MF_END** 팝업 목록에서 마지막 항목에 대 한 고 주 목록에서 마지막 항목에 대 한 합니다. 참조는 `AppendMenu` 다른 플래그에 대 한 멤버 함수입니다. **mtId** 에서 멤버를 생략 해야는 **MENUITEMTEMPLATE** 때 구조 **MF_POPUP** 에 지정 된 **mtOption**합니다.  
  
 에 할당 된 공간에서 **MENUITEMTEMPLATE** 구조에 충분 해야 합니다. **mtString** 를 null로 끝나는 문자열로 메뉴 항목의 이름을 포함 하도록 합니다.  
  
 종료 하기 전에 응용 프로그램의 메뉴 창에 할당 되지 않은 경우에 메뉴와 연결 된 시스템 리소스를 해제 해야 합니다. 응용 프로그램 메뉴를 호출 하 여 해제 된 [DestroyMenu](#destroymenu) 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&30;](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]  
  
##  <a name="m_hmenu"></a>CMenu::m_hMenu  
 지정 된 `HMENU` 창 메뉴의 핸들에 연결 된는 `CMenu` 개체입니다.  
  
```  
HMENU m_hMenu;  
```  
  
### <a name="example"></a>예제  
  예를 참조 [CMenu::LoadMenu](#loadmenu)합니다.  
  
##  <a name="measureitem"></a>CMenu::MeasureItem  
 소유자 그리기 스타일으로 메뉴 만들어질 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpMeasureItemStruct`  
 에 대 한 포인터는 `MEASUREITEMSTRUCT` 구조입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 기본적으로 아무 작업도 수행합니다. 이 멤버 함수를 재정의 하 고 입력의 `MEASUREITEMSTRUCT` 구조를 메뉴의 차원의 Windows 사용자에 게 알립니다.  
  
 참조 [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) 에 대 한 설명은 `MEASUREITEMSTRUCT` 구조입니다.  
  
### <a name="example"></a>예제  
 다음 코드는 MFC에서 [CTRLTEST](../../visual-cpp-samples.md) 샘플:  
  
 [!code-cpp[NVC_MFCWindowing #&31;](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]  
  
##  <a name="modifymenu"></a>CMenu::ModifyMenu  
 로 지정 된 위치에 있는 기존 메뉴 항목을 변경 `nPosition`합니다.  
  
```  
BOOL ModifyMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem = 0,  
    LPCTSTR lpszNewItem = NULL);

 
BOOL ModifyMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem,  
    const CBitmap* pBmp);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPosition`  
 메뉴 항목을 변경할 수를 지정 합니다. `nFlags` 매개 변수를 해석 하는 것 `nPosition` 다음과 같은 방법으로:  
  
|nFlags|NPosition의 해석|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|매개 변수가 제공 기존 메뉴 항목의 명령 ID를 지정 합니다. 모두 이것이 기본값 **MF_BYCOMMAND** 나 **MF_BYPOSITION** 설정 됩니다.|  
|**MF_BYPOSITION**|매개 변수가 제공 기존 메뉴 항목의 위치를 지정 합니다. 첫 번째 항목이 위치 0에 표시 됩니다.|  
  
 `nFlags`  
 지정 방법을 `nPosition` 해석 되 고 메뉴 항목에 대해 변경 하는 방법에 대 한 정보를 제공 합니다. 으로 설정할 수 있는 플래그는 목록에 대 한 참조는 [AppendMenu](#appendmenu) 멤버 함수입니다.  
  
 `nIDNewItem`  
 수정 된 메뉴 항목의 명령 ID를 지정 또는 `nFlags` 로 설정 된 **MF_POPUP**, 메뉴 핸들 ( `HMENU`) 팝업 메뉴의 합니다. `nIDNewItem` 매개 변수가 무시 됩니다 (필요 하지 않습니다) `nFlags` 로 설정 된 **MF_SEPARATOR**합니다.  
  
 `lpszNewItem`  
 새 메뉴 항목의 내용을 지정합니다. `nFlags` 매개 변수를 해석 하는 것 `lpszNewItem` 다음과 같은 방법으로:  
  
|nFlags|LpszNewItem의 해석|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|응용 프로그램 메뉴 항목과 연결 된 추가 데이터를 유지 관리 하는 데 사용할 수 있는 응용 프로그램에서 제공한 32 비트 값을 포함 합니다. 이 32 비트 값은 처리 하는 경우 응용 프로그램에 사용할 수 있는 **MF_MEASUREITEM** 및 **MF_DRAWITEM**합니다.|  
|**MF_STRING**|또는 null로 끝나는 문자열에 대 한 긴 포인터를 포함 한 `CString`합니다.|  
|**MF_SEPARATOR**|`lpszNewItem` (필요 없음) 매개 변수가 무시 됩니다.|  
  
 *pBmp*  
 가리키는 `CBitmap` 메뉴 항목으로 사용할 수 있는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 값을 설정 하 여 메뉴 항목의 새 상태를 지정 하는 응용 프로그램 `nFlags`합니다. 이 함수는 메뉴 항목과 연결 된 팝업 메뉴를 대체 하는 경우 이전 팝업 메뉴를 제거 하 고 팝업 메뉴에서 사용 하는 메모리를 해제 합니다.  
  
 때 `nIDNewItem` 지정 팝업 메뉴에서 삽입 되는 메뉴의 일부가 됩니다. 해당 메뉴 손상 된 경우에 삽입 된 메뉴 소멸 됩니다. 디스크 삽입된 메뉴를 분리 해야는 `CMenu` 충돌을 피하기 위해 개체입니다.  
  
 (여부 창이 표시 됩니다) 창이 변경 되, 응용 프로그램에 상주 하는 메뉴 때마다 `CWnd::DrawMenuBar`합니다. 기존 메뉴 항목의 특성을 변경 하려면 속도가 빠르므로 사용 하 여 `CheckMenuItem` 및 `EnableMenuItem` 멤버 함수입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMenu::InsertMenu](#insertmenu)합니다.  
  
##  <a name="operator_hmenu"></a>CMenu::operator HMENU  
 이 연산자를 사용 하 여 핸들을 검색 하는 `CMenu` 개체입니다.  
  
```  
operator HMENU() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하는 경우의 핸들은 `CMenu` 그렇지 그렇지 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 Windows Api를 직접 호출 하 여 핸들을 사용할 수 있습니다.  
  
##  <a name="operator_neq"></a>CMenu::operator! =  
 두 개의 메뉴가 다릅니다 논리적으로 결정 합니다.  
  
```  
BOOL operator!=(const CMenu& menu) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `menu`  
 A `CMenu` 비교할 개체입니다.  
  
### <a name="remarks"></a>주의  
 메뉴 개체를 왼쪽에서 오른쪽의 메뉴 개체와 같지 인지 테스트 합니다.  
  
##  <a name="operator_eq_eq"></a>CMenu::operator = =  
 두 개의 메뉴는 논리적으로 동일한 여부를 확인 합니다.  
  
```  
BOOL operator==(const CMenu& menu) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `menu`  
 A `CMenu` 비교할 개체입니다.  
  
### <a name="remarks"></a>주의  
 왼쪽 메뉴 개체와 같은지 여부를 테스트 (의 측면에서 `HMENU` 값) 오른쪽의 메뉴에 있습니다.  
  
##  <a name="removemenu"></a>CMenu::RemoveMenu  
 메뉴에서 연결 된 팝업 메뉴는 메뉴 항목을 삭제합니다.  
  
```  
BOOL RemoveMenu(
    UINT nPosition,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPosition`  
 메뉴 항목을 제거할 수를 지정 합니다. `nFlags` 매개 변수를 해석 하는 것 `nPosition` 다음과 같은 방법으로:  
  
|nFlags|NPosition의 해석|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|매개 변수가 제공 기존 메뉴 항목의 명령 ID를 지정 합니다. 모두 이것이 기본값 **MF_BYCOMMAND** 나 **MF_BYPOSITION** 설정 됩니다.|  
|**MF_BYPOSITION**|매개 변수가 제공 기존 메뉴 항목의 위치를 지정 합니다. 첫 번째 항목이 위치 0에 표시 됩니다.|  
  
 `nFlags`  
 지정 방법을 `nPosition` 해석 됩니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 팝업 메뉴에 대 한 핸들의 메뉴를 다시 사용할 수 있으므로 삭제 되지 않습니다. 이 함수를 호출 하기 전에 응용 프로그램이 호출할 수는 `GetSubMenu` 팝업을 검색 하려면 멤버 함수 `CMenu` 다시 사용할 수 있도록 하는 개체입니다.  
  
 (여부 창이 표시 됩니다) 창이 변경, 호출 하는 응용 프로그램에 상주 하는 메뉴 때마다 `CWnd::DrawMenuBar`합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMenu::InsertMenu](#insertmenu)합니다.  
  
##  <a name="setdefaultitem"></a>CMenu::SetDefaultItem  
 지정 된 메뉴 항목이 기본 메뉴 항목을 설정합니다.  
  
```  
BOOL SetDefaultItem(
    UINT uItem,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `uItem`  
 식별자 또는 새 기본 메뉴 항목 또는-1은 기본 항목이의 위치입니다. 이 매개 변수의 의미의 값에 따라 달라 집니다 `fByPos`합니다.  
  
 `fByPos`  
 의미를 지정 하는 값 `uItem`합니다. 이 매개 변수가 **FALSE**, `uItem` 메뉴 항목 식별자입니다. 에 메뉴 항목 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 반환 값은&0;이 아닌 값입니다. 함수가 실패하면 반환 값은&0;입니다. 확장 정보를 가져오려면 오류, Win32 함수를 사용 하 여 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 함수의 동작을 구현 [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMenu::InsertMenu](#insertmenu)합니다.  
  
##  <a name="setmenucontexthelpid"></a>CMenu::SetMenuContextHelpId  
 와 도움말 컨텍스트 ID를 연결 `CMenu`합니다.  
  
```  
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwContextHelpId`  
 상황에 맞는 도움말 ID와 연결할 `CMenu`합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0  
  
### <a name="remarks"></a>주의  
 이 식별자를 공유 하는 메뉴의 모든 항목-도움말 컨텍스트 식별자는 개별 메뉴 항목에 연결할 수 없는 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMenu::InsertMenu](#insertmenu)합니다.  
  
##  <a name="setmenuinfo"></a>CMenu::SetMenuInfo  
 메뉴에 대 한 정보를 설정합니다.  
  
```  
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpcmi`  
 에 대 한 포인터는 [MENUINFO](http://msdn.microsoft.com/library/windows/desktop/ms647575) 메뉴에 대 한 정보가 포함 된 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 반환 값은&0;이 아닌 값입니다. 그렇지 않으면 반환 값은&0;입니다.  
  
### <a name="remarks"></a>주의  
 메뉴에 대 한 특정 정보를 설정 하려면이 함수를 호출 합니다.  
  
##  <a name="setmenuitembitmaps"></a>CMenu::SetMenuItemBitmaps  
 지정한 비트맵 메뉴 항목과 연결합니다.  
  
```  
BOOL SetMenuItemBitmaps(
    UINT nPosition,  
    UINT nFlags,  
    const CBitmap* pBmpUnchecked,  
    const CBitmap* pBmpChecked);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPosition`  
 메뉴 항목을 변경할 수를 지정 합니다. `nFlags` 매개 변수를 해석 하는 것 `nPosition` 다음과 같은 방법으로:  
  
|nFlags|NPosition의 해석|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|매개 변수가 제공 기존 메뉴 항목의 명령 ID를 지정 합니다. 모두 이것이 기본값 **MF_BYCOMMAND** 나 **MF_BYPOSITION** 설정 됩니다.|  
|**MF_BYPOSITION**|매개 변수가 제공 기존 메뉴 항목의 위치를 지정 합니다. 첫 번째 항목이 위치 0에 표시 됩니다.|  
  
 `nFlags`  
 지정 방법을 `nPosition` 해석 됩니다.  
  
 `pBmpUnchecked`  
 검사 되지 않습니다 메뉴 항목에 사용할 비트맵을 지정 합니다.  
  
 `pBmpChecked`  
 확인란이 선택 된 메뉴 항목에 사용할 비트맵을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 메뉴 항목 선택 하거나 선택을 취소할 인지 Windows 메뉴 항목 옆에 있는 적절 한 비트맵을 표시 합니다.  
  
 어느 경우 `pBmpUnchecked` 또는 `pBmpChecked` 는 **NULL**, Windows 해당 특성에 대 한 메뉴 항목 옆에 있는 아무 것도 표시 합니다. 매개 변수가 모두 **NULL**, 항목이 선택 되 고 항목이 선택 되지 않은 경우 확인 표시를 제거 하는 경우 Windows에서는 기본 확인 표시를 사용 합니다.  
  
 메뉴를 소멸 시킬 때 이러한 비트맵은 제거 되지 않습니다. 응용 프로그램 파기 해야 합니다.  
  
 Windows **GetMenuCheckMarkDimensions** 함수는 메뉴 항목에 사용 되는 기본 확인란의 크기를 검색 합니다. 응용 프로그램 이러한 값을 사용 하 여이 함수와 함께 제공 된 비트맵에 대 한 적절 한 크기를 결정 합니다. 크기를 가져오고 사용자 비트맵을 만들 설정 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&32;](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing #&33;](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]  
  
##  <a name="setmenuiteminfo"></a>CMenu::SetMenuItemInfo  
 메뉴 항목에 대 한 정보를 변경합니다.  
  
```  
BOOL SetMenuItemInfo(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `uItem`  
 설명을 참조 `uItem` 에서 [SetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms648001) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `lpMenuItemInfo`  
 설명을 참조 `lpmii` 에서 **SetMenuItemInfo** 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `fByPos`  
 설명을 참조 `fByPosition` 에서 **SetMenuItemInfo** 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 [SetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms648001)에서 설명 된 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="trackpopupmenu"></a>CMenu::TrackPopupMenu  
 지정된 된 위치에 부동 팝업 메뉴를 표시 하 고 팝업 메뉴에서 항목의 선택 집합을 추적 합니다.  
  
```  
BOOL TrackPopupMenu(
    UINT nFlags,  
    int x,  
    int y,  
    CWnd* pWnd,  
    LPCRECT lpRect = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `nFlags`  
 화면 위치와 마우스 위치 플래그를 지정합니다. 참조 [TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) 목록은 사용 가능한 플래그입니다.  
  
 *x*  
 팝업 메뉴의 가로 화면 좌표 위치를 지정합니다. 값에 따라는 `nFlags` 매개 변수를 메뉴 왼쪽, 오른쪽 맞춤, 또는이 위치를 기준으로 가운데 맞춤 될 수 있습니다.  
  
 *y*  
 화면의 맨 위에 있는 메뉴의 화면 좌표에서 세로 위치를 지정합니다.  
  
 `pWnd`  
 팝업 메뉴를 소유 하는 창을 식별 합니다. 이 매개 변수 수 없습니다 **NULL**, 경우에는 **TPM_NONOTIFY** 플래그를 지정 합니다. 이 창은 수신 모든 **WM_COMMAND** 메뉴에서 메시지입니다. Windows 버전 3.1 이상에서 창에서 수신 하지 **WM_COMMAND** 될 때까지 메시지 `TrackPopupMenu` 를 반환 합니다. Windows 3.0 창 받습니다 **WM_COMMAND** 하기 전에 메시지 `TrackPopupMenu` 를 반환 합니다.  
  
 `lpRect`  
 무시됩니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드 호출의 결과 반환 합니다. [TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 부동 팝업 메뉴는 화면에서 아무 곳 이나 나타날 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&34;](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]  
  
##  <a name="trackpopupmenuex"></a>CMenu::TrackPopupMenuEx  
 지정된 된 위치에 부동 팝업 메뉴를 표시 하 고 팝업 메뉴에서 항목의 선택 집합을 추적 합니다.  
  
```  
BOOL TrackPopupMenuEx(
    UINT fuFlags,  
    int x,  
    int y,  
    CWnd* pWnd,  
    LPTPMPARAMS lptpm);
```  
  
### <a name="parameters"></a>매개 변수  
 `fuFlags`  
 확장된 메뉴에 대 한 다양 한 기능을 지정합니다. 모든 값의 목록 및 그 의미에 대 한 참조 [TrackPopupMenuEx](http://msdn.microsoft.com/library/windows/desktop/ms648003)합니다.  
  
 *x*  
 팝업 메뉴의 가로 화면 좌표 위치를 지정합니다.  
  
 *y*  
 화면의 맨 위에 있는 메뉴의 화면 좌표에서 세로 위치를 지정합니다.  
  
 `pWnd`  
 팝업 메뉴를 소유 하 고 생성된 된 메뉴에서 메시지를 수신 창에 대 한 포인터입니다. 이 창은 현재 응용 프로그램에서 모든 창 수는 있지만 안 **NULL**합니다. 지정 하는 경우 **TPM_NONOTIFY** 에 `fuFlags` 매개 변수, 함수를 모든 메시지를 보내지 않습니다 `pWnd`합니다. 이 함수에서 가리키는 창에 대 한 반환 해야 `pWnd` 받을 수는 **WM_COMMAND** 메시지입니다.  
  
 *lptpm*  
 에 대 한 포인터는 [TPMPARAMS](http://msdn.microsoft.com/library/windows/desktop/ms647586) 메뉴 화면 영역을 지정 하는 구조 겹치지 않아야 합니다. 이 매개 변수 수 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 하는 경우 **TPM_RETURNCMD** 에 `fuFlags` 매개 변수, 반환 값은 사용자가 선택한 항목의 메뉴 항목 식별자입니다. 선택 하지 않고 사용자가 메뉴를 취소 하거나 오류가 발생 하는 경우 반환 값은 0입니다.  
  
 지정 하지 않으면 **TPM_RETURNCMD** 에 `fuFlags` 함수가 성공 하면 0이 아닌 값 또는 0 매개 변수, 반환 값은 실패 하는 경우. 확장 정보를 가져오려면 오류, 호출 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)합니다.  
  
### <a name="remarks"></a>주의  
 부동 팝업 메뉴는 화면에서 아무 곳 이나 나타날 수 있습니다. 팝업 메뉴를 만들 때 오류 처리에 대 한 자세한 내용은 참조 하십시오. [TrackPopupMenuEx](http://msdn.microsoft.com/library/windows/desktop/ms648003)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CTRLTEST](../../visual-cpp-samples.md)   
 [MFC 샘플 DYNAMENU](../../visual-cpp-samples.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)

