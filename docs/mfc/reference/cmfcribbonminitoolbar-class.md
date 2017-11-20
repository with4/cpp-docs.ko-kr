---
title: "CMFCRibbonMiniToolBar 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsContextMenuMode
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::SetCommands
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::Show
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::ShowWithContextMenu
dev_langs: C++
helpviewer_keywords:
- CMFCRibbonMiniToolBar [MFC], IsContextMenuMode
- CMFCRibbonMiniToolBar [MFC], IsRibbonMiniToolBar
- CMFCRibbonMiniToolBar [MFC], SetCommands
- CMFCRibbonMiniToolBar [MFC], Show
- CMFCRibbonMiniToolBar [MFC], ShowWithContextMenu
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 32b100915d4b643b7d558d970b496301b94dc5b5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcribbonminitoolbar-class"></a>CMFCRibbonMiniToolBar 클래스
상황별 팝업 도구 모음을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|기본 생성자입니다.|  
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|`CMFCRibbonMiniToolBar::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에서는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|  
|[CMFCRibbonMiniToolBar::IsContextMenuMode](#iscontextmenumode)||  
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](#isribbonminitoolbar)|(`CMFCPopupMenu::IsRibbonMiniToolBar`를 재정의합니다.)|  
|[CMFCRibbonMiniToolBar::SetCommands](#setcommands)|도구 모음에 표시되는 명령의 목록을 설정합니다.|  
|[CMFCRibbonMiniToolBar::Show](#show)|지정된 화면 좌표에 미니 도구 모음을 표시합니다.|  
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](#showwithcontextmenu)|상황에 맞는 메뉴와 함께 미니 도구 모음을 표시합니다.|  
  
## <a name="remarks"></a>설명  
 미니 도구 모음은 일반적으로 사용자가 문서에서 개체를 선택한 후에 표시됩니다. 예를 들어 사용자가 문서 작성 프로그램에서 텍스트 블록을 선택하고 나면 응용 프로그램은 텍스트 서식 지정 명령이 포함된 미니 도구 모음을 표시합니다.  
  
 마우스 포인터가 미니 도구 모음의 범위를 벗어나면 미니 도구 모음은 투명해집니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 `CMFCRibbonPanelMenu`  
  
 [CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxRibbonMiniToolBar.h  
  
##  <a name="setcommands"></a>CMFCRibbonMiniToolBar::SetCommands  
 도구 모음에 표시되는 명령의 목록을 설정합니다.  
  
```  
void SetCommands(
    CMFCRibbonBar* pRibbonBar,  
    const CList<UINT,UINT>& lstCommands);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pRibbonBar`  
 미니 도구 모음을 표시할 단추를 검색 하는 리본 표시줄입니다.  
  
 [in] `lstCommands`  
 미니 도구 모음에 대해 표시할 명령 목록입니다. 모든 리본 범주 관련된 된 단추를 찾을 수 검색 됩니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하 여 미니 도구 모음에 표시 되는 명령의 목록을 설정 합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 사용 하는 `SetCommands` 의 메서드는 `CMFCRibbonMiniToolBar` 클래스. 이 코드 조각은의 일부인는 [MS Office 2007 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#9](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]  
  
##  <a name="show"></a>CMFCRibbonMiniToolBar::Show  
 지정된 화면 좌표에 미니 도구 모음을 표시합니다.  
  
```  
BOOL Show(
    int x,  
    int y);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `x`  
 화면 좌표에 미니 도구 모음은의 가로 위치를 지정합니다.  
  
 [in] `y`  
 화면 좌표에 미니 도구 모음은의 세로 위치를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`미니 도구 모음을 성공적으로 표시 된 경우 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="showwithcontextmenu"></a>CMFCRibbonMiniToolBar::ShowWithContextMenu  
 상황에 맞는 메뉴와 함께 미니 도구 모음을 표시합니다.  
  
```  
BOOL ShowWithContextMenu(
    int x,  
    int y,  
    UINT uiMenuResID,  
    CWnd* pWndOwner);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `x`  
 화면 좌표에서 상황에 맞는 메뉴의 가로 위치를 지정합니다.  
  
 [in] `y`  
 화면 좌표에서 상황에 맞는 메뉴의 세로 위치를 지정합니다.  
  
 [in] `uiMenuResID`  
 표시 하려면 상황에 맞는 메뉴의 리소스 ID를 지정 합니다.  
  
 [in] `pWndOwner`  
 상황에 맞는 메뉴에서 메시지를 수신 하는 창을 식별 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`상황에 맞는 메뉴를 성공적으로 표시 된 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하 여 상황에 맞는 메뉴에 있는 미니 도구 모음을 표시 합니다. 상황에 맞는 메뉴는 미니 도구 모음 아래 15 픽셀을 위치 지정된입니다.  
  
##  <a name="iscontextmenumode"></a>CMFCRibbonMiniToolBar::IsContextMenuMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsContextMenuMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="isribbonminitoolbar"></a>CMFCRibbonMiniToolBar::IsRibbonMiniToolBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsRibbonMiniToolBar() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)
