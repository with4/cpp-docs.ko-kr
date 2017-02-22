---
title: "setvbuf 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_IOFBF"
  - "_IONBF"
  - "_IOLBF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_IOFBF 상수"
  - "_IOLBF 상수"
  - "_IONBF 상수"
  - "IOFBF 상수"
  - "IOLBF 상수"
  - "IONBF 상수"
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# setvbuf 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
#include <stdio.h>  
  
```  
  
## 설명  
 이러한 상수는 `setvbuf` 에대한 버퍼의 형식을 나타냅니다.  
  
 가능한 값은 다음 매니페이스 상수들로 제공됩니다.  
  
|상수|의미|  
|--------|--------|  
|`_IOFBF`|완전 버퍼링: 버퍼는 `setvbuf` 에 호출에서 지정되고 이것의 사이즈는 `setvbuf` 호출에서 지정됩니다.  만일 버퍼 포인터가 **NULL**이면, 자동으로 할당된 지정된 크기의 버퍼를 사용합니다.|  
|`_IOLBF`|`_IOFBF`와 동일합니다.|  
|`_IONBF`|호출 하는 인수에 관계 없이, `setvbuf` 로 호출됩니다.|  
  
## 참고 항목  
 [setbuf](../c-runtime-library/reference/setbuf.md)   
 [전역 상수](../c-runtime-library/global-constants.md)