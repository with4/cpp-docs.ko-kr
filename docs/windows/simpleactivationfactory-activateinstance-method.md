---
title: "SimpleActivationFactory::ActivateInstance 메서드 | Microsoft Docs"
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
  - "module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivateInstance 메서드"
ms.assetid: 4f836e51-5a6c-4bad-b871-9f25199298b4
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SimpleActivationFactory::ActivateInstance 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 인터페이스의 인스턴스를 만듭니다.  
  
## 구문  
  
```  
STDMETHOD(  
   ActivateInstance  
)(_Deref_out_ IInspectable **ppvObject);  
```  
  
#### 매개 변수  
 `ppvObject`  
 이 작업이 완료되면, `Base` 클래스 템플릿 매개 변수에 의해 지정된 개체의 인스턴스에 대한 포인터입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## 설명  
 클래스 템플릿 매개 변수에 지정 된 기본 클래스에서 파생 되지 않은 경우 어설션 오류가 발생 \_\_WRL\_STRICT\_\_를 정의하는 경우 [RuntimeClass](../windows/runtimeclass-class.md), WinRt 또는 WinRtClassicComMix를 사용하여 구성되지 않은 또는 [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거형 값입니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [SimpleActivationFactory 클래스](../windows/simpleactivationfactory-class.md)