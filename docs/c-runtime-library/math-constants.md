---
title: "Math 상수 | Microsoft Docs"
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
  - "c.constants"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_USE_MATH_DEFINES 상수"
  - "상수, 수학"
  - "M_1_PI 상수"
  - "M_2_PI 상수"
  - "M_2_SQRTPI 상수"
  - "M_E 상수"
  - "M_LN10 상수"
  - "M_LN2 상수"
  - "M_LOG10E 상수"
  - "M_LOG2E 상수"
  - "M_PI 상수"
  - "M_PI_2 상수"
  - "M_PI_4 상수"
  - "M_SQRT1_2 상수"
  - "M_SQRT2 상수"
  - "수학 상수"
  - "USE_MATH_DEFINES 상수"
ms.assetid: db533c3f-6ae8-4520-9d35-c8fabbef3529
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Math 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
#define _USE_MATH_DEFINES // for C++  
#include <cmath>  
  
#define _USE_MATH_DEFINES // for C  
#include <math.h>  
```  
  
## 설명  
 지정된 식의 값에 대한 다음 기호를 정의합니다.  
  
|기호|식|값|  
|--------|-------|-------|  
|M\_E|e|2.71828182845904523536|  
|M\_LOG2E|log2\(e\)|1.44269504088896340736|  
|M\_LOG10E|log10\(e\)|0.434294481903251827651|  
|M\_LN2|ln\(2\)|0.693147180559945309417|  
|M\_LN10|ln\(10\)|2.30258509299404568402|  
|M\_PI|pi|3.14159265358979323846|  
|M\_PI\_2|pi\/2|1.57079632679489661923|  
|M\_PI\_4|pi\/4|0.785398163397448309616|  
|M\_1\_PI|1\/pi|0.318309886183790671538|  
|M\_2\_PI|2\/pi|0.636619772367581343076|  
|M\_2\_SQRTPI|2\/sqrt\(pi\)|1.12837916709551257390|  
|M\_SQRT2|sqrt\(2\)|1.41421356237309504880|  
|M\_SQRT1\_2|1\/sqrt\(2\)|0.707106781186547524401|  
  
 Math 상수는 표준 C\/C\+\+에서 정의되지 않습니다.  이것을 사용 하려면, 먼저 `_USE_MATH_DEFINES`을 정의해야하고 그 다음 cmath 또는 math.h를 추가합니다.  
  
 프로젝트가 릴리스 모드에서 빌드될 때, 파일 ATLComTime.h.는 math.h를 포함합니다.  만일 ATLComTime.h를 포함 하는 프로젝트에서 math 상수 중 하나 이상을 사용하는 경우, ATLComTime.h을 포함하기 전에 `_USE_MATH_DEFINES` 을 정의해야 합니다.  
  
## 참고 항목  
 [전역 상수](../c-runtime-library/global-constants.md)