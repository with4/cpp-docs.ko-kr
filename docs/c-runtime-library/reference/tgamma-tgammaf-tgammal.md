---
title: "tgamma, tgammaf, tgammal | Microsoft Docs"
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
  - "tgamma"
  - "tgammaf"
  - "tgammal"
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
  - "tgamma"
  - "tgammaf"
  - "tgammal"
  - "math/tgamma"
  - "math/tgammaf"
  - "math/tgammal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tgamma 함수"
  - "tgammaf 함수"
  - "tgammal 함수"
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# tgamma, tgammaf, tgammal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 된 값의 감마 함수를 결정합니다.  
  
## 구문  
  
```  
double tgamma(  
   double x  
);  
  
float tgamma(  
   float x  
); //C++ only  
  
long double tgamma(  
   long double x  
); //C++ only  
  
float tgammaf(  
   float x  
);  
  
long double tgammal(  
   long double x  
);  
  
```  
  
#### 매개 변수  
 \[in\] `x`  
 값의 감마 찾을입니다.  
  
## 반환 값  
 성공 하면 반환의 감마 `x`합니다.  
  
 범위 오류가 발생할 수 있습니다의 크기가 `x` 너무 크거나 너무 작은 데이터 형식에 대 한 합니다. 도메인 오류 또는 범위 오류 경우 발생할 수 있습니다 `x` \< \= 0입니다.  
  
|문제|반환|  
|--------|--------|  
|x \= ±0|±INFINITY|  
|x \= 음의 정수|NaN|  
|x \=\-무한대|NaN|  
|x \= \+ INFINITY|\+ INFINITY|  
|x \= NaN|NaN|  
|도메인 오류|NaN|  
|극 오류|±HUGE\_VAL, ±HUGE\_VALF, 또는 ±HUGE\_VALL|  
|오버플로 범위 오류|±HUGE\_VAL, ±HUGE\_VALF, 또는 ±HUGE\_VALL|  
|언더플로 범위 오류|반올림 한 후 올바른 값입니다.|  
  
 오류를 보고에 지정 된 대로 [\_matherr](../../c-runtime-library/reference/matherr.md)합니다.  
  
## 주의  
 C \+ \+에서는 오버 로드를 허용 하므로 하 고 float 및 long double 형식을 반환 하는 tgamma의 오버 로드를 호출할 수 있습니다. C 프로그램에서 tgamma는 항상 사용 하 고 double 값을 반환 합니다.  
  
 X가 자연 수 인 경우이 함수는 \(x\-1\)의 계승값을 반환 합니다.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`tgamma`, `tgammaf`,  `tgammal`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [lgamma, lgammaf, lgammal](../../c-runtime-library/reference/lgamma-lgammaf-lgammal.md)