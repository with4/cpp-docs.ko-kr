---
title: "fmax, fmaxf, fmaxl | Microsoft Docs"
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
  - "fmax"
  - "fmaxf"
  - "fmaxl"
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
  - "fmax"
  - "fmaxf"
  - "fmaxl"
  - "math/fmax"
  - "math/fmaxf"
  - "math/fmaxl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fmax 함수"
  - "fmaxf 함수"
  - "fmaxl 함수"
ms.assetid: a773ccf7-495e-4a9a-8c6d-dfb53e341e35
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# fmax, fmaxf, fmaxl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정 된 두 숫자 값 중 더 큰 숫자를 확인 합니다.  
  
## 구문  
  
```  
double fmax(  
   double x,   
   double y  
);  
  
float fmax(  
   float x,   
   float y  
); //C++ only  
  
long double fmax(  
   long double x,   
   long double y  
); //C++ only  
  
float fmaxf(  
   float x,   
   float y  
);  
  
long double fmaxl(  
   long double x,   
   long double y  
);  
  
```  
  
#### 매개 변수  
 \[in\] `x`  
 비교할 첫 번째 값입니다.  
  
 \[in\] `y`  
 비교할 두 번째 값입니다.  
  
## 반환 값  
 성공 하면 반환 중 더 큰 `x` 또는 `y`합니다. 반환 되는 값을 정확 하 게 이며 반올림의 모든 형태에 종속 되지 않습니다.  
  
 그렇지 않은 경우 반환할 수 있습니다 다음 값 중 하나:  
  
|문제|반환|  
|--------|--------|  
|`x` \= NaN|`y`|  
|`y` \= NaN|`x`|  
|`x` 및 `y` \= NaN|NaN|  
  
 이 함수에 지정 된 오류를 사용 하지 않는  [\_matherr](../../c-runtime-library/reference/matherr.md)합니다.  
  
## 주의  
 C \+ \+에서는 오버 로드를 허용 하므로 하 고 float 및 long double 형식을 반환 하는 fmax의 오버 로드를 호출할 수 있습니다. C 프로그램에서 fmax는 항상 사용 하 고 double 값을 반환 합니다.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`fmax`, `fmaxf`, `fmaxl`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmin, fminf, fminl](../Topic/fmin,%20fminf,%20fminl1.md)