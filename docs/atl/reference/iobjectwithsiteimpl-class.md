---
title: IObjectWithSiteImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl::GetSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetChildSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetSite
- ATLCOM/ATL::IObjectWithSiteImpl::m_spUnkSite
dev_langs:
- C++
helpviewer_keywords:
- IObjectWithSiteImpl class
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a9403ed1a4ba82a1e60c42ed0e57e975e73d1dd
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883790"
---
# <a name="iobjectwithsiteimpl-class"></a>IObjectWithSiteImpl 클래스
이 클래스는 해당 사이트와 통신 하는 개체를 허용 하는 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```  
  
#### <a name="parameters"></a>매개 변수  
 *T*  
 클래스에서 파생 된 `IObjectWithSiteImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IObjectWithSiteImpl::GetSite](#getsite)|사이트에 대 한 인터페이스 포인터를 쿼리합니다.|  
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|사이트를 사용 하 여 개체를 제공 `IUnknown` 포인터입니다.|  
|[IObjectWithSiteImpl::SetSite](#setsite)|사이트를 사용 하 여 개체를 제공 `IUnknown` 포인터입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|사이트의 관리 `IUnknown` 포인터입니다.|  
  
## <a name="remarks"></a>설명  
 합니다 [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) 인터페이스를 사용 하면 사이트와 통신 하는 개체입니다. 클래스 `IObjectWithSiteImpl` 이 인터페이스의 기본 구현을 제공 하 고 구현 `IUnknown` 장치에서 디버그 덤프에 정보를 전송 하 여 작성 합니다.  
  
 `IObjectWithSiteImpl` 두 메서드를 지정합니다. 클라이언트 첫 번째 호출 `SetSite`, 사이트의 전달 `IUnknown` 포인터입니다. 이 포인터는 개체 내에서 저장 되 고 나중에 호출을 통해 검색할 수 `GetSite`입니다.  
  
 클래스를 파생 하는 일반적으로 `IObjectWithSiteImpl` 컨트롤이 아닌 만들 때 개체입니다. 컨트롤에서 클래스를 파생 [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)를 제공 하는 사이트 대 한 포인터입니다. 클래스에서 파생 되지 않은 `IObjectWithSiteImpl` 고 `IOleObjectImpl`입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IObjectWithSite`  
  
 `IObjectWithSiteImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="getsite"></a>  IObjectWithSiteImpl::GetSite  
 사이트에서 식별 된 인터페이스에 대 한 포인터에 대 한 쿼리 `riid`합니다.  
  
```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```  
  
### <a name="remarks"></a>설명  
 통해 반환 된 포인터에 사이트에서이 인터페이스를 지 원하는 경우 `ppvSite`합니다. 그렇지 않으면 `ppvSite` NULL로 설정 됩니다.  
  
 참조 [IObjectWithSite::GetSite](http://msdn.microsoft.com/library/windows/desktop/ms694452) Windows SDK에에서 있습니다.  
  
##  <a name="m_spunksite"></a>  IObjectWithSiteImpl::m_spUnkSite  
 사이트의 관리 `IUnknown` 포인터입니다.  
  
```
CComPtr<IUnknown> m_spUnkSite;
```  
  
### <a name="remarks"></a>설명  
 `m_spUnkSite` 처음 호출을 통해이 포인터를 받는 [SetSite](#setsite)합니다.  
  
##  <a name="setchildsite"></a>  IObjectWithSiteImpl::SetChildSite  
 사이트를 사용 하 여 개체를 제공 `IUnknown` 포인터입니다.  
  
```
HRESULT SetChildSite(IUnknown* pUnkSite);
```  
  
### <a name="parameters"></a>매개 변수  
 *pUnkSite*  
 [in] 에 대 한 포인터를 `IUnknown` 이 개체를 관리 하는 사이트의 인터페이스 포인터입니다. NULL 인 경우 개체를 호출 해야 `IUnknown::Release` 이때 개체가 더 이상 인식 사이트 기존 사이트의.  
  
### <a name="return-value"></a>반환 값  
 S_OK 반환 합니다.  
  
##  <a name="setsite"></a>  IObjectWithSiteImpl::SetSite  
 사이트를 사용 하 여 개체를 제공 `IUnknown` 포인터입니다.  
  
```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```  
  
### <a name="remarks"></a>설명  
 참조 [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869) Windows SDK에에서 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
