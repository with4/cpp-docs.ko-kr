---
title: Module 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module
dev_langs:
- C++
helpviewer_keywords:
- Module class
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2d097c5c1193b74aa3e4d6ecea755390b0885a8d
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013062"
---
# <a name="module-class"></a>Module 클래스
관련된 개체의 컬렉션을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template<ModuleType moduleType>  
class Module;  
  
template<>  
class Module<InProc> : public Details::ModuleBase;  
  
template<>  
class Module<OutOfProc> : public Module<InProc>;  
```  
  
### <a name="parameters"></a>매개 변수  
 *moduleType*  
 하나 이상의 조합 [ModuleType](../windows/moduletype-enumeration.md) 열거형 값입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="protected-classes"></a>보호 된 클래스  
  
|name|설명|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier 클래스](../windows/module-genericreleasenotifier-class.md)|현재 모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다. 이벤트 처리기는 람다, 함수 또는 함수 포인터에 의해 지정됩니다.|  
|[Module::MethodReleaseNotifier 클래스](../windows/module-methodreleasenotifier-class.md)|현재 모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다. 이벤트 처리기 개체와 해당 포인터를-a-메서드 멤버 지정 됩니다.|  
|[Module::ReleaseNotifier 클래스](../windows/module-releasenotifier-class.md)|모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Module::~Module 소멸자](../windows/module-tilde-module-destructor.md)|현재 인스턴스 초기화를 해제 합니다 **모듈** 클래스입니다.|  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Module::Module 생성자](../windows/module-module-constructor.md)|새 인스턴스를 초기화 합니다 **모듈** 클래스입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Module::Create 메서드](../windows/module-create-method.md)|모듈의 인스턴스를 만듭니다.|  
|[Module::DecrementObjectCount 메서드](../windows/module-decrementobjectcount-method.md)|모듈에서 추적하는 개체 수를 줄입니다.|  
|[Module::GetActivationFactory 메서드](../windows/module-getactivationfactory-method.md)|모듈에 대한 활성화 팩터리를 가져옵니다.|  
|[Module::GetClassObject 메서드](../windows/module-getclassobject-method.md)|클래스 팩터리의 캐시를 가져옵니다.|  
|[Module::GetModule 메서드](../windows/module-getmodule-method.md)|모듈의 인스턴스를 만듭니다.|  
|[Module::GetObjectCount 메서드](../windows/module-getobjectcount-method.md)|이 모듈에서 관리되는 개체 수를 가져옵니다.|  
|[Module::IncrementObjectCount 메서드](../windows/module-incrementobjectcount-method.md)|모듈에서 추적하는 개체 수를 늘립니다.|  
|[Module::RegisterCOMObject 메서드](../windows/module-registercomobject-method.md)|다른 응용 프로그램이 COM 개체에 연결할 수 있도록 이 개체를 하나 이상 등록합니다.|  
|[Module::RegisterObjects 메서드](../windows/module-registerobjects-method.md)|다른 응용 프로그램에 연결할 수 있도록 COM 또는 Windows 런타임 개체를 등록 합니다.|  
|[Module::RegisterWinRTObject 메서드](../windows/module-registerwinrtobject-method.md)|다른 응용 프로그램에 연결할 수 있도록 하나 이상의 Windows 런타임 개체를 등록 합니다.|  
|[Module::Terminate 메서드](../windows/module-terminate-method.md)|모듈에 의해 인스턴스화되는 모든 팩터리가 종료됩니다.|  
|[Module::UnregisterCOMObject 메서드](../windows/module-unregistercomobject-method.md)|다른 응용 프로그램에서 COM 개체에 연결할 수 없도록 하나 이상의 COM 개체의 등록을 취소합니다.|  
|[Module::UnregisterObjects 메서드](../windows/module-unregisterobjects-method.md)|다른 응용 프로그램에서 지정된 모듈의 개체에 연결할 수 없도록 이 개체의 등록을 취소합니다.|  
|[Module::UnregisterWinRTObject 메서드](../windows/module-unregisterwinrtobject-method.md)|다른 응용 프로그램과 연결할 수 있도록 하나 이상의 Windows 런타임 개체를 등록 취소 합니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Module::Create 메서드](../windows/module-create-method.md)|모듈의 인스턴스를 만듭니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[Module::objectCount_ 데이터 멤버](../windows/module-objectcount-data-member.md)|얼마나 많은 클래스가 사용 하 여 만든 추적 합니다는 [있도록](../windows/make-function.md) 함수입니다.|  
|[Module::releaseNotifier_ 데이터 멤버](../windows/module-releasenotifier-data-member.md)|에 대 한 포인터를 보유 한 `ReleaseNotifier` 개체입니다.|  
  
### <a name="macros"></a>매크로  
  
|||  
|-|-|  
|[ActivatableClass](../windows/activatableclass-macros.md)|지정된 된 클래스의 인스턴스를 만들 수 있는 팩터리를 포함 하는 내부 캐시를 채웁니다. 이 매크로 기본 팩터리 및 그룹 ID 매개 변수를 지정합니다.|  
|[ActivatableClassWithFactory](../windows/activatableclass-macros.md)|지정된 된 클래스의 인스턴스를 만들 수 있는 팩터리를 포함 하는 내부 캐시를 채웁니다. 이 매크로 사용 하면 특정 factory 매개 변수를 지정할 수 있습니다.|  
|[ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)|지정된 된 클래스의 인스턴스를 만들 수 있는 팩터리를 포함 하는 내부 캐시를 채웁니다. 이 매크로 사용 하면 특정 팩터리 및 그룹 ID 매개 변수를 지정할 수 있습니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ModuleBase`  
  
 `Module`  
  
 `Module`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)