---
title: "asin, asinf, asinl | Microsoft Docs"
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
  - "asinf"
  - "asinl"
  - "asin"
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
  - "asin"
  - "asinl"
  - "asinf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "역 사인 함수"
  - "asin 함수"
  - "asinf 함수"
  - "asinl 함수"
  - "삼각 함수"
ms.assetid: ca05f9ea-b711-49f6-9f32-2f4019abfd69
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# asin, asinf, asinl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

아크사인 값을 계산합니다.  
  
## 구문  
  
```  
double asin(   
   double x   
);  
float asin(  
   float x  
);  // C++ only  
long double asin(  
   long double x  
);  // C++ only  
float asinf (   
   float x   
);  
long double asinl(  
   long double x  
);  
```  
  
#### 매개 변수  
 `x`  
 아크사인 값을 계산 하는 값입니다.  
  
## 반환 값  
 이 `asin` 함수는 π\/2 라디안 범위 –π\/2에서 `x` 의 아크사인\(역 사인 함수\) 반환합니다.  
  
 기본적으로 경우 `x` \-1 보다 작거나 1 보다 큰 `asin` 는 무한을 반환 합니다.  
  
|입력|SEH 예외|Matherr 예외|  
|--------|------------|----------------|  
|± ∞|`INVALID`|`_DOMAIN`|  
|± `QNAN`,`IND`|없음|`_DOMAIN`|  
|&#124;x&#124;\>1|`INVALID`|`_DOMAIN`|  
  
## 설명  
 C\+\+ 오버 로딩을 허용하기 때문에, `float` 와 `long double` 값의 `asin` 의 오버 로드를 호출 할 수 있습니다.  C 프로그램에서 `asin` 는 항상 2배를 사용하고 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`asin`, `asinf`, `asinl`|\<math.h\>|  
  
## 예제  
 자세한 내용은 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Math::Asin](https://msdn.microsoft.com/en-us/library/system.math.asin.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)