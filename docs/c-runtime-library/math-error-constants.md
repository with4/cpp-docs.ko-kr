---
title: "수학 오류 상수 | Microsoft Docs"
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
  - "_PLOSS"
  - "_UNDERFLOW"
  - "_TLOSS"
  - "_SING"
  - "_DOMAIN"
  - "_OVERFLOW"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_DOMAIN 상수"
  - "_OVERFLOW 상수"
  - "_PLOSS 상수"
  - "_SING 상수"
  - "_TLOSS 상수"
  - "_UNDERFLOW 상수"
  - "DOMAIN 상수"
  - "수학 오류 상수"
  - "OVERFLOW 상수"
  - "PLOSS 상수"
  - "SING 상수"
  - "TLOSS 상수"
  - "UNDERFLOW 상수"
ms.assetid: 4be933a6-674e-45a5-8ac9-090023542f5b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 수학 오류 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
#include <math.h>  
  
```  
  
## 설명  
 런타임 라이브러리의 수학 루틴은 수학 오류 상수를 생성할 수 있습니다.  
  
 이러한 오류는 다음과 같이 MATH.H에서 정의된 예외 형식에 해당하며 수학 오류가 발생할 때 `_matherr` 함수에 의해서 반환됩니다.  
  
|상수|의미|  
|--------|--------|  
|`_DOMAIN`|함수의 인수는 함수의 외부 도메인입니다.|  
|`_OVERFLOW`|함수의 반환 형식으로 표현하기에는 결과가 너무 큽니다.|  
|`_PLOSS`|중요 부분 손실이 발생했습니다.|  
|`_SING`|인수 이상 : 함수의 인수 값이 잘못되었습니다. \(예를 들어, 0이 아닌 값이 필요한 함수에 0이 전달되었습니다.\)|  
|`_TLOSS`|중요 전체 손실이 발생했습니다.|  
|`_UNDERFLOW`|결과가 너무 작아 나타낼 수 없습니다.|  
  
## 참고 항목  
 [\_matherr](../c-runtime-library/reference/matherr.md)   
 [전역 상수](../c-runtime-library/global-constants.md)