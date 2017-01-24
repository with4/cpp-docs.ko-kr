---
title: "shuffle_order_engine 클래스 | Microsoft Docs"
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
  - "shuffle_order_engine"
  - "std.tr1.shuffle_order_engine"
  - "tr1::shuffle_order_engine"
  - "tr1.shuffle_order_engine"
  - "std::tr1::shuffle_order_engine"
  - "random/std::tr1::shuffle_order_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "shuffle_order_engine 클래스"
ms.assetid: 0bcd1fb0-44d7-4e59-bb1b-4a9b673a960d
caps.latest.revision: 17
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# shuffle_order_engine 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본 엔진에서 반환된 값을 다시 정렬하여 임의의 시퀀스를 생성합니다.  
  
## 구문  
  
```  
template<class Engine, size_t K>  
class shuffle_order_engine;  
```  
  
#### 매개 변수  
 `Engine`  
 기본 엔진 유형입니다.  
  
 `K`  
 **테이블 크기**입니다. 버퍼\(테이블\)에 있는 요소의 수입니다.**사전 조건**: `0 < K`  
  
## 멤버  
  
||||  
|-|-|-|  
|`shuffle_order_engine::shuffle_order_engine`|`shuffle_order_engine::base`|`shuffle_order_engine::discard`|  
|`shuffle_order_engine::operator()`|`shuffle_order_engine::base_type`|`shuffle_order_engine::seed`|  
  
 엔진 멤버에 대 한 자세한 내용은 참조 [\<random\>](../standard-library/random.md)합니다.  
  
## 설명  
 이 템플릿 클래스는 기본 엔진에서 반환하는 값을 다시 정렬하여 값을 생성하는 *엔진 어댑터*에 대해 설명합니다. 각 생성자는 기본 엔진에서 반환한 `K` 값으로 내부 테이블을 채우고 값이 요청되면 이 테이블에서 임의 요소가 선택됩니다.  
  
## 요구 사항  
 **헤더:** \<random\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<random\>](../standard-library/random.md)