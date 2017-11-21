---
title: "memchr, wmemchr | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wmemchr
- memchr
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- memchr
- wmemchr
dev_langs: C++
helpviewer_keywords:
- memchr function
- wmemchr function
ms.assetid: 5a348581-28f1-4256-8434-687245f7fc9f
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dd7a16cb35257104b79d0347fe415c5b17cd4bb4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="memchr-wmemchr"></a>memchr, wmemchr
버퍼에서 문자를 찾습니다.  
  
## <a name="syntax"></a>구문  
  
```  
void *memchr(  
   const void *buf,  
   int c,  
   size_t count  
); // C only  
void *memchr(  
   void *buf,  
   int c,  
   size_t count  
); // C++ only  
const void *memchr(  
   const void *buf,  
   int c,  
   size_t count  
); // C++ only  
wchar_t *wmemchr(  
   const wchar_t * buf,   
   wchar_t c,  
   size_t count  
); // C only  
wchar_t *wmemchr(  
   wchar_t * buf,   
   wchar_t c,  
   size_t count  
); // C++ only  
const wchar_t *wmemchr(  
   const wchar_t * buf,   
   wchar_t c,  
   size_t count  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 `buf`  
 버퍼에 대한 포인터입니다.  
  
 `c`  
 찾을 문자입니다.  
  
 `count`  
 검사할 문자 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공적인 경우 `c`의 첫 번째 `buf` 위치를 가리키는 포인터를 반환합니다. 그렇지 않은 경우 `NULL`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `memchr` 및 `wmemchr`은 `buf`의 처음 `count` 바이트에서 처음 나타나는 `c`를 찾습니다. `c`를 찾거나 첫 번째 `count` 바이트를 검사하면 중지됩니다.  
  
 C에서 이러한 함수는 첫 번째 인수에 대한 `const` 포인터를 갖습니다. C++에서는 두 오버로드를 모두 사용할 수 있습니다. `const`에 대한 포인터를 갖는 오버로드는 `const`에 대한 포인터를 반환합니다. 비`const`에 대한 포인터를 갖는 버전은 비`const`에 대한 포인터를 반환합니다. 매크로 _CRT_CONST_CORRECT_OVERLOADS 모두에 정의 된는 `const` 및 비-`const` 이러한 함수의 버전을 사용할 수 있습니다. 두 C++ 오버로드에 대한 비`const` 동작이 필요한 경우 기호 _CONST_RETURN을 정의합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`memchr`|\<memory.h> 또는 \<string.h>|  
|`wmemchr`|\<wchar.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예제  
  
```  
// crt_memchr.c  
  
#include <memory.h>  
#include <stdio.h>  
  
int  ch = 'r';  
char str[] =    "lazy";  
char string[] = "The quick brown dog jumps over the lazy fox";  
char fmt1[] =   "         1         2         3         4         5";  
char fmt2[] =   "12345678901234567890123456789012345678901234567890";  
  
int main( void )  
{  
   char *pdest;  
   int result;  
   printf( "String to be searched:\n             %s\n", string );  
   printf( "             %s\n             %s\n\n", fmt1, fmt2 );  
  
   printf( "Search char: %c\n", ch );  
   pdest = memchr( string, ch, sizeof( string ) );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf( "Result:      %c found at position %d\n", ch, result );  
   else  
      printf( "Result:      %c not found\n" );  
}  
```  
  
## <a name="output"></a>출력  
  
```  
String to be searched:  
             The quick brown dog jumps over the lazy fox  
                      1         2         3         4         5  
             12345678901234567890123456789012345678901234567890  
  
Search char: r  
Result:      r found at position 12  
```  
  
## <a name="see-also"></a>참고 항목  
 [버퍼 조작](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strchr, wcschr, _mbschr, _mbschr_l](../../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md)