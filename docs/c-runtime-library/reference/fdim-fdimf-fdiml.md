---
title: "fdim, fdimf, fdiml | Microsoft Docs"
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
  - "fdim"
  - "fdimf"
  - "fdiml"
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
  - "fdim"
  - "fdimf"
  - "fdiml"
  - "math/fdim"
  - "math/fdimf"
  - "math/fdiml"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "fdim 함수"
  - "fdimf 함수"
  - "fdiml 함수"
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fdim, fdimf, fdiml
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

첫 번째 및 두 번째 값 사이의 양의 차이 확인 합니다.  
  
## 구문  
  
```  
double fdim(  
   double x,   
   double y  
);  
  
float fdim(  
   float x,   
   float y  
); //C++ only  
  
long double fdim(  
   long double x,   
   long double y  
); //C++ only  
  
float fdimf(  
   float x,   
   float y  
);  
  
long double fdiml(  
   long double x,   
   long double y  
);  
  
```  
  
#### 매개 변수  
 \[in\] `x`  
 첫 번째 값입니다.  
  
 \[in\] `y`  
 두 번째 값입니다.  
  
## 반환 값  
 사이의 양의 차이 반환 `x` 및 `y`:  
  
|반환 값|시나리오|  
|----------|----------|  
|x\-y|경우 x \> y|  
|0|경우 x \< \= y|  
  
 그렇지 않은 경우 반환할 수 있습니다 다음 오류 중 하나:  
  
|문제|반환|  
|--------|--------|  
|오버플로 범위 오류|\+ HUGE\_VAL, \+ HUGE\_VALF, 또는 \+ HUGE\_VALL|  
|언더플로 범위 오류|올바른 값 \(반올림\) 한 후|  
|`x` 또는 `y` nan|NaN|  
  
 오류를 보고에 지정 된 대로 [\_matherr](../../c-runtime-library/reference/matherr.md)합니다.  
  
## 주의  
 C \+ \+에서는 오버 로드를 허용 하므로의 오버 로드를 호출할 수 있습니다 `fdim` 및 float 및 long double 형식을 반환 하 합니다. C 프로그램에서 `fdim` 항상 걸리고 double 값을 반환 합니다.  
  
 NaN 처리를 제외 하 고이 함수는 동일 [fmax, fmaxf, fmaxl](../../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)\(`x`\-`y,` 0\).  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`fdim`, `fdimf`,  `fdiml`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmax, fmaxf, fmaxl](../../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)   
 [abs, labs, llabs \_abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)