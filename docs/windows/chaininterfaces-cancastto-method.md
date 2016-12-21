---
title: "ChainInterfaces::CanCastTo 메서드 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::ChainInterfaces::CanCastTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanCastTo 메서드"
ms.assetid: 8be44875-53ed-494b-91a0-0f8e399685bb
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ChainInterfaces::CanCastTo 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 인터페이스 ID를 비 기본 탬플릿 매개변수에 의해 정의된 각각의 특수화를 캐스팅할 수 있는지 여부를 나타냅니다.  
  
## 구문  
  
```  
__forceinline bool CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### 매개 변수  
 `riid`  
 인터페이스 ID  
  
 `ppv`  
 마지막으로 성공적으로 캐스팅 된 인터페이스 ID에 대한 포인터입니다.  
  
## 반환 값  
 모든 캐스팅 작업이 성공하면 `true`, 그렇지 않으면 `false`.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ChainInterfaces 구조체](../windows/chaininterfaces-structure.md)