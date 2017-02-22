---
title: "expm1, expm1f, expm1l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "expm1l"
  - "expm1"
  - "expm1f"
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
  - "expm1l"
  - "expm1"
  - "expm1f"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "expm1 함수"
  - "expm1f 함수"
  - "expm1l 함수"
ms.assetid: 2a4dd2d9-370c-42b0-9067-0625efa272e0
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# expm1, expm1f, expm1l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

값의 밑이 e인 지수 값에서 1을 빼서 계산합니다.  
  
## 구문  
  
```  
double expm1(   
   double x   
);  
float expm1(  
   float x  
);  // C++ only  
long double expm1(  
   long double x  
);  // C++ only  
float expm1f(  
   float x  
);  
long double expm1l(  
   long double x  
);  
```  
  
#### 매개 변수  
 `x`  
 부동 소수점 지수 값입니다.  
  
## 반환 값  
 `expm1` 함수는 성공 시 e<sup>x</sup> – 1을 나타내는 부동 소수점 값을 반환합니다.  오버플로 시 `expm1`은 `HUGE_VAL`, `expm1f`는 `HUGE_VALF`, `expm1l`은 `HUGE_VALL`을 반환하고, `errno`는 `ERANGE`로 설정됩니다.  반환 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하십시오.  
  
## 설명  
 C\+\+가 오버로딩을 허용하기 때문에 `float`와 `long double`값을 사용하고 반환하는 `expm1`의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `expm1`는 항상 `double`을 사용하고 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`expm1`, `expm1f`, `expm1l`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [exp2, exp2f, exp2l](http://msdn.microsoft.com/ko-kr/a7974629-be1e-4196-a562-6624a0732003)   
 [pow, powf, powl](../../c-runtime-library/reference/pow-powf-powl.md)