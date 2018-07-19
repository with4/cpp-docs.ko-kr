---
title: IEnumOnSTLImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b70e8012d6126b39129cff6fc86366f72459dc02
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883010"
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
 *자료*  
 COM 열거자를 ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) 인터페이스입니다.  
  
 *piid*  
 열거자 인터페이스의 인터페이스 ID에 대 한 포인터입니다.  
  
 *T*  
 열거자 인터페이스에 의해 노출 되는 항목의 형식입니다.  
  
 *복사*  
 A [복사 정책 클래스](../../atl/atl-copy-policy-classes.md)합니다.  
  
 *CollType*  
 C + + 표준 라이브러리 컨테이너 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IEnumOnSTLImpl::Clone](#clone)|구현의 [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx)합니다.|  
|[IEnumOnSTLImpl::Init](#init)|열거자를 초기화합니다.|  
|[IEnumOnSTLImpl::Next](#next)|구현의 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx)합니다.|  
|[IEnumOnSTLImpl::Reset](#reset)|구현의 [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx)합니다.|  
|[IEnumOnSTLImpl::Skip](#skip)|구현의 [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx)합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[IEnumOnSTLImpl::m_iter](#m_iter)|컬렉션에서 열거자의 현재 위치를 나타내는 반복기입니다.|  
|[IEnumOnSTLImpl::m_pcollection](#m_pcollection)|열거할 항목을 보유 하는 c + + 표준 라이브러리 컨테이너에 대 한 포인터입니다.|  
|[IEnumOnSTLImpl::m_spUnk](#m_spunk)|`IUnknown` 컬렉션을 제공 하는 개체의 포인터입니다.|  
  
## <a name="remarks"></a>설명  
 `IEnumOnSTLImpl` 열거할 항목 호환 c + + 표준 라이브러리 컨테이너에 저장 되어 있는 COM 열거자 인터페이스에 대 한 구현을 제공 합니다. 이 클래스는 비슷합니다는 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) 열거자 인터페이스에 대 한 구현을 제공 하는 클래스 배열을 기반으로 합니다.  
  
> [!NOTE]
>  참조 [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init) 간의 추가 차이점에 대 한 자세한 내용은 `CComEnumImpl` 고 `IEnumOnSTLImpl`입니다.  
  
 일반적으로 *되지* 이 인터페이스 구현에서 파생 하 여 사용자 지정 열거자 클래스를 만들어야 합니다. C + + 표준 라이브러리 컨테이너 기반 ATL 제공한 표시기를 사용 하려는 경우 것이 더 일반적의 인스턴스를 만드는 [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)합니다 에서파생하여열거자를반환하는컬렉션클래스를만들려면[ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)합니다.  
  
 그러나 (예를 들어 하나 열거자 인터페이스 외에 인터페이스를 노출 하는) 사용자 지정 열거자를 제공 해야 수행 하는 경우이 클래스에서 파생할 수 있습니다. 이런에서 것을 재정의 해야 합니다 [복제](#clone) 고유한 구현을 제공 하는 방법입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `Base`  
  
 `IEnumOnSTLImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="init"></a>  IEnumOnSTLImpl::Init  
 열거자를 초기화합니다.  
  
```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```  
  
### <a name="parameters"></a>매개 변수  
 *pUnkForRelease*  
 [in] `IUnknown` 유지 해야 하는 활성 열거자의 수명 동안 개체의 포인터입니다. 이러한 개체가 없는 경우 NULL을 전달 합니다.  
  
 *collection*  
 열거할 항목을 포함 하는 c + + 표준 라이브러리 컨테이너에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>설명  
 전달 하는 경우 `Init` 다른 개체에 저장 된 컬렉션에 대 한 참조를 사용할 수는 *pUnkForRelease* 매개 변수를 보유 하는 컬렉션 및 개체를 사용할 수 있는지에 대 한 열거자가 필요할 만큼 합니다.  
  
 모든 클라이언트에 다시 열거자 인터페이스에 대 한 포인터를 전달 하기 전에이 메서드를 호출 해야 합니다.  
  
##  <a name="clone"></a>  IEnumOnSTLImpl::Clone  
 이 메서드는 구현을 제공 합니다 [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx) 형식의 개체를 만들어 메서드 `CComEnumOnSTL`, 동일한 컬렉션 및 현재 개체에서 사용 하는 반복기를 사용 하 여 초기화 하 고 인터페이스에서 반환 새로 만든된 개체입니다.  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>매개 변수  
 *ppEnum*  
 [out] 현재 열거자에서 복제는 새로 만든된 개체에서 열거자 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
##  <a name="m_spunk"></a>  IEnumOnSTLImpl::m_spUnk  
 `IUnknown` 컬렉션을 제공 하는 개체의 포인터입니다.  
  
```
CComPtr<IUnknown> m_spUnk;
```  
  
### <a name="remarks"></a>설명  
 이 스마트 포인터에 전달 된 개체에 대 한 참조를 유지 관리 [IEnumOnSTLImpl::Init](#init), 열거자의 수명 동안 활성 상태로 그대로 확인 합니다.  
  
##  <a name="m_pcollection"></a>  IEnumOnSTLImpl::m_pcollection  
 이 멤버의 열거자 인터페이스 구현의 주행 데이터를 제공 하는 컬렉션을 가리킵니다.  
  
```
CollType* m_pcollection;
```  
  
### <a name="remarks"></a>설명  
 이 멤버를 호출 하 여 인스턴스화될 [IEnumOnSTLImpl::Init](#init)합니다.  
  
##  <a name="m_iter"></a>  IEnumOnSTLImpl::m_iter  
 이 멤버는 컬렉션 내의 현재 위치를 표시 하 고 후속 요소를 이동 하는 데 사용 하는 반복기를 보유 합니다.  
  
```
CollType::iterator m_iter;
```  
  
##  <a name="next"></a>  IEnumOnSTLImpl::Next  
 이 메서드는 구현을 제공 합니다 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) 메서드.  
  
```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```  
  
### <a name="parameters"></a>매개 변수  
 *celt*  
 [in] 요청 하는 요소의 수입니다.  
  
 *rgelt*  
 [out] 요소로 채워질 배열입니다.  
  
 *pceltFetched*  
 [out] 에 실제로 반환 된 요소 수가 *rgelt*합니다. 일 수 있습니다 보다 작은 *celt* 개 보다 적으면 *celt* 요소 목록에 남아 있습니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
##  <a name="reset"></a>  IEnumOnSTLImpl::Reset  
 이 메서드는 구현을 제공 합니다 [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx) 메서드.  
  
```
STDMETHOD(Reset)(void);
```  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
##  <a name="skip"></a>  IEnumOnSTLImpl::Skip  
 이 메서드는 구현을 제공 합니다 [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx) 메서드.  
  
```
STDMETHOD(Skip)(ULONG celt);
```  
  
### <a name="parameters"></a>매개 변수  
 *celt*  
 [in] 건너뛸 요소 수입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
