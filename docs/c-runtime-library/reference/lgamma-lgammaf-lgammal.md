---
title: "lgamma, lgammaf, lgammal | Microsoft Docs"
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
  - "lgamma"
  - "lgammaf"
  - "lgammal"
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
  - "lgamma"
  - "lgammaf"
  - "lgammal"
  - "math/lgamma"
  - "math/lgammaf"
  - "math/lgammal"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "lgamma 함수"
  - "lgammal 함수"
  - "lgammaf 함수"
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# lgamma, lgammaf, lgammal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 된 값의 감마 함수의 절대 값의 자연 로그를 확인합니다.  
  
## 구문  
  
```  
double lgamma(  
   double x  
);  
  
float lgamma(  
   float x  
); //C++ only  
  
long double lgamma(  
   long double x  
); //C++ only  
  
float lgammaf(  
   float x  
);  
  
long double lgammal(  
   long double x  
);  
  
```  
  
#### 매개 변수  
 \[in\] `x`  
 계산 값입니다.  
  
## 반환 값  
 성공 하는 경우의 절대 값의 감마 함수의 자연 로그를 반환 `x.`  
  
|문제|반환|  
|--------|--------|  
|`x` \= NaN|NaN|  
|`x` \= ±0|\+ INFINITY|  
|`x`음의 정수 \=|\+ INFINITY|  
|±INFINITY|\+ INFINITY|  
|극 오류|\+ HUGE\_VAL, \+ HUGE\_VALF, 또는 \+ HUGE\_VALL|  
|오버플로 범위 오류|±HUGE\_VAL, ±HUGE\_VALF, 또는 ±HUGE\_VALL|  
  
 오류를 보고에 지정 된 대로 [\_matherr](../../c-runtime-library/reference/matherr.md)합니다.  
  
## 주의  
 C \+ \+에서는 오버 로드를 허용 하므로의 오버 로드를 호출할 수 있습니다 `lgamma` 및 float 및 long double 형식을 반환 하 합니다. C 프로그램에서 `lgamma` 항상 걸리고 double 값을 반환 합니다.  
  
 X가 유리수 인 경우이 함수의 계승값의 로그를 반환 하는 \(`x`\-1\).  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`lgamma`, `lgammaf`,  `lgammal`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [tgamma, tgammaf, tgammal](../../c-runtime-library/reference/tgamma-tgammaf-tgammal.md)