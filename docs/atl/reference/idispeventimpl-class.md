---
title: IDispEventImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDispEventImpl
- ATLCOM/ATL::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::GetFuncInfoFromId
- ATLCOM/ATL::IDispEventImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventImpl::GetUserDefinedType
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7809a61fe39a4b4b913531de29e03c3eb440c418
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365636"
---
# <a name="idispeventimpl-class"></a>IDispEventImpl 클래스
이 클래스의 구현을 제공는 `IDispatch` 메서드.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <UINT nID, class T,
    const IID* pdiid = &IID_NULL,
    const GUID* plibid = &GUID_NULL,
    WORD wMajor = 0,
    WORD wMinor = 0, 
    class tihclass = CcomTypeInfoHolder>  
class ATL_NO_VTABLE IDispEventImpl : public IDispEventSimpleImpl<nID, T, pdiid>
```  
  
#### <a name="parameters"></a>매개 변수  
 `nID`  
 원본 개체에 대 한 고유 식별자입니다. 때 `IDispEventImpl` 의 기본 클래스에서 합성 컨트롤에 대 한이 매개 변수에 대 한 원하는 포함 된 컨트롤의 리소스 ID를 사용 합니다. 다른 경우에는 임의의 양의 정수를 사용 합니다.  
  
 `T`  
 사용자의 클래스에서 파생 된 `IDispEventImpl`합니다.  
  
 `pdiid`  
 이 클래스에서 구현 하는 이벤트 인터페이스의 IID에 대 한 포인터입니다. 이 인터페이스를 가리키는 형식 라이브러리에 정의 되어야 합니다 `plibid`, `wMajor`, 및 `wMinor`합니다.  
  
 `plibid`  
 디스패치 인터페이스를 정의 하는 형식 라이브러리에 대 한 포인터에서 가리키는 `pdiid`합니다. 경우 **& GUID_NULL**, 이벤트 소싱 개체에서 형식 라이브러리를 로드 됩니다.  
  
 `wMajor`  
 형식 라이브러리의 주 버전입니다. 기본값은 0입니다.  
  
 `wMinor`  
 형식 라이브러리의 부 버전입니다. 기본값은 0입니다.  
  
 `tihclass`  
 클래스의 형식 정보를 관리 하는 데 `T`합니다. 기본값은 형식의 클래스 `CComTypeInfoHolder`소비량이 적어지지만 아닌 다른 형식의 클래스를 제공 하 여이 템플릿 매개 변수를 재정의할 수 있습니다 `CComTypeInfoHolder`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[IDispEventImpl::_tihclass](../../atl/reference/idispeventimpl-class.md)|형식 정보를 관리 하는 데 사용 되는 클래스입니다. 기본적으로 `CComTypeInfoHolder`합니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IDispEventImpl::GetFuncInfoFromId](#getfuncinfofromid)|지정된 된 디스패치 식별자에 대 한 함수 인덱스를 찾습니다.|  
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|단일 멤버와 선택적 인수 이름 집합 Dispid 정수의 해당 집합에 매핑합니다.|  
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|개체에 대 한 형식 정보를 검색 합니다.|  
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|형식 정보 인터페이스의 수를 검색합니다.|  
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|사용자 정의 형식의 기본 형식을 검색합니다.|  
  
## <a name="remarks"></a>설명  
 `IDispEventImpl` 해당 인터페이스의 모든 메서드/이벤트에 대 한 구현 코드 제공할 필요 없이 이벤트 인터페이스를 구현 방법을 제공 합니다. `IDispEventImpl` 구현을 제공는 `IDispatch` 메서드. 처리에 관심이 있는 이벤트에 대 한 구현을 제공 하기만 하면 됩니다.  
  
 `IDispEventImpl` 적절 한 처리기 함수에 경로 이벤트 하려면 클래스에서 이벤트 싱크 맵와 함께 작동 합니다. 이 클래스를 사용 합니다.  
  

 추가 [SINK_ENTRY](composite-control-macros.md#sink_entry) 또는 [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex) 매크로를 처리 하려면 각 개체의 각 이벤트에 대 한 이벤트 싱크 맵. 사용 하는 경우 `IDispEventImpl` 합성 컨트롤의 기본 클래스를 호출할 수 있습니다 [AtlAdviseSinkMap](connection-point-global-functions.md#atladvisesinkmap) 을 설정 하 고 모든 항목 지도 싱크 이벤트에 대 한 이벤트 소스와의 연결을 중단 합니다. 다른 경우 또는 추가적인 제어를 위한 호출 [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) 소스 개체와 기본 클래스 간의 연결을 설정 합니다. 호출 [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise) 연결을 끊습니다.  

  
 파생 해야 `IDispEventImpl` (고유 값을 사용 하 여 `nID`) 이벤트를 처리 해야 하는 각 개체에 대 한 합니다. 다른 원본 개체에 대해 다음 라는 하나의 원본 개체에 대해 바이 하 여 기본 클래스를 다시 사용할 수 있지만 한 번에 단일 개체로 처리 될 수 있는 소스 개체의 최대 수의 수로 제한 됩니다 `IDispEventImpl` 기본 클래스입니다.  
  
 `IDispEventImpl` 와 동일한 기능을 제공 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)것에 대 한 포인터를 제공 하지 않고 형식 라이브러리에서 인터페이스에 대 한 형식 정보를 가져옵니다 점을 제외 하 고는 [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) 구조입니다. 사용 하 여 `IDispEventSimpleImpl` 때 또는 하지 않는 이벤트 인터페이스를 설명 하는 형식 라이브러리 형식 라이브러리를 사용 하 여 연관 된 오버 헤드를 방지 하려면.  
  
> [!NOTE]
> `IDispEventImpl` 및 `IDispEventSimpleImpl` 의 자체 구현을 제공 **iunknown:: Queryinterface** 각 활성화 `IDispEventImpl` 및 `IDispEventSimpleImpl` 기본 클래스를 별도 COM id의 클래스 멤버에 대 한 직접 액세스를 허용 하면서 프록시로 기본 COM 개체입니다.  
  
 ActiveX 이벤트 싱크만 지원 형식의 반환 값 HRESULT 또는 이벤트 처리기 메서드에서; void CE ATL 구현 다른 모든 반환 값 지원 되지 않으며 해당 동작이 정의 되지 않습니다.  
  
 자세한 내용은 참조 [지원 IDispEventImpl](../../atl/supporting-idispeventimpl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)  
  
 `IDispEventImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="getfuncinfofromid"></a>  IDispEventImpl::GetFuncInfoFromId  
 지정된 된 디스패치 식별자에 대 한 함수 인덱스를 찾습니다.  
  
