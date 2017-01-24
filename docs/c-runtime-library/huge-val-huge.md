---
title: "HUGE_VAL, _HUGE | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_HUGE"
apilocation: 
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_HUGE"
  - "HUGE_VAL"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_HUGE 상수"
  - "HUGE_VAL 상수"
  - "double 값"
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# HUGE_VAL, _HUGE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
#include <math.h>  
  
```  
  
## 설명  
 `HUGE_VAL` 는 표현할 수 있는 가장 큰 double 값입니다.  오류가 발생 하면 값이 다양한 런타임 수학 함수에 의해 반환 됩니다.  일부 함수에 대해\-`HUGE_VAL` 가 반환 됩니다.  `HUGE_VAL` 는 `_HUGE` 로 정의되지만 런타임 수학 함수는 `HUGE_VAL` 를 반환합니다.  또한 일관성을 위해 `HUGE_VAL` 를 사용해야 합니다.  
  
## 참고 항목  
 [전역 상수](../c-runtime-library/global-constants.md)