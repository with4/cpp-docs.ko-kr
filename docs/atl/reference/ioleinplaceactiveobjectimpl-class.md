---
title: "IOleInPlaceActiveObjectImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::EnableModeless
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnDocWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnFrameWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ResizeBorder
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::TranslateAccelerator
dev_langs: C++
helpviewer_keywords:
- IOleInPlaceActiveObjectImpl class
- ActiveX controls [C++], communication between container and control
- IOleInPlaceActiveObject, ATL implementation
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d88f85e83a88b0a1ce2bd4566e3ca479dddc1af
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>IOleInPlaceActiveObjectImpl 클래스
이 클래스는 전체 컨트롤과 해당 컨테이너 간의 통신을 지원 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>
class IOleInPlaceActiveObjectImpl
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IOleInPlaceActiveObjectImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](#contextsensitivehelp)|상황에 맞는 도움말을 사용 하도록 설정 합니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IOleInPlaceActiveObjectImpl::EnableModeless](#enablemodeless)|모덜리스 대화 상자를 사용 하도록 설정 합니다. ATL 구현은 `S_OK`합니다.|  
|[IOleInPlaceActiveObjectImpl::GetWindow](#getwindow)|창 핸들을 가져옵니다.|  
|[IOleInPlaceActiveObjectImpl::OnDocWindowActivate](#ondocwindowactivate)|컨테이너의 문서 창이 활성화 또는 비활성화 하는 경우 컨트롤을 알립니다. ATL 구현은 `S_OK`합니다.|  
|[IOleInPlaceActiveObjectImpl::OnFrameWindowActivate](#onframewindowactivate)|컨테이너의 최상위 프레임 창이 활성화 또는 비활성화 하는 경우 컨트롤을 알립니다. ATL 구현은 반환|  
|[IOleInPlaceActiveObjectImpl::ResizeBorder](#resizeborder)|테두리의 크기를 조정 하는 데 필요한 컨트롤에 알립니다. ATL 구현은 `S_OK`합니다.|  
|[IOleInPlaceActiveObjectImpl::TranslateAccelerator](#translateaccelerator)|컨테이너에서 메뉴 바로 가기 키 메시지를 처리합니다. ATL 구현은 **E_NOTIMPL**합니다.|  
  
  
## <a name="remarks"></a>설명  
 [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299) 인터페이스는 전체 컨트롤과 해당 컨테이너 간에 통신 하는 데 도움을 주는.; 등의 제어 및 컨테이너에 활성 상태를 통신 하 고 컨트롤을 알리는 크기를 조정 해야 자체입니다. 클래스 `IOleInPlaceActiveObjectImpl` 의 기본 구현을 제공 `IOleInPlaceActiveObject` 지원 **IUnknown** 디버그에서 장치 정보 덤프를 전송 하 여 빌드합니다.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IOleInPlaceActiveObject`  
  
 `IOleInPlaceActiveObjectImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="contextsensitivehelp"></a>IOleInPlaceActiveObjectImpl::ContextSensitiveHelp  
 상황에 맞는 도움말을 사용 하도록 설정 합니다.  
  
```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>설명  
 참조 [IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059) in the Windows SDK입니다.  
  
##  <a name="enablemodeless"></a>IOleInPlaceActiveObjectImpl::EnableModeless  
 모덜리스 대화 상자를 사용 하도록 설정 합니다.  
  
```
HRESULT EnableModeless(BOOL fEnable);
```  
  
### <a name="return-value"></a>반환 값  
 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 참조 [IOleInPlaceActiveObject::EnableModeless](http://msdn.microsoft.com/library/windows/desktop/ms680115) in the Windows SDK입니다.  
  
##  <a name="getwindow"></a>IOleInPlaceActiveObjectImpl::GetWindow  
 컨테이너는 컨트롤의 창 핸들을 가져오려면이 함수를 호출 합니다.  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>설명  
 일부 컨테이너는 현재 기간 이동 하는 경우에, 창 없는 되었습니다에 있는 컨트롤과 함께 작동 하지 않습니다. ATL의 구현 하는 경우는 **CComControl::m_bWasOnceWindowless** 데이터 멤버는 **TRUE**, 함수 반환 **E_FAIL**합니다. 그렇지 않은 경우, \* *phwnd* 않습니다 **NULL**, `GetWindow` 할당 *phwnd* 컨트롤 클래스의 데이터 멤버를 `m_hWnd` 를반환합니다.`S_OK`.  
  
 참조 [IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282) in the Windows SDK입니다.  
  
##  <a name="ondocwindowactivate"></a>IOleInPlaceActiveObjectImpl::OnDocWindowActivate  
 컨테이너의 문서 창이 활성화 또는 비활성화 하는 경우 컨트롤을 알립니다.  
  
```
HRESULT OnDocWindowActivate(BOOL fActivate);
```  
  
### <a name="return-value"></a>반환 값  
 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 참조 [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281) in the Windows SDK입니다.  
  
##  <a name="onframewindowactivate"></a>IOleInPlaceActiveObjectImpl::OnFrameWindowActivate  
 컨테이너의 최상위 프레임 창이 활성화 또는 비활성화 하는 경우 컨트롤을 알립니다.  
  
```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```  
  
### <a name="return-value"></a>반환 값  
 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 참조 [ioleinplaceactiveobject:: Onframewindowactivate](http://msdn.microsoft.com/library/windows/desktop/ms683969) in the Windows SDK입니다.  
  
##  <a name="resizeborder"></a>IOleInPlaceActiveObjectImpl::ResizeBorder  
 테두리의 크기를 조정 하는 데 필요한 컨트롤에 알립니다.  
  
```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```  
  
### <a name="return-value"></a>반환 값  
 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 참조 [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053) in the Windows SDK입니다.  
  
##  <a name="translateaccelerator"></a>IOleInPlaceActiveObjectImpl::TranslateAccelerator  
 컨테이너에서 메뉴 바로 가기 키 메시지를 처리합니다.  
  
```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 다음 반환 값을 지원합니다.  
  
 `S_OK`메시지가 성공적으로 변환 되었습니다 하는 경우.  
  
 **S_FALSE** 경우 메시지를 번역 되지 않습니다.  
  
### <a name="remarks"></a>설명  
 참조 [ioleinplaceactiveobject:: Translateaccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) in the Windows SDK입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComControl 클래스](../../atl/reference/ccomcontrol-class.md)  
 [ActiveX 컨트롤 인터페이스](http://msdn.microsoft.com/library/windows/desktop/ms692724)  
 [클래스 개요](../../atl/atl-class-overview.md)
