---
title: RuntimeClass 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClass class
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d777dd15e484ae296139bbe2bdc9b0cddcab2d59
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606334"
---
# <a name="runtimeclass-class"></a>RuntimeClass 클래스
지정된 된 인터페이스를 상속 하 고 지정 된 Windows 런타임, 클래식 COM 및 약한 참조 지원을 제공 하는 WinRT 또는 COM 클래스를 나타냅니다.  
  
이 클래스의 구현을 제공 하는 클래스 WinRT 및 COM의 상용구 구현을 제공 `QueryInterface`, `AddRef`, `Release` 등 모듈의 참조 횟수를 관리 및 지원에 대 한 클래스 팩터리를 제공 합니다. 활성화할 수 있는 개체입니다.
  
## <a name="syntax"></a>구문  
  
```
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```
  
### <a name="parameters"></a>매개 변수  
 *classFlags*  
선택적 매개 변수입니다. 하나 이상의 조합 [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거형 값입니다. `__WRL_CONFIGURATION_LEGACY__` classFlags 프로젝트의 모든 런타임 클래스에 대 한의 기본값을 변경 하려면 매크로 정의할 수 있습니다. 정의 하는 경우에 RuntimeClass 인스턴스는 기본적으로 agile 합니다. 정의 되지 않은 경우 RuntimeClass 인스턴스는 기본적으로 agile입니다. 방지 하려면 모호성 항상 지정 된 `Microsoft::WRL::FtmBase` 에 `TInterfaces` 또는 `RuntimeClassType::InhibitFtmBase`합니다. InhibitFtmBase FtmBase와 개체를 모두 사용 하는 경우 agile 됩니다.
 
 *TInterfaces*  
인터페이스 목록 외 구현 된 개체 `IUnknown`, `IInspectable` 또는 다른 인터페이스에 의해 제어 [RuntimeClassType](../windows/runtimeclasstype-enumeration.md)합니다. 다른 클래스에서 특히 파생를 나열할 수 있습니다 `Microsoft::WRL::FtmBase` 개체를 agile 확인을 구현 하면 `IMarshal`합니다.
  
## <a name="members"></a>멤버  
`RuntimeClassInitialize` 경우에 개체를 초기화 하는 함수는 `MakeAndInitialize` 템플릿 함수는 개체를 만드는 데 사용 됩니다. 초기화에 실패 한 경우 개체가 성공적으로 초기화 된 경우 S_OK 또는 COM 오류 코드를 반환 합니다. COM 오류 코드 반환 값으로 전파 됩니다 `MakeAndInitialize`합니다. 합니다 `RuntimeClassInitialize` 경우에 메서드가 호출 되지 않습니다는 `Make` 템플릿 함수는 개체를 만드는 데 사용 됩니다.

### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[RuntimeClass::RuntimeClass 생성자](../windows/runtimeclass-runtimeclass-constructor.md)|RuntimeClass 클래스의 현재 인스턴스를 초기화 합니다.|  
|[RuntimeClass::~RuntimeClass 소멸자](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|RuntimeClass 클래스의 현재 인스턴스 초기화를 취소합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
구현 세부 정보입니다.
  
## <a name="requirements"></a>요구 사항  
**헤더:** implements.h  
  
**네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)