---
title: "IOleInPlaceObjectWindowlessImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOleInPlaceObjectWindowlessImpl
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
caps.latest.revision: 20
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
ms.openlocfilehash: 06ce03a896c9948bff14b4f91ae48000d07c3edd
ms.lasthandoff: 02/24/2017

---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>IOleInPlaceObjectWindowlessImpl 클래스
이 클래스는 구현 **IUnknown** 창 없는 컨트롤 창 메시지를 수신 하 고 끌어서 놓기 작업에 참여할 수 있도록 하는 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  
  
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
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|상황에 맞는 도움말을 수 있습니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|공급 장치는 `IDropTarget` 끌어서 놓기를 지 원하는 하는 내부 활성, 창 없는 개체에 대 한 인터페이스입니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|창 핸들을 가져옵니다.|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|활성 전체 컨트롤을 비활성화합니다.|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|창 없는 컨트롤 내부에 활성화 된 컨테이너에서 메시지를 디스패치합니다.|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|이전에 비활성화 된 컨트롤을 다시 활성화합니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|표시 되는 전체 컨트롤의 어떤 부분을 나타냅니다.|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|비활성화 하 고 내부 활성화를 지 원하는 사용자 인터페이스를 제거 합니다.|  
  
## <a name="remarks"></a>주의  
 [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) 인터페이스에서 다시 활성화를 관리 하 고 있는 비활성화 제어 하 고 컨트롤의 크기를 표시할지를 결정 합니다. [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) 인터페이스를 창 없는 컨트롤 창 메시지를 수신 하 고 끌어서 놓기 작업에 참여할 수 있습니다. 클래스 `IOleInPlaceObjectWindowlessImpl` 의 기본 구현을 제공 `IOleInPlaceObject` 및 `IOleInPlaceObjectWindowless` 구현 **IUnknown** 장치에서 디버그 덤프를 정보를 전송 하 여 빌드합니다.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IOleInPlaceObjectWindowless`  
  
 `IOleInPlaceObjectWindowlessImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="a-namecontextsensitivehelpa--ioleinplaceobjectwindowlessimplcontextsensitivehelp"></a><a name="contextsensitivehelp"></a>IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp  
 반환 **E_NOTIMPL**합니다.  
  
```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```  
  
### <a name="remarks"></a>주의  
 참조 [IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetdroptargeta--ioleinplaceobjectwindowlessimplgetdroptarget"></a><a name="getdroptarget"></a>IOleInPlaceObjectWindowlessImpl::GetDropTarget  
 반환 **E_NOTIMPL**합니다.  
  
```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```  
  
### <a name="remarks"></a>주의  
 참조 [IOleInPlaceObjectWindowless::GetDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms678535) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetwindowa--ioleinplaceobjectwindowlessimplgetwindow"></a><a name="getwindow"></a>IOleInPlaceObjectWindowlessImpl::GetWindow  
 컨테이너는 컨트롤의 창 핸들을 가져오려면이 함수를 호출 합니다.  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>주의  
 일부 컨테이너에 있는 경우에 현재 기간 이동, 창 없는 되었습니다 컨트롤과 함께 작동 하지 않습니다. ATL의 구현에서 하는 경우 컨트롤 클래스의 데이터 멤버 `m_bWasOnceWindowless` 는 **TRUE**, 함수 반환 **E_FAIL**합니다. 그렇지 않은 경우, *phwnd* 없는 **NULL**, `GetWindow` 설정 \* *phwnd* 컨트롤 클래스의 데이터 멤버를 `m_hWnd` 반환 `S_OK`합니다.  
  
 참조 [IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameinplacedeactivatea--ioleinplaceobjectwindowlessimplinplacedeactivate"></a><a name="inplacedeactivate"></a>IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate  
 내부 활성 컨트롤을 비활성화 하려면 컨테이너에 의해 호출 됩니다.  
  
```
HRESULT InPlaceDeactivate(HWND* phwnd);
```  
  
### <a name="remarks"></a>주의  
 이 메서드는 컨트롤의 상태에 따라 전체 또는 부분 비활성화를 수행합니다. 필요한 경우 컨트롤의 사용자 인터페이스를 비활성화 하 고 컨트롤의 창이 있는 경우 소멸 됩니다. 컨테이너에는 컨트롤이 더 이상 활성화 된 위치에 알립니다. **IOleInPlaceUIWindow** 공간 테두리와 메뉴를 협상 하는 컨테이너에 의해 사용 되는 인터페이스 해제 됩니다.  
  
 참조 [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameonwindowmessagea--ioleinplaceobjectwindowlessimplonwindowmessage"></a><a name="onwindowmessage"></a>IOleInPlaceObjectWindowlessImpl::OnWindowMessage  
 창 없는 컨트롤 내부에 활성화 된 컨테이너에서 메시지를 디스패치합니다.  
  
```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```  
  
### <a name="remarks"></a>주의  
 참조 [IOleInPlaceObjectWindowless::OnWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms693783) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namereactivateandundoa--ioleinplaceobjectwindowlessimplreactivateandundo"></a><a name="reactivateandundo"></a>IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo  
 반환 **E_NOTIMPL**합니다.  
  
```
HRESULT ReactivateAndUndo();
```  
  
### <a name="remarks"></a>주의  
 참조 [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesetobjectrectsa--ioleinplaceobjectwindowlessimplsetobjectrects"></a><a name="setobjectrects"></a>IOleInPlaceObjectWindowlessImpl::SetObjectRects  
 컨테이너 컨트롤의 크기 및/또는 위치 변경 되었음을 알리는에 의해 호출 됩니다.  
  
```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```  
  
### <a name="remarks"></a>주의  
 컨트롤의 업데이트 `m_rcPos` 데이터 멤버 및 제어를 표시 합니다. 클립 영역을 교차 하는 컨트롤의 일부만 표시 됩니다. 컨트롤의 표시 된 클립 이전에 표시 되지만 클리핑 사라졌습니다 컨트롤의 전체 뷰를 다시 그리는 것이 함수를 호출할 수 있습니다.  
  
 참조 [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameuideactivatea--ioleinplaceobjectwindowlessimpluideactivate"></a><a name="uideactivate"></a>IOleInPlaceObjectWindowlessImpl::UIDeactivate  
 비활성화 하 고 내부 활성화를 지 원하는 컨트롤의 사용자 인터페이스를 제거 합니다.  
  
```
HRESULT UIDeactivate();
```  
  
### <a name="remarks"></a>주의  
 컨트롤 클래스의 데이터 멤버를 설정 `m_bUIActive` 를 **FALSE**합니다. 이 작업의 ATL 구현 함수가 반환 항상 `S_OK`합니다.  
  
 참조 [IOleInPlaceObject::UIDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms693348) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComControl 클래스](../../atl/reference/ccomcontrol-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

