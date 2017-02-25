---
title: "ActivationFactory::GetTrustLevel 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ActivationFactory::GetTrustLevel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetTrustLevel 메서드"
ms.assetid: 31547ae6-d2ab-4039-923c-154d53fb1a8b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ActivationFactory::GetTrustLevel 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 ActivationFactory 인스턴스화하는 개체의 신뢰 수준을 가져옵니다.  
  
## 구문  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### 매개 변수  
 `trustLvl`  
 이 작업 완료 시 런타임 클래스를 인스턴스화하는 ActivationFactory의 신뢰 수준입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 어설션 오류가 발생하고 `trustLvl` FullTrust로 설정 됩니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ActivationFactory 클래스](../windows/activationfactory-class.md)