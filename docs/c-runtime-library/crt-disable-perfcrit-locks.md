---
title: "_CRT_DISABLE_PERFCRIT_LOCKS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_CRT_DISABLE_PERFCRIT_LOCKS"
  - "CRT_DISABLE_PERFCRIT_LOCKS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CRT_DISABLE_PERFCRIT_LOCKS 상수"
  - "CRT_DISABLE_PERFCRIT_LOCKS 상수"
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _CRT_DISABLE_PERFCRIT_LOCKS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

I\/O 작업에서 성능이 중요한 잠금을 해제 합니다.  
  
## 구문  
  
```  
#define _CRT_DISABLE_PERFCRIT_LOCKS  
```  
  
## 설명  
 이 기호는 모든 I\/O 작업을 단일 스레드 I\/O 모델로 가정 하여 I\/O 바인딩된 단일 스레드 프로그램의 성능을 향상 시킬 수 있습니다.  자세한 내용은 [다중 스레드 라이브러리 성능](../c-runtime-library/multithreaded-libraries-performance.md)을 참조하십시오.  
  
## 참고 항목  
 [전역 상수](../c-runtime-library/global-constants.md)