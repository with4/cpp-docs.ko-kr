---
title: "discard_block_engine 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1.discard_block_engine"
  - "std.tr1.discard_block_engine"
  - "std::tr1::discard_block_engine"
  - "random/std::tr1::discard_block_engine"
  - "discard_block_engine"
  - "tr1::discard_block_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "discard_block_engine 클래스"
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
caps.latest.revision: 18
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# discard_block_engine 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본 엔진에서 반환된 값을 버려 임의의 시퀀스를 생성합니다.  
  
## 구문  
  
```  
template<class Engine, size_t P, size_t R> class discard_block_engine;  
```  
  
#### 매개 변수  
 `Engine`  
 기본 엔진 유형입니다.  
  
 `P`  
 **블록 크기**입니다.  각 블록에 있는 값의 수입니다.  
  
 `R`  
 **사용된 블록**입니다.  사용된 각 블록에 있는 값의 수입니다.  나머지는 버립니다\(`P` \- `R`\).  **사전 조건**: `0 < R ≤ P`  
  
## 멤버  
  
||||  
|-|-|-|  
|`discard_block_engine::discard_block_engine`|`discard_block_engine::base`|`discard_block_engine::discard`|  
|`discard_block_engine::operator()`|`discard_block_engine::base_type`|`discard_block_engine::seed`|  
  
 엔진 멤버에 대한 자세한 내용은 [\<random\>](../standard-library/random.md)을 참조하세요.  
  
## 설명  
 이 템플릿 클래스는 기본 엔진에서 반환하는 일부 값을 버려 값을 생성하는 엔진 어댑터에 대해 설명합니다.  
  
## 요구 사항  
 **헤더:** \<random\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<random\>](../standard-library/random.md)