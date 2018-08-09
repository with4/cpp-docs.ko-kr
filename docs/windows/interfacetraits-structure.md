---
title: InterfaceTraits 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits
dev_langs:
- C++
helpviewer_keywords:
- InterfaceTraits structure
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6cb96b90a069c12e65c53158717d9a89fb0aed3d
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014102"
---
# <a name="interfacetraits-structure"></a>InterfaceTraits 구조체
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template<  
   typename I0  
>  
struct __declspec(novtable) InterfaceTraits;  
template<typename CloakedType>  
struct __declspec(novtable) InterfaceTraits<CloakedIid<CloakedType>>;  
  
template<>  
struct __declspec(novtable) InterfaceTraits<Nil>;  
```  
  
### <a name="parameters"></a>매개 변수  
 *I0*  
 인터페이스의 이름입니다.  
  
 *CloakedType*  
 에 대 한 `RuntimeClass`, `Implements` 고 `ChainInterfaces`, 목록의 수 없는 인터페이스는 인터페이스 Id를 지원 합니다.  
  
## <a name="remarks"></a>설명  
 인터페이스의 공통 특성을 구현 합니다.  
  
 두 번째 템플릿은 감추어진된 인터페이스에 대 한 특수화입니다. 세 번째 템플릿은 Nil 매개 변수에 대 한 특수화입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`Base`|동의어는 *I0* 템플릿 매개 변수입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[InterfaceTraits::CanCastTo 메서드](../windows/interfacetraits-cancastto-method.md)|지정된 된 포인터에 대 한 포인터로 캐스팅 될 수 있는지 여부를 나타내는 `Base`합니다.|  
|[InterfaceTraits::CastToBase 메서드](../windows/interfacetraits-casttobase-method.md)|지정된 된 포인터에 대 한 포인터를 캐스팅 `Base`합니다.|  
|[InterfaceTraits::CastToUnknown 메서드](../windows/interfacetraits-casttounknown-method.md)|지정된 된 포인터에 대 한 포인터를 캐스팅 `IUnknown`합니다.|  
|[InterfaceTraits::FillArrayWithIid 메서드](../windows/interfacetraits-fillarraywithiid-method.md)|인터페이스 ID를 할당 `Base` 인덱스 인수에 의해 지정 된 배열 요소에 있습니다.|  
|[InterfaceTraits::Verify 메서드](../windows/interfacetraits-verify-method.md)|확인 `Base` 제대로 파생 됩니다.|  
  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[InterfaceTraits::IidCount 상수](../windows/interfacetraits-iidcount-constant.md)|인터페이스 Id 현재 연결 수를 보유 **InterfaceTraits** 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `InterfaceTraits`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)