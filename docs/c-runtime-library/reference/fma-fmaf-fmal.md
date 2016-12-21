---
title: "fma, fmaf fmal | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fma"
  - "fmaf"
  - "fmal"
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
  - "fma"
  - "fmaf"
  - "fmal"
  - "math/fma"
  - "math/fmaf"
  - "math/fmal"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "fma 함수"
  - "fmaf 함수"
  - "fmal 함수"
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fma, fmaf fmal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

두 값을 곱합니다, 그리고 세 번째 값을 추가 하 고 중간 반올림으로 인해 모든 정밀도 손실 없이 결과 반올림 합니다.  
  
## 구문  
  
```  
double fma(  
   double x,   
   double y,   
   double z  
);  
  
float fma(  
   float  x,   
   float  y,   
   float z  
); //C++ only  
  
long double fma(  
   long double  x,   
   long double  y,   
   long double z  
); //C++ only  
  
float fmaf(  
   float  x,   
   float  y,   
   float z  
);  
  
long double fmal(  
   long double  x,   
   long double  y,   
   long double z  
);  
  
```  
  
#### 매개 변수  
 \[in\] `x`  
 곱할 첫 번째 값입니다.  
  
 \[in\] `y`  
 곱할 두 번째 값입니다.  
  
 \[in\] `z`  
 추가할 값입니다.  
  
## 반환 값  
 Returns \(`x` ×    `y`\) \+ `z`. 반환 값은 다음 현재 반올림 형식을 사용 하 여 반올림 됩니다.  
  
 그렇지 않은 경우 반환할 수 있습니다 다음 값 중 하나:  
  
|문제|반환|  
|--------|--------|  
|`x` \= 무한대 `y` \= 0 또는<br /><br /> `x` \= 0, `y` 무한대 \=|NaN|  
|`x` 또는 `y` 정확한 ± 무한대 \= `z` 부호가 무한대 \=|NaN|  
|`x` 또는 `y` \= NaN|NaN|  
|없습니다 \(`x` \= 0, `y`정해 지지 않은 \=\) 및 `z` \= NaN<br /><br /> 없습니다 \(`x`무한 \= `y`\= 0\) 및 `z` \= NaN|NaN|  
|오버플로 범위 오류|±HUGE\_VAL, ±HUGE\_VALF, 또는 ±HUGE\_VALL|  
|언더플로 범위 오류|올바른 값을 반올림 한 후입니다.|  
  
 오류를 보고에 지정 된 대로 [\_matherr](../../c-runtime-library/reference/matherr.md)합니다.  
  
## 주의  
 C \+ \+에서는 오버 로드를 허용 하므로의 오버 로드를 호출할 수 있습니다 `fma` 및 float 및 long double 형식을 반환 하 합니다. C 프로그램에서 `fma` 항상 걸리고 double 값을 반환 합니다.  
  
 이 함수는 무한 정밀도로 수행 된 하 고 다음 최종 결과 반올림 처럼 값을 계산 합니다.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`fma`, `fmaf`,  `fmal`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [remainder, remainderf, remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)   
 [remquo, remquof, remquol](../../c-runtime-library/reference/remquo-remquof-remquol.md)