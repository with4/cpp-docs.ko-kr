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
ms.openlocfilehash: 26c3542f5bea21d1b705cd3253e6828ff73677df
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889009"
---
# <a name="runtimeclass-class"></a>RuntimeClass 클래스
지정된 된 인터페이스를 상속 하 고 지정 된 Windows 런타임, 클래식 COM 및 약한 참조 지원을 제공 하는 WinRT 또는 COM 클래스를 나타냅니다.  
  
이 클래스의 구현을 제공 하는 클래스 WinRT 및 COM 상용구 구현을 제공 `QueryInterface`, `AddRef`, `Release` 등에서 해당 모듈의 참조 횟수를 관리 하 고에 대 한 클래스 팩터리를 제공 하는 데 지원 활성화할 수 있는 개체입니다.
  
## <a name="syntax"></a>구문  
  
```
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```
  
#### <a name="parameters"></a>매개 변수  
 `classFlags`  
선택적 매개 변수는 음수일 합니다. 하나 이상의 조합이 [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거형 값입니다. `__WRL_CONFIGURATION_LEGACY__` classFlags 프로젝트의 모든 런타임 클래스에 대 한의 기본값을 변경 하려면 매크로 정의할 수 있습니다. 을 정의한 경우 속성이 RuntimeClass 인스턴스는 기본적으로 agile입니다. 정의 되지 않은 경우 RuntimeClass 인스턴스는 기본적으로 agile입니다. 방지 하려면 모호성 항상 지정에서 Microsoft::WRL::FtmBase `TInterfaces` 또는 RuntimeClassType::InhibitFtmBase 합니다. 단, InhibitFtmBase 및 FtmBase 모두 사용 하는 개체는 agile 됩니다.
 
 `TInterfaces`  
인터페이스 목록 개체가 구현 하는 IUnknown, IInspectable 또는 다른 인터페이스에 의해 제어 외 [RuntimeClassType](../windows/runtimeclasstype-enumeration.md)합니다. 또한 개체를 agile 고 IMarshal 구현가 특히 Microsoft::WRL::FtmBase에서 파생 될 다른 클래스도 나열할 수 있습니다.
  
## <a name="members"></a>멤버  
`RuntimeClassInitialize` MakeAndInitialize 템플릿 함수는 개체를 생성 하는 데 사용 되는 경우 개체를 초기화 하는 함수입니다. 초기화에 실패 한 경우 성공적으로 초기화 되었으므로 개체 하면 s_ok이 고 또는 COM 오류 코드가 반환 합니다. COM 오류 코드가 MakeAndInitialize의 반환 값으로 전파 됩니다. Note 만들기 템플릿 함수 개체를 만드는 데 사용 되는 경우 RuntimeClassInitialize 메서드가 호출 되지 않습니다.

### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[RuntimeClass::RuntimeClass 생성자](../windows/runtimeclass-runtimeclass-constructor.md)|RuntimeClass 클래스의 현재 인스턴스를 초기화합니다.|  
|[RuntimeClass::~RuntimeClass 소멸자](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|RuntimeClass 클래스의 현재 인스턴스 초기화를 취소 합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
구현 정보입니다.
  
## <a name="requirements"></a>요구 사항  
**헤더:** implements.h  
  
**네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
[Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)
