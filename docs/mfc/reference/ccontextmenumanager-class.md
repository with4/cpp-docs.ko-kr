---
title: CContextMenuManager 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::AddMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuById
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuByName
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuNames
- AFXCONTEXTMENUMANAGER/CContextMenuManager::LoadState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ResetState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SaveState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SetDontCloseActiveMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ShowPopupMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::TrackPopupMenu
dev_langs:
- C++
helpviewer_keywords:
- CContextMenuManager [MFC], CContextMenuManager
- CContextMenuManager [MFC], AddMenu
- CContextMenuManager [MFC], GetMenuById
- CContextMenuManager [MFC], GetMenuByName
- CContextMenuManager [MFC], GetMenuNames
- CContextMenuManager [MFC], LoadState
- CContextMenuManager [MFC], ResetState
- CContextMenuManager [MFC], SaveState
- CContextMenuManager [MFC], SetDontCloseActiveMenu
- CContextMenuManager [MFC], ShowPopupMenu
- CContextMenuManager [MFC], TrackPopupMenu
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1eb3bb0d96723f14f6dec56853d52860f0568c03
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ccontextmenumanager-class"></a>CContextMenuManager 클래스
`CContextMenuManager` 개체 관리 바로 가기 메뉴, 상황에 맞는 메뉴 라고도 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CContextMenuManager : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CContextMenuManager::CContextMenuManager](#ccontextmenumanager)|`CContextMenuManager` 개체를 생성합니다.|  
|`CContextMenuManager::~CContextMenuManager`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CContextMenuManager::AddMenu](#addmenu)|새 바로 가기 메뉴를 추가합니다.|  
|[CContextMenuManager::GetMenuById](#getmenubyid)|제공 된 리소스 ID와 연결 된 메뉴에 대 한 핸들 반환|  
|[CContextMenuManager::GetMenuByName](#getmenubyname)|제공 된 메뉴 이름과 일치 하는 메뉴에 대 한 핸들을 반환 합니다.|  
|[CContextMenuManager::GetMenuNames](#getmenunames)|메뉴 이름 목록을 반환합니다.|  
|[CContextMenuManager::LoadState](#loadstate)|Windows 레지스트리에 저장 된 바로 가기 메뉴를 로드 합니다.|  
|[CContextMenuManager::ResetState](#resetstate)|상황에 맞는 메뉴 관리자에서 바로 가기 메뉴를 지웁니다.|  
|[CContextMenuManager::SaveState](#savestate)|바로 가기 메뉴를 Windows 레지스트리에 저장합니다.|  
|[CContextMenuManager::SetDontCloseActiveMenu](#setdontcloseactivemenu)|컨트롤 여부는 `CContextMenuManager` 새 바로 가기 메뉴를 표시 하는 경우 현재 바로 가기 메뉴를 닫습니다.|  
|[CContextMenuManager::ShowPopupMenu](#showpopupmenu)|지정 된 바로 가기 메뉴를 표시합니다.|  
|[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)|지정 된 바로 가기 메뉴를 표시합니다. 선택한 메뉴 명령의 인덱스를 반환합니다.|  
  
## <a name="remarks"></a>설명  
 `CContextMenuManager` 바로 가기 메뉴를 관리 하 고 일관 된 모양이 있는지 확인 합니다.  
  
 만들지 마십시오는 `CContextMenuManager` 수동으로 개체입니다. 응용 프로그램의 프레임 워크 만듭니다는 `CContextMenuManager` 개체입니다. 하지만 호출 해야 [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) 응용 프로그램을 초기화할 경우. 컨텍스트 관리자를 초기화 한 다음 메서드를 사용 하 여 [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) 응용 프로그램에 대 한 컨텍스트 관리자에 대 한 포인터를 가져올 수 있습니다.  
  
 런타임 시 호출 하 여 바로 가기 메뉴를 만들 수 `AddMenu`합니다. 첫 번째 수신 사용자 입력 없이 메뉴를 표시 하려면 호출 `ShowPopupMenu`합니다. `TrackPopupMenu` 메뉴 만들기 및 사용자 입력을 대기 하려면이 사용 됩니다. `TrackPopupMenu` 사용자 아무 것도 선택 하지 않고 종료 된 경우에 선택한 명령이 나 0의 인덱스를 반환 합니다.  
  
 `CContextMenuManager` 도 저장 하 고 Windows 레지스트리에 해당 상태를 로드할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 메뉴를 추가 하는 방법을 `CContextMenuManager` 개체 및 활성 팝업 메뉴 닫기 방법 때는 `CContextMenuManager` 새 팝업 메뉴를 표시 하는 개체입니다. 이 코드 조각은의 일부인는 [사용자 지정 페이지 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CContextMenuManager`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcontextmenumanager.h  
  
##  <a name="addmenu"></a>  CContextMenuManager::AddMenu  
 새 바로 가기 메뉴를 추가 하는 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)합니다.  
  
```  
BOOL AddMenu(
    UINT uiMenuNameResId,  
    UINT uiMenuResId);

 
BOOL AddMenu(
    LPCTSTR lpszName,  
    UINT uiMenuResId);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiMenuNameResId`  
 새 메뉴 이름을 포함 하는 문자열에 대 한 리소스 ID입니다.  
  
 [in] `uiMenuResId`  
 메뉴 리소스 id입니다.  
  
 [in] `lpszName`  
 새 메뉴 이름을 포함 하는 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 0이 아닌 메서드가 실패 하는 경우 0입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 실패 하는 경우 `uiMenuResId` 유효 하지 않거나 경우 이름이 같은 다른 메뉴에 이미 포함 되어는 `CContextMenuManager`합니다.  
  
##  <a name="ccontextmenumanager"></a>  CContextMenuManager::CContextMenuManager  
 생성 된 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) 개체입니다.  
  
```  
CContextMenuManager();
```  
  
### <a name="remarks"></a>설명  
 대부분의 경우에서 만들지 마십시오는 `CContextMenuManager` 수동으로 합니다. 응용 프로그램의 프레임 워크 만듭니다는 `CContextMenuManager` 개체입니다. 호출 해야 [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) 응용 프로그램을 초기화 하는 중입니다. 컨텍스트 관리자에 대 한 포인터를 가져오려면, 호출 [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager)합니다.  
  
##  <a name="getmenubyid"></a>  CContextMenuManager::GetMenuById  
 Id가 지정 된 리소스 ID와 연결 된 메뉴에 대 한 핸들을 반환 합니다.  
  
```  
HMENU GetMenuById(UINT nMenuResId) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nMenuResId`  
 메뉴에 대 한 리소스 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 연결 된 메뉴에 대 한 핸들 또는 `NULL` 메뉴를 찾을 수 없는 경우.  
  
##  <a name="getmenubyname"></a>  CContextMenuManager::GetMenuByName  
 특정 메뉴에 대 한 핸들을 반환합니다.  
  
```  
HMENU GetMenuByName(
    LPCTSTR lpszName,  
    UINT* puiOrigResID = NULL) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszName`  
 검색할 메뉴의 이름을 포함 하는 문자열입니다.  
  
 [out] `puiOrigResID`  
 `UINT`에 대한 포인터입니다. 경우이 매개 변수에 지정된 된 메뉴의 리소스 ID를 포함 찾을 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 이름과 일치 하는 메뉴에 대 한 핸들 `lpszName`합니다. `NULL` 이라는 메뉴가 없는 경우 `lpszName`합니다.  
  
### <a name="remarks"></a>설명  
 일치 하는 메뉴 발견 되 면 `lpszName`, `GetMenuByName` 매개 변수에서 메뉴 리소스 ID를 저장 `puiOrigResID`합니다.  
  
##  <a name="getmenunames"></a>  CContextMenuManager::GetMenuNames  
 메뉴 이름에 추가 된 목록을 반환 하는 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)합니다.  
  
```  
void GetMenuNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `listOfNames`  
 에 대 한 참조는 [CStringList](../../mfc/reference/cstringlist-class.md) 매개 변수입니다. 이 메서드는이 매개 변수에 메뉴 이름 목록이 씁니다.  
  
##  <a name="loadstate"></a>  CContextMenuManager::LoadState  
 와 관련 된 정보를 로드는 [CContextMenuManager 클래스](../../mfc/reference/ccontextmenumanager-class.md) Windows 레지스트리에서 합니다.  
  
```  
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 레지스트리 키의 상대 경로 포함 하는 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 `lpszProfileName` 매개 변수는 레지스트리 항목에 대 한 절대 경로가 아닙니다. 응용 프로그램에 대 한 기본 레지스트리 키의 끝에 추가 하는 상대 경로 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) 및 [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) 각각.  
  
 메서드를 사용 하 여 [CContextMenuManager::SaveState](#savestate) 바로 가기 메뉴를 레지스트리에 저장 합니다.  
  
##  <a name="resetstate"></a>  CContextMenuManager::ResetState  
 와 연결 된 바로 가기 메뉴에서 모든 항목이 제거 된 [CContextMenuManager 클래스](../../mfc/reference/ccontextmenumanager-class.md)합니다.  
  
```  
virtual BOOL ResetState();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 메서드가 성공 하면 `FALSE` 오류가 발생 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드가 팝업 메뉴를 지우고에서 제거 된 `CContextMenuManager`합니다.  
  
##  <a name="savestate"></a>  CContextMenuManager::SaveState  
 와 관련 된 정보를 저장 하는 [CContextMenuManager 클래스](../../mfc/reference/ccontextmenumanager-class.md) Windows 레지스트리에 합니다.  
  
```  
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszProfileName`  
 레지스트리 키의 상대 경로 포함 하는 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 `lpszProfileName` 매개 변수는 레지스트리 항목에 대 한 절대 경로가 아닙니다. 응용 프로그램에 대 한 기본 레지스트리 키의 끝에 추가 하는 상대 경로 를 가져오거나 기본 레지스트리 키를 설정 하려면 메서드를 사용 하 여 [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) 및 [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) 각각.  
  
 메서드를 사용 하 여 [CContextMenuManager::LoadState](#loadstate) 레지스트리에서 바로 가기 메뉴를 로드할 수 있습니다.  
  
##  <a name="setdontcloseactivemenu"></a>  CContextMenuManager::SetDontCloseActiveMenu  
 컨트롤 여부는 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) 새 팝업 메뉴를 표시 하는 경우 활성 팝업 메뉴를 닫습니다.  
  
```  
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bSet`  
 활성 팝업 메뉴 닫기 여부를 제어 하는 부울 매개 변수입니다. 값이 `TRUE` 활성 팝업 메뉴 닫혀 있지 않으면 나타냅니다. `FALSE` 활성 팝업 메뉴 닫혀 있는지를 나타냅니다.  
  
### <a name="remarks"></a>설명  
 기본적으로는 `CContextMenuManager` 활성 팝업 메뉴를 닫습니다.  
  
##  <a name="showpopupmenu"></a>  CContextMenuManager::ShowPopupMenu  
 지정 된 바로 가기 메뉴를 표시합니다.  
  
```  
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bOwnMessage = FALSE,  
    BOOL bRightAlign = FALSE);

 
virtual CMFCPopupMenu* ShowPopupMenu(
    HMENU hmenuPopup,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bOwnMessage = FALSE,  
    BOOL bAutoDestroy = TRUE,  
    BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiMenuResId`  
 이 메서드는 표시 된 메뉴의 리소스 ID입니다.  
  
 [in] `x`  
 가로 클라이언트 좌표에서 바로 가기 메뉴에 대 한 오프셋입니다.  
  
 [in] `y`  
 클라이언트 좌표에서 바로 가기 메뉴에 대 한 세로 오프셋  
  
 [in] `pWndOwner`  
 바로 가기 메뉴의 부모 창에 대 한 포인터입니다.  
  
 [in] `bOwnMessage`  
 메시지가 라우팅되는 방식을 나타내는 부울 매개 변수입니다. 경우 `bOwnMessage` 은 `FALSE`, 표준 MFC 라우팅이 사용 됩니다. 그렇지 않으면 `pWndOwner` 는 메시지를 수신 합니다.  
  
 [in] `hmenuPopup`  
 이 메서드는 표시 되는 메뉴의 핸들입니다.  
  
 [in] `bAutoDestroy`  
 메뉴는 자동으로 소멸 됩니다 여부를 나타내는 부울 매개 변수입니다.  
  
 [in] `bRightAlign`  
 메뉴 항목을 정렬 하는 방법을 나타내는 부울 매개 변수입니다. 경우 `bRightAlign` 은 `TRUE`, 메뉴는 오른쪽에서 왼쪽 읽기 순서에 대 한 오른쪽 정렬 합니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 메서드 오버 로드 메서드가 성공적으로; 메뉴를 표시 하는 경우 0이 아닌 반환 그렇지 않으면 0입니다. 두 번째 메서드 오버 로드에 대 한 포인터를 반환 합니다. [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) 올바르게 고, 그렇지 않으면 바로 가기 메뉴를 표시 하는 경우 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 메서드를 유사한 [CContextMenuManager::TrackPopupMenu](#trackpopupmenu) 두 방법 모두 바로 가기 메뉴를 표시 한다는 점에서 합니다. 그러나 `TrackPopupMenu` 선택 된 메뉴 명령의 인덱스를 반환 합니다.  
  
 경우 매개 변수 `bAutoDestroy` 은 `FALSE`, 상속 된 직접 호출 해야 `DestroyMenu` 메서드 메모리 리소스를 해제 합니다. 기본 구현은 `ShowPopupMenu` 매개 변수를 사용 하지 않는 `bAutoDestroy`합니다. 나중에 사용할 수 나 사용자 지정 클래스에서 파생 된 제공 하는 `CContextMenuManager` 클래스입니다.  
  
##  <a name="trackpopupmenu"></a>  CContextMenuManager::TrackPopupMenu  
 지정 된 바로 가기 메뉴를 표시 하 고 선택한 바로 가기 메뉴 명령의 인덱스를 반환 합니다.  
  
```  
virtual UINT TrackPopupMenu(
    HMENU hmenuPopup,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hmenuPopup`  
 이 메서드는 표시 되는 바로 가기 메뉴의 핸들입니다.  
  
 [in] `x`  
 가로 클라이언트 좌표에서 바로 가기 메뉴에 대 한 오프셋입니다.  
  
 [in] `y`  
 세로 클라이언트 좌표에서 바로 가기 메뉴에 대 한 오프셋입니다.  
  
 [in] `pWndOwner`  
 바로 가기 메뉴의 부모 창에 대 한 포인터입니다.  
  
 [in] `bRightAlign`  
 메뉴 항목을 정렬 하는 방법을 나타내는 부울 매개 변수입니다. 경우 `bRightAlign` 은 `TRUE`, 메뉴는 오른쪽에서 왼쪽 읽기 순서에 대 한 오른쪽 정렬 합니다. 경우 `bRightAlign` 은 `FALSE`, 메뉴는 왼쪽에서 오른쪽 읽기 순서에 대 한 왼쪽으로 정렬 합니다.  
  
### <a name="return-value"></a>반환 값  
 사용자가 선택; 명령 메뉴 명령 ID 사용자가 메뉴 명령 선택 하지 않고 바로 가기 메뉴를 닫을 경우 0입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 바로 가기 메뉴를 표시 하려면 모달 호출으로 작동 합니다. 사용자의 바로 가기 메뉴를 닫습니다 하거나 명령을 선택할 때까지 응용 프로그램 코드에서 다음 줄으로 계속 되지 않습니다. 바로 가기 메뉴를 표시 하는 데 사용할 수 있는 다른 방법은 것 [CContextMenuManager::ShowPopupMenu](#showpopupmenu)합니다. 해당 메서드에 대 한 모달 호출 아니며 선택한 명령 ID를 반환 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)
