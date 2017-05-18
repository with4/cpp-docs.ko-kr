---
title: "COleDropSource 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDropSource
- AFXOLE/COleDropSource
- AFXOLE/COleDropSource::COleDropSource
- AFXOLE/COleDropSource::GiveFeedback
- AFXOLE/COleDropSource::OnBeginDrag
- AFXOLE/COleDropSource::QueryContinueDrag
dev_langs:
- C++
helpviewer_keywords:
- drag operations
- drop target, dragging data to
- COleDropSource class
- drag and drop, drop source
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
caps.latest.revision: 24
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
ms.openlocfilehash: f3d0e5b7184cf305459173065b8e1cc07e032aef
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="coledropsource-class"></a>COleDropSource 클래스
데이터를를 놓기 대상에 놓을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleDropSource : public CCmdTarget  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleDropSource::COleDropSource](#coledropsource)|`COleDropSource` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleDropSource::GiveFeedback](#givefeedback)|끌어서 놓기 작업 중 커서를 변경합니다.|  
|[COleDropSource::OnBeginDrag](#onbegindrag)|끌어서 놓기 작업 중에 마우스 캡처를 처리합니다.|  
|[COleDropSource::QueryContinueDrag](#querycontinuedrag)|끌어 하는지 여부를 확인 하는 검사를 계속 해야 합니다.|  
  
## <a name="remarks"></a>주의  
 [COleDropTarget](../../mfc/reference/coledroptarget-class.md) 끌어서 놓기 작업의 수신 부분을 처리 하는 클래스입니다. `COleDropSource` 개체는 끌기 작업이 시작 되 면을 끌기 작업 중 사용자 의견을 제공 하 고 끌기 작업이 종료 되는 시기를 결정 하는 일을 담당 합니다.  
  
 사용 하는 `COleDropSource` 개체 생성자를 호출 합니다. 마우스 클릭과 같은 이벤트를 사용 하 여 끌기 작업 시작을 결정 하는 프로세스를 간소화 하는이 [COleDataSource::DoDragDrop](../../mfc/reference/coledatasource-class.md#dodragdrop), [COleClientItem::DoDragDrop](../../mfc/reference/coleclientitem-class.md#dodragdrop), 또는 [COleServerItem::DoDragDrop](../../mfc/reference/coleserveritem-class.md#dodragdrop) 함수입니다. 이러한 함수를 만듭니다를 `COleDropSource` 수에 대 한 개체입니다. 기본 동작을 수정 하려는 경우는 `COleDropSource` 재정의 가능 함수입니다. 이러한 멤버 함수는 프레임 워크에서 적절 한 시간에 호출 됩니다.  
  
 끌어서 놓기 작업에 대 한 자세한 내용은 문서를 참조 OLE를 사용 하 여 [끌어서 놓기 (OLE)](../../mfc/drag-and-drop-ole.md)합니다.  
  
 자세한 내용은 참조 [IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropSource`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="coledropsource"></a>COleDropSource::COleDropSource  
 `COleDropSource` 개체를 생성합니다.  
  
```  
COleDropSource();
```  
  
##  <a name="givefeedback"></a>COleDropSource::GiveFeedback  
 호출한 후에 프레임 워크에서 호출 [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) 또는 [COleDropTarget::DragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter)합니다.  
  
```  
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```  
  
### <a name="parameters"></a>매개 변수  
 `dropEffect`  
 선택한 데이터와 함께 지정 된이 위치에 발생 한 감소 하는 경우 사용자에 게 표시 하려면 원하는 효과 발생 하는 일반적으로 나타내는 합니다. 일반적으로 가장 최근의 호출에 의해 반환 되는 값은이 [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) 또는 [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover)합니다. 다음 중 하나 이상을 수 있습니다.  
  
- `DROPEFFECT_NONE`감소 하는 것은 허용 되지 않습니다.  
  
- `DROPEFFECT_COPY`복사 작업이 수행 됩니다.  
  
- `DROPEFFECT_MOVE`이동 작업이 수행 됩니다.  
  
- `DROPEFFECT_LINK`원래 데이터를 삭제 된 데이터에서 링크를 설정할 수 합니다.  
  
- `DROPEFFECT_SCROLL`끌기 스크롤 발생 하려고 하거나 대상에서 발생 합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **DRAGDROP_S_USEDEFAULTCURSORS** 끌어 진행 중인 경우, **NOERROR** 없는 경우.  
  
### <a name="remarks"></a>주의  
 이 시점에 발생 한 감소 하는 경우 어떻게 되는지 하는 방법에 대 한 사용자에 게 피드백을 제공 하려면이 함수를 재정의 합니다. 기본 구현은 OLE 기본 커서를 사용 합니다. 끌어서 놓기 작업에 대 한 자세한 내용은 문서를 참조 OLE를 사용 하 여 [끌어서 놓기 (OLE)](../../mfc/drag-and-drop-ole.md)합니다.  
  
 자세한 내용은 참조 [IDropSource::GiveFeedback](http://msdn.microsoft.com/library/windows/desktop/ms693723), [IDropTarget::DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129), 및 [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="onbegindrag"></a>COleDropSource::OnBeginDrag  
 에 의해 호출 프레임 워크는 이벤트가 발생 하는 경우 마우스 왼쪽된 단추를 누르는 것과 같은 끌기 작업을 시작할 수 있습니다.  
  
```  
virtual BOOL OnBeginDrag(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 선택한 데이터를 포함 하는 창을 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 이 속성을 0이 아닌 끌어 허용 된 경우, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 끌기 프로세스가 시작 되는 방식을 수정 하려는 경우이 함수를 재정의 합니다. 기본 구현에서 마우스를 캡처할 하 고 마우스 왼쪽 또는 오른쪽 단추를 클릭 하거나 esc 키, 마우스를 해제 되는 시간에 도달할 때까지 끌기 모드에서 제공 됩니다.  
  
##  <a name="querycontinuedrag"></a>COleDropSource::QueryContinueDrag  
 끌기를 시작 된 후이 함수 반복적으로 호출 프레임 워크는 끌기 작업 취소 또는 완료 될 때까지 합니다.  
  
```  
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed, 
    DWORD dwKeyState);
```  
  
### <a name="parameters"></a>매개 변수  
 *bEscapePressed*  
 마지막으로 호출한 이후 ESC 키를 눌렀는지 여부를 나타내는 `COleDropSource::QueryContinueDrag`합니다.  
  
 `dwKeyState`  
 키보드의 한정자 키의 상태를 포함합니다. 다음 수 만큼의 조합입니다.: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, 및 **MK_RBUTTON**합니다.  
  
### <a name="return-value"></a>반환 값  
 **DRAGDROP_S_CANCEL** 경우 ESC 키 또는 오른쪽 단추를 누르면 또는 왼쪽된 단추를 끌기 시작 전에 발생 합니다. **DRAGDROP_S_DROP** 놓기 작업이 발생 해야 하는 경우. 그렇지 않으면 `S_OK`합니다.  
  
### <a name="remarks"></a>주의  
 이 함수 끌기 지점 변경 하려는 경우 취소 되는 재정의 나 감소 하는 발생 합니다.  
  
 기본 구현은 삭제를 시작 하거나 끌기를 다음과 같이 취소 합니다. ESC 키 또는 마우스 오른쪽 단추를 누를 때에 끌기 작업을 취소 합니다. 왼쪽된 마우스 단추를 끌기 시작 된 후 발생 한 경우에 놓기 작업을 시작 합니다. 그렇지 않으면 반환 `S_OK` 고 더 이상 없는 작업을 수행 합니다.  
  
 이 함수를 자주 호출 했으므로 것을 최적화할 최대한 많이 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 HIERSVR](../../visual-cpp-samples.md)   
 [MFC 샘플 OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




