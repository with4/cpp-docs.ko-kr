---
title: "iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l | Microsoft Docs"
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
  - "_iswcsym_l"
  - "__iswcsym"
  - "__iscsym"
  - "_iswcsymf_l"
  - "_iscsym_l"
  - "__iswcsymf"
  - "__iscsymf"
  - "_iscsymf_l"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_iswcsym_l"
  - "_iswcsymf_l"
  - "iscsymf"
  - "iswcsymf"
  - "__iswcsym"
  - "__iswcsymf"
  - "iscsym"
  - "iswcsym"
  - "__iscsym"
  - "_iscsym_l"
  - "_iscsymf_l"
  - "__iscsymf"
  - "ctype/iscsym"
  - "ctype/iscsymf"
  - "ctype/__iscsym"
  - "ctype/__iscsymf"
  - "ctype/__iscsym_l"
  - "ctype/__iscsymf_l"
  - "ctype/__iswcsym"
  - "ctype/__iswcsymf"
  - "ctype/__iswcsym_l"
  - "ctype/__iswcsymf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "iscsymf_l 함수"
  - "iswsym_l 함수"
  - "_iswcsym_l 함수"
  - "iscsym_l 함수"
  - "_iscsymf_l 함수"
  - "_iswcsymf_l 함수"
  - "_iscsym_l 함수"
  - "__iscsym 함수"
  - "__iswcsymf 함수"
  - "iswsymf_l 함수"
  - "__iscsymf 함수"
  - "__iswcsym 함수"
  - "iscsym 함수"
  - "iscsymf 함수"
ms.assetid: 944dfb99-f2b8-498c-9f55-dbcf370d0a2c
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정수가 식별자로 사용할 수 있는 문자를 나타내는지 여부를 결정합니다.  
  
## 구문  
  
```  
int __iscsym(   
   int c   
);  
int __iswcsym(   
   wint_t c   
);  
int __iscsymf(   
   int c   
);  
int __iswcsymf(   
   wint_t c   
);  
int _iscsym_l(   
   int c,  
   _locale_t locale  
);  
int _iswcsym_l(   
   wint_t c,  
   _locale_t locale  
);  
int _iscsymf_l(   
   int c,  
   _locale_t locale  
);  
int _iswcsymf_l(   
   wint_t c,  
   _locale_t locale  
);  
#define iscsym __iscsym  
#define iscsymf __iscsymf  
```  
  
#### 매개 변수  
 `c`  
 테스트할 정수입니다. 함수의 좁은 문자 버전에 대해 `c`는 0\-255 범위 안에 있어야 합니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 둘 다 `__iscsym` 및 `__iswcsym` 경우 0이 아닌 값을 반환 `c` 문자, 밑줄 또는 숫자인 됩니다. 둘 다 `__iscsymf` 및 `__iswcsymf` 경우 0이 아닌 값을 반환 `c` 문자 또는 밑줄은입니다.`c`가 테스트 조건을 만족하지 않는 경우 이러한 루틴은 각각 0을 반환합니다.`_l` 접미사가 있는 이러한 함수 버전은 로캘 종속 동작에 현재 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
## 설명  
 전처리기 매크로 \_CTYPE\_DISABLE\_MACROS 정의 되지 않은 경우 이러한 루틴은 매크로로 정의 됩니다. 이러한 루틴의 매크로 버전을 사용 하면 인수를 두 번 이상 평가할 수 있습니다. 인수 목록 내에서 의도 하지 않은 식을 사용할 때 주의 해야 합니다.  
  
 이전 버전과 호환성을 위해 `iscsym` 및 `iscsymf` 매크로로 정의 된 경우에만 [\_\_STDC\_\_](../../preprocessor/predefined-macros.md) 정의 되지 않았거나 0;으로 정의 그렇지 않으면은 정의 되지 않습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`iscsym`, `iscsymf`, `__iscsym`, `__iswcsym`, `__iscsymf`, `__iswcsymf`, `_iscsym_l`, `_iswcsym_l`, `_iscsymf_l`, `_iswcsymf_l`|C: \< ctype.h \><br /><br /> C \+ \+: \< cctype \> 또는 \< ctype.h \>|  
  
 `iscsym`, `iscsymf`, `__iscsym`, `__iswcsym`, `__iscsymf`, `__iswcsymf`, `_iscsym_l`, `_iswcsym_l`, `_iscsymf_l`, 및 `_iswcsymf_l` 루틴은 Microsoft 전용입니다. 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)