---
title: "MakeAllocator::Allocate 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::MakeAllocator::Allocate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Allocate 메서드"
ms.assetid: a01997bc-4ff1-4ed0-9def-e4aaa15b0598
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# MakeAllocator::Allocate 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
__forceinline void* Allocate();  
```  
  
## 반환 값  
 성공 하면 할당된 메모리에 대한 포인터 그렇지 않으면 `nullptr`.  
  
## 설명  
 메모리를 할당하고 현재 MakeAllocator 개체와 연결합니다.  
  
 할당된 메모리의 크기는 현재 MakeAllocator 템플릿 매개 변수로 지정된 형식의 크기입니다.  
  
 개발자만 다른 메모리 할당 모델을 구현하려면 Allocate\(\) 메서드를 재정의 해야 합니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [MakeAllocator 클래스](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)