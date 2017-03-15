---
title: "IDispEventImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
caps.latest.revision: 22
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 235955f8573ae7e430be3de2a96efdd7496d15de
ms.lasthandoff: 02/24/2017

---
# <a name="idispeventimpl-class"></a>IDispEventImpl 클래스
이 클래스의 구현을 제공는 `IDispatch` 메서드.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  
  
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
 원본 개체에 대 한 고유 식별자입니다. 때 `IDispEventImpl` 는 기본 클래스에서 복합 컨트롤에 대 한이 매개 변수에 포함된 된 원하는 컨트롤의 리소스 ID를 사용 합니다. 다른 경우에는 임의의 양의 정수를 사용 합니다.  
  
 `T`  
 사용자의 클래스에서 파생 된 `IDispEventImpl`합니다.  
  
 `pdiid`  
 이 클래스에서 구현 하는 이벤트 인터페이스의 IID에 대 한 포인터입니다. 이 인터페이스를 가리키는 형식 라이브러리에 정의 되어 있어야 `plibid`, `wMajor`, 및 `wMinor`합니다.  
  
 `plibid`  
 Dispatch 인터페이스를 정의 하는 형식 라이브러리에 대 한 포인터를 가리키고 `pdiid`합니다. 경우 **GUID_NULL / /**, 형식 라이브러리는 이벤트 원본을 지정 하는 개체에서 로드 됩니다.  
  
 `wMajor`  
 형식 라이브러리의 주 버전입니다. 기본값은 0입니다.  
  
 `wMinor`  
 형식 라이브러리의 부 버전입니다. 기본값은 0입니다.  
  
 `tihclass`  
 클래스의 형식 정보를 관리 하는 데 `T`합니다. 기본값은 형식의 클래스 `CComTypeInfoHolder`; 그러나 아닌 다른 형식의 클래스를 제공 하 여이 템플릿 매개 변수를 재정의할 수 있습니다 `CComTypeInfoHolder`합니다.  
  
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
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|단일 멤버와 선택적 인수 이름 집합을 해당 집합이 Dispid 정수에 매핑됩니다.|  
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|개체에 대 한 형식 정보를 검색 합니다.|  
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|형식 정보 인터페이스의 수를 검색합니다.|  
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|사용자 정의 형식의 기본 형식을 검색합니다.|  
  
## <a name="remarks"></a>주의  
 `IDispEventImpl`해당 인터페이스에서 모든 메서드/이벤트에 대 한 구현 코드를 제공할 필요 없이 이벤트 인터페이스를 구현 방법을 제공 합니다. `IDispEventImpl`구현을 제공 하는 `IDispatch` 메서드. 처리에 관심이 이벤트에 대 한 구현을 제공 해야 합니다.  
  
 `IDispEventImpl`와 함께 작동는 [이벤트 싱크 맵](http://msdn.microsoft.com/library/32542b3d-ac43-4139-8ac4-41c48481744f) 경로 이벤트를 적절 한 처리기 함수를 클래스에 있습니다. 이 클래스를 사용 합니다.  
  

 추가 [SINK_ENTRY](http://msdn.microsoft.com/library/33a5fff6-5248-47c0-8cf4-8bdf760e86e5) 또는 [SINK_ENTRY_EX](http://msdn.microsoft.com/library/e1d14342-838f-4791-ac2f-5dae2801c1ac) 매크로를 처리 하는 각 개체의 각 이벤트에 대 한 이벤트 싱크 맵. 사용 하는 경우 `IDispEventImpl` 합성 컨트롤의 기본 클래스를 호출할 수 있습니다 [AtlAdviseSinkMap](http://msdn.microsoft.com/library/0757a6af-3de3-4179-8b4f-ccd137d919b4) 를 설정 하 고 모든 항목에 지도 이벤트 싱크에 대 한 이벤트 소스와의 연결을 끊고 있습니다. 다른 경우 또는 추가적인 제어를 위한 호출 [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) 소스 개체와 기본 클래스 간의 연결을 설정 합니다. 호출 [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise) 연결을 끊습니다.  

  
 파생 해야 `IDispEventImpl` (에 대 한 고유한 값을 사용 하 여 `nID`) 이벤트를 처리 해야 하는 각 개체에 대 한 합니다. 다른 원본 개체에 대해 다음 라는 하나의 원본 개체에 대해 바이 하 여 기본 클래스를 다시 사용할 수 있지만 한 번에 하나의 개체에 의해 처리 될 수 있는 소스 개체의 최대 수의 수로 제한 됩니다 `IDispEventImpl` 기본 클래스입니다.  
  
 `IDispEventImpl`와 동일한 기능을 제공 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)에 대 한 포인터로 제공 된 것 보다는 형식 라이브러리에서 인터페이스에 대 한 형식 정보를 가져와서 제외 하 고는 [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) 구조입니다. 사용 하 여 `IDispEventSimpleImpl` 때 또는 하지 않는 이벤트 인터페이스를 설명 하는 형식 라이브러리 형식 라이브러리를 사용 하 여 연관 된 오버 헤드를 방지 해야 합니다.  
  
> [!NOTE]
> `IDispEventImpl`및 `IDispEventSimpleImpl` 의 자체 구현을 제공 **IUnknown::QueryInterface** 각 활성화 `IDispEventImpl` 및 `IDispEventSimpleImpl` 기본 클래스에 기본 COM 개체의 클래스 멤버에 대 한 직접 액세스를 허용 하는 동안 역할을 별도 COM id입니다.  
  
 ActiveX 이벤트 싱크만 지 원하는 형식의 반환 값 HRESULT 또는 이벤트 처리기 메서드에서; void CE ATL 구현 다른 모든 반환 값 지원 되지 않으며 해당 동작이 정의 되지 않습니다.  
  
 자세한 내용은 참조 [지원 IDispEventImpl](../../atl/supporting-idispeventimpl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)  
  
 `IDispEventImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="a-namegetfuncinfofromida--idispeventimplgetfuncinfofromid"></a><a name="getfuncinfofromid"></a>IDispEventImpl::GetFuncInfoFromId  
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
 [in] 디스패치 ID는 함수입니다.  
  
 `lcid`  
 [in] 로캘 컨텍스트의 함수 id입니다.  
  
 `info`  
 [in] 함수를 호출 하는 방법을 나타내는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="a-namegetidsofnamesa--idispeventimplgetidsofnames"></a><a name="getidsofnames"></a>IDispEventImpl::GetIDsOfNames  
 단일 멤버와 선택적 인수 이름 집합에 대 한 후속 호출에 사용할 수 있는 Dispid 정수의 해당 집합에 매핑합니다 [idispatch:: Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d)합니다.  
  
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
  
##  <a name="a-namegettypeinfoa--idispeventimplgettypeinfo"></a><a name="gettypeinfo"></a>IDispEventImpl::GetTypeInfo  
 인터페이스의 형식 정보를 가져오는 데 사용할 수 있는 개체의 형식 정보를 검색합니다.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegettypeinfocounta--idispeventimplgettypeinfocount"></a><a name="gettypeinfocount"></a>IDispEventImpl::GetTypeInfoCount  
 개체에서 제공하는 형식 정보 인터페이스의 수를 검색합니다(0 또는 1).  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>주의  
 참조 [IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetuserdefinedtypea--idispeventimplgetuserdefinedtype"></a><a name="getuserdefinedtype"></a>IDispEventImpl::GetUserDefinedType  
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
  
### <a name="remarks"></a>주의  
 참조 [ITypeInfo::GetRefTypeInfo](http://msdn.microsoft.com/en-us/61d3b31d-6591-4e55-9e82-5246a168be00)합니다.  
  
##  <a name="a-nameidispeventimpla--idispeventimplidispeventimpl"></a><a name="idispeventimpl"></a>IDispEventImpl::IDispEventImpl  
 생성자입니다. 클래스 템플릿 매개 변수 값을 저장 `plibid`, `pdiid`, `wMajor`, 및 `wMinor`합니다.  
  
```
IDispEventImpl();
```  
  
##  <a name="a-nametihclassa--idispeventimpltihclass"></a><a name="tihclass"></a>IDispEventImpl::tihclass  
 이 형식 정의 클래스 템플릿 매개 변수 인스턴스의 `tihclass`합니다.  
  
```
typedef tihclass _tihclass;
```  
  
### <a name="remarks"></a>주의  
 기본적으로 클래스는 `CComTypeInfoHolder`합니다. `CComTypeInfoHolder`클래스에 대 한 형식 정보를 관리합니다.  
  
## <a name="see-also"></a>참고 항목  
 [_ATL_FUNC_INFO 구조](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl 클래스](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventSimpleImpl 클래스](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY](http://msdn.microsoft.com/library/33a5fff6-5248-47c0-8cf4-8bdf760e86e5)   
 [SINK_ENTRY_EX](http://msdn.microsoft.com/library/e1d14342-838f-4791-ac2f-5dae2801c1ac)   
 [SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7)   
 [클래스 개요](../../atl/atl-class-overview.md)
