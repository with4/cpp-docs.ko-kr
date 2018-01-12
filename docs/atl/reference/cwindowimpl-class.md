---
title: "CWindowImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWindowImpl
- ATLWIN/ATL::CWindowImpl
- ATLWIN/ATL::CWindowImpl::Create
- ATLWIN/ATL::DefWindowProc
- ATLWIN/ATL::GetCurrentMessage
- ATLWIN/ATL::GetWindowProc
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::SubclassWindow
- ATLWIN/ATL::UnsubclassWindow
- ATLWIN/ATL::GetWndClassInfo
- ATLWIN/ATL::WindowProc
- ATLWIN/ATL::m_pfnSuperWindowProc
dev_langs: C++
helpviewer_keywords:
- CWindowImpl class
- subclassing windows, ATL
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3aa14c3ae6c083cbf440d8b5b94fcb3754bd6fff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cwindowimpl-class"></a>CWindowImpl 클래스
창을 만들거나 서브클래싱하기 위한 메서드를 제공합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```    
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 `CWindowImpl`에서 파생된 새 클래스입니다.  
  
 *TBase*  
 클래스의 기본 클래스입니다. 기본적으로 기본 클래스는 [CWindow](../../atl/reference/cwindow-class.md)합니다.  
  
 `TWinTraits`  
 A [특성 클래스](../../atl/understanding-window-traits.md) 창 스타일을 정의 하는 합니다. 기본값은 `CControlWinTraits`입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CWindowImpl::Create](#create)|창을 만듭니다.|  
  
### <a name="cwindowimplbaset-methods"></a>CWindowImplBaseT 메서드  
  
|||  
|-|-|  
|[DefWindowProc](#defwindowproc)|기본 메시지 처리를 제공합니다.|  
|[GetCurrentMessage](#getcurrentmessage)|현재 메시지를 반환합니다.|  
|[GetWindowProc](#getwindowproc)|현재 창 프로시저를 반환합니다.|  
|[OnFinalMessage](#onfinalmessage)|마지막 메시지를 받은 후 호출됩니다(일반적으로 `WM_NCDESTROY`).|  
|[SubclassWindow](#subclasswindow)|창을 서브클래싱합니다.|  
|[UnsubclassWindow](#unsubclasswindow)|이전에 서브클래싱된 창을 복원합니다.|  
  
### <a name="static-methods"></a>정적 메서드  
  
|||  
|-|-|  
|[GetWndClassInfo](#getwndclassinfo)|정적 인스턴스를 반환 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)에 대 한 관리 창 클래스 정보입니다.|  
|[WindowProc](#windowproc)|창으로 보내는 메시지를 처리합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|창 클래스의 원본 창 프로시저를 가리킵니다.|  
  
## <a name="remarks"></a>설명  
 사용할 수 있습니다 `CWindowImpl` 창이 나 하위 클래스는 기존 창을 만들 수 있습니다. `CWindowImpl` 창 프로시저는 메시지 맵을 사용 하 여 메시지를 적절 한 처리기입니다.  
  
 `CWindowImpl::Create`관리 되는 창 클래스 정보를 기반으로 창을 만듭니다 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)합니다. `CWindowImpl`포함 된 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) 의미 하는 매크로 `CWndClassInfo` 는 새 창 클래스 등록 합니다. Superclass 기존 창 클래스를 하려는 경우에서 클래스를 파생 `CWindowImpl` 포함는 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 매크로입니다. 이 경우 `CWndClassInfo`는 기존 클래스를 기반으로 하는 창 클래스 등록하지만 `CWindowImpl::WindowProc`를 사용합니다. 예:  
  
 [!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]  
  
> [!NOTE]
>  `CWndClassInfo`는 한 윈도우 클래스의 정보만 관리하기 때문에, `CWindowImpl`의 인스턴스를 통해 생성된 각 창은 동일한 창 클래스를 기반으로 합니다.  
  
 `CWindowImpl`은 또한 창 서브클래싱도 지원합니다. `SubclassWindow` 메서드는 기존 창을 `CWindowImpl` 개체에 연결하고 창 프로시저를 `CWindowImpl::WindowProc`로 변경합니다. `CWindowImpl`의 각 인스턴스는 다른 창을 서브클래싱할 수 있습니다.  
  
> [!NOTE]
>  지정 된 모든 작업에 대 한 `CWindowImpl` 개체 중 하나를 호출, **만들기** 또는 `SubclassWindow`합니다. 동일한 개체에서 두 메서드를 모두 호출하지는 마십시오.  
  
 외에 `CWindowImpl`, ATL 제공 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) 다른 개체에 포함 된 창을 만들 수 있습니다.  
  
 기본 클래스 소멸자 (~ **CWindowImplRoot**) 사라지도록 보장 창 개체 소멸 되기 전에 합니다.  
  
 `CWindowImpl`파생 **CWindowImplBaseT**에서 파생 되는 **CWindowImplRoot**에서 파생 되는 **TBase** 및 [CMessageMap](../../atl/reference/cmessagemap-class.md)합니다.  
  
|추가 정보|보기|  
|--------------------------------|---------|  
|컨트롤 만들기|[ATL 자습서](../../atl/active-template-library-atl-tutorial.md)|  
|ATL에서 창 사용하기|[ATL 창 클래스](../../atl/atl-window-classes.md)|  
|ATL 프로젝트 마법사|[ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CWindowImplBaseT`  
  
 `CWindowImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="create"></a>CWindowImpl::Create  
 새 창 클래스를 기반으로 창을 만듭니다.  
  
```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `hWndParent`  
 [in] 부모 또는 소유자 창에 대 한 핸들입니다.  
  
 `rect`  
 [in] A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 창의 위치를 지정 하는 구조입니다. `RECT` 포인터에 의해 또는 참조로 전달할 수 있습니다.  
  
 `szWindowName`  
 [in] 창 이름을 지정합니다. 기본값은 **NULL**합니다.  
  
 `dwStyle`  
 [in] 창 스타일입니다. 이 값은 창에 대 한 특성 클래스에서 제공 하는 스타일와 결합 됩니다. 기본값을 사용 하는 특성 클래스를 완전히 제어할 스타일을 제공합니다. 가능한 값 목록은 참조 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) Windows sdk에서입니다.  
  
 `dwExStyle`  
 [in] 확장된 창 스타일입니다. 이 값은 창에 대 한 특성 클래스에서 제공 하는 스타일와 결합 됩니다. 기본값을 사용 하는 특성 클래스를 완전히 제어할 스타일을 제공합니다. 가능한 값 목록은 참조 하십시오. [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows sdk에서입니다.  
  
 `MenuOrID`  
 [in] 에 대 한 자식 창, 창 식별자입니다. 최상위 창에 대 한 메뉴 창에 대 한 처리 합니다. 기본값은 **0U**합니다.  
  
 `lpCreateParam`  
 [in] 창 만들기 데이터에 대 한 포인터입니다. 에 대 한 전체 설명은 마지막 매개 변수를 대 한 설명을 참조 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 새로 만든된 창에 대 한 핸들입니다. 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 **만들** 아직 등록 되지 않은 경우 먼저 창 클래스를 등록 합니다. 새로 만든된 창에 자동으로 연결 되는 `CWindowImpl` 개체입니다.  
  
> [!NOTE]
>  호출 하지 마십시오 **만들기** 이미 호출한 경우 [SubclassWindow](#subclasswindow)합니다.  
  
 기존 창 클래스를 기반으로 하는 창 클래스를 사용 하려면에서 클래스를 파생 `CWindowImpl` 포함는 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 매크로입니다. 에 저장 된 기존 창 클래스의 창 프로시저 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)합니다. 자세한 내용은 참조는 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 개요입니다.  
  
> [!NOTE]
>  0에 대 한 값으로 사용 되는 경우는 `MenuOrID` 매개 변수를 0U로 지정 해야 합니다 (기본값) 컴파일러 오류가 발생 하지 않도록 합니다.  
  
##  <a name="defwindowproc"></a>CWindowImpl::DefWindowProc  
 에 의해 호출 [WindowProc](#windowproc) 메시지를 처리 하는 메시지 맵에 의해 처리 되지 않습니다.  
  
```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```  
  
### <a name="parameters"></a>매개 변수  
 `uMsg`  
 [in] 창에 전송 하는 메시지입니다.  
  
 `wParam`  
 [in] 추가 메시지 관련 정보입니다.  
  
 `lParam`  
 [in] 추가 메시지 관련 정보입니다.  
  
### <a name="return-value"></a>반환 값  
 메시지 처리의 결과입니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 `DefWindowProc` 호출은 [CallWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633571) Win32 함수에 지정 된 창 프로시저에 메시지 정보를 보내거나 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)합니다.  
  
 자동으로 매개 변수가 없는 함수는 현재 메시지에서 필요한 매개 변수를 검색합니다.  
  
##  <a name="getcurrentmessage"></a>CWindowImpl::GetCurrentMessage  
 패키지에 현재 메시지를 반환 된 `MSG` 구조입니다.  
  
```
const MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>반환 값  
 현재 메시지입니다.  
  
##  <a name="getwindowproc"></a>CWindowImpl::GetWindowProc  
 반환 `WindowProc`, 현재 창 프로시저입니다.  
  
```
virtual WNDPROC GetWindowProc();
```  
  
### <a name="return-value"></a>반환 값  
 현재 창 프로시저입니다.  
  
### <a name="remarks"></a>설명  
 사용자의 창 프로시저로 바꾸려면이 메서드를 재정의 합니다.  
  
##  <a name="getwndclassinfo"></a>CWindowImpl::GetWndClassInfo  
 에 의해 호출 [만들기](#create) 창 클래스 정보에 액세스할 수 있습니다.  
  
```
static CWndClassInfo& GetWndClassInfo();
```  
  
### <a name="return-value"></a>반환 값  
 정적 인스턴스 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)합니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 `CWindowImpl` 를 통해이 메서드를 가져옵니다는 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) 새 창 클래스를 지정 하는 매크로입니다.  
  
 Superclass 기존 창 클래스에서 클래스 파생 `CWindowImpl` 포함는 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 재정의 하는 매크로 `GetWndClassInfo`합니다. 자세한 내용은 참조는 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 개요입니다.  
  
 사용 하 여 외에도 `DECLARE_WND_CLASS` 및 `DECLARE_WND_SUPERCLASS` 재정의할 수 매크로 `GetWndClassInfo` 사용자 구현으로 합니다.  
  
##  <a name="m_pfnsuperwindowproc"></a>CWindowImpl::m_pfnSuperWindowProc  
 창에 따라 다음 창 프로시저 중 하나를 가리킵니다.  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>설명  
  
|창 유형으로|창 프로시저|  
|--------------------|----------------------|  
|통해 지정 된 새 창 클래스를 기반으로 하는 창을 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) 매크로입니다.|[DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572) Win32 함수입니다.|  
|통해 지정 된 기존 클래스를 수정 하는 창 클래스를 기반으로 창을 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 매크로입니다.|기존 창 클래스의 창 프로시저입니다.|  
|서브클래싱된 창입니다.|서브클래싱된 창의 원본 창 프로시저입니다.|  
  
 [CWindowImpl::DefWindowProc](#defwindowproc) 보내는 메시지는 정보에 저장 하 고 창 프로시저를 `m_pfnSuperWindowProc`합니다.  
  
##  <a name="onfinalmessage"></a>CWindowImpl::OnFinalMessage  
 마지막 메시지를 받은 후에 호출 (일반적으로 `WM_NCDESTROY`).  
  
```
virtual void OnFinalMessage(HWND hWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `hWnd`  
 [in] 제거 되 고 한 창 핸들입니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 `OnFinalMessage` 아무 것도 수행 되지만 창을 삭제 하기 전에 정리를 처리 하려면이 함수를 재정의할 수 있습니다. 창 소멸 시 개체를 자동으로 삭제 하려는 경우 호출할 수 있습니다 `delete this;` 이 함수에 있습니다.  
  
##  <a name="subclasswindow"></a>CWindowImpl::SubclassWindow  
 로 식별 되는 창을 서브 클래스 `hWnd` 에 연결 된 `CWindowImpl` 개체입니다.  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `hWnd`  
 [in] 서브클래싱된 되 고 창에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 창이 서브클래싱된 않으면 고, 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 서브클래싱된 창을 사용 하 여 이제 [CWindowImpl::WindowProc](#windowproc)합니다. 원본 창 프로시저에 저장 된 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)합니다.  
  
> [!NOTE]
>  호출 하지 마십시오 `SubclassWindow` 이미 호출한 경우 [만들기](#create)합니다.  
  
##  <a name="unsubclasswindow"></a>CWindowImpl::UnsubclassWindow  
 서브클래싱된 창을 분리는 `CWindowImpl` 개체에 저장 된 원래 창 프로시저를 복원 및 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)합니다.  
  
```
HWND UnsubclassWindow();
```  
  
### <a name="return-value"></a>반환 값  
 이전에 서브클래싱된 창 핸들입니다.  
  
##  <a name="windowproc"></a>CWindowImpl::WindowProc  
 이 정적 함수는 창 프로시저를 구현합니다.  
  
```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```  
  
### <a name="parameters"></a>매개 변수  
 `hWnd`  
 [in] 창 핸들입니다.  
  
 `uMsg`  
 [in] 창에 전송 하는 메시지입니다.  
  
 `wParam`  
 [in] 추가 메시지 관련 정보입니다.  
  
 `lParam`  
 [in] 추가 메시지 관련 정보입니다.  
  
### <a name="return-value"></a>반환 값  
 메시지 처리의 결과입니다.  
  
### <a name="remarks"></a>설명  
 `WindowProc`기본 메시지 맵을 사용 하 여 (사용 하 여 선언 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)) 메시지를 적절 한 처리기를 합니다. 필요한 경우 `WindowProc` 호출 [DefWindowProc](#defwindowproc) 추가 메시지 처리에 대 한 합니다. 최종 메시지 처리 되지 않은 경우 `WindowProc` 다음 작업을 수행 합니다.  
  
-   창을 서브클래싱 하지 않았으면 unsubclassing 수행 합니다.  
  
-   
          `m_hWnd`을 지웁니다.  
  
-   호출 [OnFinalMessage](#onfinalmessage) 창을 소멸 되기 전에 합니다.  
  
 재정의할 수 `WindowProc` 메시지를 처리 하기 위한 다른 메커니즘을 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [CComControl 클래스](../../atl/reference/ccomcontrol-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
