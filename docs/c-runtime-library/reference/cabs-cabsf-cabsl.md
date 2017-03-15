---
title: "cab 파일, cabsf, cabsl | Microsoft Docs"
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
  - "cabs"
  - "cabsf"
  - "cabsl"
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
  - "cabs"
  - "cabsf"
  - "cabsl"
  - "complex/cabs"
  - "complex/cabsf"
  - "complex/cabsl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cabs 함수"
  - "cabsf 함수"
  - "cabsl 함수"
ms.assetid: 6b8eb453-cc8f-4972-bebf-351cbdfdfc15
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# cab 파일, cabsf, cabsl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

복소수의 절대 값을 검색합니다.  
  
## 구문  
  
```  
double cabs(   
   _Dcomplex z   
);  
float cabs(   
   _Fcomplex z   
);  // C++ only  
long double cabs(   
   _Lcomplex z   
);  // C++ only  
float cabsf(   
   _Fcomplex z   
);  
long double cabsl(   
   _Lcomplex z   
);  
```  
  
#### 매개 변수  
 `z`  
 복소수입니다.  
  
## 반환 값  
 절대값 `z`합니다.  
  
## 설명  
 C \+ \+에서는 오버 로드를 허용 하므로의 오버 로드를 호출할 수 있습니다 `cabs` 변수가 있는 `_Fcomplex` 또는 `_Lcomplex` 값 및 반환 `float` 또는 `long double` 값입니다. C 프로그램에서 `cabs` 항상는 `_Dcomplex` 값과 반환은 `double` 값입니다.  
  
## 요구 사항  
  
|루틴|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`cabs`, `cabsf`, `cabsl`|\<complex.h\>|\< ccomplex \>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [norm, normf, norml](../../c-runtime-library/reference/norm-normf-norml1.md)   
 [creal, crealf, creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [cproj, cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [conj, conjf, conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)   
 [cimag, cimagf, cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)   
 [carg를, cargf cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)