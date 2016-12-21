---
title: "erf, erff, erfl, erfc, erfcf, erfcl | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "erff"
  - "erfl"
  - "erf"
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
  - "erfl"
  - "erf"
  - "erff"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erf 함수"
  - "erff 함수"
  - "erfl 함수"
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# erf, erff, erfl, erfc, erfcf, erfcl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

값의 오차 함수 또는 보상 오차 함수를 계산합니다.  
  
## 구문  
  
```  
double erf(    double x ); float erf(    float x ); // C++ only long double erf(    long double x ); // C++ only float erff(    float x ); long double erfl(    long double x ); double erfc(    double x ); float erfc(    float x ); // C++ only long double erfc(    long double x ); // C++ only float erfcf(    float x ); long double erfcl(    long double x );  
```  
  
#### 매개 변수  
 `x`  
 부동 소수점 값입니다.  
  
## 반환 값  
 `erf` 함수는 `x`의 가우스 오차 함수를 반환합니다.  `erfc` 함수는 `x`의 가우스 보상 오차 함수를 반환합니다.  
  
## 설명  
 `erf` 함수는 다음과 같이 정의되는 x의 가우스 오차 함수를 계산합니다.  
  
 ![x의 오차 함수](../../c-runtime-library/reference/media/crt_erf_formula.png "CRT\_erf\_formula")  
  
 가우스 보상 오차 함수는 1 \- erf\(x\)로 정의됩니다.  `erf` 함수는 \-1.0~1.0 범위의 값을 반환합니다.  반환되는 오류가 없습니다.  `erfc` 함수는 0~2 범위의 값을 반환합니다.  `x`가 `erfc`에 대해 너무 크면 `errno` 변수가 `ERANGE`로 설정되어 있습니다.  
  
 C\+\+에서는 오버로드를 허용하므로 `float` 및 `long double` 형식을 사용 및 반환하는 `erf` 및 `erfc`의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `erf` 및 `erfc`는 항상 `double`을 사용하고 반환합니다.  
  
## 요구 사항  
  
|함수|필수 헤더|  
|--------|-----------|  
|`erf`, `erff`, `erfl`, `erfc`, `erfcf`, `erfcl`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)