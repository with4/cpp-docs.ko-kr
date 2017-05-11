---
title: strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcstok_s_l
- _mbstok_s_l
- _mbstok_s
- strtok_s
- wcstok_s
- _strtok_s_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcstok_s_l
- _wcstok_s_l
- _tcstok_s
- _mbstok_s_l
- strtok_s
- wcstok_s
- _mbstok_s
- _strtok_s_l
dev_langs:
- C++
helpviewer_keywords:
- _strtok_s_l function
- _mbstok_s_l function
- strings [C++], searching
- mbstok_s_l function
- wcstok_s_l function
- _wcstok_s_l function
- _tcstok_s function
- _tcstok_s_l function
- strtok_s_l function
- wcstok_s function
- tokens, finding in strings
- mbstok_s function
- _mbstok_s function
- strtok_s function
ms.assetid: 7696c972-f83b-4617-8c82-95973e9fdb46
caps.latest.revision: 28
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 4313f785ba5197c3659e74384b7d6ecda8e8c7be
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="strtoks-strtoksl-wcstoks-wcstoksl-mbstoks-mbstoksl"></a>strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l
현재 로캘 또는 전달된 로캘을 사용하여 문자열의 다음 토큰을 찾습니다. 이러한 버전의 [strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l](../../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 향상된 보안 기능이 포함되어 있습니다.  
  
> [!IMPORTANT]
> Windows 런타임에서 실행되는 응용 프로그램에서는  `_mbstok_s` 및 `_mbstok_s_l`을 사용할 수는 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
  
      char *strtok_s(  
char *strToken,  
const char *strDelimit,  
   char **context  
);  
char *_strtok_s_l(  
char *strToken,  
const char *strDelimit,  
   char **context,  
_locale_tlocale  
);  
wchar_t *wcstok_s(  
wchar_t *strToken,  
const wchar_t *strDelimit,   
   wchar_t**context  
);  
wchar_t *_wcstok_s_l(  
wchar_t *strToken,  
const wchar_t *strDelimit,   
   wchar_t**context,  
_locale_tlocale  
);  
unsigned char *_mbstok_s(  
unsigned char*strToken,  
const unsigned char *strDelimit,   
   char **context  
);  
unsigned char *_mbstok_s(  
unsigned char*strToken,  
const unsigned char *strDelimit,   
   char **context,  
_locale_tlocale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `strToken`  
 토큰을 하나 이상 포함하는 문자열입니다.  
  
 `strDelimit`  
 구분 기호 문자 집합입니다.  
  
 `context`  
 `strtok_s` 호출 간의 위치 정보를 저장하는 데 사용됩니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 `strToken`에서 발견된 다음 토큰에 대한 포인터를 반환합니다. 토큰이 더 이상 없으면 `NULL`을 반환합니다. 각 호출에서는 반환된 토큰 다음에 오는 첫 번재 구분 기호의 `NULL` 문자를 대체하여 `strToken`을 수정합니다.  
  
### <a name="error-conditions"></a>오류 조건  
  
|`strToken`|`strDelimit`|`context`|반환 값|`errno`|  
|----------------|------------------|---------------|------------------|-------------|  
|`NULL`|모두|null 포인터에 대한 포인터|`NULL`|`EINVAL`|  
|모두|`NULL`|any|`NULL`|`EINVAL`|  
|any|모두|`NULL`|`NULL`|`EINVAL`|  
  
 `strToken`은 `NULL`이지만 컨텍스트가 유효한 컨텍스트 포인터에 대한 포인터이면 오류는 발생하지 않습니다.  
  
## <a name="remarks"></a>설명  
 `strtok_s` 함수는 `strToken`에서 다음 토큰을 찾습니다. `strDelimit`의 문자 집합은 현재 호출을 통해 `strToken`에서 찾을 토큰에 사용 가능한 구분 기호를 지정합니다. `wcstok_s` 및 `_mbstok_s`는 `strtok_s`의 와이드 문자 및 멀티바이트 문자 버전입니다. `wcstok_s` 및 `_wcstok_s_l`의 인수 및 반환 값은 와이드 문자열이며 `_mbstok_s` 및 `_mbstok_s_l`의 인수와 반환 값은 멀티바이트 문자열입니다. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. 오류 조건표에 나와 있는 오류 조건이 발생하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 이러한 함수는 `errno`를 `EINVAL`로 설정하고 `NULL`을 반환합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstok_s`|`strtok_s`|`_mbstok_s`|`wcstok_s`|  
|`_tcstok_s_l`|`_strtok_s_l`|`_mbstok_s_l`|`_wcstok_s_l`|  
  
 첫 번째 `strtok_s` 호출에서 함수는 선행 구분 기호를 건너뛰고 `strToken`의 첫 번째 토큰에 대한 포인터를 반환하여 null 문자로 토큰을 종료합니다. `strtok_s`에 대한 일련의 호출을 통해 나머지 `strToken`에서 더 많은 토큰을 분할할 수 있습니다. `strtok_s`를 호출할 때마다 해당 호출에서 반환된 후에 null 문자를 삽입하여 `strToken`을 수정합니다. `context` 포인터는 읽고 있는 문자열과 다음 토큰을 읽을 문자열 내 위치를 추적합니다. `strToken`에서 다음 토큰을 읽으려면 `strToken` 인수에 `NULL` 값을 사용하여 `strtok_s`를 호출하고 같은 `context` 매개 변수를 전달합니다. `NULL` `strToken` 인수를 사용하면 `strtok_s`가 수정된 `strToken`에서 다음 토큰을 검색합니다. `strDelimit` 인수는 구분 기호 집합이 달라질 수 있도록 호출 간에 어떤 값이든 가져올 수 있습니다.  
  
 `context` 매개 변수는 `strtok` 및 `_strtok_l`에서 사용되는 정적 버퍼보다 우선하므로 같은 스레드에서 두 문자열을 동시에 구문 분석할 수 있습니다.  
  
 출력값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`strtok_s`|\<string.h>|  
|`_strtok_s_l`|\<string.h>|  
|`wcstok_s`,<br /><br /> `_wcstok_s_l`|\<string.h> 또는 \<wchar.h>|  
|`_mbstok_s`,<br /><br /> `_mbstok_s_l`|\<mbstring.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_strtok_s.c  
// In this program, a loop uses strtok_s  
// to print all the tokens (separated by commas  
// or blanks) in two strings at the same time.  
//  
  
#include <string.h>  
#include <stdio.h>  
  
char string1[] =  
    "A string\tof ,,tokens\nand some  more tokens";  
char string2[] =  
    "Another string\n\tparsed at the same time.";  
char seps[]   = " ,\t\n";  
char *token1 = NULL;  
char *token2 = NULL;  
char *next_token1 = NULL;  
char *next_token2 = NULL;  
  
int main( void )  
{  
    printf( "Tokens:\n" );  
  
    // Establish string and get the first token:  
    token1 = strtok_s( string1, seps, &next_token1);  
    token2 = strtok_s ( string2, seps, &next_token2);  
  
    // While there are tokens in "string1" or "string2"  
    while ((token1 != NULL) || (token2 != NULL))  
    {  
        // Get next token:  
        if (token1 != NULL)  
        {  
            printf( " %s\n", token1 );  
            token1 = strtok_s( NULL, seps, &next_token1);  
        }  
        if (token2 != NULL)  
        {  
            printf("        %s\n", token2 );  
            token2 = strtok_s (NULL, seps, &next_token2);  
        }  
    }  
}  
```  
  
```Output  
Tokens:  
 A  
        Another  
 string  
        string  
 of  
        parsed  
 tokens  
        at  
 and  
        the  
 some  
        same  
 more  
        time.  
 tokens  
```  
  
## <a name="see-also"></a>참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, _mbscspn, _mbscspn_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
