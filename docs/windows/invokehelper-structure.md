---
title: "InvokeHelper 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::InvokeHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InvokeHelper 구조체"
ms.assetid: 555ad2bc-4dd6-4e65-a2e2-1242c395f0e5
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# InvokeHelper 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
template<  
   typename TDelegateInterface,  
   typename TCallback,  
   unsigned int argCount  
>  
struct InvokeHelper;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 0> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 1> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 2> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 3> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 4> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 5> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 6> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 7> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 8> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 9> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
```  
  
#### 매개 변수  
 `TDelegateInterface`  
 `TCallback`  
 이벤트 핸들러 함수의 형식.  
  
 `argCount`  
 InvokeHelper 전문화 프로그램에 있는 인수의 수입니다.  
  
## 설명  
 지정된 수와 인수의 형식에 따라 invoke \(\) 메서드는 구현을 제공합니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`Traits`|각 이벤트 처리기 인수의 형식을 정의하는 클래스에 대한 약어입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[InvokeHelper::InvokeHelper 생성자](../windows/invokehelper-invokehelper-constructor.md)|InvokeHelper 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[InvokeHelper::Invoke 메서드](../windows/invokehelper-invoke-method.md)|지정한 개수의 인수를 포함하는 시그니처를 가진 이벤트 처리기를 호출 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[InvokeHelper::callback\_ 데이터 멤버](../windows/invokehelper-callback-data-member.md)|이벤트가 발생할 때 호출할 이벤트 처리기를 나타냅니다.|  
  
## 상속 계층  
 `InvokeHelper`  
  
## 요구 사항  
 **헤더:** event.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)