---
title: "trunc, truncf truncl | Microsoft Docs"
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
  - "trunc"
  - "truncf"
  - "truncl"
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
  - "trunc"
  - "truncf"
  - "truncl"
  - "math/trunc"
  - "math/truncf"
  - "math/truncl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "trunc 함수"
  - "truncf 함수"
  - "truncl 함수"
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# trunc, truncf truncl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 된 부동 소수점 값 보다 작거나는 가장 가까운 정수를 결정 합니다.  
  
## 구문  
  
```  
double trunc(  
   double x  
);  
  
float trunc(  
   float x  
); //C++ only  
  
long double trunc(  
   long double x  
); //C++ only  
  
float trunc(  
   float x  
); //C++ only  
  
long double truncl(  
   long double x  
);  
  
```  
  
#### 매개 변수  
 \[in\] `x`  
 자를 값입니다.  
  
## 반환 값  
 성공 하는 경우의 정수 값을 반환 합니다. `x`, 0으로 반올림 합니다.  
  
 그렇지 않으면 수 있습니다 다음 중 하나를 반환 합니다.  
  
|문제|반환|  
|--------|--------|  
|`x` ±INFINITY \=|x|  
|`x` \=  ±0|x|  
|`x` \= NaN|NaN|  
  
 오류를 보고에 지정 된 대로 [\_matherr](../../c-runtime-library/reference/matherr.md)합니다.  
  
## 주의  
 C \+ \+에서는 오버 로드를 허용 하므로의 오버 로드를 호출할 수 있습니다 `trunc` 및 float 및 long double 형식을 반환 하 합니다. C 프로그램에서 `trunc` 항상 걸리고 double 값을 반환 합니다.  
  
 부동 소수점 값이 가장 큰 정확한 정수는 이기 때문에이 함수는 자체적으로 오버플로 하지 않습니다. 그러나 함수는 정수 형식으로 값을 반환 하 여 오버플로가 발생할 수 있습니다.  
  
 정수를 부동 소수점에서 암시적으로 변환 하 여 내림할 수도 있습니다. 그러나이 대상 형식으로 저장할 수 있는 값으로 제한입니다.  
  
## 요구 사항  
  
|함수|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`trunc`, `truncf`,  `truncl`|\<math.h\>|\<cmath\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)를 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)