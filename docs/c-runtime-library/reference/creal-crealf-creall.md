---
title: "creal, crealf, creall | Microsoft Docs"
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
  - "creal"
  - "crealf"
  - "creall"
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
  - "creal"
  - "crealf"
  - "creall"
  - "complex/creal"
  - "complex/crealf"
  - "complex/creall"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "creal 함수"
  - "crealf 함수"
  - "creall 함수"
ms.assetid: fa3ac62f-7aa3-4238-a71f-d6b00cd0c7c8
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# creal, crealf, creall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

복소수의 실수 부분을 검색합니다.  
  
## 구문  
  
```  
double creal(   
   _Dcomplex z   
);  
float creal(   
   _Fcomplex z   
);  // C++ only  
long double creal(   
   _Lcomplex z   
);  // C++ only  
float crealf(   
   _Fcomplex z   
);  
long double creall(   
  _Lcomplex z   
);  
```  
  
#### 매개 변수  
 `z`  
 복소수입니다.  
  
## 반환 값  
 실수 부분입니다 `z`합니다.  
  
## 설명  
 C \+ \+에서는 오버 로드를 허용 하므로의 오버 로드를 호출할 수 있습니다 `creal` 변수가 있는 `_Fcomplex` 또는 `_Lcomplex` 값 및 반환 `float` 또는 `long double` 값입니다. C 프로그램에서 `creal` 항상는 `_Dcomplex` 값과 반환은 `double` 값입니다.  
  
## 요구 사항  
  
|루틴|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`creal`, `crealf`, `creall`|\<complex.h\>|\< ccomplex \>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [norm, normf, norml](../../c-runtime-library/reference/norm-normf-norml1.md)   
 [cproj, cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [conj, conjf, conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [cimag, cimagf, cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)   
 [carg를, cargf cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)   
 [cab 파일, cabsf, cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)