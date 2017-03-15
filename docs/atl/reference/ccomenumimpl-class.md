---
title: "CComEnumImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComEnumImpl
- ATL::CComEnumImpl
- CComEnumImpl
dev_langs:
- C++
helpviewer_keywords:
- CComEnumImpl class
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
caps.latest.revision: 19
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
ms.openlocfilehash: 6dc6a8ed6a318642efe58dfb94835d45b2163b54
ms.lasthandoff: 02/24/2017

---
# <a name="ccomenumimpl-class"></a>CComEnumImpl 클래스
이 클래스는 COM 열거자 인터페이스 열거 되 고 항목이 배열에 저장 되는 위치에 대 한 구현을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Base,
    const IID* piid, class T, class Copy>  
class ATL_NO_VTABLE CComEnumImpl : public Base
```  
  
#### <a name="parameters"></a>매개 변수  
 `Base`  
 COM 열거자 ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) 인터페이스입니다.  
  
 `piid`  
 열거자 인터페이스의 인터페이스 ID에 대 한 포인터입니다.  
  
 `T`  
 열거자 인터페이스에 의해 노출 되는 항목의 형식입니다.  
  
 `Copy`  
 동종 [복사 정책 클래스](../../atl/atl-copy-policy-classes.md)합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComEnumImpl::CComEnumImpl](#ccomenumimpl)|생성자입니다.|  
|[CComEnumImpl:: ~ CComEnumImpl](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComEnumImpl::Clone](#clone)|구현 [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx)합니다.|  
|[CComEnumImpl::Init](#init)|열거자를 초기화합니다.|  
|[CComEnumImpl::Next](#next)|구현 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx)합니다.|  
|[CComEnumImpl::Reset](#reset)|구현 [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx)합니다.|  
|[CComEnumImpl::Skip](#skip)|구현 [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx)합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CComEnumImpl::m_begin](#m_begin)|배열에서 첫 번째 항목에 대 한 포인터입니다.|  
|[CComEnumImpl::m_dwFlags](#m_dwflags)|복사를 통해 전달 된 플래그 `Init`합니다.|  
|[CComEnumImpl::m_end](#m_end)|배열의 마지막 항목 바로 위치에 대 한 포인터입니다.|  
|[CComEnumImpl::m_iter](#m_iter)|배열에 있는 현재 항목에 대 한 포인터입니다.|  
|[CComEnumImpl::m_spUnk](#m_spunk)|**IUnknown** 열거 되는 컬렉션을 제공 하는 개체의 포인터입니다.|  
  
## <a name="remarks"></a>주의  
 `CComEnumImpl`배열에 열거 되 고 항목이 저장 되는 COM 열거자 인터페이스에 대 한 구현을 제공 합니다. 이 클래스는 유사는 `IEnumOnSTLImpl` 열거자 인터페이스의 구현을 제공 하는 클래스는 c + + 표준 라이브러리 컨테이너에 기반 합니다.  
  
> [!NOTE]
>  추가 차이점에 대 한 내용은 `CComEnumImpl` 및 `IEnumOnSTLImpl`, 참조 [CComEnumImpl::Init](#init)합니다.  
  
 일반적으로 *하지* 이 인터페이스 구현에서 파생 하 여 사용자 지정 열거자 클래스를 만들어야 합니다. 배열을 기반으로 하는 ATL 제공 열거자를 사용 하려는 경우의 인스턴스를 만드는 일반적인 [CComEnum](../../atl/reference/ccomenum-class.md)합니다.  
  
 그러나 (예를 들어 하나 열거자 인터페이스 외에 인터페이스를 노출 하는) 사용자 지정 열거자를 제공할 필요가 없는 경우이 클래스에서 파생 수 있습니다. 이 상황에서는 재정의 해야 합니다 가능성이 큽니다는 [CComEnumImpl::Clone](#clone) 메서드를 사용자 지정 구현을 제공 합니다.  
  
 자세한 내용은 참조 [ATL 컬렉션 및 열거자](../../atl/atl-collections-and-enumerators.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `Base`  
  
 `CComEnumImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="a-nameccomenumimpla--ccomenumimplccomenumimpl"></a><a name="ccomenumimpl"></a>CComEnumImpl::CComEnumImpl  
 생성자입니다.  
  
