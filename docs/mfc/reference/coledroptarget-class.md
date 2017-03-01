---
title: "COleDropTarget 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDropTarget
dev_langs:
- C++
helpviewer_keywords:
- COleDropTarget class
- drag and drop, drop target
- drop commands, accepting
- drop commands
ms.assetid: a58c9a48-6a93-4357-b078-4594df258311
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0e9429d531d6af86bc571b1f871fbcd4a8fe2532
ms.lasthandoff: 02/24/2017

---
# <a name="coledroptarget-class"></a>COleDropTarget 클래스
창과 OLE 라이브러리 사이의 통신 메커니즘을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleDropTarget : public CCmdTarget  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleDropTarget::COleDropTarget](#coledroptarget)|`COleDropTarget` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleDropTarget::OnDragEnter](#ondragenter)|커서 창에 처음 전달 될 때 호출 합니다.|  
|[COleDropTarget::OnDragLeave](#ondragleave)|창 밖으로 커서를 끌 때 호출 됩니다.|  
|[COleDropTarget::OnDragOver](#ondragover)|창 위에 커서를 끌 때 반복적으로 호출 합니다.|  
|[COleDropTarget::OnDragScroll](#ondragscroll)|커서를 창 스크롤 영역으로 끌 있는지 여부를 확인 하려면 호출 됩니다.|  
|[COleDropTarget::OnDrop](#ondrop)|기본 처리기는 창에 데이터를 놓을 때 호출 됩니다.|  
|[COleDropTarget::OnDropEx](#ondropex)|초기 처리기 창에 데이터를 놓을 때 호출 됩니다.|  
|[COleDropTarget::Register](#register)|유효한 놓기 대상으로 창을 등록합니다.|  
|[COleDropTarget::Revoke](#revoke)|인해 창에서 유효한 놓기 대상이 되 고 작동이 중지 됩니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스의 개체를 만들면 창을 OLE 끌어서 놓기 메커니즘을 통해 데이터를 받아들일 수 있습니다.  
  
 Drop 명령이 적용에 대 한 창을 가져오려면 먼저 만들어야의 개체는 `COleDropTarget` 클래스를 다음 호출의 [등록](#register) 원하는에 대 한 포인터는 함수 `CWnd` 유일한 매개 변수로 개체입니다.  
  
 끌어서 놓기 작업에 대 한 자세한 내용은 문서를 참조 OLE를 사용 하 여 [끌어서 놓기 (OLE)](../../mfc/drag-and-drop-ole.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropTarget`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="a-namecoledroptargeta--coledroptargetcoledroptarget"></a><a name="coledroptarget"></a>COleDropTarget::COleDropTarget  
 클래스의 개체를 생성 `COleDropTarget`합니다.  
  
```  
COleDropTarget();
```  
  
### <a name="remarks"></a>주의  
 호출 [등록](#register) 창에이 개체를 연결할 수 있습니다.  
  
##  <a name="a-nameondragentera--coledroptargetondragenter"></a><a name="ondragenter"></a>COleDropTarget::OnDragEnter  
 커서를 먼저 창으로 끌 때에 프레임 워크에서 호출 합니다.  
  
```  
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 커서를 입력 하는 창을 가리킵니다.  
  
 `pDataObject`  
 삭제할 수 있는 데이터를 포함 하는 데이터 개체를 가리킵니다.  
  
 `dwKeyState`  
 보조 키의 상태를 포함합니다. 다음 수 만큼의 조합입니다.: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, 및 **MK_RBUTTON**합니다.  
  
 `point`  
 클라이언트 좌표에서 커서의 현재 위치를 포함합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 위치에서 놓기를 시도한 결과로 얻어지는 효과 `point`합니다. 다음 중 하나 이상을 수 있습니다.  
  
- `DROPEFFECT_NONE`감소 하는 것은 허용 되지 않습니다.  
  
- `DROPEFFECT_COPY`복사 작업이 수행 됩니다.  
  
- `DROPEFFECT_MOVE`이동 작업이 수행 됩니다.  
  
- `DROPEFFECT_LINK`원래 데이터를 삭제 된 데이터에서 링크를 설정할 수 합니다.  
  
- `DROPEFFECT_SCROLL`끌기 스크롤 발생 하려고 하거나 대상에서 발생 합니다.  
  
### <a name="remarks"></a>주의  
 놓기 작업을 창에서 수행할 수 있도록이 함수를 재정의 합니다. 기본 구현 호출 하 여 [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter)만 반환 `DROPEFFECT_NONE` 기본적으로 합니다.  
  
 자세한 내용은 참조 [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameondragleavea--coledroptargetondragleave"></a><a name="ondragleave"></a>COleDropTarget::OnDragLeave  
 끌기 작업이 적용 되는 동안 커서가 창을 벗어나면 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 커서를 떠나 창을 가리킵니다.  
  
### <a name="remarks"></a>주의  
 끌기 작업이 지정된 된 창 밖으로 나갈 때 특별 한 동작을 원하는 경우이 함수를 재정의 합니다. 이 함수의 기본 구현에서는 호출 [CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave)합니다.  
  
 자세한 내용은 참조 [IDropTarget::DragLeave](http://msdn.microsoft.com/library/windows/desktop/ms680110) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameondragovera--coledroptargetondragover"></a><a name="ondragover"></a>COleDropTarget::OnDragOver  
 창 위에 커서를 끌 때에 프레임 워크에서 호출 합니다.  
  
```  
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 커서를 이동 하는 창의를 가리킵니다.  
  
 `pDataObject`  
 삭제할 데이터를 포함 하는 데이터 개체를 가리킵니다.  
  
 `dwKeyState`  
 보조 키의 상태를 포함합니다. 다음 수 만큼의 조합입니다.: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, 및 **MK_RBUTTON**합니다.  
  
 `point`  
 클라이언트 좌표에서 커서의 현재 위치를 포함합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 위치에서 놓기를 시도한 결과로 얻어지는 효과 `point`합니다. 다음 중 하나 이상을 수 있습니다.  
  
- `DROPEFFECT_NONE`감소 하는 것은 허용 되지 않습니다.  
  
- `DROPEFFECT_COPY`복사 작업이 수행 됩니다.  
  
- `DROPEFFECT_MOVE`이동 작업이 수행 됩니다.  
  
- `DROPEFFECT_LINK`원래 데이터를 삭제 된 데이터에서 링크를 설정할 수 합니다.  
  
- `DROPEFFECT_SCROLL`끌기 스크롤 이루어진다는 것 또는 대상에서 발생을 나타냅니다.  
  
### <a name="remarks"></a>주의  
 놓기 작업을 창에서 수행할 수 있도록이 함수를 재정의 해야 합니다. 이 함수의 기본 구현에서는 호출 [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover)를 반환 하 `DROPEFFECT_NONE` 기본적으로 합니다. 이 함수를 끌어서 놓기 작업 중에 자주 호출 했으므로 것을 최적화할 최대한 많이 있습니다.  
  
 자세한 내용은 참조 [IDropTarget::DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCOleContainer #&21;](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]  
  
##  <a name="a-nameondragscrolla--coledroptargetondragscroll"></a><a name="ondragscroll"></a>COleDropTarget::OnDragScroll  
 호출 하기 전에 프레임 워크에서 호출 [OnDragEnter](#ondragenter) 또는 [OnDragOver](#ondragover) 알아보려면 여부 `point` 스크롤 영역에 있습니다.  
  
```  
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 커서를 현재 창을 가리킵니다.  
  
 `dwKeyState`  
 보조 키의 상태를 포함합니다. 다음 수 만큼의 조합입니다.: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, 및 **MK_RBUTTON**합니다.  
  
 `point`  
 화면을 기준으로 픽셀 단위로 커서의 위치를 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 위치에서 놓기를 시도한 결과로 얻어지는 효과 `point`합니다. 다음 중 하나 이상을 수 있습니다.  
  
- `DROPEFFECT_NONE`감소 하는 것은 허용 되지 않습니다.  
  
- `DROPEFFECT_COPY`복사 작업이 수행 됩니다.  
  
- `DROPEFFECT_MOVE`이동 작업이 수행 됩니다.  
  
- `DROPEFFECT_LINK`원래 데이터를 삭제 된 데이터에서 링크를 설정할 수 합니다.  
  
- `DROPEFFECT_SCROLL`끌기 스크롤 이루어진다는 것 또는 대상에서 발생을 나타냅니다.  
  
### <a name="remarks"></a>주의  
 이 이벤트에 대 한 특별 한 동작을 제공 하려는 경우이 함수를 재정의 합니다. 이 함수의 기본 구현에서는 호출 [CView::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll)를 반환 하 `DROPEFFECT_NONE` 커서의 창 테두리 내부에 기본 스크롤 영역 안으로 끌 때 창을 스크롤하여 표시 합니다.  
  
##  <a name="a-nameondropa--coledroptargetondrop"></a><a name="ondrop"></a>COleDropTarget::OnDrop  
 Drop 작업이 발생할 때 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL OnDrop(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 커서를 현재 창을 가리킵니다.  
  
 `pDataObject`  
 삭제할 데이터를 포함 하는 데이터 개체를 가리킵니다.  
  
 `dropEffect`  
 Drop 작업에 대 한 사용자가 선택 하는 효과입니다. 다음 중 하나 이상을 수 있습니다.  
  
- `DROPEFFECT_COPY`복사 작업이 수행 됩니다.  
  
- `DROPEFFECT_MOVE`이동 작업이 수행 됩니다.  
  
- `DROPEFFECT_LINK`원래 데이터를 삭제 된 데이터에서 링크를 설정할 수 합니다.  
  
 `point`  
 화면을 기준으로 픽셀 단위로 커서의 위치를 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 드롭다운에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크 첫 번째 호출 [OnDropEx](#ondropex)합니다. 하는 경우는 `OnDropEx` 함수의 삭제를 처리 하지 않는, 프레임 워크에는 다음이 멤버 함수 호출 `OnDrop`합니다. 일반적으로 응용 프로그램 재정의 [OnDropEx](../../mfc/reference/cview-class.md#ondropex) 오른쪽 마우스 단추를 처리 하는 뷰 클래스에 끌어 놓습니다. 일반적으로 뷰 클래스 [OnDrop](../../mfc/reference/cview-class.md#ondrop) 간단한 끌어서 놓기를 처리 하는 데 사용 됩니다.  
  
 기본 구현은 `COleDropTarget::OnDrop` 호출 [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop)만 반환 **FALSE** 기본적으로 합니다.  
  
 자세한 내용은 참조 [IDropTarget::Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameondropexa--coledroptargetondropex"></a><a name="ondropex"></a>COleDropTarget::OnDropEx  
 Drop 작업이 발생할 때 프레임 워크에서 호출 합니다.  
  
```  
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropDefault,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 커서를 현재 창을 가리킵니다.  
  
 `pDataObject`  
 삭제할 데이터를 포함 하는 데이터 개체를 가리킵니다.  
  
 `dropDefault`  
 현재 키 상태를 기반으로 기본 놓기 작업에 대 한 사용자가 선택 하는 효과입니다. 수 `DROPEFFECT_NONE`합니다. 끌어서 놓기 작업 결과 주의 섹션에 설명 되어 있습니다.  
  
 `dropList`  
 목록 놓기 원본에서 지 원하는 끌어서 놓기 작업 결과입니다. 비트 OR를 사용 하 여 놓기 효과 값을 결합할 수 있습니다 ( **|**) 작업입니다. 끌어서 놓기 작업 결과 주의 섹션에 설명 되어 있습니다.  
  
 `point`  
 화면을 기준으로 픽셀 단위로 커서의 위치를 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 위치에서 삭제 시도가에서 발생 하는 놓기 효과 `point`합니다. 끌어서 놓기 작업 결과 주의 섹션에 설명 되어 있습니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 먼저이 함수를 호출합니다. 프레임 워크는 다음 호출의 삭제를 처리 하지 않는 [OnDrop](#ondrop)합니다. 재정의 하는 일반적으로 [OnDropEx](../../mfc/reference/cview-class.md#ondropex) 오른쪽 마우스 단추를 지원 하기 위해 뷰 클래스에 끌어 놓습니다. 일반적으로 뷰 클래스 [OnDrop](../../mfc/reference/cview-class.md#ondrop) 간단한 끌어서 놓기 지원의 경우를 처리 하는 데 사용 됩니다.  
  
 기본 구현은 `COleDropTarget::OnDropEx` 호출 [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex)합니다. 기본적으로 [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex) 를 나타내는 값을 더미 반환는 [OnDrop](#ondrop) 멤버 함수를 호출 해야 합니다.  
  
 끌어서 놓기 작업 결과 놓기 작업과 관련 된 작업에 설명 합니다. 끌어서 놓기 작업 결과의 다음 목록을 참조 합니다.  
  
- `DROPEFFECT_NONE`감소 하는 것은 허용 되지 않습니다.  
  
- `DROPEFFECT_COPY`복사 작업이 수행 됩니다.  
  
- `DROPEFFECT_MOVE`이동 작업이 수행 됩니다.  
  
- `DROPEFFECT_LINK`원래 데이터를 삭제 된 데이터에서 링크를 설정할 수 합니다.  
  
- `DROPEFFECT_SCROLL`끌기 스크롤 이루어진다는 것 또는 대상에서 발생을 나타냅니다.  
  
 자세한 내용은 참조 [IDropTarget::Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameregistera--coledroptargetregister"></a><a name="register"></a>COleDropTarget::Register  
 창 OLE Dll은 유효한 놓기 대상으로 등록 하려면이 함수를 호출 합니다.  
  
```  
BOOL Register(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 놓기 대상으로 등록할 수 있는 창을 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 등록이 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 놓기 작업의 수락이 함수를 호출 해야 합니다.  
  
 자세한 내용은 참조 [RegisterDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms678405) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namerevokea--coledroptargetrevoke"></a><a name="revoke"></a>COleDropTarget::Revoke  
 이 함수 호출을 통해 놓기 대상으로 등록 된 모든 창을 삭제 하기 전에 호출 [등록](#register) 놓기 대상의 목록에서 제거 합니다.  
  
```  
virtual void Revoke();
```  
  
### <a name="remarks"></a>주의  
 이 함수에서 자동으로 호출 되는 [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) 때문에 일반적으로 없습니다이 함수를 명시적으로 호출 하는 데 필요한 등록 된 창에 대 한 처리기입니다.  
  
 자세한 내용은 참조 [RevokeDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms692643) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 HIERSVR](../../visual-cpp-samples.md)   
 [MFC 샘플 OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDropSource 클래스](../../mfc/reference/coledropsource-class.md)

