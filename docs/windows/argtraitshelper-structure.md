---
title: ArgTraitsHelper 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
dev_langs:
- C++
helpviewer_keywords:
- ArgTraitsHelper structure
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fe97cc63de1f83d110e37451c1ceb91c7ad59f49
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652463"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper 구조체
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template<typename TDelegateInterface>  
struct ArgTraitsHelper;  
```  
  
### <a name="parameters"></a>매개 변수  
 *TDelegateInterface*  
 대리자 인터페이스입니다.  
  
## <a name="remarks"></a>설명  
 대리자 인수의 공통 된 특징을 정의할 수 있습니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`methodType`|`decltype(&TDelegateInterface::Invoke)`의 동의어입니다.|  
|`Traits`|`ArgTraits<methodType>`의 동의어입니다.|  
  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[ArgTraitsHelper::args 상수](../windows/argtraitshelper-args-constant.md)|데 도움이 됩니다 [argtraits:: Args](../windows/argtraits-args-constant.md) 매개 변수 개수를 유지는 `Invoke` 대리자 인터페이스의 메서드입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ArgTraitsHelper`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)