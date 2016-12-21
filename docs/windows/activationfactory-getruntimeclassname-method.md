---
title: "ActivationFactory::GetRuntimeClassName 메서드 | Microsoft Docs"
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
  - "module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRuntimeClassName 메서드"
ms.assetid: 74e34f0a-9c51-4b40-89f5-45c6c5886ece
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActivationFactory::GetRuntimeClassName 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 ActivationFactory 인스턴스화하는 개체의 런타임 클래스 이름을 가져옵니다.  
  
## 구문  
  
```  
STDMETHOD(  
   GetRuntimeClassName  
)(_Out_ HSTRING* runtimeName);  
```  
  
#### 매개 변수  
 `runtimeName`  
 이 작업 완료 시, 현재 ActivationFactory 인스턴스화하는 개체의 런타임 클래스 이름을 포함하는 문자열에 대한 핸들입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 설명 하는 HRESULT입니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ActivationFactory 클래스](../windows/activationfactory-class.md)