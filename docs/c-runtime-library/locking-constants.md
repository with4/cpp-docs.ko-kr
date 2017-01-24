---
title: "_locking 상수 | Microsoft Docs"
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
  - "_LK_RLCK"
  - "_LK_NBLCK"
  - "_LK_LOCK"
  - "_LK_NBRLCK"
  - "_LK_UNLCK"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_LK_LOCK 상수"
  - "_LK_NBLCK 상수"
  - "_LK_NBRLCK 상수"
  - "_LK_RLCK 상수"
  - "_LK_UNLCK 상수"
  - "LK_LOCK 상수"
  - "LK_NBLCK 상수"
  - "LK_NBRLCK 상수"
  - "LK_RLCK 상수"
  - "LK_UNLCK 상수"
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _locking 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
#include <sys/locking.h>  
  
```  
  
## 설명  
 `_locking` 함수를 호출하는 것에서 *mode* 인수는 수행되는 닫힌 작업을 지정합니다.  
  
 *모드* 는 다음 매니페스트 상수 중 하나여야 합니다.  
  
 `_LK_LOCK`  
 지정된 바이트를 잠급니다.  바이트를 잠글 수 없으면, 함수가 1 초 후에 다시 시도 합니다.  10 번 시도 후에도 바이트를 잠글 수 없는 경우, 함수는 오류를 반환 합니다.  
  
 `_LK_RLCK`  
 `_LK_LOCK`와 동일합니다.  
  
 `_LK_NBLCK`  
 지정된 바이트를 잠급니다.  바이트를 잠글 수 없는 경우, 함수는 오류를 반환합니다.  
  
 `_LK_NBRLCK`  
 `_LK_NBLCK`와 동일합니다.  
  
 `_LK_UNLCK`  
 지정된 바이트를 엽니다. \(바이트는 이전에 잠겨져야 합니다.\)  
  
## 참고 항목  
 [\_locking](../c-runtime-library/reference/locking.md)   
 [전역 상수](../c-runtime-library/global-constants.md)