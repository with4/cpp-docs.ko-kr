---
title: "CMFCTabDropTarget 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragEnter
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragLeave
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragOver
- AFXBASETABCTRL/CMFCTabDropTarget::OnDropEx
- AFXBASETABCTRL/CMFCTabDropTarget::Register
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabDropTarget [MFC], OnDragEnter
- CMFCTabDropTarget [MFC], OnDragLeave
- CMFCTabDropTarget [MFC], OnDragOver
- CMFCTabDropTarget [MFC], OnDropEx
- CMFCTabDropTarget [MFC], Register
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ff17f7312f5e04b6ae900e792523155705a3b4a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctabdroptarget-class"></a>CMFCTabDropTarget 클래스
탭 컨트롤 및 OLE 라이브러리 사이의 통신 메커니즘을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCTabDropTarget : public COleDropTarget  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|||  
|-|-|  
|이름|설명|  
|`CMFCTabDropTarget::CMFCTabDropTarget`|기본 생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|||  
|-|-|  
|이름|설명|  
|[CMFCTabDropTarget::OnDragEnter](#ondragenter)|사용자 탭 창에 개체를 끌 때 프레임 워크에서 호출 됩니다. (재정의 [COleDropTarget::OnDragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).)|  
|[CMFCTabDropTarget::OnDragLeave](#ondragleave)|포커스가 있는 탭 창 외부에서 개체를 끌 때 프레임 워크에서 호출 됩니다. (재정의 [COleDropTarget::OnDragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave).)|  
|[CMFCTabDropTarget::OnDragOver](#ondragover)|포커스가 있는 탭 창으로 개체를 끌 때 프레임 워크에서 호출 됩니다. (재정의 [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover).)|  
|[CMFCTabDropTarget::OnDropEx](#ondropex)|끌기 작업의 끝에 마우스 단추를 놓을 때 프레임 워크에서 호출 됩니다. (재정의 [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).)|  
|[CMFCTabDropTarget::Register](#register)|OLE 끌어서 놓기 작업의 대상이 될 수 있는 형식으로 컨트롤을 등록 합니다.|  
  
### <a name="remarks"></a>설명  
 이 클래스는 끌어서 놓기 지원에는 `CMFCBaseTabCtrl` 클래스입니다. 응용 프로그램에 사용 하 여 OLE 라이브러리를 초기화 하는 경우는 [AfxOleInit](ole-initialization.md#afxoleinit) 함수 `CMFCBaseTabCtrl` 개체 끌어서 놓기 작업에 대해 자신을 등록 합니다.  
  
 `CMFCTabDropTarget` 클래스 활성 끌기 작업이 발생할 때 커서 아래에 있는 탭 하 여 기본 클래스를 확장 합니다. 끌어서 놓기 작업에 대 한 자세한 내용은 참조 [끌어서 놓기 (OLE)](../../mfc/drag-and-drop-ole.md)합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 `CMFCTabDropTarget` 개체를 생성하고 해당 `Register` 메서드를 사용하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#39](../../mfc/reference/codesnippet/cpp/cmfctabdroptarget-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleDropTarget](../../mfc/reference/coledroptarget-class.md)  
  
 [CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxbasetabctrl.h  
  
##  <a name="ondragenter"></a>CMFCTabDropTarget::OnDragEnter  
 사용자 탭 창에 개체를 끌 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pWnd`|사용되지 않습니다.|  
|[in] `pDataObject`|사용자가을 끌 하는 개체에 대 한 포인터입니다.|  
|[in] `dwKeyState`|보조 키의 상태가 포함 됩니다. 이 개수에 관계 없이 다음의 조합을: `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, 및 `MK_RBUTTON`합니다.|  
|[in] `point`|클라이언트 좌표에서 커서의 위치입니다.|  
  
### <a name="return-value"></a>반환 값  
 효과 삭제 하 여 지정 된 위치에서 발생 한 경우 결과 `point`합니다. 다음 중 하나 이상을 수 있습니다.  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>설명  
 이 메서드가 반환 `DROPEFFECT_NONE` 도구 모음 프레임 워크를 사용자 지정 모드에 있지 않습니다. 되었거나 클립보드 데이터 형식을 사용할 수 없는 경우. 그렇지 않으면 호출한 결과 반환 `CMFCBaseTabCtrl::OnDragEnter` 제공 된 매개 변수를 사용 합니다.  
  
 사용자 지정 모드에 대 한 자세한 내용은 참조 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)합니다. 클립보드 데이터 형식에 대 한 자세한 내용은 참조 [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)합니다.  
  
##  <a name="ondragleave"></a>CMFCTabDropTarget::OnDragLeave  
 포커스가 있는 탭 창 외부에서 개체를 끌 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pWnd`|사용되지 않습니다.|  
  
### <a name="remarks"></a>설명  
 이 메서드를 호출는 `CMFCBaseTabCtrl::OnDragLeave` 메서드 끌기 작업을 수행 하도록 합니다.  
  
##  <a name="ondragover"></a>CMFCTabDropTarget::OnDragOver  
 포커스가 있는 탭 창으로 개체를 끌 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pWnd`|사용되지 않습니다.|  
|[in] `pDataObject`|사용자가을 끌 하는 개체에 대 한 포인터입니다.|  
|[in] `dwKeyState`|보조 키의 상태가 포함 됩니다. 이 개수에 관계 없이 다음의 조합을: `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, 및 `MK_RBUTTON`합니다.|  
|[in] `point`|클라이언트 좌표에서 마우스 포인터의 위치입니다.|  
  
### <a name="return-value"></a>반환 값  
 효과 삭제 하 여 지정 된 위치에서 발생 한 경우 결과 `point`합니다. 다음 중 하나 이상을 수 있습니다.  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>설명  
 이 메서드는 활성 끌기 작업이 발생할 때 커서 아래에 있는 탭을 만듭니다. 반환 `DROPEFFECT_NONE` 도구 모음 프레임 워크를 사용자 지정 모드에 있지 않습니다. 되었거나 클립보드 데이터 형식을 사용할 수 없는 경우. 그렇지 않으면 호출한 결과 반환 `CMFCBaseTabCtrl::OnDragOver` 제공 된 매개 변수를 사용 합니다.  
  
 사용자 지정 모드에 대 한 자세한 내용은 참조 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)합니다. 클립보드 데이터 형식에 대 한 자세한 내용은 참조 [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)합니다.  
  
##  <a name="ondropex"></a>CMFCTabDropTarget::OnDropEx  
 끌기 작업의 끝에 마우스 단추를 놓을 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pWnd`|사용되지 않습니다.|  
|[in] `pDataObject`|사용자가을 끌 하는 개체에 대 한 포인터입니다.|  
|[in] `dropEffect`|기본 놓기 작업 합니다.|  
|[in] `dropList`|사용되지 않습니다.|  
|[in] `point`|클라이언트 좌표에서 마우스 포인터의 위치입니다.|  
  
### <a name="return-value"></a>반환 값  
 결과 놓기 효과입니다. 다음 중 하나 이상을 수 있습니다.  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>설명  
 이 메서드를 호출 `CMFCBaseTabCtrl::OnDrop` 사용자 지정 모드의 도구 모음 프레임 워크는 클립보드 데이터 형식을 사용할 수 있는 경우. 경우에 대 한 호출 `CMFCBaseTabCtrl::OnDrop` 반환이이 메서드는 0이 아닌 값을 반환 하 여 지정 된 기본 놓기 효과 `dropEffect`합니다. 그렇지 않으면이 메서드가 반환 `DROPEFFECT_NONE`합니다. 끌어서 놓기 작업 결과 대 한 자세한 내용은 참조 [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex)합니다.  
  
 사용자 지정 모드에 대 한 자세한 내용은 참조 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)합니다. 클립보드 데이터 형식에 대 한 자세한 내용은 참조 [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)합니다.  
  
##  <a name="register"></a>CMFCTabDropTarget::Register  
 OLE 끌어서 놓기 작업의 대상이 될 수 있는 형식으로 컨트롤을 등록 합니다.  
  
```  
BOOL Register(CMFCBaseTabCtrl *pOwner);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pOwner`|놓기 대상으로 등록 하는 탭 컨트롤입니다.|  
  
### <a name="return-value"></a>반환 값  
 등록에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 호출 [COleDropTarget::Register](../../mfc/reference/coledroptarget-class.md#register) 끌어서 놓기 작업에 대 한 컨트롤을 등록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [끌어서 놓기(OLE)](../../mfc/drag-and-drop-ole.md)



