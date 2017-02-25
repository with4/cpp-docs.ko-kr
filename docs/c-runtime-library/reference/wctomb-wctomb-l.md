---
title: "wctomb, _wctomb_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wctomb_l"
  - "wctomb"
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
  - "wctomb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wctomb_l 함수"
  - "문자, 변환"
  - "문자열 변환, 멀티바이트 문자열"
  - "문자열 변환, 와이드 문자"
  - "wctomb 함수"
  - "wctomb_l 함수"
  - "와이드 문자, 변환"
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# wctomb, _wctomb_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

와이드 바이트 문자를 해당 멀티바이트 문자로 변환합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [wctomb\_s, \_wctomb\_s\_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)를 참조하십시오.  
  
## 구문  
  
```  
int wctomb(  
   char *mbchar,  
   wchar_t wchar   
);  
int _wctomb_l(  
   char *mbchar,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `mbchar`  
 멀티 바이트 문자의 주소입니다.  
  
 `wchar`  
 와이드 문자  
  
## 반환 값  
 `wctomb`가 와이드 문자를 멀티 바이트 문자로 변환한다면, 와이드 문자의 바이트 수\(이는 `MB_CUR_MAX`보다 클 수 없습니다\)를 반환합니다.  `wchar`가 와이드 문자 null 문자 \(L'\\0'\)이면, `wctomb`는 1을 반환합니다.  대상 포인터 `mbchar`가 NULL이면, `wctomb`는 0을 반환합니다.  현재 로캘에서 변환이 불가능한 경우, `wctomb`는 \-1을 반환하고, `errno`가 `EILSEQ`으로 설정됩니다.  
  
## 설명  
 `wctomb` 함수는 자신의 `wchar` 인수를 해당하는 멀티 바이트 문자로 변환하고 결과를 `mbchar`에 저장합니다.  프로그램의 모든 위치에서 함수를 호출할 수 있습니다.  `wctomb` 는 로캘 종속 동작에 대해 현재 로캘을 사용합니다; `_wctomb_l` 는 대신에 전달 된 로캘을 사용하는 것을 제외하고는 `wctomb` 와 같습니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 `wctomb` 매개 변수의 유효성을 검사합니다.  `mbchar`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다.  계속 실행하는 것이 허용된 경우, `errno`는 `EINVAL` 로 설정되고 함수는 \-1을 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`wctomb`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 이 프로그램은 wctomb 함수의 동작을 보여줍니다.  
  
```  
// crt_wctomb.cpp  
// compile with: /W3  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int i;  
   wchar_t wc = L'a';  
   char *pmb = (char *)malloc( MB_CUR_MAX );  
  
   printf( "Convert a wide character:\n" );  
   i = wctomb( pmb, wc ); // C4996  
   // Note: wctomb is deprecated; consider using wctomb_s  
   printf( "   Characters converted: %u\n", i );  
   printf( "   Multibyte character: %.1s\n\n", pmb );  
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