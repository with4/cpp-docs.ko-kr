---
title: "ceil, ceilf, ceill | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "ceilf"
  - "ceil"
  - "ceill"
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
  - "ceil"
  - "ceilf"
  - "ceill"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "천장 값 계산"
  - "ceil 함수"
  - "ceilf 함수"
  - "ceill 함수"
ms.assetid: f4e5acab-5c8f-4b10-9ae2-9561e6453718
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# ceil, ceilf, ceill
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

값의 최대를 계산 합니다.  
  
## 구문  
  
```  
double ceil(   
   double x   
);  
float ceil(  
   float x  
);  // C++ only  
long double ceil(  
   long double x  
);  // C++ only  
float ceilf(  
   float x  
);  
long double ceill(  
   long double x  
);  
```  
  
#### 매개 변수  
 `x`  
 부동 소수점 값.  
  
## 반환 값  
 이 `ceil` 함수는 `x` 이 같거나 더 큰 더 큰 정수를 표현하는 부동 소수점 값을 반환합니다.  반환되는 오류가 없습니다.  
  
|입력|SEH 예외|Matherr 예외|  
|--------|------------|----------------|  
|± `QNAN`,`IND`|없음|`_DOMAIN`|  
  
 `ceil` 스트리밍 SIMD 확장 2 \(SSE2\)을 사용하여구현을 했습니다.  정보 및 SSE2 구현을 사용하는 방법에 대한 제한 사항을 참조 하십시오. [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
## 설명  
 C \+ \+ 오버 로딩을 허용하기 때문에 오버 로드인 `ceil` 을 호출할 수 있습니다.  C 프로그램에서 `ceil` 는 항상 2배를 사용하고 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`ceil`, `ceilf`, `ceill`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
 이 [floor](../../c-runtime-library/reference/floor-floorf-floorl.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Math::Ceiling](https://msdn.microsoft.com/en-us/library/system.math.ceiling.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)