```
CComEnumImpl();
```  
  
##  <a name="a-namedtora--ccomenumimplccomenumimpl"></a><a name="dtor"></a>CComEnumImpl:: ~ CComEnumImpl  
 소멸자입니다.  
  
```
~CComEnumImpl();
```  
  
##  <a name="a-nameinita--ccomenumimplinit"></a><a name="init"></a>CComEnumImpl::Init  
 모든 클라이언트에 다시 열거자 인터페이스에 대 한 포인터를 전달 하기 전에이 메서드를 호출 해야 합니다.  
  
```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```  
  
### <a name="parameters"></a>매개 변수  
 *begin*  
 열거할 항목을 포함 하는 배열의 첫 번째 요소에 대 한 포인터입니다.  
  
 `end`  
 열거할 항목을 포함 하는 배열의 마지막 요소 바로 뒤의 위치에 대 한 포인터입니다.  
  
 *pUnk*  
 [in] **IUnknown** 활성화 되어 있어야 열거자의 수명 동안 하는 개체의 포인터입니다. 전달 **NULL** 이러한 개체가 없는 경우.  
  
 `flags`  
 열거자 배열의 소유권 해야 하거나의 복사본을 만들어 여부를 지정 하는 플래그입니다. 가능한 값은 다음과 같습니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 한 번 호출만-열거자 초기화를 사용 하 여 다음 버리는 것입니다.  
  
 다른 개체에 저장 된 배열의 항목에 대 한 포인터를 전달 하면 (및 데이터를 복사 하는 열거자를 묻지 않음) 하는 경우 사용할 수 있습니다는 *펑크* 매개 변수를 보유 하는 배열 및 개체를 사용할 수 있는지에 대 한 열거자가 필요할 만큼 되도록 합니다. 열거자는 단순히 활성화 상태로 유지 하는 개체에 COM 참조를 보유 합니다. COM 참조는 열거자가 소멸 될 때 자동으로 해제 됩니다.  
  
 `flags` 매개 변수를 사용 하는 열거자에 전달 된 배열 요소를 처리 해야 방법을 지정할 수 있습니다. `flags`값 중 하나를 수행할 수는 **CComEnumFlags** 아래에 표시 된 열거:  
  
 `enum CComEnumFlags`  
  
 `{`  
  
 `AtlFlagNoCopy = 0,`  
  
 `AtlFlagTakeOwnership = 2, // BitOwn`  
  
 `AtlFlagCopy = 3           // BitOwn | BitCopy`  
  
 `};`  
  
 **AtlFlagNoCopy** 열거자가 배열의 수명 제어 되지 않는 것을 의미 합니다. 두 배열의 경우 정적 또는 식별 되는 개체 됩니다 *펑크* 더 이상 필요 없는 경우 배열 해제 해야 합니다.  
  
 **AtlFlagTakeOwnership** 배열의 소멸은 열거자가 제어할 수 있다는 것을 의미 합니다. 이 경우 배열 해야 동적으로 할당 된 사용 하 여 **새**합니다. 열거자는 해당 소멸자에서 배열을 삭제 됩니다. 일반적으로 전달 합니다 **NULL** 에 대 한 *펑크*이지만 몇 가지 이유로 열거자의 소멸 알려야 하는 경우에 여전히 유효한 포인터를 전달할 수 있습니다.  
  
 **AtlFlagCopy** 새 배열이 전달 된 배열에 복사 하 여 만들 수 있다는 것을 의미 `Init`합니다. 새 배열의 수명은 열거자가 제어할 수 있습니다. 열거자는 해당 소멸자에서 배열을 삭제 됩니다. 일반적으로 전달 합니다 **NULL** 에 대 한 *펑크*이지만 몇 가지 이유로 열거자의 소멸 알려야 하는 경우에 여전히 유효한 포인터를 전달할 수 있습니다.  
  
