---
title: "wctomb_s, _wctomb_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wctomb_s_l"
  - "wctomb_s"
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
  - "wctomb_s"
  - "_wctomb_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_wctomb_s_l 함수"
  - "문자, 변환"
  - "문자열 변환, 멀티바이트 문자열"
  - "문자열 변환, 와이드 문자"
  - "wctomb_s 함수"
  - "wctomb_s_l 함수"
  - "와이드 문자, 변환"
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
caps.latest.revision: 18
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wctomb_s, _wctomb_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

와이드 바이트 문자를 해당 멀티바이트 문자로 변환합니다.  [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) 의 버젼은 보안 향상과 관련된 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)로 설명됩니다.  
  
## 구문  
  
```  
errno_t wctomb_s(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar   
);  
errno_t _wctomb_s_l(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 \[out\] `pRetValue`  
 바이트의 수 또는 결과를 나타내는 코드  
  
 \[out\] `mbchar`  
 멀티 바이트 문자의 주소입니다.  
  
 \[in\] `sizeInBytes`  
 버퍼의 크기 : `mbchar`  
  
 \[in\] `wchar`  
 와이드 문자  
  
 \[in\] `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다.  
  
 오류 조건  
  
|`mbchar`|`sizeInBytes`|반환 값|`pRetValue`|  
|--------------|-------------------|----------|-----------------|  
|`NULL`|\>0|`EINVAL`|수정 안 됨|  
|any|\>`INT_MAX`|`EINVAL`|수정 안 됨|  
|any|너무 작습니다.|`EINVAL`|수정 안 됨|  
  
 위의 오류 조건이 발생하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, `wctomb` 은 `EINVAL` 를 반환하고, `errno` 에 `EINVAL`를 설정합니다.  
  
## 설명  
 `wctomb_s` 함수는 자신의 `wchar` 인수를 해당하는 멀티 바이트 문자로 변환하고 결과를 `mbchar`에 저장합니다.  프로그램의 모든 위치에서 함수를 호출할 수 있습니다.  
  
 `wctomb_s`가 와이드 문자를 멀티 바이트 문자로 변환할 때, 와이드 문자의 바이트의 크기\(`MB_CUR_MAX`보다는 작은 값\)를 `pRetValue`가 가리키는 정수에 넣습니다.  `wchar`가 와이드 null 문자\(L'\\0'\)일 경우, `wctomb_s`는 `pRetValue`를 1로 채웁니다.  대상 포인터 `mbchar`가 NULL 이면 `wctomb_s`는 `pRetValue`에 0을 저장합니다.  현재 로케일에서의 변환이 불가능 한 경우 `wctomb_s`는 `pRetValue`에 \-1을 저장합니다.  
  
 `wctomb_s` 는 로캘 종속 정보에 대해 현재의 로캘을 사용 합니다. `_wctomb_s_l` 는 전달 된 로캘을 사용 하는 것을 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`wctomb_s`|\<stdlib.h\>|  
|`_wctomb_s_l`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 이 프로그램은 `wctomb` 함수의 동작을 보여 줍니다.  
  
```  
// crt_wctomb_s.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    int i;  
    wchar_t wc = L'a';  
    char *pmb = (char *)malloc( MB_CUR_MAX );  
  
    printf_s( "Convert a wide character:\n" );  
    wctomb_s( &i, pmb, MB_CUR_MAX, wc );  
    printf_s( "   Characters converted: %u\n", i );  
    printf_s( "   Multibyte character: %.1s\n\n", pmb );  
}  
```  
  
  **와이드 문자를 변환합니다.**  
 **변환된 문자: 1**  
 **멀티바이트 문자 : a**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)