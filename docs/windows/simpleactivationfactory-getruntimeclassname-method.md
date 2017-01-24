---
title: "SimpleActivationFactory::GetRuntimeClassName 메서드 | Microsoft Docs"
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
  - "module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName"
dev_langs: 
  - "C++"
ms.assetid: 3aa07487-9a42-46f8-8893-37ba6315e50b
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SimpleActivationFactory::GetRuntimeClassName 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

런타임 클래스 이름에 지정된 클래스의 인스턴스를 `Base` 클래스 탬플릿 매개변수에 의해 가져옵니다.  
  
## 구문  
  
```  
STDMETHOD(  
   GetRuntimeClassName  
)(_Out_ HSTRING* runtimeName);  
```  
  
#### 매개 변수  
 `runtimeName`  
 이 작업이 완료되면, 런타임 클래스 이름입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## 설명  
 만일 \_\_WRL\_STRICT\_\_가 정의된 경우, 어설트 오류를 발생합니다. 만일 `Base` 클래스 탬플릿 매개변수에 의해 지정된 클래스가 [런타임클래스](../windows/runtimeclass-class.md) 로부터 도출되지 않았을 경우, 또는 WinRt 혹은 WinRtClaasicComMix [런타임클래스형식](../windows/runtimeclasstype-enumeration.md) 열거 값으로 구성되지 않았을 경우 입니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [SimpleActivationFactory 클래스](../windows/simpleactivationfactory-class.md)