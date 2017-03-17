---
title: "IDispEventSimpleImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl::Advise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventAdvise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventUnadvise
- ATLCOM/ATL::IDispEventSimpleImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventSimpleImpl::Invoke
- ATLCOM/ATL::IDispEventSimpleImpl::Unadvise
dev_langs:
- C++
helpviewer_keywords:
- IDispEventSimpleImpl class
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 6b7bc2c64139726f84f1c19c7d6b40e8d68cdc18
ms.lasthandoff: 02/24/2017

---
# <a name="idispeventsimpleimpl-class"></a>IDispEventSimpleImpl 클래스
이 클래스의 구현을 제공는 `IDispatch` 형식 라이브러리에서 형식 정보를 가져오지 않고 메서드.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <UINT nID, class T, const IID* pdiid>  
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```    
  
#### <a name="parameters"></a>매개 변수  
 `nID`  
 원본 개체에 대 한 고유 식별자입니다. 때 `IDispEventSimpleImpl` 는 기본 클래스에서 복합 컨트롤에 대 한이 매개 변수에 포함된 된 원하는 컨트롤의 리소스 ID를 사용 합니다. 다른 경우에는 임의의 양의 정수를 사용 합니다.  
  
 `T`  
 사용자의 클래스에서 파생 된 `IDispEventSimpleImpl`합니다.  
  
 `pdiid`  
 이 클래스에서 구현 하는 이벤트 인터페이스의 IID에 대 한 포인터입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IDispEventSimpleImpl::Advise](#advise)|기본 이벤트 소스와의 연결을 설정합니다.|  
|[IDispEventSimpleImpl::DispEventAdvise](#dispeventadvise)|이벤트 소스와의 연결을 설정합니다.|  
|[IDispEventSimpleImpl::DispEventUnadvise](#dispeventunadvise)|이벤트 소스와의 연결이 끊어집니다.|  
|[IDispEventSimpleImpl::GetIDsOfNames](#getidsofnames)|반환 **E_NOTIMPL**합니다.|  
|[IDispEventSimpleImpl::GetTypeInfo](#gettypeinfo)|반환 **E_NOTIMPL**합니다.|  
|[IDispEventSimpleImpl::GetTypeInfoCount](#gettypeinfocount)|반환 **E_NOTIMPL**합니다.|  
|[IDispEventSimpleImpl::Invoke](#invoke)|이벤트 처리기 호출 나열 이벤트 싱크 맵.|  
|[IDispEventSimpleImpl::Unadvise](#unadvise)|기본 이벤트 소스와의 연결이 끊어집니다.|  
  
## <a name="remarks"></a>주의  
 `IDispEventSimpleImpl`해당 인터페이스에서 모든 메서드/이벤트에 대 한 구현 코드를 제공할 필요 없이 이벤트 인터페이스를 구현 방법을 제공 합니다. `IDispEventSimpleImpl`구현을 제공 하는 `IDispatch` 메서드. 처리에 관심이 이벤트에 대 한 구현을 제공 해야 합니다.  
  
 `IDispEventSimpleImpl`와 함께 작동는 [이벤트 싱크 맵](http://msdn.microsoft.com/library/32542b3d-ac43-4139-8ac4-41c48481744f) 경로 이벤트를 적절 한 처리기 함수를 클래스에 있습니다. 이 클래스를 사용 합니다.  
  
-   추가 [SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7) 매크로를 처리 하는 각 개체의 각 이벤트에 대 한 이벤트 싱크 맵.  
  
-   에 대 한 포인터를 전달 하 여 각 이벤트에 대 한 형식 정보를 제공 된 [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) 각 항목에 대 한 매개 변수로 구조입니다. 에 x86 플랫폼에는 `_ATL_FUNC_INFO.cc` 값 CC_CDECL __stdcall의 메서드를 호출 하는 콜백 함수 이어야 합니다.  
  
-   호출 [DispEventAdvise](#dispeventadvise) 소스 개체와 기본 클래스 간의 연결을 설정 합니다.  
  
-   호출 [DispEventUnadvise](#dispeventunadvise) 연결을 끊습니다.  
  
 파생 해야 `IDispEventSimpleImpl` (에 대 한 고유한 값을 사용 하 여 `nID`) 이벤트를 처리 해야 하는 각 개체에 대 한 합니다. 다른 원본 개체에 대해 다음 라는 하나의 원본 개체에 대해 바이 하 여 기본 클래스를 다시 사용할 수 있지만 한 번에 하나의 개체에 의해 처리 될 수 있는 소스 개체의 최대 수의 수로 제한 됩니다 `IDispEventSimpleImpl` 기본 클래스입니다.  
  
 **IDispEventSimplImpl** 와 동일한 기능을 제공 [IDispEventImpl](../../atl/reference/idispeventimpl-class.md)를 제외한 형식 라이브러리에서 인터페이스에 대 한 형식 정보를 가져오지 않습니다. 마법사의 경우에 기반으로 하는 코드 생성 `IDispEventImpl`, 사용할 수 있지만 `IDispEventSimpleImpl` 코드를 직접 추가 하 여 합니다. 사용 하 여 `IDispEventSimpleImpl` 이벤트 인터페이스를 설명 하는 형식 라이브러리 형식 라이브러리를 사용 하 여 연관 된 오버 헤드를 방지 하려면 않거나는 때입니다.  
  
> [!NOTE]
> `IDispEventImpl`및 `IDispEventSimpleImpl` 의 자체 구현을 제공 **IUnknown::QueryInterface** 각 활성화 `IDispEventImpl` 또는 `IDispEventSimpleImpl` 기본 클래스에 기본 COM 개체의 클래스 멤버에 대 한 직접 액세스를 허용 하는 동안 역할을 별도 COM id입니다.  
  
 ActiveX 이벤트 싱크만 지 원하는 형식의 반환 값 HRESULT 또는 이벤트 처리기 메서드에서; void CE ATL 구현 다른 모든 반환 값 지원 되지 않으며 해당 동작이 정의 되지 않습니다.  
  
 자세한 내용은 참조 [지원 IDispEventImpl](../../atl/supporting-idispeventimpl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 `IDispEventSimpleImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="advise"></a>IDispEventSimpleImpl::Advise  
 이 메서드를 나타내는 이벤트 소스와 연결을 설정 *펑크*합니다.  
  
