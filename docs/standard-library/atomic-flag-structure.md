---
title: "atomic_flag 구조체 | Microsoft Docs"
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
  - "atomic/std::atomic_flag"
dev_langs: 
  - "C++"
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
caps.latest.revision: 14
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# atomic_flag 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

설명 원자 단위로 설정하고 `bool` 플레그를 해제합니다.  원자 플래그에 대한 작업은 항상 잠금 해제 합니다.  
  
## 구문  
  
```  
struct atomic_flag;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[atomic\_flag::clear 메서드](../Topic/atomic_flag::clear%20Method.md)|저장된 `false` 플래그를 로 설정합니다.|  
|[atomic\_flag::test\_and\_set 메서드](../Topic/atomic_flag::test_and_set%20Method.md)|저장된 플래그 `true` 설정하고, 초기 플래그 값을 반환 합니다.|  
  
## 설명  
 `atomic_flag` 개체는 [atomic\_flag\_clear](../Topic/atomic_flag_clear%20Function.md), [atomic\_flag\_clear\_explicit](../Topic/atomic_flag_clear_explicit%20Function.md), [atomic\_flag\_test\_and\_set](../Topic/atomic_flag_test_and_set%20Function.md), 및 [atomic\_flag\_test\_and\_set\_explicit](../Topic/atomic_flag_test_and_set_explicit%20Function.md) non\-맴버 함수에 전달할 수 있습니다.  이 `ATOMIC_FLAG_INIT` 값을 사용하여 초기화할 수 있습니다.  
  
## 요구 사항  
 **헤더:** atomic  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<atomic\>](../standard-library/atomic.md)