```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 함수의 ID에 대 한 참조입니다.  
  
 *dispidMember*  
 [in] 함수의 디스패치 ID입니다.  
  
 `lcid`  
 [in] 로캘 컨텍스트의 함수 id입니다.  
  
 `info`  
 [in] 함수를 호출 하는 방법을 나타내는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="getidsofnames"></a>  IDispEventImpl::GetIDsOfNames  
 단일 멤버 및 선택적 인수 이름 집합 해당 집합이 Dispid 후속 호출에서 사용할 수 있는 정수를 매핑합니다 [idispatch:: Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d)합니다.  
  
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
  
##  <a name="gettypeinfo"></a>  IDispEventImpl::GetTypeInfo  
 인터페이스의 형식 정보를 가져오는 데 사용할 수 있는 개체의 형식 정보를 검색합니다.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="gettypeinfocount"></a>  IDispEventImpl::GetTypeInfoCount  
 개체에서 제공하는 형식 정보 인터페이스의 수를 검색합니다(0 또는 1).  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>설명  
 참조 [IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12) in the Windows SDK입니다.  
  
##  <a name="getuserdefinedtype"></a>  IDispEventImpl::GetUserDefinedType  
 사용자 정의 형식의 기본 형식을 검색합니다.  
  
```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```  
  
### <a name="parameters"></a>매개 변수  
 `pTI`  
 [in] 에 대 한 포인터는 [ITypeInfo](http://msdn.microsoft.com/en-us/f3356463-3373-4279-bae1-953378aa2680) 사용자 정의 형식을 포함 하는 인터페이스입니다.  
  
 *hrt*  
 [in] 검색할 유형 설명에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 Variant의 형식입니다.  
  
### <a name="remarks"></a>설명  
 참조 [ITypeInfo::GetRefTypeInfo](http://msdn.microsoft.com/en-us/61d3b31d-6591-4e55-9e82-5246a168be00)합니다.  
  
##  <a name="idispeventimpl"></a>  IDispEventImpl::IDispEventImpl  
 생성자입니다. 클래스 템플릿 매개 변수 값을 저장 `plibid`, `pdiid`, `wMajor`, 및 `wMinor`합니다.  
  
```
IDispEventImpl();
```  
  
##  <a name="tihclass"></a>  IDispEventImpl::tihclass  
 이 typedef는 템플릿 매개 변수 클래스의 인스턴스 `tihclass`합니다.  
  
```
typedef tihclass _tihclass;
```  
  
### <a name="remarks"></a>설명  
 기본적으로 클래스는 `CComTypeInfoHolder`합니다. `CComTypeInfoHolder` 클래스에 대 한 형식 정보를 관리합니다.  
  
## <a name="see-also"></a>참고 항목  
 [_ATL_FUNC_INFO 구조](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl 클래스](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventSimpleImpl 클래스](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY](composite-control-macros.md#sink_entry)   
 [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)   
 [클래스 개요](../../atl/atl-class-overview.md)