---
title: "isascii, __isascii, iswascii | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "iswascii"
  - "__isascii"
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
  - "iswascii"
  - "istascii"
  - "__isascii"
  - "_istascii"
  - "isascii"
  - "ctype/isascii"
  - "ctype/__isascii"
  - "corecrt_wctype/iswascii"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__isascii 함수"
  - "_isascii 함수"
  - "isascii 함수"
  - "_istascii 함수"
  - "istascii 함수"
  - "iswascii 함수"
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# isascii, __isascii, iswascii
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

특정 문자가 ASCII 문자인지 여부를 결정합니다.  
  
## 구문  
  
```  
int __isascii(   
   int c   
);  
int iswascii(   
   wint_t c   
);  
#define isascii __isascii  
```  
  
#### 매개 변수  
 `c`  
 테스트할 정수입니다.  
  
## 반환 값  
 `c`가 ASCII 문자의 특정 표현이면 이러한 각 루틴이 0이 아닌 값을 반환합니다.`__isascii`가 ASCII 문자\(0x00\-0x7F 범위 내에 포함\)이면 `c`가 0이 아닌 값을 반환합니다.`iswascii`가 ASCII 문자의 와이드 문자 표현이면 `c`가 0이 아닌 값을 반환합니다.`c`가 테스트 조건을 만족하지 않는 경우 이러한 루틴은 각각 0을 반환합니다.  
  
## 설명  
 둘 다 `__isascii` 및 `iswascii` 전처리기 매크로 \_CTYPE\_DISABLE\_MACROS 정의 되어 있지 않으면 매크로로 구현 됩니다.  
  
 이전 버전과 호환성을 위해 `isascii` 경우에만 매크로로 구현 됩니다 [\_\_STDC\_\_](../../preprocessor/predefined-macros.md) 정의 되지 않았거나 0;으로 정의 그렇지 않으면 정의 되지 않습니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_istascii`|`__isascii`|`__isascii`|`iswascii`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`isascii`, `__isascii`|C: \< ctype.h \><br /><br /> C \+ \+: \< cctype \> 또는 \< ctype.h \>|  
|`iswascii`|C: \< wctype.h \>, \< ctype.h \> 또는 \< wchar.h \><br /><br /> C \+ \+: \< cwctype \>, \< cctype \>, \< wctype.h \>, \< ctype.h \> 또는 \< wchar.h \>|  
  
 `isascii`, `__isascii` 및 `iswascii` 함수는 Microsoft 전용입니다. 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)