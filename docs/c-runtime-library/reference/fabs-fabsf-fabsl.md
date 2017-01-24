---
title: "fabs, fabsf, fabsl | Microsoft Docs"
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
  - "fabsf"
  - "fabs"
  - "fabsl"
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
  - "fabs"
  - "fabsf"
  - "fabsl"
  - "math\fabs"
  - "math\fabsf"
  - "math\fabsl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "절대 값"
  - "fabsf 함수"
  - "절대값 계산"
  - "fabs 함수"
  - "fabsl 함수"
ms.assetid: 23bca210-f408-4f5e-b46b-0ccaaec31e36
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fabs, fabsf, fabsl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 인수의 절대값을 계산합니다.  
  
## 구문  
  
```  
double fabs(   
   double x   
);  
float fabs(  
   float x   
); // C++ only  
long double fabs(  
   long double x  
); // C++ only  
float fabsf(   
   float x   
);  
long double fabsl(  
   long double x  
);  
```  
  
#### 매개 변수  
 `x`  
 부동 소수점 값입니다.  
  
## 반환 값  
 `fabs` 인수의 절대 값을 반환 하는 함수 `x`합니다. 반환되는 오류가 없습니다.  
  
|입력|SEH 예외|Matherr 예외|  
|--------|------------|----------------|  
|± QNAN,IND|없음|\_DOMAIN|  
  
## 설명  
 C \+ \+ 오버 로드의 오버 로드를 호출할 수 있도록 허용 `fabs` \< cmath \> 헤더를 포함 하는 경우. C 프로그램에서 `fabs` 항상 걸리고 double 값을 반환 합니다.  
  
## 요구 사항  
  
|함수|필수 C 헤더|필수 c \+ \+ 헤더|  
|--------|-------------|-------------------|  
|`fabs`, `fabsf`, `fabsl`|\<math.h\>|\< cmath \> 또는 \< h. h \>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 예를 참조 [abs](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)합니다.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [abs, labs, llabs \_abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)   
 [\_cabs](../../c-runtime-library/reference/cabs.md)   
 [labs, llabs](../../misc/labs-llabs.md)