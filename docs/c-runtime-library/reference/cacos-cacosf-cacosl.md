---
title: "cacos, cacosf, cacosl | Microsoft Docs"
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
  - "cacos"
  - "cacosf"
  - "cacosl"
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
  - "cacos"
  - "cacosf"
  - "cacosl"
  - "complex/cacos"
  - "complex/cacosf"
  - "complex/cacosl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cacos 함수"
  - "cacosf 함수"
  - "cacosl 함수"
ms.assetid: 78118c00-0a07-49c1-8a13-4bf19ce3aea8
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# cacos, cacosf, cacosl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

실제 축 \[에서 1 \+ 1\] 간격에서 벗어난 분기 컷 복소수의 아크코사인 값을 검색합니다.  
  
## 구문  
  
```  
_Dcomplex cacos(   
  _Dcomplex z   
);  
_Fcomplex cacos(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex cacos(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex cacosf(   
   _Fcomplex z   
);  
_Lcomplex cacosl(   
   _Lcomplex z   
);  
```  
  
#### 매개 변수  
 `z`  
 라디안에서 각도 나타내는 복소수.  
  
## 반환 값  
 아크코사인 `z`, 을 라디안에서입니다. 결과가 허수 축을 따라로 제한 되지 않습니다.는 실제 축 간격 \[0, π\]. 도메인 오류가 발생 합니다 `z` \[\-1, \+ 1\] 간격을 벗어납니다.  
  
## 설명  
 C\+\+에서는 오버로드를 허용하므로 `cacos` 및 `_Fcomplex` 값을 사용 및 반환하는 `_Lcomplex`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `cacos` 항상 사용 하 고 반환 된 `_Dcomplex` 값입니다.  
  
## 요구 사항  
  
|루틴|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`cacos`, `cacosf`, `cacosl`|\<complex.h\>|\< ccomplex \>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [catanh, catanhf, catanhl](../../c-runtime-library/reference/catanh-catanhf-catanhl.md)   
 [ctanh, ctanhf, ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [catan, catanf, catanl](../../c-runtime-library/reference/catan-catanf-catanl.md)   
 [csinh를, csinhf csinhl](../../c-runtime-library/reference/csinh-csinhf-csinhl.md)   
 [casinh, casinhf, casinhl](../../c-runtime-library/reference/casinh-casinhf-casinhl.md)   
 [ccosh를, ccoshf ccoshl](../../c-runtime-library/reference/ccosh-ccoshf-ccoshl.md)   
 [cacosh, cacoshf, cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [ctan, ctanf, ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [csin, csinf, csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [casin, casinf, casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [ccos, ccosf, ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)   
 [csqrt, csqrtf, csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)