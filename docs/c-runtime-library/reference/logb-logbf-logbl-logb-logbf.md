---
title: "logb, logbf, logbl, _logb, _logbf | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "logb"
  - "_logb"
  - "_logbl"
  - "logbf"
  - "logbl"
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
  - "logb"
  - "logbl"
  - "_logb"
  - "_logbf"
  - "logbf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_logb 함수"
  - "_logbf 함수"
  - "지수, 부동 소수점 숫자"
  - "지수 및 가수"
  - "부동 소수점 함수"
  - "부동 소수점 함수, 가수 및 지수"
  - "logb 함수"
  - "logbf 함수"
  - "logbl 함수"
  - "가수, 부동 소수점 변수"
ms.assetid: 780c4daa-6fe6-4fbc-9412-4c1ba1a1766f
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# logb, logbf, logbl, _logb, _logbf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 인수의 지수 값을 추출합니다.  
  
## 구문  
  
```  
double logb(  
   double x   
);  
float logb(  
   float x   
); // C++ only  
long double logb(  
   long double x   
); // C++ only   
float logbf(  
   float x   
);  
long double logbl(  
   long double x   
);  
double _logb(  
   double x   
);  
float _logbf(  
   float x   
);  
```  
  
#### 매개 변수  
 x  
 부동 소수점 값  
  
## 반환 값  
 `logb`은  `x` 의 비편향 값 지수를 반환합니다. 부동 소수점 값을 나타내는 부호 있는 정수입니다.  
  
## 설명  
 `logb` 함수는 부동 소수점 인수  `x` 의 지수 값을 추출합니다,  `x` 는 무한 범위를 사용하여 표현 했습니다.  인수  `x`  는 비 정규화된 경우, 표준화되어 있는 것 처럼 처리됩니다.  
  
 C\+\+가 오버로딩을 허용하기 때문에 `float` 또는 `long double` 값을 사용하고 반환하는 `logb`의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `logb`는 항상 `double`을 사용하고 반환합니다.  
  
|입력|SEH 예외|Matherr 예외|  
|--------|------------|----------------|  
|± QNAN,IND|없음|\_DOMAIN|  
|± 0|ZERODIVIDE|\_SING|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_logb`|\<float.h\>|  
|`logb`, `logbf`, `logbl`, `_logbf`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)