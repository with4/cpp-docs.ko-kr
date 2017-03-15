---
title: "CreateActivationFactory 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::CreateActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateActivationFactory 함수"
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# CreateActivationFactory 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows 런타임에 의해 활성화될 수 있는 지정된 클래스의 인스턴스를 생성하는 팩터리를 만듭니다.  
  
## 구문  
  
```cpp  
  
template<typename Factory>  
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(  
      _In_ unsigned int *flags,    
      _In_ const CreatorMap* entry,   
      REFIID riid,   
     _Outptr_ IUnknown **ppFactory) throw();  
  
```  
  
#### 매개 변수  
 `flags`  
 하나 이상의 [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거형 값의 조합입니다.  
  
 `entry`  
 매개변수 `riid` 에 관한 초기화와 등록 정보를 포함하는 [CreatorMap](../windows/creatormap-structure.md) 에 대한 포인터.  
  
 `riid`  
 인터페이스 ID에 대한 참조  
  
 `ppFactory`  
 완료 되면 이 작업에는 정품 인증 팩터리에 대한 포인터를 성공적으로 완료합니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## 설명  
 어설션 오류가 발생하면 템플릿 매개 변수 `Factory` 는 IActivationFactory 인터페이스에서 파생되지 않습니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers::Details 네임스페이스](../windows/microsoft-wrl-wrappers-details-namespace.md)