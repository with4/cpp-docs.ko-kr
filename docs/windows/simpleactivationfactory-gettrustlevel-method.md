---
title: "SimpleActivationFactory::GetTrustLevel 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel"
dev_langs: 
  - "C++"
ms.assetid: 99aa9bc9-d954-4a6f-902b-4abe00e43039
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# SimpleActivationFactory::GetTrustLevel 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`Base` 클래스 탬플릿 매개변수에 의해 지정된 클래스의 인스턴스 신뢰 수준을 가져옵니다.  
  
## 구문  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### 매개 변수  
 `trustLvl`  
 이 작업 완료 시, 현재 클래스 개체의 신뢰 수준입니다.  
  
## 반환 값  
 항상 S\_OK입니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [SimpleActivationFactory 클래스](../windows/simpleactivationfactory-class.md)