---
title: "c16rtomb, c32rtomb1 | Microsoft Docs"
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
  - "c16rtomb"
  - "c32rtomb"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "c16rtomb"
  - "c32rtomb"
  - "uchar/c16rtomb"
  - "uchar/c32rtomb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "c16rtomb 함수"
  - "c32rtomb 함수"
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# c16rtomb, c32rtomb
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

UTF\-16 또는 UTF\-32 와이드 문자를 현재 로캘의 멀티바이트 문자로 변환합니다.  
  
## 구문  
  
```  
size_t c16rtomb(  
    char *mbchar,   
    char16_t wchar,  
    mbstate_t *state  
);  
size_t c32rtomb(  
    char *mbchar,   
    char32_t wchar,  
    mbstate_t *state  
);  
```  
  
#### 매개 변수  
 \[out\] `mbchar`  
 변환된 멀티바이트 문자를 저장하는 배열에 대한 포인터입니다.  
  
 \[in\] `wchar`  
 변환할 와이드 문자입니다.  
  
 \[in, out\] `state`  
 `mbstate_t` 개체에 대한 포인터입니다.  
  
## 반환 값  
 배열 개체 `mbchar`에 저장된 바이트 수\(이동 시퀀스 포함\)입니다.`wchar`이 유효한 와이드 문자가 아닌 경우 값\(`size_t`\)\(\-1\)이 반환되며 `errno`가 `EILSEQ`로 설정되고 `state`의 값은 지정되지 않습니다.  
  
## 설명  
 `c16rtomb` 함수는 UTF\-16 문자 `wchar`을 현재 로캘에서 해당하는 멀티바이트 반각 문자 시퀀스로 변환합니다.`mbchar`이 null 포인터가 아닌 경우 함수는 `mbchar`에서 가리키는 배열 개체에 변환된 시퀀스를 저장합니다. 최대 `MB_CUR_MAX`바이트까지 `mbchar`에 저장되며, `state`는 결과적인 멀티바이트 이동 상태로 설정됩니다.`wchar`이 null 와이드 문자인 경우 초기 이동 상태를 복원하는 데 필요한 시퀀스가 저장되고, 필요한 경우 null 문자가 뒤에 나오며, `state`는 초기 변환 상태로 설정됩니다.`c32rtomb` 함수는 동일하지만, UTF\-32 문자를 변환합니다.  
  
 `mbchar`이 null 포인터인 경우 동작은 내부 버퍼로 `mbchar`를 대체하고, 와이드 null 문자로 `wchar`를 대체하는 함수에 대한 호출과 동일합니다.  
  
 `state` 변환 상태 개체를 통해 이 함수와, 멀티바이트 출력 문자의 이동 상태를 유지 관리하는 다시 시작 가능한 다른 함수에 대해 후속 호출을 수행할 수 있습니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수의 사용을 혼합하는 경우 또는 `setlocale`에 대한 호출이 다시 시작할 수 있는 함수 호출 사이에 수행된 경우에는 결과가 정의되지 않습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`c16rtomb`, `c32rtomb`|C, C\+\+: \<uchar.h\>|  
  
 호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtoc16, mbrtoc32](../../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb\_s](../../c-runtime-library/reference/wcrtomb-s.md)