---
title: "ChainInterfaces::FillArrayWithIid 메서드 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::ChainInterfaces::FillArrayWithIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FillArrayWithIid 메서드"
ms.assetid: f1ce699c-dfb6-40a9-9ea0-e6703d3cf971
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ChainInterfaces::FillArrayWithIid 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 인터페이스 IDs의 배열에서 지정된 위치에서 `I0` 템플릿 매개변수에 의해 정의된 인터페이스 ID를 저장합니다.  
  
## 구문  
  
```  
__forceinline static void FillArrayWithIid(  
   _Inout_ unsigned long &index,  
   _In_ IID* iids  
);  
```  
  
#### 매개 변수  
 `index`  
 `iids` 배열에서 인덱스 값에 대한 포인터.  
  
 `iids`  
 인터페이스 ID의 배열입니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ChainInterfaces 구조체](../windows/chaininterfaces-structure.md)