---
title: "conj, conjf, conjl | Microsoft Docs"
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
  - "conj"
  - "conjf"
  - "conjl"
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
  - "conj"
  - "conjf"
  - "conjl"
  - "complex/conj"
  - "complex/conjf"
  - "complex/conjl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conj 함수"
  - "conjf 함수"
  - "conjl 함수"
ms.assetid: 792fccfa-19c6-4890-99f9-a3b89effccd6
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# conj, conjf, conjl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

복소수의 켤레 복소수를 검색합니다.  
  
## 구문  
  
```  
_Dcomplex conj(   
   _Dcomplex z   
);  
_Fcomplex conj(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex conj(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex conjf(   
   _Fcomplex z   
);  
_Lcomplex conjl(   
   _Lcomplex z   
);  
```  
  
#### 매개 변수  
 `z`  
 복소수입니다.  
  
## 반환 값  
 켤레 복소수입니다 `z`합니다.  결과 동일한 실수와 허수 부분으로 `z`, 를 같지만 부호가 다른 합니다.  
  
## 설명  
 C\+\+에서는 오버로드를 허용하므로 `conj` 및 `_Fcomplex` 값을 사용 및 반환하는 `_Lcomplex`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `conj` 항상 사용 하 고 반환 된 `_Dcomplex` 값입니다.  
  
## 요구 사항  
  
|루틴|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`conj`, `conjf`, `conjl`|\<complex.h\>|\< ccomplex \>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [norm, normf, norml](../../c-runtime-library/reference/norm-normf-norml1.md)   
 [creal, crealf, creall](../../c-runtime-library/reference/creal-crealf-creall.md)   
 [cproj, cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)   
 [cimag, cimagf, cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)   
 [carg를, cargf cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)   
 [cab 파일, cabsf, cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)