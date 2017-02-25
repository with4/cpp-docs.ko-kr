---
title: "memcmp, wmemcmp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "memcmp"
  - "wmemcmp"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "memcmp"
  - "wmemcmp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "memcmp 함수"
  - "wmemcmp 함수"
ms.assetid: 0c21c3e3-8ee4-40e5-add1-eb26d225fd8d
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# memcmp, wmemcmp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

두 개의 버퍼에서 문자를 비교합니다.  
  
## 구문  
  
```  
  
      int memcmp(  
   const void *buf1,  
   const void *buf2,  
   size_t count  
);  
int wmemcmp(  
   const wchar_t * buf1,  
   const wchar_t * buf2,  
   size_t count  
);  
```  
  
#### 매개 변수  
 `buf1`  
 첫 번째 버퍼.  
  
 `buf2`  
 두 번째 버퍼.  
  
 `count`  
 \[in\] 비교할 문자 수입니다. \( `memcmp`, `wmemcmp`에 대한 와이드 문자에서 바이트를 비교합니다\).  
  
## 반환 값  
 반환 값은 버퍼 사이의 관계를 나타냅니다.  
  
|반환 값|buf1 및 buf2에 대한 `count` 문자의 첫 번째 관계|  
|----------|-----------------------------------------|  
|\< 0|`buf1` \< `buf2`|  
|0|`buf1` \= `buf2`|  
|\> 0|`buf1` \> `buf2`|  
  
## 설명  
 첫 번째 `buf1` 및 `buf2` 에 대한 `count` 문자를 비교하고 서로의 관계를 나타내는 값을 반환합니다.  0이 아닌 반환 값의 부호는 버퍼에 있는 값의 첫 번째와 다른 쌍 사이의 차이에서 나옵니다.  값은 `unsigned char` 에서 `memcmp`로 그리고 `wchar_t` 에서 `wmemcmp`로 해석됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`memcmp`|\<memory.h\> 또는 \<string.h\>|  
|`wmemcmp`|\<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_memcmp.c  
/* This program uses memcmp to compare  
 * the strings named first and second. If the first  
 * 19 bytes of the strings are equal, the program  
 * considers the strings to be equal.  
 */  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char first[]  = "12345678901234567890";  
   char second[] = "12345678901234567891";  
   int int_arr1[] = {1,2,3,4};  
   int int_arr2[] = {1,2,3,4};  
   int result;  
  
   printf( "Compare '%.19s' to '%.19s':\n", first, second );  
   result = memcmp( first, second, 19 );  
   if( result < 0 )  
      printf( "First is less than second.\n" );  
   else if( result == 0 )  
      printf( "First is equal to second.\n" );  
   else  
      printf( "First is greater than second.\n" );  
  
   printf( "Compare '%d,%d' to '%d,%d':\n", int_arr1[0], int_arr1[1], int_arr2[0], int_arr2[1]);  
   result = memcmp( int_arr1, int_arr2, sizeof(int) * 2 );  
   if( result < 0 )  
      printf( "int_arr1 is less than int_arr2.\n" );  
   else if( result == 0 )  
      printf( "int_arr1 is equal to int_arr2.\n" );  
   else   
      printf( "int_arr1 is greater than int_arr2.\n" );  
}  
```  
  
## Output  
  
```  
Compare '1234567890123456789' to '1234567890123456789':  
First is equal to second.  
Compare '1,2' to '1,2':  
int_arr1 is equal to int_arr2.  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [버퍼 조작](../../c-runtime-library/buffer-manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)