> [!NOTE]
>  유형으로 배열 요소를 지정 하는이 메서드의 프로토타입 **T**여기서 **T** 클래스에 템플릿 매개 변수로 정의 되었습니다. 이 COM 인터페이스 메서드를 사용 하 여 노출 되는 동일한 유형의 [CComEnumImpl::Next](#next)합니다. 이 방식은 세 가지는 달리 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md),이 클래스는 다른 저장소를 지원 하지 않습니다 및 데이터 형식을 노출 합니다. 배열에 있는 요소의 데이터 형식을 COM 인터페이스를 사용 하 여 노출 하는 데이터 형식으로 동일 해야 합니다.  
  
##  <a name="a-nameclonea--ccomenumimplclone"></a><a name="clone"></a>CComEnumImpl::Clone  
 이 메서드는의 구현을 제공는 [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx) 형식의 개체를 만들어 메서드 `CComEnum`, 동일한 배열 및 현재 개체에서 사용 하는 반복기를 사용 하 여 초기화 하 고 새로 만든된 개체에서 인터페이스를 반환 합니다.  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppEnum`  
 [out] 현재 열거자에서 복제는 새로 만든된 개체에서 열거자 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 복제 된 열거자 하지 확인 자신의 원래 열거자가 사용 되는 데이터의 복사본 (또는 소유권 가져오기). 필요한 경우 복제 된 열거자 상태로 유지 합니다 원래 열거자 (COM 참조를 사용 하 여)으로 소요 되는 데이터에 사용할 수 있는 인지 확인 합니다.  
  
##  <a name="a-namemspunka--ccomenumimplmspunk"></a><a name="m_spunk"></a>CComEnumImpl::m_spUnk  
 이 스마트 포인터에 전달 된 개체에 대 한 참조를 유지 관리 [CComEnumImpl::Init](#init), 상태가 활성 상태로 열거자의 수명 동안 보장 합니다.  
  
```
CComPtr<IUnknown> m_spUnk;
```  
  
##  <a name="a-namembegina--ccomenumimplmbegin"></a><a name="m_begin"></a>CComEnumImpl::m_begin  
 열거할 항목을 포함 하는 배열의 마지막 요소 바로 뒤의 위치에 대 한 포인터입니다.  
  
```
T* m_begin;
```  
  
##  <a name="a-namemenda--ccomenumimplmend"></a><a name="m_end"></a>CComEnumImpl::m_end  
 열거할 항목을 포함 하는 배열의 첫 번째 요소에 대 한 포인터입니다.  
  
```
T* m_end;
```  
  
##  <a name="a-namemitera--ccomenumimplmiter"></a><a name="m_iter"></a>CComEnumImpl::m_iter  
 열거할 항목을 포함 하는 배열의 현재 요소에 대 한 포인터입니다.  
  
```
T* m_iter;
```  
  
##  <a name="a-namemdwflagsa--ccomenumimplmdwflags"></a><a name="m_dwflags"></a>CComEnumImpl::m_dwFlags  
 에 전달 되는 플래그 [CComEnumImpl::Init](#init)합니다.  
  
```
DWORD m_dwFlags;
```  
  
##  <a name="a-namenexta--ccomenumimplnext"></a><a name="next"></a>CComEnumImpl::Next  
 이 메서드는의 구현을 제공는 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) 메서드.  
  
```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```  
  
### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 요청 하는 요소의 수입니다.  
  
 `rgelt`  
 [out] 배열 요소를 채울 수입니다.  
  
 `pceltFetched`  
 [out] 에 실제로 반환 된 요소의 수 `rgelt`합니다. 이 수 미만 `celt` 보다 적을 경우 `celt` 요소 목록에 유지 합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="a-namereseta--ccomenumimplreset"></a><a name="reset"></a>CComEnumImpl::Reset  
 이 메서드는의 구현을 제공는 [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx) 메서드.  
  
```
STDMETHOD(Reset)(void);
```  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="a-nameskipa--ccomenumimplskip"></a><a name="skip"></a>CComEnumImpl::Skip  
 이 메서드는의 구현을 제공는 [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx) 메서드.  
  
```
STDMETHOD(Skip)(ULONG celt);
```  
  
### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 건너뛸 요소 수입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 E_INVALIDARG를 반환 `celt` 이&0; 이면 보다 작으면 S_FALSE를 반환 합니다. `celt` 반환 되는 요소가 그렇지 않은 경우는 S_OK를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumOnSTLImpl 클래스](../../atl/reference/ienumonstlimpl-class.md)   
 [CComEnum 클래스](../../atl/reference/ccomenum-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

