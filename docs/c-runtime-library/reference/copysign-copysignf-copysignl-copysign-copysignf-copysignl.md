---
title: "copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "copysignf"
  - "copysignl"
  - "_copysignl"
  - "_copysign"
  - "_copysignf"
  - "copysign"
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
  - "_copysignl"
  - "copysign"
  - "copysignf"
  - "_copysign"
  - "copysignl"
  - "_copysignf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_copysign 함수"
  - "_copysignf 함수"
  - "_copysignl 함수"
  - "copysign 함수"
  - "copysignf 함수"
  - "copysignl 함수"
ms.assetid: 009216d6-72a2-402d-aa6c-91d924b2c9e4
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인수 크기와 다른 부호를 가지고 있는 값을 반환합니다.  
  
## 구문  
  
```  
double copysign(   
   double x,  
   double y   
);  
float copysign(   
   float x,  
   float y   
); // C++ only  
long double copysign(   
   long double x,  
   long double y   
); // C++ only  
float copysignf(   
   float x,  
   float y   
); // C++ only  
long double copysignl(   
   long double x,  
   long double y   
); // C++ only  
double _copysign(   
   double x,  
   double y   
);  
long double _copysignl(   
   long double x,  
   long double y   
);  
```  
  
#### 매개 변수  
 `x`  
 결과의 크기를 반환하는 부동 소수점 값입니다.  
  
 `y`  
 결과의 부호를 반환하는 부동 소수점 값입니다.  
  
 [부동 소수점 지원 루틴](../../c-runtime-library/floating-point-support.md)  
  
## 반환 값  
 `copysign`  기능은  `x`  의 크기와  `y` 의 부호를 결합한 부동 소수점 값을 반환합니다.  반환되는 오류가 없습니다.  
  
## 설명  
 C\+\+가 오버로딩을 허용하기 때문에 `float` 또는 `long double` 값을 사용하고 반환하는 `copysign`의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `copysign`는 항상 `double`을 사용하고 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_copysign`|\<float.h\>|  
|`copysign`, `copysignf`, `copysignl`, `_copysignf` `_copysignl`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [\_chgsign, \_chgsignf, \_chgsignl](../../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)