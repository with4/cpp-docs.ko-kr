---
title: "Module 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Module 클래스"
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Module 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

관련 개체의 컬렉션을 나타냅니다.  
  
## 구문  
  
```  
  
template<  
   ModuleType moduleType  
>  
class Module;  
  
template<>  
class Module<InProc> : public Details::ModuleBase;  
  
template<>  
class Module<OutOfProc> : public Module<InProc>;  
```  
  
#### 매개 변수  
 `moduleType`  
 하나 이상의 [ModuleType](../windows/moduletype-enumeration.md) 열거형 값의 조합입니다.  
  
## 멤버  
  
### Protected 클래스  
  
|Name|설명|  
|----------|--------|  
|[Module::GenericReleaseNotifier 클래스](../windows/module-genericreleasenotifier-class.md)|현재 모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출 합니다.  이벤트 처리기는 람다 함수, 함수 포인터에 의해 지정 됩니다.|  
|[Module::MethodReleaseNotifier 클래스](../windows/module-methodreleasenotifier-class.md)|현재 모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출 합니다.  이벤트 처리기는 개체와 해당 포인터에\-a\-메서드 멤버에 의해 지정 됩니다.|  
|[Module::ReleaseNotifier 클래스](../windows/module-releasenotifier-class.md)|모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출 합니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[Module::~Module 소멸자](../windows/module-tilde-module-destructor.md)|모듈 클래스의 현재 인스턴스를 초기화 해제합니다.|  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[Module::Module 생성자](../windows/module-module-constructor.md)|모듈 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[Module::Create 메서드](../windows/module-create-method.md)|모듈의 인스턴스를 만듭니다.|  
|[Module::DecrementObjectCount 메서드](../windows/module-decrementobjectcount-method.md)|모듈에 의해 추적 되는 개체의 수를 감소시킵니다.|  
|[Module::GetActivationFactory 메서드](../windows/module-getactivationfactory-method.md)|모듈에 대한 정품 인증 팩터리를 가져옵니다.|  
|[Module::GetClassObject 메서드](../windows/module-getclassobject-method.md)|캐시 클래스 팩터리를 검색합니다.|  
|[Module::GetModule 메서드](../windows/module-getmodule-method.md)|모듈의 인스턴스를 만듭니다.|  
|[Module::GetObjectCount 메서드](../windows/module-getobjectcount-method.md)|이 모듈에서 관리 되는 개체의 수를 검색 합니다.|  
|[Module::IncrementObjectCount 메서드](../windows/module-incrementobjectcount-method.md)|모듈에 의해 추적 되는 개체의 수를 증가시킵니다.|  
|[Module::RegisterCOMObject 메서드](../windows/module-registercomobject-method.md)|다른 응용 프로그램에 연결할 수 있도록 하나 이상의 COM 개체를 등록 합니다.|  
|[Module::RegisterObjects 메서드](../windows/module-registerobjects-method.md)|COM 또는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 개체가 다른 응용 프로그램에 연결할 수 있도록 등록합니다.|  
|[Module::RegisterWinRTObject 메서드](../windows/module-registerwinrtobject-method.md)|다른 응용 프로그램에 연결할 수 있도록 하나 이상의 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 또는 COM 개체를 등록 합니다.|  
|[Module::Terminate 메서드](../windows/module-terminate-method.md)|모든 팩터리에 모듈을 종료하여 발생 합니다.|  
|[Module::UnregisterCOMObject 메서드](../windows/module-unregistercomobject-method.md)|다른 응용 프로그램에 연결할 수 없는 하나 이상의 COM 개체를 등록 취소 합니다.|  
|[Module::UnregisterObjects 메서드](../windows/module-unregisterobjects-method.md)|다른 응용 프로그램에 연결할 수 없습니다. 그 결과 개체에 지정된 모듈을 등록 취소 합니다.|  
|[Module::UnregisterWinRTObject 메서드](../windows/module-unregisterwinrtobject-method.md)|다른 응용 프로그램에 연결할 수 없도록 하나 이상의 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 또는 COM 개체를 등록하지 않습니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[Module::Create 메서드](../windows/module-create-method.md)|모듈의 인스턴스를 만듭니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[Module::objectCount\_ 데이터 멤버](../windows/module-objectcount-data-member.md)|얼마나 많은 클래스에서 [Make](../windows/make-function.md) 함수를 사용해 생성된 트랙을 유지합니다.|  
|[Module::releaseNotifier\_ 데이터 멤버](../windows/module-releasenotifier-data-member.md)|ReleaseNotifier 개체에 대 한 포인터를 보유합니다.|  
  
### 매크로  
  
|||  
|-|-|  
|[ActivatableClass](../windows/activatableclass-macros.md)|지정된 된 클래스의 인스턴스를 만들 수 있는 공장을 포함 하는 내부 캐시를 채웁니다.  이 매크로 기본 팩터리 및 그룹 ID 매개 변수를 지정합니다.|  
|[ActivatableClassWithFactory](../windows/activatableclass-macros.md)|지정된 된 클래스의 인스턴스를 만들 수 있는 공장을 포함 하는 내부 캐시를 채웁니다.  이 매크로 팩터리를 특정 매개 변수로 지정할 수 있습니다.|  
|[ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)|지정된 된 클래스의 인스턴스를 만들 수 있는 공장을 포함 하는 내부 캐시를 채웁니다.  이 매크로를 사용하면 특정 공장 및 그룹 ID 매개 변수를 지정할 수 있습니다.|  
  
## 상속 계층  
 `ModuleBase`  
  
 `Module`  
  
 `Module`  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)