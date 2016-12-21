---
title: "RuntimeClass::GetTrustLevel 메서드 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::RuntimeClass::GetTrustLevel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetTrustLevel 메서드"
ms.assetid: bd90407e-6dd7-41c3-9ea0-c402c276014a
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClass::GetTrustLevel 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 RuntimeClass 개체의 신뢰 수준을 가져옵니다.  
  
## 구문  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
## 매개 변수  
 `trustLvl`  
 이 작업 완료 시, 현재 Runtime클래스 개체의 신뢰 수준입니다.  
  
## 반환 값  
 항상 S\_OK입니다.  
  
## 설명  
 \_\_WRL\_STRICT\_\_or \_\_WRL\_FORCE\_INSPECTABLE\_CLASS\_MACRO\_\_ 정의 되지 않은 경우 어설션 오류가 생성 됩니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [RuntimeClass 클래스](../windows/runtimeclass-class.md)