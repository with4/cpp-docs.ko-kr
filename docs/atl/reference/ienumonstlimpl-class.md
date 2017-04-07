---
title: "IEnumOnSTLImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl::Clone
- ATLCOM/ATL::IEnumOnSTLImpl::Init
- ATLCOM/ATL::IEnumOnSTLImpl::Next
- ATLCOM/ATL::IEnumOnSTLImpl::Reset
- ATLCOM/ATL::IEnumOnSTLImpl::Skip
- ATLCOM/ATL::IEnumOnSTLImpl::m_iter
- ATLCOM/ATL::IEnumOnSTLImpl::m_pcollection
- ATLCOM/ATL::IEnumOnSTLImpl::m_spUnk
dev_langs:
- C++
helpviewer_keywords:
- IEnumOnSTLImpl class
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
caps.latest.revision: 20
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
ms.openlocfilehash: 291993d2914d6082b69bfe7816d7c805e93494c4
ms.lasthandoff: 02/24/2017

---
# <a name="ienumonstlimpl-class"></a>IEnumOnSTLImpl 클래스
이 클래스는 c + + 표준 라이브러리 컬렉션을 기반으로 하는 열거자 인터페이스를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>  
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```  
  
#### <a name="parameters"></a>매개 변수  
 `Base`  
 COM 열거자 ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) 인터페이스입니다.  
  
 `piid`  
 열거자 인터페이스의 인터페이스 ID에 대 한 포인터입니다.  
  
 `T`  
 열거자 인터페이스에 의해 노출 되는 항목의 형식입니다.  
  
 `Copy`  
 A [복사 정책 클래스](../../atl/atl-copy-policy-classes.md)합니다.  
  
 `CollType`  
 C + + 표준 라이브러리 컨테이너 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IEnumOnSTLImpl::Clone](#clone)|구현 [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx)합니다.|  
|[IEnumOnSTLImpl::Init](#init)|열거자를 초기화합니다.|  
|[IEnumOnSTLImpl::Next](#next)|구현 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx)합니다.|  
|[IEnumOnSTLImpl::Reset](#reset)|구현 [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx)합니다.|  
|[IEnumOnSTLImpl::Skip](#skip)|구현 [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx)합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[IEnumOnSTLImpl::m_iter](#m_iter)|컬렉션에서 열거자의 현재 위치를 나타내는 반복기입니다.|  
|[IEnumOnSTLImpl::m_pcollection](#m_pcollection)|열거할 항목을 보유 하는 c + + 표준 라이브러리 컨테이너에 대 한 포인터입니다.|  
|[IEnumOnSTLImpl::m_spUnk](#m_spunk)|**IUnknown** 컬렉션을 제공 하는 개체의 포인터입니다.|  
  
## <a name="remarks"></a>주의  
 `IEnumOnSTLImpl`열거 되 고 항목 호환 c + + 표준 라이브러리 컨테이너에 저장 되는 위치는 COM 열거자 인터페이스에 대 한 구현을 제공 합니다. 이 클래스는 유사는 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) 열거자 인터페이스에 대 한 구현을 제공 하는 클래스 배열을 기반으로 합니다.  
  
> [!NOTE]
>  참조 [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init) 추가 차이점에 대 한 내용은 `CComEnumImpl` 및 `IEnumOnSTLImpl`합니다.  
  
 일반적으로 *하지* 이 인터페이스 구현에서 파생 하 여 사용자 지정 열거자 클래스를 만들어야 합니다. 인스턴스를 만드는 일반적인는 c + + 표준 라이브러리 컨테이너에 따라 ATL 제공 표시기를 사용 하려는 경우 [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md), 또는에서 파생 하 여 열거자를 반환 하는 컬렉션 클래스를 만드는 [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)합니다.  
  
 그러나 (예를 들어 하나 열거자 인터페이스 외에 인터페이스를 노출 하는) 사용자 지정 열거자를 제공할 필요가 없는 경우이 클래스에서 파생 수 있습니다. 이러한 상황에서는 재정의 해야 합니다 가능성이 큽니다는 [복제](#clone) 메서드를 사용자 지정 구현을 제공 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `Base`  
  
 `IEnumOnSTLImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="init"></a>IEnumOnSTLImpl::Init  
 열거자를 초기화합니다.  
  
