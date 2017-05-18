---
title: "CMFCDropDownFrame 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::Create
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentMenuBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentPopupMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::RecalcLayout
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::SetAutoDestroy
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownFrame class
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5f045e4a3b580f12e64758737495c32963bea6db
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdropdownframe-class"></a>CMFCDropDownFrame 클래스
드롭다운 도구 모음 및 드롭다운 도구 모음 단추에 드롭다운 프레임 창 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCDropDownFrame : public CMiniFrameWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|||  
|-|-|  
|이름|설명|  
|`CMFCDropDownFrame::CMFCDropDownFrame`|기본 생성자입니다.|  
|`CMFCDropDownFrame::~CMFCDropDownFrame`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|||  
|-|-|  
|이름|설명|  
|[CMFCDropDownFrame::Create](#create)|
          `CMFCDropDownFrame` 개체를 만듭니다.|  
|`CMFCDropDownFrame::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|[CMFCDropDownFrame::GetParentMenuBar](#getparentmenubar)|드롭 다운 프레임의 부모 메뉴 모음을 검색합니다.|  
|[CMFCDropDownFrame::GetParentPopupMenu](#getparentpopupmenu)|드롭 다운 프레임의 부모 팝업 메뉴를 검색합니다.|  
|`CMFCDropDownFrame::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식으로 연결 된 개체입니다.|  
|[CMFCDropDownFrame::RecalcLayout](#recalclayout)|드롭 다운 프레임 위치를 변경합니다.|  
|[CMFCDropDownFrame::SetAutoDestroy](#setautodestroy)|자식 드롭다운 도구 모음 창이 자동으로 소멸 됩니다 있는지 여부를 설정 합니다.|  
  
### <a name="remarks"></a>설명  
 이 클래스는 사용자 코드에서 직접 사용할 수 없습니다.  
  
 프레임 워크에서이 클래스를 사용 하 여 프레임 동작을 제공 하는 `CMFCDropDownToolbar` 및 `CMFCDropDownToolbarButton` 클래스입니다. 이러한 클래스에 대 한 자세한 내용은 참조 [CMFCDropDownToolBar 클래스](../../mfc/reference/cmfcdropdowntoolbar-class.md) 및 [CMFCDropDownToolbarButton 클래스](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는에 대 한 포인터를 검색 하는 방법을 한 `CMFCDropDownFrame` 에서 개체는 `CFrameWnd` 클래스 및 자식 드롭다운 도구 모음 창을 자동으로 소멸 되도록 설정 하는 방법입니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp #&36;](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdropdowntoolbar.h  
  
##  <a name="create"></a>CMFCDropDownFrame::Create  
 
          `CMFCDropDownFrame` 개체를 만듭니다.  
  
```  
virtual BOOL Create(
    CWnd* pWndParent,  
    int x,  
    int y,  
    CMFCDropDownToolBar* pWndOriginToolbar);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pWndParent`|드롭 다운 프레임의 부모 창입니다.|  
|[in] `x`|드롭다운 프레임의 위치에 대 한 가로 화면 좌표입니다.|  
|[in] `y`|드롭다운 프레임의 위치에 대 한 세로 화면 좌표입니다.|  
|[in] `pWndOriginToolbar`|이 메서드를 사용 하 여 새 드롭다운 프레임 개체를 채울 드롭다운 단추가 있는 도구 모음입니다.|  
  
### <a name="return-value"></a>반환 값  
 `TRUE`드롭 다운 프레임 성공적으로 생성 되었으면; 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 기본 [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) 메서드를 사용 하 여 드롭 다운 프레임 창 만들기는 `WS_POPUP` 스타일입니다. 드롭 다운 프레임 창이 지정된 된 화면 좌표에 나타납니다. 이 메서드는 실패 하는 경우는 [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) 메서드 반환 `FALSE`합니다.  
  
 `CMFCDropDownFrame` 클래스는 제공 된 복사본을 만듭니다 `CMFCDropDownToolBar` 매개 변수입니다. 단추 이미지와 단추 상태에서이 메서드는 복사는 `pWndOriginToolbar` 매개 변수는 `m_pWndOriginToolbar` 데이터 멤버입니다.  
  
##  <a name="getparentmenubar"></a>CMFCDropDownFrame::GetParentMenuBar  
 드롭 다운 프레임의 부모 메뉴 모음을 검색합니다.  
  
```  
CMFCMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>반환 값  
 드롭 다운 프레임의 부모 메뉴 모음에 대 한 포인터 또는 `NULL` 프레임 부모가 없는 경우.  
  
### <a name="remarks"></a>주의  
 이 메서드는 부모 단추를 클릭 하 여 부모 메뉴 모음을 검색합니다. 이 메서드는 반환 `NULL` 드롭 다운 프레임에 부모 단추가 되었거나 부모 단추에 부모 메뉴 모음에 없습니다.  
  
##  <a name="getparentpopupmenu"></a>CMFCDropDownFrame::GetParentPopupMenu  
 드롭 다운 프레임의 부모 팝업 메뉴를 검색합니다.  
  
```  
CMFCDropDownFrame* GetParentPopupMenu() const;  
```  
  
### <a name="return-value"></a>반환 값  
 드롭 다운 프레임의 부모 드롭다운 메뉴에 대 한 포인터 또는 `NULL` 프레임 부모가 없는 경우.  
  
### <a name="remarks"></a>주의  
 이 메서드는 부모 단추를 클릭 하 여 부모 메뉴를 검색합니다. 이 메서드는 반환 `NULL` 드롭 다운 프레임에 부모 단추가 또는 부모 단추에는 부모 메뉴에 없는 경우.  
  
##  <a name="recalclayout"></a>CMFCDropDownFrame::RecalcLayout  
 드롭 다운 프레임 위치를 변경합니다.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `bNotify`|사용되지 않습니다.|  
  
### <a name="remarks"></a>주의  
 프레임 워크 드롭다운 프레임을 만들거나 부모 창의 크기를 조정할 때이 메서드를 호출 합니다. 이 메서드는 부모 창의 크기와 위치를 사용 하 여 드롭 다운 프레임의 크기와 위치를 계산 합니다.  
  
##  <a name="setautodestroy"></a>CMFCDropDownFrame::SetAutoDestroy  
 자식 드롭다운 도구 모음 창이 자동으로 소멸 됩니다 있는지 여부를 설정 합니다.  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bAutoDestroy`  
 `TRUE`자동으로 연결 된 드롭다운 도구 모음 창을;를 삭제 하려면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 경우 `bAutoDestroy` 는 `TRUE`, 그런 다음 `CMFCDropDownFrame` 소멸자에는 연결 된 드롭다운 도구 모음 창 소멸 시킵니다. 기본값은 `TRUE`입니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar 클래스](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCDropDownToolbarButton 클래스](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

