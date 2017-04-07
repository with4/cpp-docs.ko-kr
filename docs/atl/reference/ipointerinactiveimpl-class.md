---
title: "IPointerInactiveImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl::GetActivationPolicy
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveMouseMove
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveSetCursor
dev_langs:
- C++
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
caps.latest.revision: 21
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 05cf4b2247cabe713cfc6b0dd54c95c01e5bbddc
ms.lasthandoff: 02/24/2017

---
# <a name="ipointerinactiveimpl-class"></a>IPointerInactiveImpl 클래스
이 클래스는 구현 **IUnknown** 및 [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) 인터페이스 메서드.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>
class IPointerInactiveImpl
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IPointerInactiveImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|개체에 대 한 현재 정품 인증 정책을 검색합니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IPointerInactiveImpl::OnInactiveMouseMove](#oninactivemousemove)|마우스 포인터에 올려 놓을, 개체를 나타내는 개체 마우스 이벤트를 발생 시킬 수에 알립니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|비활성 개체에 대 한 마우스 포인터를 설정합니다. ATL 구현은 **E_NOTIMPL**합니다.|  
  
## <a name="remarks"></a>주의  
 비활성 개체는 단순히 로드 또는 실행 중입니다. 현재 개체와 달리 비활성 개체는 Windows 마우스 및 키보드 메시지를 받을 수 없습니다. 따라서 비활성 개체 리소스를 적게 사용 하 고는 일반적으로 더 효율적입니다.  
  
 [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) 인터페이스, 최소 수준의 비활성을 유지 하면서 마우스 상호 작용을 지원 하기 위해 개체를 사용 합니다. 이 기능은 컨트롤에 특히 유용 합니다.  
  
 클래스 `IPointerInactiveImpl` 구현 하는 `IPointerInactive` 단순히 반환 메서드 **E_NOTIMPL**합니다. 그러나 구현 **IUnknown** 장치에서 디버그 덤프를 정보를 전송 하 여 빌드합니다.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IPointerInactive`  
  
 `IPointerInactiveImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="getactivationpolicy"></a>IPointerInactiveImpl::GetActivationPolicy  
 개체에 대 한 현재 정품 인증 정책을 검색합니다.  
  
```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>주의  
 참조 [IPointerInactive::GetActivationPolicy](http://msdn.microsoft.com/library/windows/desktop/ms692470) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="oninactivemousemove"></a>IPointerInactiveImpl::OnInactiveMouseMove  
 마우스 포인터에 올려 놓을, 개체를 나타내는 개체 마우스 이벤트를 발생 시킬 수에 알립니다.  
  
```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>주의  
 참조 [IPointerInactive::OnInactiveMouseMove](http://msdn.microsoft.com/library/windows/desktop/ms693374) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="oninactivesetcursor"></a>IPointerInactiveImpl::OnInactiveSetCursor  
 비활성 개체에 대 한 마우스 포인터를 설정합니다.  
  
```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>주의  
 참조 [IPointerInactive::OnInactiveSetCursor](http://msdn.microsoft.com/library/windows/desktop/ms694336) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

