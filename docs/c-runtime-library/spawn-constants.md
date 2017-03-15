---
title: "spawn 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_P_NOWAIT"
  - "_P_OVERLAY"
  - "_P_WAIT"
  - "_P_DETACH"
  - "_P_NOWAITO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_P_DETACH 상수"
  - "_P_NOWAIT 상수"
  - "_P_NOWAITO 상수"
  - "_P_OVERLAY 상수"
  - "_P_WAIT 상수"
  - "P_DETACH 상수"
  - "P_NOWAIT 상수"
  - "P_NOWAITO 상수"
  - "P_OVERLAY 상수"
  - "P_WAIT 상수"
  - "spawn 상수"
ms.assetid: e0533e88-d362-46fc-b53c-5f193226d879
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# spawn 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
#include <process.h>  
```  
  
## 설명  
 `mode` 인수는 작업이 수행되는 동안 호출 프로세스의 작업을 얻도록 결정합니다.  `mode` 에 대해 다음 값을 가질 수 있습니다.  
  
|상수|의미|  
|--------|--------|  
|`_P_OVERLAY`|오버레이 호출 프로세스는 새 프로세스, 호출 프로세스 파괴를 사용합니다.\(`_exec` 호출과 같은 효과\)|  
|`_P_WAIT`|새 프로세스의 실행이 완료될때 까지 호출 스레드를 일시 중단합니다.\(동기적 `_spawn`\)|  
|`_P_NOWAIT`, `_P_NOWAITO`|호출 프로세스와 새 프로세스를 동시에 실행합니다.\(비동기 `_spawn`\)|  
|`_P_DETACH`|호출 프로세스를 계속 실행합니다; 새 프로세스는 콘솔이나 키보드에서 액세스없이 백그라운드에서 실행됩니다.  새 프로세스에 대하여 `_cwait` 의 호출이 실패합니다.  이 작업은 비동기 작업이므로 `_spawn` 입니다.|  
  
## 참고 항목  
 [\_spawn, \_wspawn 함수](../c-runtime-library/spawn-wspawn-functions.md)   
 [전역 상수](../c-runtime-library/global-constants.md)