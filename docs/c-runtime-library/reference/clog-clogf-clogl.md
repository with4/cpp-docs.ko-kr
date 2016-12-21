---
title: "clog, clogf, clogl | Microsoft Docs"
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
  - "clog"
  - "clogf"
  - "clogl"
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
  - "clog"
  - "clogf"
  - "clogl"
  - "complex/clog"
  - "complex/clogf"
  - "complex/clogl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "clog 함수"
  - "clogf 함수"
  - "clogl 함수"
ms.assetid: 870b9b0b-6618-46f3-bfcf-da595cbd5e18
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# clog, clogf, clogl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

분기의 음수 실제 축을 따라 잘라내기는 복소수의 자연 로그를 검색 합니다.  
  
## 구문  
  
```  
_Dcomplex clog(   
   _Dcomplex z   
);  
_Fcomplex clog(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex clog(   
   _Lcomplex z   
);  // C++ only  
_Fcomplex clogf(   
   _Fcomplex z   
);  
_Lcomplex clogl(   
   _Lcomplex z   
);  
```  
  
#### 매개 변수  
 `z`  
 로그의 밑입니다.  
  
## 반환 값  
 자연 로그 `z`합니다. 결과가 축에 실제 및 가상 축 간격 \[, −iπ \+ iπ\]에 제한 되지 않습니다.  
  
 가능한 반환 값은 같습니다.  
  
|z 매개 변수|반환 값|  
|-------------|----------|  
|양수|Z의 밑수 10|  
|0|\- ∞|  
|음수|NaN|  
|NaN|NaN|  
|\+ ∞|\+ ∞|  
  
## 설명  
 C\+\+에서는 오버로드를 허용하므로 `clog` 및 `_Fcomplex` 값을 사용 및 반환하는 `_Lcomplex`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `clog` 항상 사용 하 고 반환 된 `_Dcomplex` 값입니다.  
  
## 요구 사항  
  
|루틴|C 헤더|C\+\+ 헤더|  
|--------|----------|--------------|  
|`clog`, `clogf`, `clogl`|\<complex.h\>|\< ccomplex \>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## 참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [cexp, cexpf, cexpl](../../c-runtime-library/reference/cexp-cexpf-cexpl.md)   
 [cpow, cpowf, cpowl](../../c-runtime-library/reference/cpow-cpowf-cpowl.md)   
 [clog10, clog10f, clog10l](../../c-runtime-library/reference/clog10-clog10f-clog10l.md)