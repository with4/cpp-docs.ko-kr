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
ms.openlocfilehash: f16a10ef5119730fb492c4adb890aedcc09d3174
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461535"
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
 *I0*  
 (필수) 인터페이스 ID 0입니다.  
  
 *I1*  
 (필수) 인터페이스 ID 1입니다.  
  
 *I2*  
 (선택 사항) 인터페이스 ID 2입니다.  
  
 *I3*  
 (선택 사항) 인터페이스 ID 3입니다.  
  
 *I4*  
 (선택 사항) ID 4 인터페이스입니다.  
  
 *I5*  
 (선택 사항) 인터페이스 ID 5입니다.  
  
 *I6*  
 (선택 사항) 인터페이스 ID 6입니다.  
  
 *I7*  
 (선택 사항) 인터페이스 ID 7입니다.  
  
 *I8*  
 (선택 사항) 인터페이스 ID 8입니다.  
  
 *I9*  
 (선택 사항) 인터페이스 ID 9입니다.  
  
 *DerivedType*  
 파생된 형식입니다.  
  
 *BaseType*  
 파생 형식이 기본 형식입니다.  
  
 *hasImplements*  
 경우에 해당 하는 부울 값 **true**를 사용할 수 없습니다는 [MixIn](../windows/mixin-structure.md) 에서 파생 되지 않은 클래스를 사용 하 여 구조를 [구현](../windows/implements-structure.md) 갖는 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ChainInterfaces::CanCastTo 메서드](../windows/chaininterfaces-cancastto-method.md)|지정 된 인터페이스 ID 각 ChainInterface 템플릿 매개 변수를 정의한 특수화로 캐스팅 될 수 있는지 여부를 나타냅니다.|  
|[ChainInterfaces::CastToUnknown 메서드](../windows/chaininterfaces-casttounknown-method.md)|정의한 형식의 인터페이스 포인터를 캐스팅 합니다 *I0* IUnknown에 대 한 포인터를 템플릿 매개 변수입니다.|  
|[ChainInterfaces::FillArrayWithIid 메서드](../windows/chaininterfaces-fillarraywithiid-method.md)|인터페이스 ID가 정의한 저장소 합니다 *I0* 인터페이스 Id의 지정된 된 배열에 지정된 된 위치에 템플릿 매개 변수입니다.|  
|[ChainInterfaces::Verify 메서드](../windows/chaininterfaces-verify-method.md)|템플릿 매개 변수에서 정의 된 각 인터페이스가 확인 *I0* 를 통해 *I9* 에서 상속 `IUnknown` 및/또는 `IInspectable`를 올바르고 *I0* 에서 상속 *I1* 를 통해 *I9*합니다.|  
  
### <a name="protected-constants"></a>보호 된 상수  
  
|name|설명|  
|----------|-----------------|  
|[ChainInterfaces::IidCount 상수](../windows/chaininterfaces-iidcount-constant.md)|템플릿 매개 변수에서 지정한 인터페이스에 포함 된 인터페이스 Id의 총 *I0* 를 통해 *I9*합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `I0`  
  
 `ChainInterfaces`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)