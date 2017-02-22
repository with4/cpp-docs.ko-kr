---
title: "_WAIT_CHILD, _WAIT_GRANDCHILD | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_WAIT_GRANDCHILD"
  - "WAIT_CHILD"
  - "WAIT_GRANDCHILD"
  - "_WAIT_CHILD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_WAIT_CHILD 상수"
  - "_WAIT_GRANDCHILD 상수"
  - "WAIT_CHILD 상수"
  - "WAIT_GRANDCHILD 상수"
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# _WAIT_CHILD, _WAIT_GRANDCHILD
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
#include <process.h>  
  
```  
  
## 설명  
 `_cwait` 함수는 다른 프로세스를 대기하는 프로세스에서 사용할 수 있습니다. \(프로세스 ID가 알려진 경우\)  동작 인수는 다음 값 중 하나가 될 수 있습니다.  
  
|상수|의미|  
|--------|--------|  
|`_WAIT_CHILD`|호출 프로세스는 지정된 새 프로세스가 종료될 때까지 대기합니다.|  
|`_WAIT_GRANDCHILD`|프로세스 호출은 지정된 새 프로세스 및 해당 새 프로세스에 의해 생성된 모든 프로세스가 종료될 때까지 대기합니다.|  
  
## 참고 항목  
 [\_cwait](../c-runtime-library/reference/cwait.md)   
 [전역 상수](../c-runtime-library/global-constants.md)