```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```  
  
### <a name="parameters"></a>매개 변수  
 `pUnkForRelease`  
 [in] **IUnknown** 활성화 되어 있어야 열거자의 수명 동안 하는 개체의 포인터입니다. 전달 **NULL** 이러한 개체가 없는 경우.  
  
 `collection`  
 열거할 항목을 보유 하는 c + + 표준 라이브러리 컨테이너에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 전달 하는 경우 `Init` 다른 개체에 저장 된 컬렉션에 대 한 참조를 사용할 수 있습니다는 `pUnkForRelease` 매개 변수 열거자에서 필요한 만큼의 개체와 보유 컬렉션에 사용할 수 있는 인지 확인 합니다.  
  
 모든 클라이언트에 다시 열거자 인터페이스에 대 한 포인터를 전달 하기 전에이 메서드를 호출 해야 합니다.  
  
##  <a name="clone"></a>IEnumOnSTLImpl::Clone  
 이 메서드는의 구현을 제공는 [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx) 형식의 개체를 만들어 메서드 `CComEnumOnSTL`를 동일한 컬렉션 및 현재 개체에서 사용 하는 반복기를 사용 하 여 초기화 하 고 새로 만든된 개체에서 인터페이스를 반환 합니다.  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppEnum`  
 [out] 현재 열거자에서 복제는 새로 만든된 개체에서 열거자 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="m_spunk"></a>IEnumOnSTLImpl::m_spUnk  
 **IUnknown** 컬렉션을 제공 하는 개체의 포인터입니다.  
  
```
CComPtr<IUnknown> m_spUnk;
```  
  
### <a name="remarks"></a>주의  
 이 스마트 포인터에 전달 된 개체에 대 한 참조를 유지 관리 [IEnumOnSTLImpl::Init](#init), 상태가 활성 상태로 열거자의 수명 동안 보장 합니다.  
  
##  <a name="m_pcollection"></a>IEnumOnSTLImpl::m_pcollection  
 이 멤버는 데이터 구동 열거자 인터페이스의 구현을 제공 하는 컬렉션을 가리킵니다.  
  
```
CollType* m_pcollection;
```  
  
### <a name="remarks"></a>주의  
 이 멤버에 대 한 호출에 의해 초기화 됩니다 [IEnumOnSTLImpl::Init](#init)합니다.  
  
##  <a name="m_iter"></a>IEnumOnSTLImpl::m_iter  
 이 멤버는 컬렉션 내의 현재 위치를 표시 하 고 후속 요소를 이동 하는 데 사용 하는 반복기를 보유 합니다.  
  
```
CollType::iterator m_iter;
```  
  
##  <a name="next"></a>IEnumOnSTLImpl::Next  
 이 메서드는의 구현을 제공는 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) 메서드.  
  
```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```  
  
### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 요청 하는 요소의 수입니다.  
  
 `rgelt`  
 [out] 배열 요소를 채울 수입니다.  
  
 `pceltFetched`  
 [out] 에 실제로 반환 된 요소의 수 `rgelt`합니다. 이 수 미만 `celt` 보다 적을 경우 `celt` 요소 목록에 남아 있습니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="reset"></a>IEnumOnSTLImpl::Reset  
 이 메서드는의 구현을 제공는 [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx) 메서드.  
  
```
STDMETHOD(Reset)(void);
```  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="skip"></a>IEnumOnSTLImpl::Skip  
 이 메서드는의 구현을 제공는 [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx) 메서드.  
  
```
STDMETHOD(Skip)(ULONG celt);
```  
  
### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 건너뛸 요소 수입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

