---
title: "IDispatchImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDispatchImpl
- ATLCOM/ATL::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::GetIDsOfNames
- ATLCOM/ATL::IDispatchImpl::GetTypeInfo
- ATLCOM/ATL::IDispatchImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispatchImpl::Invoke
dev_langs: C++
helpviewer_keywords:
- dual interfaces, classes
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e20a9edee01480aa529ffcd0441f7096d30715fd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="idispatchimpl-class"></a>IDispatchImpl 클래스
에 대 한 기본 구현을 제공는 `IDispatch` 이중 인터페이스의 일부가 됩니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T,
        const IID* piid= &__uuidof(T),
        const GUID* plibid = &CAtlModule::m_libid,
        WORD wMajor = 1,
        WORD wMinor = 0, 
        class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IDispatchImpl : public T
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `T`  
 이중 인터페이스입니다.  
  
 [in] `piid`  
 IID에 대 한 포인터 `T`합니다.  
  
 [in] `plibid`  
 인터페이스에 대 한 정보를 포함 하는 형식 라이브러리의 LIBID에 대 한 포인터입니다. 서버 수준의 형식 라이브러리는 기본적으로 전달 됩니다.  
  
 [in] `wMajor`  
 형식 라이브러리의 주 버전입니다. 기본적으로 값은 1입니다.  
  
 [in] `wMinor`  
 형식 라이브러리의 부 버전입니다. 기본적으로 값은 0입니다.  
  
 [in] `tihclass`  
 클래스의 형식 정보를 관리 하는 데 `T`합니다. 기본적으로 이 값은 `CComTypeInfoHolder`입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[IDispatchImpl::IDispatchImpl](#idispatchimpl)|생성자입니다. 호출 `AddRef` 이중 인터페이스에 대 한 형식 정보를 관리 하는 보호 된 멤버 변수에 있습니다. 이 소멸자는 `Release`을 호출합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IDispatchImpl::GetIDsOfNames](#getidsofnames)|이름 집합을 해당하는 디스패치 식별자 집합에 매핑합니다.|  
|[IDispatchImpl::GetTypeInfo](#gettypeinfo)|이중 인터페이스에 대 한 형식 정보를 검색 합니다.|  
|[IDispatchImpl::GetTypeInfoCount](#gettypeinfocount)|이중 인터페이스에 사용할 수 있는 형식 정보 인지 확인 합니다.|  
|[IDispatchImpl::Invoke](#invoke)|메서드 및 이중 인터페이스에 의해 노출 되는 속성에 대 한 액세스를 제공 합니다.|  
  
## <a name="remarks"></a>설명  
 `IDispatchImpl`에 대 한 기본 구현을 제공는 `IDispatch` 이중 인터페이스 개체에 포함 합니다. 이중 인터페이스에서 파생 `IDispatch` 자동화 호환 유형을 하 고 사용 합니다. dispinterface 마찬가지로 이중 인터페이스 지원 초기 바인딩 및 런타임에 바인딩; 그러나 이중 인터페이스는 vtable 바인딩도 지원합니다.  
  
 다음 예제에서는 구현 하는 일반적인 `IDispatchImpl`합니다.  
  
 [!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]  
  
 기본적으로는 `IDispatchImpl` 클래스에 대 한 형식 정보를 조회 `T` 레지스트리에 합니다. 등록 되지 않은 인터페이스를 구현 하려면 사용할 수 있습니다는 `IDispatchImpl` 미리 정의 된 버전 번호를 사용 하 여 레지스트리를 액세스 하지 않고 클래스입니다. 만드는 경우는 `IDispatchImpl` 에 대 한 값으로 0xFFFF를 가진 개체를 `wMajor` 및에 대 한 값으로 0xFFFF `wMinor`, `IDispatchImpl` 클래스 레지스트리 대신.dll 파일에서 형식 라이브러리를 검색 합니다.  
  
 `IDispatchImpl`형식의 정적 멤버가 포함 된 `CComTypeInfoHolder` 이중 인터페이스에 대 한 형식 정보를 관리 하는 합니다. 동일한 이중를 구현 하는 여러 개체가 있는 경우 인터페이스에 인스턴스가 하나만 `CComTypeInfoHolder` 사용 됩니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `T`  
  
 `IDispatchImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="getidsofnames"></a>IDispatchImpl::GetIDsOfNames  
 이름 집합을 해당하는 디스패치 식별자 집합에 매핑합니다.  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```  
  
### <a name="remarks"></a>설명  
 참조 [IDispatch::GetIDsOfNames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) in the Windows SDK입니다.  
  
##  <a name="gettypeinfo"></a>IDispatchImpl::GetTypeInfo  
 이중 인터페이스에 대 한 형식 정보를 검색 합니다.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>설명  
 참조 [IDispatch::GetTypeInfo](http://msdn.microsoft.com/en-us/cc1ec9aa-6c40-4e70-819c-a7c6dd6b8c99) in the Windows SDK입니다.  
  
##  <a name="gettypeinfocount"></a>IDispatchImpl::GetTypeInfoCount  
 이중 인터페이스에 사용할 수 있는 형식 정보 인지 확인 합니다.  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>설명  
 참조 `IDispatch::GetTypeInfoCount` in the Windows SDK입니다.  
  
##  <a name="idispatchimpl"></a>IDispatchImpl::IDispatchImpl  
 생성자입니다. 호출 `AddRef` 이중 인터페이스에 대 한 형식 정보를 관리 하는 보호 된 멤버 변수에 있습니다. 소멸자 호출 **릴리스**합니다.  
  
```
IDispatchImpl();
```  
  
##  <a name="invoke"></a>IDispatchImpl::Invoke  
 메서드 및 이중 인터페이스에 의해 노출 되는 속성에 대 한 액세스를 제공 합니다.  
  
```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID riid,
    LCID lcid,
    WORD wFlags,
    DISPPARAMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* pexcepinfo,
    UINT* puArgErr);
```  
  
### <a name="remarks"></a>설명  
 참조 [idispatch:: Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d) in the Windows SDK입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
