---
title: "_CrtSetDebugFillThreshold | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetDebugFillThreshold"
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
apitype: "DLLExport"
f1_keywords: 
  - "_CrtSetDebugFillThreshold"
  - "CrtSetDebugFillThreshold"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtSetDebugFillThreshold 함수"
  - "0xFD"
  - "버퍼 채우기 동작"
  - "CrtSetDebugFillThreshold 함수"
  - "디버그, 버퍼 채우기 동작"
ms.assetid: 6cb360e8-56ae-4248-b17f-e28aee3e0ed7
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# _CrtSetDebugFillThreshold
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

디버그 함수에서 버퍼 채우기 동작을 제어하는 임계값을 검색하고 수정합니다.  
  
## 구문  
  
```  
size_t _CrtSetDebugFillThreshold(  
   size_t _NewThreshold  
);  
```  
  
#### 매개 변수  
 `newThreshold`  
 새 임계값입니다.  
  
## 반환 값  
 이전 임계값입니다.  
  
## 설명  
 보안이 강화된 CRT 함수의 디버그 버전은 특수 문자 \(0xFD\)를 사용하여 전달된 버퍼를 채웁니다.  이것은 잘못된 크기가 함수에 전달된 경우를 찾는 것을 도와줍니다.  불행하게도, 성능 또한 줄어듭니다.  성능을 향상시키기 위해서는, 임계값보다 큰 버퍼에 버퍼 채우기를 비활성화시키기 위해 `_CrtSetDebugFillThreshold`를 사용합니다.  0의 임계값은 모든 버퍼를 해제시킵니다.  
  
 기본 임계값은 `SIZE_T_MAX`입니다.  
  
 영향을 미치는 함수의 목록은 다음과 같습니다.  
  
-   [strcpy\_s, wcscpy\_s, \_mbscpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)  
  
-   [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)  
  
-   [\_mbsnbcpy\_s, \_mbsnbcpy\_s\_l](../../c-runtime-library/reference/mbsnbcpy-s-mbsnbcpy-s-l.md)  
  
-   [strcat\_s, wcscat\_s, \_mbscat\_s](../../c-runtime-library/reference/strcat-s-wcscat-s-mbscat-s.md)  
  
-   [strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)  
  
-   [\_mbsnbcat\_s, \_mbsnbcat\_s\_l](../../c-runtime-library/reference/mbsnbcat-s-mbsnbcat-s-l.md)  
  
-   [\_strset\_s, \_strset\_s\_l, \_wcsset\_s, \_wcsset\_s\_l, \_mbsset\_s, \_mbsset\_s\_l](../../c-runtime-library/reference/strset-s-strset-s-l-wcsset-s-wcsset-s-l-mbsset-s-mbsset-s-l.md)  
  
-   [\_strnset\_s, \_strnset\_s\_l, \_wcsnset\_s, \_wcsnset\_s\_l, \_mbsnset\_s, \_mbsnset\_s\_l](../../c-runtime-library/reference/strnset-s-strnset-s-l-wcsnset-s-wcsnset-s-l-mbsnset-s-mbsnset-s-l.md)  
  
-   [\_mbsnbset\_s, \_mbsnbset\_s\_l](../../c-runtime-library/reference/mbsnbset-s-mbsnbset-s-l.md)  
  
-   [\_makepath\_s, \_wmakepath\_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)  
  
-   [\_splitpath\_s, \_wsplitpath\_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)  
  
-   [\_strlwr\_s, \_strlwr\_s\_l, \_mbslwr\_s, \_mbslwr\_s\_l, \_wcslwr\_s, \_wcslwr\_s\_l](../../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)  
  
-   [\_strupr\_s, \_strupr\_s\_l, \_mbsupr\_s, \_mbsupr\_s\_l, \_wcsupr\_s, \_wcsupr\_s\_l](../../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)  
  
-   [strerror\_s, \_strerror\_s, \_wcserror\_s, \_\_wcserror\_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)  
  
-   [\_itoa\_s, \_i64toa\_s, \_ui64toa\_s, \_itow\_s, \_i64tow\_s, \_ui64tow\_s](../../c-runtime-library/reference/itoa-s-i64toa-s-ui64toa-s-itow-s-i64tow-s-ui64tow-s.md)  
  
-   [\_ecvt\_s](../../c-runtime-library/reference/ecvt-s.md)  
  
-   [\_fcvt\_s](../../c-runtime-library/reference/fcvt-s.md)  
  
-   [\_gcvt\_s](../../c-runtime-library/reference/gcvt-s.md)  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_CrtSetDebugFillThreshold`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
## 예제  
  
```  
// crt_crtsetdebugfillthreshold.cpp  
// compile with: /MTd  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <crtdbg.h>  
  
void Clear( char buff[], size_t size )  
{  
   for( int i=0; i<size; ++i )  
      buff[i] = 0;  
}  
  
void Print( char buff[], size_t size )  
{  
   for( int i=0; i<size; ++i )  
      printf( "%02x  %c\n", (unsigned char)buff[i], buff[i] );  
}  
  
int main( void )  
{  
   char buff[10];  
  
   printf( "With buffer-filling on:\n" );  
   strcpy_s( buff, _countof(buff), "howdy" );  
   Print( buff, _countof(buff) );  
  
   _CrtSetDebugFillThreshold( 0 );  
  
   printf( "With buffer-filling off:\n" );  
   Clear( buff, _countof(buff) );  
   strcpy_s( buff, _countof(buff), "howdy" );  
   Print( buff, _countof(buff) );  
}  
```  
  
```  
With buffer-filling on:  
68  h  
6f  o  
77  w  
64  d  
79  y  
00  
fd  ²  
fd  ²  
fd  ²  
fd  ²  
With buffer-filling off:  
68  h  
6f  o  
77  w  
64  d  
79  y  
00  
00  
00  
00  
00  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)