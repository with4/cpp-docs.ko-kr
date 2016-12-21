---
title: "RuntimeClass::DecrementReference 메서드 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::RuntimeClass::DecrementReference"
dev_langs: 
  - "C++"
ms.assetid: f5ecfeaa-2865-455b-9208-94a0685fd2c6
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClass::DecrementReference 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 RuntimeClass 개체의 참조 횟수를 감소시킵니다.  
  
## 구문  
  
```  
ULONG DecrementReference();  
```  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [RuntimeClass 클래스](../windows/runtimeclass-class.md)