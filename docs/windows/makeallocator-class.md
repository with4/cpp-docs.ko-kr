---
title: MakeAllocator 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
dev_langs:
- C++
helpviewer_keywords:
- MakeAllocator class
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c87f1191bc90cd2aec9207f3a4657349c9859bf4
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605921"
---
# <a name="makeallocator-class"></a>MakeAllocator 클래스
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<  
   typename T,  
   bool hasWeakReferenceSupport =   
         !__is_base_of(RuntimeClassFlags<InhibitWeakReference>, T)>
 class MakeAllocator;  
  
template<typename T>  
class MakeAllocator<T, false>;  
  
template<typename T>  
class MakeAllocator<T, true>;  
```  
  
### <a name="parameters"></a>매개 변수  
 *T*  
 형식 이름.  
  
 *hasWeakReferenceSupport*  
 **true** ; 약한 참조를 지 원하는 개체에 대 한 메모리를 할당 하려면 **false** 약한 참조를 지원 하지 않는 개체에 대 한 메모리를 할당할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 약한 참조 지원을 유무는 활성화 가능한 클래스에 대 한 메모리를 할당합니다.  
  
 재정의 된 **MakeAllocator** 사용자 정의 메모리 할당 모델을 구현 하는 클래스입니다.  
  
 **MakeAllocator** 개체를 생성 하는 동안 throw 하는 경우 메모리 누수를 방지 하려면 일반적으로 사용 됩니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[MakeAllocator::MakeAllocator 생성자](../windows/makeallocator-makeallocator-constructor.md)|새 인스턴스를 초기화 합니다 **MakeAllocator** 클래스입니다.|  
|[MakeAllocator::~MakeAllocator 소멸자](../windows/makeallocator-tilde-makeallocator-destructor.md)|현재 인스턴스 초기화를 해제 합니다 **MakeAllocator** 클래스입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[MakeAllocator::Allocate 메서드](../windows/makeallocator-allocate-method.md)|메모리를 할당 하 고 현재 연결 **MakeAllocator** 개체입니다.|  
|[MakeAllocator::Detach 메서드](../windows/makeallocator-detach-method.md)|의해 할당 된 메모리를 분리 합니다 [할당](../windows/makeallocator-allocate-method.md) 현재 메서드에서 **MakeAllocator** 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `MakeAllocator`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)