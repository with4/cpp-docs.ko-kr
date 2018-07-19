---
title: ChainInterfaces 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces
dev_langs:
- C++
helpviewer_keywords:
- ChainInterfaces structure
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18814a4ad87cefa39201d369926c0778931d4d64
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861138"
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces 구조체
인터페이스 ID 집합에 적용할 수 있는 확인 및 초기화 함수를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   typename I0,  
   typename I1,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
struct ChainInterfaces : I0;  
template <  
   typename DerivedType,  
   typename BaseType,  
   bool hasImplements,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8,  
   typename I9  
>  
struct ChainInterfaces<MixIn<DerivedType, BaseType, hasImplements>, I1, I2, I3, I4, I5, I6, I7, I8, I9>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `I0`  
 (필수) 인터페이스 ID 0입니다.  
  
 `I1`  
 (필수) 인터페이스 ID 1입니다.  
  
 `I2`  
 (선택 사항) 인터페이스 ID 2입니다.  
  
 `I3`  
 (선택 사항) 인터페이스 ID 3입니다.  
  
 `I4`  
 (선택 사항) 인터페이스 ID 4입니다.  
  
 `I5`  
 (선택 사항) 인터페이스 ID 5입니다.  
  
 `I6`  
 (선택 사항) 인터페이스 ID 6입니다.  
  
 `I7`  
 (선택 사항) 인터페이스 ID 7입니다.  
  
 `I8`  
 (선택 사항) 인터페이스 ID 8입니다.  
  
 `I9`  
 (선택 사항) 인터페이스 ID 9입니다.  
  
 `DerivedType`  
 파생된 형식입니다.  
  
 `BaseType`  
 파생 형식의 기본 형식입니다.  
  
 `hasImplements`  
 부울 값 경우 `true`, 사용할 수 없습니다는 [MixIn](../windows/mixin-structure.md) 에서 파생 되지 않는 클래스와 구조체는 [구현](../windows/implements-structure.md) 구조체입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ChainInterfaces::CanCastTo 메서드](../windows/chaininterfaces-cancastto-method.md)|지정 된 인터페이스 ID 각 ChainInterface 템플릿 매개 변수를 정의한 특수화도 캐스팅 될 수 있는지 여부를 나타냅니다.|  
|[ChainInterfaces::CastToUnknown 메서드](../windows/chaininterfaces-casttounknown-method.md)|`I0` 템플릿 매개 변수에 의해 정의된 형식의 인터페이스 포인터를 IUnknown에 대한 포인터에 캐스팅합니다.|  
|[ChainInterfaces::FillArrayWithIid 메서드](../windows/chaininterfaces-fillarraywithiid-method.md)|저장소에 정의 된 인터페이스 ID는 `I0` 인터페이스 Id의 지정된 된 배열에 지정된 된 위치에 템플릿 매개 변수입니다.|  
|[ChainInterfaces::Verify 메서드](../windows/chaininterfaces-verify-method.md)|템플릿 매개 변수 `I0`-`I9`에 의해 정의된 각 인터페이스가 IUnknown 및/또는 IInspectable에서 상속하는지, `I0`이 `I1`부터 `I9`까지 상속하는지 확인합니다.|  
  
### <a name="protected-constants"></a>보호 된 상수  
  
|이름|설명|  
|----------|-----------------|  
|[ChainInterfaces::IidCount 상수](../windows/chaininterfaces-iidcount-constant.md)|템플릿 매개 변수 `I0`부터 `I9`까지에서 지정한 인터페이스에 포함된 인터페이스 ID의 총 개수입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `I0`  
  
 `ChainInterfaces`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)