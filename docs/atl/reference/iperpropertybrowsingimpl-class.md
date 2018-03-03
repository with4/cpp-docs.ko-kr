---
title: "IPerPropertyBrowsingImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetDisplayString
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedStrings
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedValue
- ATLCTL/ATL::IPerPropertyBrowsingImpl::MapPropertyToPage
dev_langs:
- C++
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dca0c4e519703408af1ca5b6834e4b311c70bd21
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="iperpropertybrowsingimpl-class"></a>IPerPropertyBrowsingImpl 클래스
이 클래스는 구현 **IUnknown** 및 클라이언트 개체의 속성 페이지의 정보에 액세스할 수 있습니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IPerPropertyBrowsingImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|지정된 된 속성을 설명 하는 문자열을 검색 합니다.|  
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|지정 된 속성이 허용 될 수 있는 값에 해당 하는 문자열의 배열을 검색 합니다.|  
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|검색 한 **VARIANT** 주어진된 DISPID로 식별 되는 속성의 값이 포함 합니다. 검색 문자열 이름으로 연결 된 DISPID `GetPredefinedStrings`합니다. ATL 구현은 **E_NOTIMPL**합니다.|  
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|지정 된 속성과 연결 된 속성 페이지의 CLSID를 검색 합니다.|  
  
## <a name="remarks"></a>설명  
 [IPerPropertyBrowsing](http://msdn.microsoft.com/library/windows/desktop/ms678432) 인터페이스 개체의 속성 페이지의 정보에 액세스할 클라이언트 수 있습니다. 클래스 `IPerPropertyBrowsingImpl` 이 인터페이스의 기본 구현을 제공 하 고 구현 **IUnknown** 디버그에서 장치 정보 덤프를 전송 하 여 빌드합니다.  
  
> [!NOTE]
>  클래스를 파생 해야 Microsoft Access 컨테이너 응용 프로그램을 사용 중인 경우 `IPerPropertyBrowsingImpl`합니다. 그렇지 않으면 액세스 컨트롤을 로드 되지 않습니다.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IPerPropertyBrowsing`  
  
 `IPerPropertyBrowsingImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="getdisplaystring"></a>IPerPropertyBrowsingImpl::GetDisplayString  
 지정된 된 속성을 설명 하는 문자열을 검색 합니다.  
  
```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```  
  
### <a name="remarks"></a>설명  
 참조 [IPerPropertyBrowsing::GetDisplayString](http://msdn.microsoft.com/library/windows/desktop/ms688734) in the Windows SDK입니다.  
  
##  <a name="getpredefinedstrings"></a>IPerPropertyBrowsingImpl::GetPredefinedStrings  
 각 0 항목 배열을 채웁니다.  
  
```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```  
  
### <a name="return-value"></a>반환 값  
 ATL의 구현의 [GetPredefinedValue](#getpredefinedvalue) 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>설명  
 참조 [IPerPropertyBrowsing::GetPredefinedStrings](http://msdn.microsoft.com/library/windows/desktop/ms679724) in the Windows SDK입니다.  
  
##  <a name="getpredefinedvalue"></a>IPerPropertyBrowsingImpl::GetPredefinedValue  
 검색 한 **VARIANT** 주어진된 DISPID로 식별 되는 속성의 값이 포함 합니다. 검색 문자열 이름으로 연결 된 DISPID `GetPredefinedStrings`합니다.  
  
```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>설명  
 ATL의 구현의 [GetPredefinedStrings](#getpredefinedstrings) 해당 문자열이 없거나를 검색 합니다.  
  
 참조 [IPerPropertyBrowsing::GetPredefinedValue](http://msdn.microsoft.com/library/windows/desktop/ms690401) in the Windows SDK입니다.  
  
##  <a name="mappropertytopage"></a>IPerPropertyBrowsingImpl::MapPropertyToPage  
 지정 된 속성과 연결 된 속성 페이지의 CLSID를 검색 합니다.  
  
```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```  
  
### <a name="remarks"></a>설명  
 ATL 개체의 속성 매핑이 두를 사용 하 여이 정보를 가져옵니다.  
  
 참조 [IPerPropertyBrowsing::MapPropertyToPage](http://msdn.microsoft.com/library/windows/desktop/ms694476) in the Windows SDK입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IPropertyPageImpl 클래스](../../atl/reference/ipropertypageimpl-class.md)   
 [ISpecifyPropertyPagesImpl 클래스](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
