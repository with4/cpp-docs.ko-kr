---
title: "nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl | Microsoft Docs"
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
  - "nextafterf"
  - "_nextafterf"
  - "nextafter"
  - "nextafterl"
  - "_nextafter"
  - "nexttoward"
  - "nexttowardf"
  - "nexttowardl"
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
  - "nextafter"
  - "_nextafter"
  - "nextafterf"
  - "nextafterl"
  - "_nextafterf"
  - "math/nextafter"
  - "math/nextafterf"
  - "math/nextafterl"
  - "nexttoward"
  - "nexttowardf"
  - "nexttowardl"
  - "math/nexttoward"
  - "math/nexttowardf"
  - "math/nexttowardl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_nextafter 함수"
  - "nextafter 함수"
  - "_nextafterf 함수"
  - "nextafterf 함수"
  - "nextafterl 함수"
  - "nexttoward 함수"
  - "nexttowardf 함수"
  - "nexttowardl 함수"
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음으로 표현 가능한 부동 소수점 값을 반환합니다.  
  
## 구문  
  
```  
double nextafter(  
   double x,  
   double y   
);  
  
float nextafter(  
   float x,  
   float y   
); /* C++ only, requires <cmath> */  
  
long double nextafter(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nextafterf(  
   float x,  
   float y   
);   
  
long double nextafterl(  
   long double x,  
   long double y   
);  
  
double _nextafter(  
   double x,  
   double y   
);  
  
float _nextafterf(  
   float x,  
   float y   
); /* x64 only */  
  
double nexttoward(  
   double x,  
   long double y   
);  
  
float nexttoward(  
   float x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
long double nexttoward(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nexttowardf(  
   float x,  
   long double y   
);   
  
long double nexttowardl(  
   long double x,  
   long double y   
);  
```  
  
#### 매개 변수  
 `x`  
 부터 현재 까지의 부동 소수점 값입니다.  
  
 `y`  
 부동 소수점 값으로 이동입니다.  
  
## 반환 값  
 후 반환 형식의 다음 표현 가능한 부동 소수점 값을 반환 `x` 방향으로 `y`합니다. 경우 `x`\=`y`, 함수 반환 `y`, 트리거된 예외가 없는 반환 형식으로 변환 합니다. 경우 `x` 과 같지 않은 `y`, 및 결과 0 또는 denormal, FE\_UNDERFLOW 및 FE\_INEXACT 부동 소수점 예외 상태를 설정 하 고 올바른 결과가 반환 됩니다. 어느 경우 `x` 또는 `y` 는 NAN이 반환 값은 입력된 Nan 중 하나입니다. 경우 `x` 한정 되어 있으므로 결과 무한 또는 형식으로 표현 되지 하 고 올바르게 서명 된 무한대 또는 NAN이 반환 됩니다, FE\_OVERFLOW 및 FE\_INEXACT 부동 소수점 예외 상태를 설정 및 `errno` ERANGE로 설정 됩니다.  
  
## 설명  
 `nextafter` 및 `nexttoward` 함수 패밀리는 매개 변수 형식 제외 하 고 해당 `y`합니다. 경우 `x` 및 `y` 가 반환 되는 값은 같기 `y` 반환 형식으로 변환 합니다.  
  
 오버 로드를 호출할 수 있으므로 c \+ \+ 오버 로드를 \< cmath \>를 포함 하는 경우 `nextafter` 및 `nexttoward` 반환 하는 `float` 및 `long double` 형식입니다. C 프로그램에서 `nextafter` 및 `nexttoward` 항상 반환 `double`합니다.  
  
 `_nextafter` 및 `_nextafterf` 함수는 Microsoft 전용입니다.`_nextafterf` x64 용으로 컴파일할 때이 함수는 사용할 수만 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더\(C\)|필수 헤더\(C\+\+\)|  
|--------|----------------|--------------------|  
|`nextafter`, `nextafterf`, `nextafterl`, `_nextafterf`, `nexttoward`, `nexttowardf`, `nexttowardl`|\<math.h\>|\<math.h\> 또는 \<cmath\>|  
|`_nextafter`|\<float.h\>|\< float.h \> 또는 \< cfloat \>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [isnan, \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)