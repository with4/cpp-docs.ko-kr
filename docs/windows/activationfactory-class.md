---
title: ActivationFactory 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- ActivationFactory class
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18ce213d6c4bedd0bcaa2be1af33281ae69f6ad1
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461507"
---
# <a name="activationfactory-class"></a>ActivationFactory 클래스
Windows 런타임으로 활성화할 클래스를 하나 이상 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ActivationFactory : public Details::RuntimeClass<typename Details::InterfaceListHelper<IActivationFactory, I0, I1, I2, Details::Nil>::TypeT, RuntimeClassFlags<WinRt | InhibitWeakReference>, false>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *I0*  
 0 번째 인터페이스입니다.  
  
 *I1*  
 첫 번째 인터페이스입니다.  
  
 *I2*  
 두 번째 인터페이스입니다.  
  
## <a name="remarks"></a>설명  
 **ActivationFactory** 등록 방법 및에 대 한 기본 기능을 제공 합니다 `IActivationFactory` 인터페이스입니다. **ActivationFactory** 사용자 지정 팩터리 구현을 제공할 수 있습니다.  
  
 다음 코드 조각에는 기호로 ActivationFactory를 사용 하는 방법을 보여 줍니다.  
  
 [!code-cpp[wrl-microsoft__wrl__activationfactory#1](../windows/codesnippet/CPP/activationfactory-class_1.cpp)]  
  
 다음 코드 조각에 사용 하는 방법을 보여 줍니다 합니다 [구현](../windows/implements-structure.md) 세 개 이상의 인터페이스 Id를 지정 하는 구조입니다.  
  
 `struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[ActivationFactory::ActivationFactory 생성자](../windows/activationfactory-activationfactory-constructor.md)|초기화 된 **ActivationFactory** 클래스입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ActivationFactory::AddRef 메서드](../windows/activationfactory-addref-method.md)|현재 참조 수가 증가 **ActivationFactory** 개체입니다.|  
|[ActivationFactory::GetIids 메서드](../windows/activationfactory-getiids-method.md)|구현된 인터페이스 ID의 배열을 가져옵니다.|  
|[ActivationFactory::GetRuntimeClassName 메서드](../windows/activationfactory-getruntimeclassname-method.md)|개체의 런타임 클래스 이름을 가져옵니다 현재 **ActivationFactory** 인스턴스화합니다.|  
|[ActivationFactory::GetTrustLevel 메서드](../windows/activationfactory-gettrustlevel-method.md)|현재 ActivationFactory 인스턴스화하는 개체의 신뢰 수준을 가져옵니다.|  
|[ActivationFactory::QueryInterface 메서드](../windows/activationfactory-queryinterface-method.md)|지정된 된 인터페이스에 대 한 포인터를 검색합니다.|  
|[ActivationFactory::Release 메서드](../windows/activationfactory-release-method.md)|현재 참조 횟수를 감소 **ActivationFactory** 개체입니다.|  
  
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
  
 `ActivationFactory`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)