```
HRESULT Advise(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>매개 변수  
 *pUnk*  
 [in] 에 대 한 포인터는 **IUnknown** 이벤트 소스 개체의 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`또는 모든 오류 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 이벤트에서 발생 합니다. 연결이 설정 되 면 *펑크* 이벤트 싱크 맵을 통해 클래스에 대 한 처리기로 라우팅됩니다.  
  
> [!NOTE]
>  클래스에 여러에서 파생 된 경우 `IDispEventSimpleImpl` 클래스 해야 관심 있는 특정 기본 클래스를 사용 하 여 호출 범위를 지정 하 여이 메서드의 호출을 명확 합니다.  
  
 `Advise`연결 기준으로 개체의 기본 이벤트 원본의 IID를 가져옵니다 기본 이벤트 소스와 [AtlGetObjectSourceInterface](http://msdn.microsoft.com/library/a8528f45-fbfb-4e24-ad1a-1d69b2897155)합니다.  
  
##  <a name="dispeventadvise"></a>IDispEventSimpleImpl::DispEventAdvise  
 이 메서드를 나타내는 이벤트 소스와 연결을 설정 *펑크*합니다.  
  
```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>매개 변수  
 *pUnk*  
 [in] 에 대 한 포인터는 **IUnknown** 이벤트 소스 개체의 인터페이스입니다.  
  
 `piid`  
 이벤트 소스 개체의 IID에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`또는 모든 오류 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 이벤트에서 발생 하는 이후에 *펑크* 이벤트 싱크 맵을 통해 클래스에 대 한 처리기로 라우팅됩니다.  
  
> [!NOTE]
>  클래스에 여러에서 파생 된 경우 `IDispEventSimpleImpl` 클래스 해야 관심 있는 특정 기본 클래스를 사용 하 여 호출 범위를 지정 하 여이 메서드의 호출을 명확 합니다.  
  
 `DispEventAdvise`에 지정 된 이벤트 소스와 연결을 설정 `pdiid`합니다.  
  
##  <a name="dispeventunadvise"></a>IDispEventSimpleImpl::DispEventUnadvise  
 가 나타내는 이벤트 소스와 연결을 끊는 *펑크*합니다.  
  
```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>매개 변수  
 *pUnk*  
 [in] 에 대 한 포인터는 **IUnknown** 이벤트 소스 개체의 인터페이스입니다.  
  
 `piid`  
 이벤트 소스 개체의 IID에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`또는 모든 오류 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 연결이 끊어지면 이벤트 싱크 맵에 나열 된 처리기 함수에 이벤트가 더 이상 라우팅됩니다.  
  
> [!NOTE]
>  클래스에 여러에서 파생 된 경우 `IDispEventSimpleImpl` 클래스 해야 관심 있는 특정 기본 클래스를 사용 하 여 호출 범위를 지정 하 여이 메서드의 호출을 명확 합니다.  
  
 `DispEventAdvise`에 지정 된 이벤트 소스와 설정 된 연결이 `pdiid`합니다.  
  
##  <a name="getidsofnames"></a>IDispEventSimpleImpl::GetIDsOfNames  
 이 구현 **IDispatch::GetIDsOfNames** 반환 **E_NOTIMPL**합니다.  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```  
  
### <a name="remarks"></a>주의  
 참조 [IDispatch::GetIDsOfNames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="gettypeinfo"></a>IDispEventSimpleImpl::GetTypeInfo  
 이 구현 **IDispatch::GetTypeInfo** 반환 **E_NOTIMPL**합니다.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```  
  
### <a name="remarks"></a>주의  
 참조 [IDispatch::GetTypeInfo](http://msdn.microsoft.com/en-us/cc1ec9aa-6c40-4e70-819c-a7c6dd6b8c99) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="gettypeinfocount"></a>IDispEventSimpleImpl::GetTypeInfoCount  
 이 구현 **IDispatch::GetTypeInfoCount** 반환 **E_NOTIMPL**합니다.  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```  
  
### <a name="remarks"></a>주의  
 참조 [IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="invoke"></a>IDispEventSimpleImpl::Invoke  
 이 구현 **idispatch:: Invoke** 이벤트 처리기 나열 이벤트 싱크 맵 호출 합니다.  
  
```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID /* riid */,
    LCID lcid,
    WORD /* wFlags */,
    DISPPARMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* /* pexcepinfo */,
    UINT* /* puArgErr */);
```  
  
### <a name="remarks"></a>주의  
 참조 [idispatch:: Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d)합니다.  
  
##  <a name="unadvise"></a>IDispEventSimpleImpl::Unadvise  
 가 나타내는 이벤트 소스와 연결을 끊는 *펑크*합니다.  
  
```
HRESULT Unadvise(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>매개 변수  
 *pUnk*  
 [in] 에 대 한 포인터는 **IUnknown** 이벤트 소스 개체의 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`또는 모든 오류 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 연결이 끊어지면 이벤트 싱크 맵에 나열 된 처리기 함수에 이벤트가 더 이상 라우팅됩니다.  
  
> [!NOTE]
>  클래스에 여러에서 파생 된 경우 `IDispEventSimpleImpl` 클래스 해야 관심 있는 특정 기본 클래스를 사용 하 여 호출 범위를 지정 하 여이 메서드의 호출을 명확 합니다.  
  
 `Unadvise`에 지정 된 기본 이벤트 소스와 설정 된 연결이 `pdiid`합니다.  
  
 **Unavise** 기준으로 개체의 기본 이벤트 원본의 IID 가져옵니다 나누기 대 한 기본 이벤트 소스와 연결 [AtlGetObjectSourceInterface](http://msdn.microsoft.com/library/a8528f45-fbfb-4e24-ad1a-1d69b2897155)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [_ATL_FUNC_INFO 구조](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl 클래스](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventImpl 클래스](../../atl/reference/idispeventimpl-class.md)   
 [SINK_ENTRY_INFO](http://msdn.microsoft.com/library/1a0ae260-2c82-4926-a537-db01e5f206a7)   
 [클래스 개요](../../atl/atl-class-overview.md)

