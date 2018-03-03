---
title: "구조를 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements
dev_langs:
- C++
helpviewer_keywords:
- Implements structure
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 63da9ea650c34b7b1ed75d351587c39e52a88098
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="implements-structure"></a>Implements 구조체
지정된 인터페이스에 대해 QueryInterface 및 GetIid를 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   typename I0,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
struct __declspec(novtable) Implements : Details::ImplementsHelper<RuntimeClassFlags<WinRt>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT>, Details::ImplementsBase;  
template <  
   int flags,  
   typename I0,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8  
>  
struct __declspec(novtable) Implements<RuntimeClassFlags<flags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : Details::ImplementsHelper<RuntimeClassFlags<flags>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT>, Details::ImplementsBase;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `I0`  
 0 번째 인터페이스 id입니다. (필수)  
  
 `I1`  
 첫 번째 인터페이스 id입니다. 이 매개 변수는 선택 사항입니다.  
  
 `I2`  
 두 번째 인터페이스 id입니다. 이 매개 변수는 선택 사항입니다.  
  
 `I3`  
 세 번째 인터페이스 id입니다. 이 매개 변수는 선택 사항입니다.  
  
 `I4`  
 네 번째 인터페이스 id입니다. 이 매개 변수는 선택 사항입니다.  
  
 `I5`  
 다섯 번째 인터페이스 id입니다. 이 매개 변수는 선택 사항입니다.  
  
 `I6`  
 여섯 번째 인터페이스 id입니다. 이 매개 변수는 선택 사항입니다.  
  
 `I7`  
 일곱 번째 인터페이스 id입니다. 이 매개 변수는 선택 사항입니다.  
  
 `I8`  
 여덟 번째 인터페이스 id입니다. 이 매개 변수는 선택 사항입니다.  
  
 `I9`  
 아홉 번째 인터페이스 id입니다. 이 매개 변수는 선택 사항입니다.  
  
 `flags`  
 클래스에 대 한 플래그를 구성 합니다. 하나 이상의 [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거형에 지정 된 한 [RuntimeClassFlags](../windows/runtimeclassflags-structure.md) 구조입니다.  
  
## <a name="remarks"></a>설명  
 지정 된 인터페이스 목록에서 파생 되 고 도우미 템플릿 QueryInterface 및 GetIid를 자동으로 구현 합니다.  
  
 각 `I0` 통해 `I9` 인터페이스 매개 변수가 IInspectable, 어느 IUnknown에서 파생 되어야 합니다 또는 [ChainInterfaces](../windows/chaininterfaces-structure.md) 서식 파일입니다. `flags` 매개 변수 지원에 대해 IUnknown 또는 IInspectable 생성 되는지 여부를 결정 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`ClassFlags`|`RuntimeClassFlags<WinRt>`의 동의어입니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Implements::CanCastTo 메서드](../windows/implements-cancastto-method.md)|지정된 된 인터페이스에 대 한 포인터를 가져옵니다.|  
|[Implements::CastToUnknown 메서드](../windows/implements-casttounknown-method.md)|기본 IUnknown 인터페이스에 대 한 포인터를 가져옵니다.|  
|[Implements::FillArrayWithIid 메서드](../windows/implements-fillarraywithiid-method.md)|지정 된 배열 요소에 현재 0 번째 템플릿 매개 변수로 지정 된 인터페이스 ID를 삽입 합니다.|  
  
### <a name="protected-constants"></a>보호 된 상수  
  
|name|설명|  
|----------|-----------------|  
|[Implements::IidCount 상수](../windows/implements-iidcount-constant.md)|구현 된 인터페이스 Id의 수를 보유합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `ImplementsBase`  
  
 `ImplementsHelper`  
  
 `Implements`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)