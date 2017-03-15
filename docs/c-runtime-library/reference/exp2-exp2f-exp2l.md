---
title: "exp2, exp2f, exp2l | Microsoft Docs"
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
  - "exp2"
  - "exp2f"
  - "exp2l"
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
  - "exp2"
  - "math/exp2"
  - "exp2f"
  - "math/exp2f"
  - "exp2l"
  - "math/exp2l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exp2 함수"
  - "exp2f 함수"
  - "exp2l 함수"
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# exp2, exp2f, exp2l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정 된 값 \(즉, 2ˣ\) 2를 계산 합니다.  
  
## 구문  
  
```  
double exp2(  
   double x  
);  
  
float exp2(  
   float x  
);  // C++ only  
  
long double exp2(  
   long double x  
); // C++ only  
  
float exp2f(  
   float x  
);  
  
long double exp2l(  
   long double x  
);  
  
```  
  
#### 매개 변수  
 \[in\] `x`  
 지 수의 값입니다.  
  
## 반환 값  
 성공 하는 경우의 밑이 2 인 지 수를 반환 `x` \(2ˣ\). 그렇지 않은 경우 반환할 수 있습니다 다음 값 중 하나:  
  
|문제|반환|  
|--------|--------|  
|`x` \= ±0|1|  
|`x` \=\-무한대|\+0|  
|`x` \= \+ INFINITY|\+ INFINITY|  
|`x` \= NaN|NaN|  
|오버플로 범위 오류|\+ HUGE\_VAL, \+ HUGE\_VALF, 또는 \+ HUGE\_VALL|  
|언더플로 범위 오류|올바른 결과 반올림 한 후|  
  
 오류를 보고에 지정 된 대로 [\_matherr](../../c-runtime-library/reference/matherr.md)합니다.  
  
## 주의  
 C \+ \+에서는 오버 로드를 허용 하므로의 오버 로드를 호출할 수 있습니다 `exp2` 및 float 및 long double 형식을 반환 하 합니다. C 프로그램에서 `exp2` 항상 걸리고 double 값을 반환 합니다.  
  
## 요구 사항  
  
|루틴|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`exp`, `expf`, `expl`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [exp, expf](../../c-runtime-library/reference/exp-expf.md)   
 [log2, log2f, log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)