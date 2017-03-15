---
title: "cos, cosf, cosl, cosh, coshf, coshl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "coshl"
  - "cosh"
  - "cos"
  - "cosl"
  - "cosf"
  - "coshf"
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
  - "coshl"
  - "cos"
  - "cosf"
  - "cosh"
  - "cosl"
  - "coshf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "코사인 계산"
  - "cos 함수"
  - "cosf 함수"
  - "cosh 함수"
  - "coshf 함수"
  - "coshl 함수"
  - "코사인"
  - "코사인, 계산"
  - "cosl 함수"
  - "하이퍼볼릭 함수"
  - "삼각 함수"
ms.assetid: ae90435e-6b68-4a47-a81f-be87d5c08f16
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# cos, cosf, cosl, cosh, coshf, coshl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

코사인\(`cos`, `cosf`, 혹은 `cosl`\), 혹은 쌍곡 코사인 \(`cosh`, `coshf`, 혹은 `coshl`\)을 계산합니다.  
  
## 구문  
  
```  
double cos(   
   double x   
);  
float cos(  
   float x   
);  // C++ only  
long double cos(  
   long double x  
);  // C++ only  
float cosf(   
   float x   
);  
long double cosl(  
   long double x  
);  
double cosh(   
   double x   
);  
float cosh(  
   float x   
);  // C++ only  
long double cosh(  
   long double x  
);  // C++ only  
float coshf(  
   float x   
);  
long double coshl(  
   long double x  
);  
```  
  
#### 매개 변수  
 `x`  
 라디안에서 단위의 각도입니다.  
  
## 반환 값  
 이 `x`의 쌍곡 코사인 혹은 코사인 입니다.  이 `x` 가 크거나 263과 같거나 \-263과 같거나 작은 경우, `cos`, `cosf`, 혹은 `cosl` 로 호출된 결과인 중요한 손실이 발생합니다.  
  
 기본적으로, `cosh`, `coshf` 혹은 `coshl` 보다 큰 결과인 경우, 함수는 `HUGE_VAL` 을 반환하고 `errno` 을 `ERANGE`으로 설정합니다.  
  
|입력|SEH 예외|Matherr 예외|  
|--------|------------|----------------|  
|± `QNAN`,`IND`|없음|`_DOMAIN`|  
|± ∞  \(`cosf`, `cos`, `cosl`\)|`INVALID`|`_DOMAIN`|  
|x ≥ 7.104760e\+002 \(`cosh`, `coshf`, `coshl`\)|`INEXACT`\+`OVERFLOW`|`OVERFLOW`|  
  
## 설명  
 C\+\+가 오버로딩을 허용하기 때문에 `float` 혹은 `long double` 값을 사용하고 반환하는 `cos` 과 `cosh` 의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `cos` 및 `cosh`는 항상 `double`을 사용하고 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`cos`, `cosh`, `cosf`, `coshf`, `cosl`, `coshl`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
  
-   [System::Math::Cos](https://msdn.microsoft.com/en-us/library/system.math.cos.aspx)  
  
-   [System::Math::Cosh](https://msdn.microsoft.com/en-us/library/system.math.cosh.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [\_CIcos](../../c-runtime-library/cicos.md)