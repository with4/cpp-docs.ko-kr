---
title: strstr, wcsstr, _mbsstr, _mbsstr_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsstr
- wcsstr
- _mbsstr_l
- strstr
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fstrstr
- _ftcsstr
- strstr
- wcsstr
- _mbsstr
- _tcsstr
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], searching
- mbsstr function
- _ftcsstr function
- ftcsstr function
- fstrstr function
- _tcsstr function
- substrings, finding
- mbsstr_l function
- tcsstr function
- _mbsstr function
- wcsstr function
- _fstrstr function
- _mbsstr_l function
- strstr function
ms.assetid: 03d70c3f-2473-45cb-a5f8-b35beeb2748a
caps.latest.revision: 32
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 0402f647be21541222fe215760715eea1dee39d9
ms.lasthandoff: 02/24/2017

---
# <a name="strstr-wcsstr-mbsstr-mbsstrl"></a>strstr, wcsstr, _mbsstr, _mbsstr_l
문자열에서 처음 나오는 검색 문자열에 대한 포인터를 반환합니다.  
  
> [!IMPORTANT]
>  `_mbsstr` 및 `_mbsstr_l`은 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
char *strstr(  
   const char *str,  
   const char *strSearch   
); // C only  
char *strstr(  
   char *str,  
   const char *strSearch   
); // C++ only  
const char *strstr(  
   const char *str,  
   const char *strSearch   
); // C++ only  
wchar_t *wcsstr(  
   const wchar_t *str,  
   const wchar_t *strSearch   
); // C only  
wchar_t *wcsstr(  
   wchar_t *str,  
   const wchar_t *strSearch   
); // C++ only  
const wchar_t *wcsstr(  
   const wchar_t *str,  
   const wchar_t *strSearch   
); // C++ only  
unsigned char *_mbsstr(  
   const unsigned char *str,  
   const unsigned char *strSearch   
); // C only  
unsigned char *_mbsstr(  
   unsigned char *str,  
   const unsigned char *strSearch   
); // C++ only  
const unsigned char *_mbsstr(  
   const unsigned char *str,  
   const unsigned char *strSearch   
); // C++ only  
unsigned char *_mbsstr_l(  
   const unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C only  
unsigned char *_mbsstr_l(  
   unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbsstr_l(  
   const unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 `str`  
 검색할 Null 종료 문자열입니다.  
  
 `strSearch`  
 검색할 Null 종료 문자열입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 `str`에서 처음 나오는 `strSearch`에 대한 포인터를 반환하거나, `str`에 `strSearch`가 없으면 `NULL`을 반환합니다. `strSearch`가 길이가&0;인 문자열을 가리키면 함수는 `str`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `strstr` 함수는 `str`에서 처음 나오는 `strSearch`에 대한 포인터를 반환합니다. 종료 null 문자는 검색에 포함되지 않습니다. `wcsstr`은 `strstr`의 와이드 문자 버전이고 `_mbsstr`은 멀티바이트 버전입니다. `wcsstr`의 인수 및 반환 값은 와이드 문자열이며 `_mbsstr`의 인수와 반환 값은 멀티바이트 문자열입니다. `_mbsstr`은 매개 변수의 유효성을 검사합니다. `str` 또는 `strSearch`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 `_mbsstr`은 `errno`를 `EINVAL`로 설정하고 0을 반환합니다. `strstr` 및 `wcsstr`는 매개 변수의 유효성을 검사하지 않습니다. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
> [!IMPORTANT]
>  이러한 함수에서는 버퍼 오버런 문제로 인한 위협이 발생할 수 있습니다. 버퍼 오버런은 시스템 공격에 이용될 수 있습니다. 버퍼 오버런 문제가 발생하면 임의 코드를 실행할 수 있게 되어 보증하지 않은 방식으로 권한이 상승할 수 있기 때문입니다. 자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요.  
  
 C에서 이러한 함수는 첫 번째 인수에 대한 `const` 포인터를 갖습니다. C++에서는 두 오버로드를 모두 사용할 수 있습니다. `const`에 대한 포인터를 사용하는 오버로드는 `const`에 대한 포인터를 반환합니다. 비`const`에 대한 포인터를 사용하는 버전은 비`const`에 대한 포인터를 반환합니다. 이러한 함수의 `const` 및 비`const` 버전을 모두 사용할 수 있는 경우 매크로 _CONST_CORRECT_OVERLOADS가 정의됩니다. 두 C++ 오버로드에 대한 비`const` 동작이 필요한 경우 기호 _CONST_RETURN을 정의합니다.  
  
 출력 값은 `LC_CTYPE`의 로캘 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. `_l` 접미사가 없는 이러한 함수 버전은 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용한다는 점을 제외하고는 동일합니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsstr`|`strstr`|`_mbsstr`|`wcsstr`|  
|**n/a**|**n/a**|`_mbsstr_l`|**n/a**|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`strstr`|\<string.h>|  
|`wcsstr`|\<string.h> 또는 \<wchar.h>|  
|`_mbsstr`, `_mbsstr_l`|\<mbstring.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
  
      // crt_strstr.c  
  
#include <string.h>  
#include <stdio.h>  
  
char str[] =    "lazy";  
char string[] = "The quick brown dog jumps over the lazy fox";  
char fmt1[] =   "         1         2         3         4         5";  
char fmt2[] =   "12345678901234567890123456789012345678901234567890";  
  
int main( void )  
{  
   char *pdest;  
   int  result;  
   printf( "String to be searched:\n   %s\n", string );  
   printf( "   %s\n   %s\n\n", fmt1, fmt2 );  
   pdest = strstr( string, str );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf( "%s found at position %d\n", str, result );  
   else  
      printf( "%s not found\n", str );  
}  
```  
  
```Output  
String to be searched:  
   The quick brown dog jumps over the lazy fox  
            1         2         3         4         5  
   12345678901234567890123456789012345678901234567890  
  
lazy found at position 36  
```  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 [System::String::IndexOf](https://msdn.microsoft.com/en-us/library/system.string.indexof.aspx)  
  
## <a name="see-also"></a>참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, _mbscspn, _mbscspn_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l](../../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)   
 [basic_string::find](http://msdn.microsoft.com/Library/e8254589-ae65-4414-b28f-54ba8f544656)
