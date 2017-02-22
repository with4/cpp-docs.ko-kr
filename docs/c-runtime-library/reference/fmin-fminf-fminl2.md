---
title: "fmin, fminf, fminl2 | Microsoft Docs"
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
  - "fmin"
  - "fminf"
  - "fminl"
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
  - "fmin"
  - "fminf"
  - "fminl"
  - "math/fmin"
  - "math/fminf"
  - "math/fminl"
helpviewer_keywords: 
  - "fmin 함수"
  - "fminf 함수"
  - "fminl 함수"
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# fmin, fminf, fminl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정 된 두 값 중 더 작은 숫자를 결정합니다.  
  
## 구문  
  
```  
double fmin(  
   double x,   
   double y  
);  
  
float fmin(  
   float x,   
   float y  
); //C++ only  
  
long double fmin(  
   long double x,   
   long double y  
); //C++ only  
  
float fminf(  
   float x,   
   float y  
);  
  
long double fminl(  
   long double x,   
   long double y  
);  
  
```  
  
#### 매개 변수  
 `x`  
 비교할 첫 번째 값입니다.  
  
 `y`  
 비교할 두 번째 값입니다.  
  
## 반환 값  
 성공 하면 반환 중 더 작은 `x` 또는 `y`합니다.  
  
|입력|결과|  
|--------|--------|  
|`x` 가 NaN|`y`|  
|`y` 가 NaN|`x`|  
|`x` 및 `y` NaN은|nan|  
  
 함수는 발생 하지는 않지만 [\_matherr](../../c-runtime-library/reference/matherr.md) 를 호출할 수 있는 부동 소수점 예외를 발생 시킬 또는 값을 변경 `errno`합니다.  
  
## 주의  
 C \+ \+에서는 오버 로드를 허용 하므로의 오버 로드를 호출할 수 있습니다 `fmin` 및 float 및 long double 형식을 반환 하 합니다. C 프로그램에서 `fmin` 항상 걸리고 double 값을 반환 합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`fmin`, `fminf`,  `fminl`|C: \< h. h \><br /><br /> C \+ \+: \< h. h \> 또는 \< cmath \>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)