---
title: IOleInPlaceObjectWindowlessImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetDropTarget
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::OnWindowMessage
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::SetObjectRects
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::UIDeactivate
dev_langs:
- C++
helpviewer_keywords:
- IOleInPlaceObjectWindowless, ATL implementation
- activation [C++], ATL
- IOleInPlaceObjectWindowlessImpl class
- ActiveX controls [C++], communication between container and control
- controls [ATL], windowless
- deactivating ATL
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f5616258405eb8346132d32b8f7fd71d0b4794d6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365004"
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>IOleInPlaceObjectWindowlessImpl 클래스
이 클래스는 구현 **IUnknown** 창 없는 컨트롤 창 메시지를 수신 하 고 끌어서 놓기 작업에 참여할 수 있도록 하는 방법을 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IOleInPlaceObjectWindowlessImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|상황에 맞는 도움말을 사용 하도록 설정 합니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|제공 된 `IDropTarget` 끌어서 놓기를 지원 하는 내부 활성, 창 없는 개체에 대 한 인터페이스입니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|창 핸들을 가져옵니다.|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|활성 전체 컨트롤을 비활성화합니다.|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|내부 활성화에 있는 창 없는 컨트롤 컨테이너에서 메시지를 디스패치합니다.|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|이전에 비활성화 된 컨트롤을 다시 활성화합니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|표시 되는 전체 컨트롤의 어떤 부분을 나타냅니다.|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|비활성화 하 고 내부 활성화를 지 원하는 사용자 인터페이스를 제거 합니다.|  
  
## <a name="remarks"></a>설명  
 [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) 인터페이스 재 활성화를 관리 하 고 제어 하 고 컨트롤의 크기를 표시할지를 결정 하는 현재 위치를 비활성화 합니다. [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) 인터페이스 창 없는 컨트롤 창 메시지를 수신 하 고 끌어서 놓기 작업에 참여할 수 있습니다. 클래스 `IOleInPlaceObjectWindowlessImpl` 의 기본 구현을 제공 `IOleInPlaceObject` 및 `IOleInPlaceObjectWindowless` 구현 **IUnknown** 디버그에서 장치 정보 덤프를 전송 하 여 빌드합니다.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IOleInPlaceObjectWindowless`  
  
 `IOleInPlaceObjectWindowlessImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="contextsensitivehelp"></a>  IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp  
 반환 **E_NOTIMPL**합니다.  
  
```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```  
  
### <a name="remarks"></a>설명  
 참조 [IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059) in the Windows SDK입니다.  
  
##  <a name="getdroptarget"></a>  IOleInPlaceObjectWindowlessImpl::GetDropTarget  
 반환 **E_NOTIMPL**합니다.  
  
```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```  
  
### <a name="remarks"></a>설명  
 참조 [IOleInPlaceObjectWindowless::GetDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms678535) in the Windows SDK입니다.  
  
##  <a name="getwindow"></a>  IOleInPlaceObjectWindowlessImpl::GetWindow  
 컨테이너는 컨트롤의 창 핸들을 가져오려면이 함수를 호출 합니다.  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>설명  
 일부 컨테이너는 현재 기간 이동 하는 경우에, 창 없는 되었습니다에 있는 컨트롤과 함께 작동 하지 않습니다. ATL의 구현 하는 경우 컨트롤 클래스의 데이터 멤버 `m_bWasOnceWindowless` 은 **TRUE**, 함수 반환 **E_FAIL**합니다. 그렇지 않은 경우, *phwnd* 않습니다 **NULL**, `GetWindow` 설정 \* *phwnd* 컨트롤 클래스의 데이터 멤버를 `m_hWnd` 반환`S_OK`.  
  
 참조 [IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282) in the Windows SDK입니다.  
  
##  <a name="inplacedeactivate"></a>  IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate  
 내부 활성 컨트롤을 비활성화 하 고 컨테이너에 의해 호출 됩니다.  
  
```
HRESULT InPlaceDeactivate(HWND* phwnd);
```  
  
### <a name="remarks"></a>설명  
 이 메서드는 컨트롤의 상태에 따라 전체 또는 일부 비활성화를 수행합니다. 컨트롤의 사용자 인터페이스를 비활성화 하 고 컨트롤의 창이 있는 경우 제거 됩니다. 컨테이너는 컨트롤이 더 이상 활성화 된 위치에 알림이 전송 됩니다. **IOleInPlaceUIWindow** 메뉴를 협상 하 고 공간 테두리를 컨테이너에 의해 사용 되는 인터페이스 해제 됩니다.  
  
 참조 [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) in the Windows SDK입니다.  
  
##  <a name="onwindowmessage"></a>  IOleInPlaceObjectWindowlessImpl::OnWindowMessage  
 내부 활성화에 있는 창 없는 컨트롤 컨테이너에서 메시지를 디스패치합니다.  
  
```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```  
  
### <a name="remarks"></a>설명  
 참조 [IOleInPlaceObjectWindowless::OnWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms693783) in the Windows SDK입니다.  
  
##  <a name="reactivateandundo"></a>  IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo  
 반환 **E_NOTIMPL**합니다.  
  
```
HRESULT ReactivateAndUndo();
```  
  
### <a name="remarks"></a>설명  
 참조 [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) in the Windows SDK입니다.  
  
##  <a name="setobjectrects"></a>  IOleInPlaceObjectWindowlessImpl::SetObjectRects  
 컨트롤의 크기 및/또는 위치 변경 되었음을 알리기 위해 컨테이너에 의해 호출 됩니다.  
  
```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```  
  
### <a name="remarks"></a>설명  
 컨트롤의 업데이트 `m_rcPos` 데이터 멤버 및 제어를 표시 합니다. 클립 영역을 교차 하는 컨트롤의 일부만 표시 됩니다. 컨트롤의 표시 된 클립 이전에 표시 되지만 클리핑 제거 된 컨트롤의 전체 뷰를 다시 그리게이 함수를 호출할 수 있습니다.  
  
 참조 [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) in the Windows SDK입니다.  
  
##  <a name="uideactivate"></a>  IOleInPlaceObjectWindowlessImpl::UIDeactivate  
 비활성화 하 고 내부 활성화를 지 원하는 컨트롤의 사용자 인터페이스를 제거 합니다.  
  
```
HRESULT UIDeactivate();
```  
  
### <a name="remarks"></a>설명  
 컨트롤 클래스의 데이터 멤버를 설정 `m_bUIActive` 를 **FALSE**합니다. 이 ATL 구성 함수에서 반환 항상 `S_OK`합니다.  
  
 참조 [IOleInPlaceObject::UIDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms693348) in the Windows SDK입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComControl 클래스](../../atl/reference/ccomcontrol-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
