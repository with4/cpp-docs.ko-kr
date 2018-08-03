---
title: ClassFactory 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory
dev_langs:
- C++
helpviewer_keywords:
- ClassFactory class
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97c07b5cf97578c49da9d4a72b5a232b559ec0ab
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463868"
---
# <a name="classfactory-class"></a>ClassFactory 클래스
`IClassFactory` 인터페이스의 기본 기능을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ClassFactory : public Details::RuntimeClass<  
   typename Details::InterfaceListHelper<IClassFactory,   
   I0,   
   I1,   
   I2,   
   Details::Nil>::TypeT,   
   RuntimeClassFlags<ClassicCom | InhibitWeakReference>,   
      false>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *I0*  
 0 번째 인터페이스입니다.  
  
 *I1*  
 첫 번째 인터페이스입니다.  
  
 *I2*  
 두 번째 인터페이스입니다.  
  
## <a name="remarks"></a>설명  
 활용 `ClassFactory` 는 사용자 정의 팩터리 구현을 제공 합니다.  
  
 프로그래밍 패턴을 사용 하는 방법에 설명 합니다 [구현](../windows/implements-structure.md) 클래스 팩터리 세 개 이상의 인터페이스를 지정 하는 구조입니다.  
  
 `struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[ClassFactory::ClassFactory 생성자](../windows/classfactory-classfactory-constructor.md)||  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ClassFactory::AddRef 메서드](../windows/classfactory-addref-method.md)|현재 ClassFactory 개체에 대 한 참조 횟수를 증가 시킵니다.|  
|[ClassFactory::LockServer 메서드](../windows/classfactory-lockserver-method.md)|현재 ClassFactory 개체에서 추적하는 기본 개체 수를 늘리거나 줄입니다.|  
|[ClassFactory::QueryInterface 메서드](../windows/classfactory-queryinterface-method.md)|매개 변수에 의해 지정 된 인터페이스에 대 한 포인터를 검색 합니다.|  
|[ClassFactory::Release 메서드](../windows/classfactory-release-method.md)|현재 ClassFactory 개체에 대 한 참조 횟수를 감소 시킵니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ClassFactory`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft:: wrl Namespace](../windows/microsoft-wrl-namespace.md)   
 [RuntimeClassType 열거형](../windows/runtimeclasstype-enumeration.md)