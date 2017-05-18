---
title: "IDispatchImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- dual interfaces, classes
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
caps.latest.revision: 27
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: fff4cbc0a3f87b584f1a4211f4aad37228ed4da7
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="idispatchimpl-class"></a>IDispatchImpl 클래스
에 대 한 기본 구현을 제공 하는 `IDispatch` 이중 인터페이스의 일부입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  
  
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
 에 대 한 포인터의 IID `T`합니다.  
  
 [in] `plibid`  
 포인터는 인터페이스에 대 한 정보를 포함 하는 형식 라이브러리의 LIBID입니다. 서버 수준의 형식 라이브러리는 기본적으로 전달 됩니다.  
  
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
|[IDispatchImpl::IDispatchImpl](#idispatchimpl)|생성자입니다. 호출 `AddRef` 이중 인터페이스에 대 한 형식 정보를 관리 하 고 보호 된 멤버 변수입니다. 이 소멸자는 `Release`을 호출합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IDispatchImpl::GetIDsOfNames](#getidsofnames)|이름 집합을 해당하는 디스패치 식별자 집합에 매핑합니다.|  
|[IDispatchImpl::GetTypeInfo](#gettypeinfo)|이중 인터페이스에 대 한 형식 정보를 검색 합니다.|  
|[IDispatchImpl::GetTypeInfoCount](#gettypeinfocount)|이중 인터페이스에 대해 사용할 수 있는 형식 정보를 결정 합니다.|  
|[IDispatchImpl::Invoke](#invoke)|메서드 및 이중 인터페이스에 의해 노출 되는 속성에 대 한 액세스를 제공 합니다.|  
  
## <a name="remarks"></a>주의  
 `IDispatchImpl`에 대 한 기본 구현을 제공 하는 `IDispatch` 개체에는 이중 인터페이스의 일부입니다. 이중 인터페이스에서 파생 `IDispatch` 만 자동화 호환 형식을 사용 합니다. dispinterface 마찬가지로 이중 인터페이스 지원 초기 바인딩 및 런타임에 바인딩; 그러나 이중 인터페이스는 vtable 바인딩도 지원합니다.  
  
 다음 예제에서는 구현 하는 일반적인 `IDispatchImpl`합니다.  
  
 [!code-cpp[NVC_ATL_COM&#47;](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]  
  
 기본적으로는 `IDispatchImpl` 클래스에 대 한 형식 정보를 조회 `T` 레지스트리에 있습니다. 사용할 수는 등록 되지 않은 인터페이스를 구현 하려면는 `IDispatchImpl` 에 미리 정의 된 버전 번호를 사용 하 여 레지스트리를 액세스 하지 않고 클래스입니다. 만드는 경우는 `IDispatchImpl` 개체에 대 한 값으로 0xFFFF를 `wMajor` 및에 대 한 값으로 0xFFFF `wMinor`, `IDispatchImpl` 레지스트리 대신.dll 파일에서 형식 라이브러리를 검색 하는 클래스입니다.  
  
 `IDispatchImpl`형식의 정적 멤버가 포함 된 `CComTypeInfoHolder` 하는 이중 인터페이스에 대 한 형식 정보를 관리 합니다. 동일한 듀얼를 구현 하는 여러 개체가 있는 경우 인터페이스를 하나의 인스턴스만 `CComTypeInfoHolder` 사용 됩니다.  
  
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
  
### <a name="remarks"></a>주의  
 참조 [IDispatch::GetIDsOfNames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="gettypeinfo"></a>IDispatchImpl::GetTypeInfo  
 이중 인터페이스에 대 한 형식 정보를 검색 합니다.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>주의  
 참조 [IDispatch::GetTypeInfo](http://msdn.microsoft.com/en-us/cc1ec9aa-6c40-4e70-819c-a7c6dd6b8c99) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="gettypeinfocount"></a>IDispatchImpl::GetTypeInfoCount  
 이중 인터페이스에 대해 사용할 수 있는 형식 정보를 결정 합니다.  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>주의  
 See `IDispatch::GetTypeInfoCount` in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="idispatchimpl"></a>IDispatchImpl::IDispatchImpl  
 생성자입니다. 호출 `AddRef` 이중 인터페이스에 대 한 형식 정보를 관리 하 고 보호 된 멤버 변수입니다. 소멸자를 호출 하 여 **릴리스**합니다.  
  
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
  
### <a name="remarks"></a>주의  
 참조 [idispatch:: Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

