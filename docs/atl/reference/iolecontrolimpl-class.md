---
title: "IOleControlImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOleControlImpl
- ATLCTL/ATL::IOleControlImpl
- ATLCTL/ATL::IOleControlImpl::FreezeEvents
- ATLCTL/ATL::IOleControlImpl::GetControlInfo
- ATLCTL/ATL::IOleControlImpl::OnAmbientPropertyChange
- ATLCTL/ATL::IOleControlImpl::OnMnemonic
dev_langs: C++
helpviewer_keywords: IOleControlImpl class
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 23375f8f76e1a58bf29e3e3e269077fea4ae8d61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl 클래스
이 클래스의 기본 구현을 제공는 **IOleControl** 인터페이스와 구현 **IUnknown**합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>
class IOleControlImpl
```   
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IOleControlImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IOleControlImpl::FreezeEvents](#freezeevents)|컨테이너를 무시 또는 컨트롤에서 이벤트를 수신 여부를 나타냅니다.|  
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|컨트롤의 키보드 동작에 대 한 정보를 채웁니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|컨테이너의 앰비언트 속성 중 하나 이상이 변경 된 컨트롤에 알립니다. ATL 구현은 `S_OK`합니다.|  
|[IOleControlImpl::OnMnemonic](#onmnemonic)|사용자가 지정 된 키를 눌렀습니다 컨트롤에 알립니다. ATL 구현은 **E_NOTIMPL**합니다.|  
  
## <a name="remarks"></a>설명  
 클래스 `IOleControlImpl` 의 기본 구현을 제공는 [IOleControl](http://msdn.microsoft.com/library/windows/desktop/ms694320) 인터페이스와 구현 **IUnknown** 디버그에서 장치 정보 덤프를 전송 하 여 빌드합니다.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IOleControl`  
  
 `IOleControlImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="freezeevents"></a>IOleControlImpl::FreezeEvents  
 ATL의 구현에서 `FreezeEvents` 컨트롤 클래스를 증가 시킵니다. `m_nFreezeEvents` 데이터 멤버 경우 `bFreeze` 은 **TRUE**, 하 고 감소 `m_nFreezeEvents` 경우 `bFreeze` 은 **FALSE**.  
  
```
HRESULT FreezeEvents(BOOL bFreeze);
```  
  
### <a name="remarks"></a>설명  
 `FreezeEvents`그런 다음 반환 `S_OK`합니다.  
  
 참조 [IOleControl::FreezeEvents](http://msdn.microsoft.com/library/windows/desktop/ms678482) in the Windows SDK입니다.  
  
##  <a name="getcontrolinfo"></a>IOleControlImpl::GetControlInfo  
 컨트롤의 키보드 동작에 대 한 정보를 채웁니다.  
  
```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```  
  
### <a name="remarks"></a>설명  
 참조 [IOleControl:GetControlInfo](http://msdn.microsoft.com/library/windows/desktop/ms693730) in the Windows SDK입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
##  <a name="onambientpropertychange"></a>IOleControlImpl::OnAmbientPropertyChange  
 컨테이너의 앰비언트 속성 중 하나 이상이 변경 된 컨트롤에 알립니다.  
  
```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="return-value"></a>반환 값  
 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 참조 [IOleControl::OnAmbientPropertyChange](http://msdn.microsoft.com/library/windows/desktop/ms690175) in the Windows SDK입니다.  
  
##  <a name="onmnemonic"></a>IOleControlImpl::OnMnemonic  
 사용자가 지정 된 키를 눌렀습니다 컨트롤에 알립니다.  
  
```
HRESULT OnMnemonic(LPMSG pMsg);
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>설명  
 참조 [IOleControl::OnMnemonic](http://msdn.microsoft.com/library/windows/desktop/ms680699) in the Windows SDK입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IOleObjectImpl 클래스](../../atl/reference/ioleobjectimpl-class.md)   
 [ActiveX 컨트롤 인터페이스](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [클래스 개요](../../atl/atl-class-overview.md)
