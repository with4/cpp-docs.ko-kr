---
title: "wctob | Microsoft Docs"
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
  - "wctob"
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
  - "wctob"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "문자, 변환"
  - "wctob 함수"
  - "와이드 문자, 변환"
ms.assetid: 46aec98b-c2f2-4e9d-9d89-7db99ba8a9a6
caps.latest.revision: 14
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wctob
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

와이드 문자가 멀티 바이트 문자에 해당하는지를 결정하고 멀티 바이트 문자 표현을 반환합니다.  
  
## 구문  
  
```  
int wctob(  
   wint_t wchar  
);  
```  
  
#### 매개 변수  
 `wchar`  
 변환할 값입니다.  
  
## 반환 값  
 `wctob`가 성공적으로 와이드 문자를 변환한 경우, 멀티 바이트 문자가 정확히 1바이트 길이를 가질 때에만 해당하는 멀티 바이트 문자 표현을 반환합니다.  `wctob`가 와이드 문자를 만나는 경우, 이를 멀티 바이트 문자로 변환할 수 없으며, 멀티바이트 문자가 정확히 1바이트 길이를 가지지 않는 경우 \-1을 반환합니다.  
  
## 설명  
 멀티바이트 문자가 정확히 1바이트 길이를 가진 경우, `wctob` 함수는 `wchar`에 포함된 와이드 문자를 `int` 반환 값에 의해 전달되는 멀티 바이트 문자로 변환합니다.  
  
 `wctob`가 실패하고 해당하는 멀티 바이트 문자가 발견되지 않은 경우, 이 함수는 `errno`를 `EILSEQ`로 설정하고 \-1을 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`wctob`|\<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 이 프로그램은 `wcstombs` 함수의 동작을 보여 줍니다.  
  
```  
// crt_wctob.c  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    int     bChar = 0;  
    wint_t  wChar = 0;  
  
    // Set the corresponding wide character to exactly one byte.  
    wChar = (wint_t)'A';  
  
    bChar = wctob( wChar );  
    if (bChar == WEOF)  
    {  
        printf( "No corresponding multibyte character was found.\n");  
    }  
    else  
    {  
        printf( "Determined the corresponding multibyte character to"  
                " be \"%c\".\n", bChar);  
    }  
}  
  
```  
  
  **해당하는 멀티 바이트 문자를 "A"로 결정했습니다.**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)