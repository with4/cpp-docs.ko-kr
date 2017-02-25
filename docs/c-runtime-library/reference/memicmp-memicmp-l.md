---
title: "_memicmp, _memicmp_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_memicmp_l"
  - "_memicmp"
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
  - "_memicmp"
  - "memicmp_l"
  - "_memicmp_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_memicmp 함수"
  - "_memicmp_l 함수"
  - "memicmp 함수"
  - "memicmp_l 함수"
ms.assetid: 0a6eb945-4077-4f84-935d-1aaebe8db8cb
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _memicmp, _memicmp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\(소문자\) 두 개의 버퍼에서 문자를 비교합니다.  
  
## 구문  
  
```  
int _memicmp(  
   const void *buf1,  
   const void *buf2,  
   size_t count   
);  
int _memicmp_l(  
   const void *buf1,  
   const void *buf2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `buf1`  
 첫 번째 버퍼.  
  
 `buf2`  
 두 번째 버퍼.  
  
 `count`  
 Number of characters.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 반환 값은 버퍼 사이의 관계를 나타냅니다.  
  
|반환 값|buf1 와 buf2의 첫 번째 count 바이트의 관계|  
|----------|-------------------------------------|  
|\< 0|`buf1` 은 `buf2` 보다 작습니다.|  
|0|`buf1` 는 `buf2` 와 같습니다.|  
|\> 0|`buf1`는 `buf2`보다 큰 경우|  
|`_NLSCMPERROR`|오류가 발생했습니다.|  
  
## 설명  
 `_memicmp` 함수는 두 버퍼 `buf1` 와 `buf2` 바이트의 첫 번째 `count` 문자를 바이트 단위로 비교합니다.   대\/소문자를 구분하지 않고 비교합니다.  
  
 `buf1` 또는 `buf2` 은 null 포인터입니다. 이 함수는 설명된 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 로서 잘못된 매개변수 핸들러를 적용합니다.  계속해서 실행하도록 허용된 경우, 함수는 `_NLSCMPERROR` 를 반환하고 `errno` 을 `EINVAL`으로 설정합니다.  
  
 `_memicmp` 는 로캘 종속 동작에 대해 현재 로캘을 사용 합니다. `_memicmp_l` 는 대신에 전달 된 로캘을 사용 하는 것을 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_memicmp`|\<memory.h\> 또는 \<string.h\>|  
|`_memicmp_l`|\<memory.h\> 또는 \<string.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_memicmp.c  
// This program uses _memicmp to compare  
// the first 29 letters of the strings named first and  
// second without regard to the case of the letters.  
  
#include <memory.h>  
#include <stdio.h>  
#include <string.h>  
  
int main( void )  
{  
   int result;  
   char first[] = "Those Who Will Not Learn from History";  
   char second[] = "THOSE WHO WILL NOT LEARN FROM their mistakes";  
   // Note that the 29th character is right here ^  
  
   printf( "Compare '%.29s' to '%.29s'\n", first, second );  
   result = _memicmp( first, second, 29 );  
   if( result < 0 )  
      printf( "First is less than second.\n" );  
   else if( result == 0 )  
      printf( "First is equal to second.\n" );  
   else if( result > 0 )  
      printf( "First is greater than second.\n" );  
}  
```  
  
  **'Those Who Will Not Learn from' 를 'THOSE WHO WILL NOT LEARN FROM' 에 비교합니다.**  
**첫 번째는 두 번째와 같습니다.**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [버퍼 조작](../../c-runtime-library/buffer-manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [\_stricmp, \_wcsicmp, \_mbsicmp, \_stricmp\_l, \_wcsicmp\_l, \_mbsicmp\_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)