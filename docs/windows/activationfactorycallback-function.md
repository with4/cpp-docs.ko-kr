---
title: "ActivationFactoryCallback 함수 | Microsoft Docs"
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
  - "module/Microsoft::WRL::Details::ActivationFactoryCallback"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivationFactoryCallback 함수"
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActivationFactoryCallback 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(  
   HSTRING activationId,  
   IActivationFactory **ppFactory  
);  
```  
  
#### 매개 변수  
 `activationId`  
 런타임 클래스 이름을 지정하는 문자열을 처리 합니다.  
  
 `ppFactory`  
 이 작업이 완료될 때, 매개변수 `activationId` 에 해당하는 정품인증 팩터리.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 설명 하는 HRESULT입니다.  거의 실패인 HRESULT는 CLASS\_E\_CLASSNOTAVAILABLE와 E\_INVALIDARG입니다.  
  
## 설명  
 지정된 정품 인증 id는 정품 인증 팩터리를 가져옵니다.  
  
 Windows 런타임은 런타임 클래스 이름을 사용하여 지정된 개체를 요청하기 위해 이 콜백 함수를 호출 합니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)