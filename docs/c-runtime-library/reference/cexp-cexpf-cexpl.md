---
title: "cexp, cexpf, cexpl | Microsoft Docs"
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
  - "cexp"
  - "cexpf"
  - "cexpl"
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
  - "cexp"
  - "cexpf"
  - "cexpl"
  - "complex/cepx"
  - "complex/cexpf"
  - "complex/cexpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cexp 함수"
  - "cexpl 함수"
  - "cexpf 함수"
ms.assetid: f27fd5a9-70c7-4957-a7ee-5256d19bd1da
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# cexp, cexpf, cexpl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

복소수의 밑이 e인 지수 값을 계산합니다.  
  
## 구문  
  
```  
_Dcomplex cexp(   
   _Dcomplex z   
);  
_Fcomplex cexp(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex cexp(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex cexpf(   
  _Fcomplex z   
);  
_Lcomplex cexpl(   
   _Lcomplex z   
);  
```  
  
#### 매개 변수  
 `z`  
 지수를 나타내는 복소수입니다.  
  
## 반환 값  
 `e`의 `z` 승 값입니다.  
  
## 설명  
 C\+\+에서는 오버로드를 허용하므로 `cexp` 및 `_Fcomplex` 값을 사용 및 반환하는 `_Lcomplex`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `cexp`는 항상 `_Dcomplex` 값을 사용 및 반환합니다.  
  
## 요구 사항  
  
|루틴|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`cexp`, `cexpf`, `cexpl`|\<complex.h\>|\<complex.h\>|  
  
 호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cpow, cpowf, cpowl](../../c-runtime-library/reference/cpow-cpowf-cpowl.md)   
 [clog10, clog10f, clog10l](../../c-runtime-library/reference/clog10-clog10f-clog10l.md)   
 [clog, clogf, clogl](../../c-runtime-library/reference/clog-clogf-clogl.md)