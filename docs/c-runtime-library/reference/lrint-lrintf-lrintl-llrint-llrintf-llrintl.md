---
title: "lrint, lrintf, lrintl, llrint, llrintf, llrintl | Microsoft Docs"
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
  - "lrint"
  - "lrintl"
  - "lrintf"
  - "llrint"
  - "llrintf"
  - "llrintl"
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
  - "lrint"
  - "lrintf"
  - "lrintl"
  - "llrint"
  - "llrintf"
  - "llrintl"
  - "math/lrint"
  - "math/lrintf"
  - "math/lrintl"
  - "math/llrint"
  - "math/llrintf"
  - "math/llrintl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "lrint 함수"
  - "lrintf 함수"
  - "lrintl 함수"
  - "llrint 함수"
  - "llrintf 함수"
  - "llrintl 함수"
ms.assetid: 28ccd5b3-5e6f-434f-997d-a21d51b8ce7f
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# lrint, lrintf, lrintl, llrint, llrintf, llrintl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 반올림 모드 및 방향을 사용 하 여 지정된 된 부동 소수점 값을 가장 가까운 정수 값을 반올림 합니다.  
  
## 구문  
  
```  
long int lrint(  
   double x  
);  
  
long int lrint(  
   float x  
); //C++ only  
  
long int lrint(  
   long double x  
); //C++ only  
  
long int lrintf(  
   float x  
);  
  
long int lrintl(  
   long double x  
);  
  
long long int llrint(  
   double x  
);  
  
long long int llrint(  
   float x  
); //C++ only  
  
long long int llrint(  
   long double x  
); //C++ only  
  
long long int llrintf(  
   float x  
);  
  
long long int llrintl(  
   long double x  
);  
  
```  
  
#### 매개 변수  
 \[in\] `x`  
 반올림할 값입니다.  
  
## 반환 값  
 성공 하는 경우의 반올림된 한 정수 계열 값을 반환 합니다. `x`합니다.  
  
|문제|반환|  
|--------|--------|  
|`x` 반환 형식의 범위를 벗어났습니다.<br /><br /> `x` \= ±∞<br /><br /> `x` \= NaN|FE\_INVALID 발생 하 고 영 \(0\)를 반환 합니다.|  
  
## 주의  
 C \+ \+에서는 오버 로드를 허용 하므로의 오버 로드를 호출할 수 있습니다 `lrint` 및 `llrint` 인수로 float 및 long double 유형입니다. C 프로그램에서 `lrint` 및 `llrint` 항상 double을 수행 합니다.  
  
 경우 `x` 해당 하는 부동 소수점을 나타내지 않는 이러한 함수는 정수 계열 값의 FE\_INEXACT을 발생 시킵니다.  
  
 **Microsoft 전용**: 반환 값은 정의 된 구현 결과 반환 형식으로의 범위를 벗어나는 또는 매개 변수는 NaN 또는 무한 합니다. Microsoft 컴파일러는 \(0\) 값이 0을 반환합니다.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`lrint`, `lrintf`, `lrintl`, `llrint`, `llrintf`, `llrintl`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)