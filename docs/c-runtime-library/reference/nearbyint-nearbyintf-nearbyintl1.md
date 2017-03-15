---
title: "nearbyint, nearbyintf, nearbyintl1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "nearbyint"
  - "nearbyintf"
  - "nerabyintl"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "nearbyint"
  - "nearbyintf"
  - "nearbyintl"
  - "math/nearbyint"
  - "math/narbyintf"
  - "math/narbyintl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nearbyint 함수"
  - "nearbyintf 함수"
  - "nearbyintl 함수"
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# nearbyint, nearbyintf, nearbyintl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 된 부동 소수점 값을 정수로 반올림 하 고 부동 소수점 형식에서 해당 값을 반환 합니다.  
  
## 구문  
  
```  
double nearbyint(  
   double x  
);  
  
float nearbyint(  
   float x  
); //C++ only  
  
long double nearbyint(  
   long double x  
); //C++ only  
  
float nearbyintf(  
   float x  
);  
  
long double nearbyintl(  
   long double x  
);  
  
```  
  
#### 매개 변수  
 \[in\] `x`  
 반올림할 값입니다.  
  
## 반환 값  
 성공 하면 반환 `x`, fegetround로 정의 된 현재 반올림 형식을 사용 하는 가장 가까운 정수로 반올림 합니다. 그렇지 않으면 함수에서 다음 값 중 하나를 반환할 수 있습니다.  
  
|문제|반환|  
|--------|--------|  
|`x` ±INFINITY \=|수정 되지 않은 상태로 ±INFINITY|  
|`x` \= ±0|수정 되지 않은 상태로 ±0|  
|`x` \= NaN|NaN|  
  
 통해 오류가 보고 되지 않습니다 [\_matherr](../../c-runtime-library/reference/matherr.md)특히이 함수는 모든 FE\_INEXACT 예외를 보고 하지 않습니다.  
  
## 주의  
 이 함수가 사이의 주요 차이점 및 `rint` 는이 함수는 정확 하지 않습니다 부동 소수점 예외가 발생 하지 않습니다.  
  
 최대 부동 소수점 값에는 정확한 정수는 이기 때문에이 함수는 되지 오버플로가 발생 했습니다. 자체로; 대신, 출력 반환 값을 사용 하는 함수의 버전에 따라 오버플로 일으킬 수 있습니다.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`nearbyint`, `nearbyintf`,  `nearbyintl`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)