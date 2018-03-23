---
title: InterfaceTraits 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits
dev_langs:
- C++
helpviewer_keywords:
- InterfaceTraits structure
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4b4b219091393b1195b60ae78347f952c2c9d37a
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="interfacetraits-structure"></a>InterfaceTraits 구조체
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<  
   typename I0  
>  
struct __declspec(novtable) InterfaceTraits;  
template<typename CloakedType>  
struct __declspec(novtable) InterfaceTraits<CloakedIid<CloakedType>>;  
  
template<>  
struct __declspec(novtable) InterfaceTraits<Nil>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `I0`  
 인터페이스의 이름입니다.  
  
 `CloakedType`  
 RuntimeClass, Implements 및 ChainInterfaces에 대 한 인터페이스를 목록에 저장 되지 않습니다 인터페이스 Id를 지원 합니다.  
  
## <a name="remarks"></a>설명  
 인터페이스의 공통 특성을 구현 합니다.  
  
 두 번째 템플릿은 숨겨진된 인터페이스에 대 한 특수화입니다. 세 번째 템플릿은 Nil 매개 변수에 대 한 특수화입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`Base`|`I0` 템플릿 매개 변수의 동의어입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[InterfaceTraits::CanCastTo 메서드](../windows/interfacetraits-cancastto-method.md)|지정된 된 포인터에 대 한 포인터로 캐스팅 될 수 있는지 여부를 나타냅니다. `Base`합니다.|  
|[InterfaceTraits::CastToBase 메서드](../windows/interfacetraits-casttobase-method.md)|지정된 된 포인터에 대 한 포인터를 캐스팅 `Base`합니다.|  
|[InterfaceTraits::CastToUnknown 메서드](../windows/interfacetraits-casttounknown-method.md)|지정된 된 포인터를 IUnknown에 대 한 포인터를 캐스팅합니다.|  
|[InterfaceTraits::FillArrayWithIid 메서드](../windows/interfacetraits-fillarraywithiid-method.md)|인터페이스 ID를 할당 `Base` index 인수로 지정 된 배열 요소에 있습니다.|  
|[InterfaceTraits::Verify 메서드](../windows/interfacetraits-verify-method.md)|자료 제대로 파생 된 것을 확인 합니다.|  
  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[InterfaceTraits::IidCount 상수](../windows/interfacetraits-iidcount-constant.md)|현재 InterfaceTraits 개체와 연결 된 Id 인터페이스의 수를 보유 합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `InterfaceTraits`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)