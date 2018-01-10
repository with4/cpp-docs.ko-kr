---
title: "CContainedWindowT 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CContainedWindowT
- ATLWIN/ATL::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::Create
- ATLWIN/ATL::CContainedWindowT::DefWindowProc
- ATLWIN/ATL::CContainedWindowT::GetCurrentMessage
- ATLWIN/ATL::CContainedWindowT::RegisterWndSuperclass
- ATLWIN/ATL::CContainedWindowT::SubclassWindow
- ATLWIN/ATL::CContainedWindowT::SwitchMessageMap
- ATLWIN/ATL::CContainedWindowT::UnsubclassWindow
- ATLWIN/ATL::CContainedWindowT::WindowProc
- ATLWIN/ATL::CContainedWindowT::m_dwMsgMapID
- ATLWIN/ATL::CContainedWindowT::m_lpszClassName
- ATLWIN/ATL::CContainedWindowT::m_pfnSuperWindowProc
- ATLWIN/ATL::CContainedWindowT::m_pObject
dev_langs: C++
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4cf792fed2f7a5cac45826649224a565228f9d73
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ccontainedwindowt-class"></a>CContainedWindowT 클래스
이 클래스는 다른 개체에 포함 된 창을 구현 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class CContainedWindowT : public TBase
```  
  
#### <a name="parameters"></a>매개 변수  
 *TBase*  
 새 클래스의 기본 클래스입니다. 기본 클래스는 `CWindow`합니다.  
  
 `TWinTraits`  
 창 스타일을 정의 하는 특성 클래스입니다. 기본값은 `CControlWinTraits`입니다.  
  
> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md) 의 특수화 `CContainedWindowT`합니다. 기본 클래스 또는 특성을 변경 하려는 경우 사용 하 여 `CContainedWindowT` 직접 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CContainedWindowT::CContainedWindowT](#ccontainedwindowt)|생성자입니다. 어떤 메시지 맵에 포함된 된 창의 메시지 처리를 지정 하려면 데이터 멤버를 초기화 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CContainedWindowT::Create](#create)|창을 만듭니다.|  
|[CContainedWindowT::DefWindowProc](#defwindowproc)|기본 메시지 처리를 제공합니다.|  
|[CContainedWindowT::GetCurrentMessage](#getcurrentmessage)|현재 메시지를 반환합니다.|  
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|포함 된 창의 창 클래스를 등록합니다.|  
|[CContainedWindowT::SubclassWindow](#subclasswindow)|창을 서브클래싱합니다.|  
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|변경 내용이 포함된 된 창의 메시지를 처리 하는 메시지 맵을 사용 됩니다.|  
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|이전에 서브클래싱된 창을 복원합니다.|  
|[CContainedWindowT::WindowProc](#windowproc)|(정적) 포함 된 창으로 전송 된 메시지를 처리 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|어떤 메시지 맵에 포함된 된 창의 메시지 처리를 식별 합니다.|  
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|새 창 클래스의 기반이 될 기존 창 클래스의 이름을 지정 합니다.|  
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|창 클래스의 원본 창 프로시저를 가리킵니다.|  
|[CContainedWindowT::m_pObject](#m_pobject)|포함 하는 개체를 가리킵니다.|  
  
## <a name="remarks"></a>설명  
 `CContainedWindowT`다른 개체에 포함 된 창을 구현 합니다. `CContainedWindowT`창 프로시저는 메시지를 적절 한 처리기에 직접 메시지를 포함 하는 개체에 매핑합니다. 생성할 때는 `CContainedWindowT` 개체를 사용 해야 하는 어떤 메시지 맵을 지정 합니다.  
  
 `CContainedWindowT`기존 창 클래스 슈퍼 클 래 싱 하 여 새 창을 만들 수 있습니다. **만들기** 메서드는 먼저 기존 클래스에 기반 하는 창 클래스 등록 `CContainedWindowT::WindowProc`합니다. **만들** 그런 다음이 새 창 클래스를 기반으로 창을 만듭니다. 각 인스턴스에 `CContainedWindowT` 슈퍼 클래스는 다양 한 창 클래스를 수 있습니다.  
  
 `CContainedWindowT`은 또한 창 서브클래싱도 지원합니다. `SubclassWindow` 메서드는 기존 창을 `CContainedWindowT` 개체에 연결하고 창 프로시저를 `CContainedWindowT::WindowProc`로 변경합니다. `CContainedWindowT`의 각 인스턴스는 다른 창을 서브클래싱할 수 있습니다.  
  
> [!NOTE]
>  지정 된 모든 작업에 대 한 `CContainedWindowT` 개체 중 하나를 호출, **만들기** 또는 `SubclassWindow`합니다. 동일한 개체에서 두 메서드를 호출 하지 않아야 합니다.  
  
 사용 하는 경우는 **컨트롤 추가 기준** 옵션 ATL 프로젝트 마법사에서 마법사가 자동으로 추가 `CContainedWindowT` 컨트롤을 구현 하는 클래스 데이터 멤버입니다. 다음 예제에서는 포함된 된 창의 선언 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]  
  
|추가 정보|보기|  
|--------------------------------|---------|  
|컨트롤 만들기|[ATL 자습서](../../atl/active-template-library-atl-tutorial.md)|  
|ATL에서 창 사용하기|[ATL 창 클래스](../../atl/atl-window-classes.md)|  
|ATL 프로젝트 마법사|[ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)|  
|Windows|[Windows](http://msdn.microsoft.com/library/windows/desktop/ms632595) 및 Windows SDK의 후속 항목|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `TBase`  
  
 `CContainedWindowT`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="ccontainedwindowt"></a>CContainedWindowT::CContainedWindowT  
 이 생성자는 데이터 멤버를 초기화 합니다.  
  
```
CContainedWindowT(
    LPTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);

CContainedWindowT(
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0)
    CContainedWindowT();
```     
  
### <a name="parameters"></a>매개 변수  
 `lpszClassName`  
 [in] 포함된 된 창의 기반이 될 기존 창 클래스의 이름입니다.  
  
 `pObject`  
 [in] 메시지 맵을 선언 하는 포함 하는 개체에 대 한 포인터입니다. 이 개체의이 클래스에서 파생 되어야 [CMessageMap](../../atl/reference/cmessagemap-class.md)합니다.  
  
 `dwMsgMapID`  
 [in] 포함된 된 창의 메시지를 처리 하는 메시지 맵을 식별 합니다. 기본값인 0으로 선언 된 기본 메시지 맵을 지정 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)합니다. 대체 메시지 맵을 사용 하려면 사용 하 여 선언 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), 전달 `msgMapID`합니다.  
  
### <a name="remarks"></a>설명  
 통해 새 창을 만들 하려면 [만들기](#create)에 대 한 기존 창 클래스의 이름을 전달 해야는 `lpszClassName` 매개 변수입니다. 예를 들어 참조는 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) 개요입니다.  
  
 세 명의 생성자 가지가 있습니다.  
  
-   3 개의 인수를 사용 하 여 생성자는 일반적으로 호출 됩니다.  
  
-   두 개의 인수를 사용 하 여 생성자에서 클래스 이름을 사용 하 여 **TBase::GetWndClassName**합니다.  
  
-   인수 없는 생성자는 나중에 인수를 제공 하려는 경우에 사용 됩니다. 나중에 호출 하는 경우 창 클래스 이름, 메시지 맵 개체 및 메시지 맵 ID를 제공 해야 **만들기**합니다.  
  
 경우 기존 창 서브 통해 [SubclassWindow](#subclasswindow), `lpszClassName` 값 사용 되지 것입니다; 따라서 전달할 수 있습니다 **NULL** 이 매개 변수에 대 한 합니다.  
  
##  <a name="create"></a>CContainedWindowT::Create  
 호출 [RegisterWndSuperclass](#registerwndsuperclass) 기존 클래스에 기반 하는 창 클래스 등록 [CContainedWindowT::WindowProc](#windowproc)합니다.  
  
```
HWND Create(  
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    LPCTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszClassName`  
 [in] 포함된 된 창의 기반이 될 기존 창 클래스의 이름입니다.  
  
 `pObject`  
 [in] 메시지 맵을 선언 하는 포함 하는 개체에 대 한 포인터입니다. 이 개체의이 클래스에서 파생 되어야 [CMessageMap](../../atl/reference/cmessagemap-class.md)합니다.  
  
 `dwMsgMapID`  
 [in] 포함된 된 창의 메시지를 처리 하는 메시지 맵을 식별 합니다. 기본값인 0으로 선언 된 기본 메시지 맵을 지정 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)합니다. 대체 메시지 맵을 사용 하려면 사용 하 여 선언 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), 전달 `msgMapID`합니다.  
  
 `hWndParent`  
 [in] 부모 또는 소유자 창에 대 한 핸들입니다.  
  
 `rect`  
 [in] A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 창의 위치를 지정 하는 구조입니다. `RECT` 포인터에 의해 또는 참조로 전달할 수 있습니다.  
  
 `szWindowName`  
 [in] 창 이름을 지정합니다. 기본값은 **NULL**합니다.  
  
 `dwStyle`  
 [in] 창 스타일입니다. 기본값은 **WS_CHILD &#124; WS_VISIBLE**합니다. 가능한 값 목록은 참조 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) Windows sdk에서입니다.  
  
 `dwExStyle`  
 [in] 확장된 창 스타일입니다. 기본값은 0, 의미 없는 확장된 스타일입니다. 가능한 값 목록은 참조 하십시오. [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows sdk에서입니다.  
  
 `MenuOrID`  
 [in] 에 대 한 자식 창, 창 식별자입니다. 최상위 창에 대 한 메뉴 창에 대 한 처리 합니다. 기본값은 **0U**합니다.  
  
 `lpCreateParam`  
 [in] 창 만들기 데이터에 대 한 포인터입니다. 에 대 한 전체 설명은 마지막 매개 변수를 대 한 설명을 참조 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 새로 만든된 창에 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 기존 창 클래스 이름에 저장 됩니다 [m_lpszClassName](#m_lpszclassname)합니다. **만들** 그런 다음이 새 클래스를 기반으로 창을 만듭니다. 새로 만든된 창에 자동으로 연결 되는 `CContainedWindowT` 개체입니다.  
  
> [!NOTE]
>  호출 하지 마십시오 **만들기** 이미 호출한 경우 [SubclassWindow](#subclasswindow)합니다.  
  
> [!NOTE]
>  0에 대 한 값으로 사용 되는 경우는 `MenuOrID` 매개 변수를 0U로 지정 해야 합니다 (기본값) 컴파일러 오류가 발생 하지 않도록 합니다.  
  
##  <a name="defwindowproc"></a>CContainedWindowT::DefWindowProc  
 에 의해 호출 [WindowProc](#windowproc) 메시지를 처리 하는 메시지 맵에 의해 처리 되지 않습니다.  
  
```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
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
  
##  <a name="getcurrentmessage"></a>CContainedWindowT::GetCurrentMessage  
 현재 메시지를 반환 합니다 ( **m_pCurrentMsg**).  
  
```
const _ATL_MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>반환 값  
 패키지에 현재 메시지는 `MSG` 구조입니다.  
  
##  <a name="m_dwmsgmapid"></a>CContainedWindowT::m_dwMsgMapID  
 포함 된 창에 대 한 현재 사용 중인 메시지 맵의 식별자를 포함 합니다.  
  
```
DWORD m_dwMsgMapID;
```  
  
### <a name="remarks"></a>설명  
 이 메시지 맵은 포함 하는 개체에 선언 되어야 합니다.  
  
 기본 메시지 맵을 사용 하 여 선언 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), 항상 0으로 식별 됩니다. 대체 메시지 맵을 사용 하 여 선언 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map),으로 식별 되 `msgMapID`합니다.  
  
 `m_dwMsgMapID`생성자가 먼저 초기화 되 고 호출 하 여 변경할 수 있습니다 [SwitchMessageMap](#switchmessagemap)합니다. 예를 들어 참조는 [CContainedWindowT 개요](../../atl/reference/ccontainedwindowt-class.md)합니다.  
  
##  <a name="m_lpszclassname"></a>CContainedWindowT::m_lpszClassName  
 기존 창 클래스의 이름을 지정합니다.  
  
```
LPTSTR m_lpszClassName;
```  
  
### <a name="remarks"></a>설명  
 창을 만들 때 [만들기](#create) 이 기존 클래스에 기반 하는 새 창 클래스 등록 [CContainedWindowT::WindowProc](#windowproc)합니다.  
  
 `m_lpszClassName`생성자에 의해 초기화 됩니다. 예를 들어 참조는 [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) 개요입니다.  
  
##  <a name="m_pfnsuperwindowproc"></a>CContainedWindowT::m_pfnSuperWindowProc  
 포함된 된 창의 서브클래싱된 경우 `m_pfnSuperWindowProc` 창 클래스의 원본 창 프로시저를 가리킵니다.  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>설명  
 포함 된 창을 슈퍼 클래스로 지정 된 경우 기존 클래스를 수정 하는 창 클래스에 기반 것을 의미 `m_pfnSuperWindowProc` 기존 창 클래스의 창 프로시저를 가리킵니다.  
  
 [DefWindowProc](#defwindowproc) 메서드 창 프로시저에 저장 된 메시지 정보는 전송 `m_pfnSuperWindowProc`합니다.  
  
##  <a name="m_pobject"></a>CContainedWindowT::m_pObject  
 포함 하는 개체를 가리키는 `CContainedWindowT` 개체입니다.  
  
```
CMessageMap* m_pObject;
```  
  
### <a name="remarks"></a>설명  
 해당 클래스에서 파생 되어야이 컨테이너 [CMessageMap](../../atl/reference/cmessagemap-class.md), 포함 된 창에서 사용 하는 메시지 맵을 선언 합니다.  
  
 `m_pObject`생성자에 의해 초기화 됩니다. 예를 들어 참조는 [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) 개요입니다.  
  
##  <a name="registerwndsuperclass"></a>CContainedWindowT::RegisterWndSuperclass  
 에 의해 호출 [만들기](#create) 포함 된 창의 창 클래스를 등록 합니다.  
  
```
ATOM RegisterWndSuperClass();
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 atom 고유 하 게 식별 하는 등록 되는 창 클래스 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 창 클래스는 기존 클래스를 기반으로 하지만 사용 하 여 [CContainedWindowT::WindowProc](#windowproc)합니다. 기존 창 클래스의 이름 및 창 프로시저에 저장 됩니다 [m_lpszClassName](#m_lpszclassname) 및 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)각각.  
  
##  <a name="subclasswindow"></a>CContainedWindowT::SubclassWindow  
 로 식별 되는 창을 서브 클래스 `hWnd` 에 연결 된 `CContainedWindowT` 개체입니다.  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `hWnd`  
 [in] 서브클래싱된 되 고 창에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 창이 서브클래싱된 않으면 고, 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 서브클래싱된 창을 사용 하 여 이제 [CContainedWindowT::WindowProc](#windowproc)합니다. 원본 창 프로시저에 저장 된 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)합니다.  
  
> [!NOTE]
>  호출 하지 마십시오 `SubclassWindow` 이미 호출한 경우 [만들기](#create)합니다.  
  
##  <a name="switchmessagemap"></a>CContainedWindowT::SwitchMessageMap  
 포함된 된 창의 메시지를 처리할 수 있는 메시지 맵이 사용 되는 변경 됩니다.  
  
```
void SwitchMessageMap(DWORD dwMsgMapID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwMsgMapID`  
 [in] 메시지 맵 식별자입니다. 기본 메시지 맵을 사용 하려면 사용 하 여 선언 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), 0을 전달 합니다. 대체 메시지 맵을 사용 하려면 사용 하 여 선언 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), 전달 `msgMapID`합니다.  
  
### <a name="remarks"></a>설명  
 메시지 맵은 포함 하는 개체에 정의 되어야 합니다.  
  
 처음 생성자에 메시지 맵 식별자를 지정 합니다.  
  
##  <a name="unsubclasswindow"></a>CContainedWindowT::UnsubclassWindow  
 서브클래싱된 창을 분리는 `CContainedWindowT` 개체에 저장 된 원래 창 프로시저를 복원 및 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)합니다.  
  
```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bForce`  
 [in] 로 설정 **TRUE** 복원할 원본 창 프로시저를 강제로 경우에이 대 한 창 프로시저 `CContainedWindowT` 개체 현재 활성화 되지 않았습니다. 경우 `bForce` 로 설정 된 **FALSE** 및이 대 한 창 프로시저 `CContainedWindowT` 개체 현재 활성 상태 이면 원본 창 프로시저를 복원 되지 것입니다.  
  
### <a name="return-value"></a>반환 값  
 이전에 서브클래싱된 창 핸들입니다. 경우 `bForce` 로 설정 된 **FALSE** 및이 대 한 창 프로시저 `CContainedWindowT` 개체 현재 활성 상태인 반환 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 창이 소멸 되기 전에 원본 창 프로시저를 복원 하려는 경우에이 방법을 사용 합니다. 그렇지 않으면 [WindowProc](#windowproc) 는 자동으로 이렇게 창이 소멸 될 때입니다.  
  
##  <a name="windowproc"></a>CContainedWindowT::WindowProc  
 이 정적 메서드 창 프로시저를 구현합니다.  
  
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
 `WindowProc`메시지 맵에 식별 되는 메시지를 보냅니다 [m_dwMsgMapID](#m_dwmsgmapid)합니다. 필요한 경우 `WindowProc` 호출 [DefWindowProc](#defwindowproc) 추가 메시지 처리에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWindow 클래스](../../atl/reference/cwindow-class.md)   
 [CWindowImpl 클래스](../../atl/reference/cwindowimpl-class.md)   
 [CMessageMap 클래스](../../atl/reference/cmessagemap-class.md)   
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)   
 [클래스 개요](../../atl/atl-class-overview.md)
