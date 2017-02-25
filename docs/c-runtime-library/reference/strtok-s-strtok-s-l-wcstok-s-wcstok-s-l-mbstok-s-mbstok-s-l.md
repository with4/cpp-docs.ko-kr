---
title: "strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcstok_s_l"
  - "_mbstok_s_l"
  - "_mbstok_s"
  - "strtok_s"
  - "wcstok_s"
  - "_strtok_s_l"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tcstok_s_l"
  - "_wcstok_s_l"
  - "_tcstok_s"
  - "_mbstok_s_l"
  - "strtok_s"
  - "wcstok_s"
  - "_mbstok_s"
  - "_strtok_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbstok_s 함수"
  - "_mbstok_s_l 함수"
  - "_strtok_s_l 함수"
  - "_tcstok_s 함수"
  - "_tcstok_s_l 함수"
  - "_wcstok_s_l 함수"
  - "mbstok_s 함수"
  - "mbstok_s_l 함수"
  - "문자열[C++], 검색"
  - "strtok_s 함수"
  - "strtok_s_l 함수"
  - "토큰, 문자열에서 찾기"
  - "wcstok_s 함수"
  - "wcstok_s_l 함수"
ms.assetid: 7696c972-f83b-4617-8c82-95973e9fdb46
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 로캘 또는 전달된 로케일을 사용하여 문자열의 다음 토큰을 찾습니다.  이러한 버전의 [strtok, \_strtok\_l, wcstok, \_wcstok\_l, \_mbstok, \_mbstok\_l](../../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함됩니다.  
  
> [!IMPORTANT]
>  `_mbstok_s` 와 `_mbstok_s_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
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
  
#### 매개 변수  
 `strToken`  
 토큰 또는 토큰을 포함 하는 문자열입니다.  
  
 `strDelimit`  
 구분 기호 문자 집합입니다.  
  
 `context`  
 `strtok_s`에 대한 호출 사이 위치 정보를 저장하는데 사용됩니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `strToken`에서 발견되는 다음 토큰에 대한 포인터를 반환합니다.  토큰이 더 이상 발견되지 않으면, `NULL` 을 반환합니다.  각 호출은 반환된 토큰 후에 발생되는 첫 번째 구분 기호 문자 `NULL` 를 대체하여 `strToken` 를 수정합니다.  
  
### 오류 조건  
  
|`strToken`|`strDelimit`|`context`|반환 값|`errno`|  
|----------------|------------------|---------------|----------|-------------|  
|`NULL`|any|null 포인터에 대한 포인터입니다.|`NULL`|`EINVAL`|  
|any|`NULL`|any|`NULL`|`EINVAL`|  
|any|any|`NULL`|`NULL`|`EINVAL`|  
  
 `strToken` 가 `NULL` 이고 컨텍스트가 유효한 컨텍스트 포인터에 대한 포인터이면, 오류가 없습니다.  
  
## 설명  
 `strtok_s` 함수는 `strToken`에서 다음 토큰을 찾습니다.  `strDelimit` 에서 문자 집합은 현재 호출된 `strToken` 에서 찾을 수 있는 토큰의 사용 가능한 구분 기호를 지정합니다.  `wcstok_s` 및 `_mbstok_s`는 `strtok_s`의 와이드 및 멀티 바이트 문자 버전입니다.  `wcstok_s` 및 `_wcstok_s_l` 의 인수 및 반환 값은 와이드 문자열이며, `_mbstok_s` 및 `_mbstok_s_l` 는 멀티바이트 문자열입니다.  그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다.  [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로, 오류가 발생하면, 오류 조건 테이블에서와 같이, 잘못된 매개 변수 처리기는 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `NULL`을 반환합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcstok_s`|`strtok_s`|`_mbstok_s`|`wcstok_s`|  
|`_tcstok_s_l`|`_strtok_s_l`|`_mbstok_s_l`|`_wcstok_s_l`|  
  
 첫 번째로 `strtok_s` 함수를 호출하면 선행 구분 기호를 생략하고 null 문자를 사용하는 토큰을 종료하는 `strToken`에서 첫 번째 토큰에 대한 포인터를 반환합니다.  더 많은 토큰은 `strtok_s`에 대한 일련의 호출에 의해 `strToken` 의 나머지에서 나누어질 수 있습니다.  `strtok_s` 를 호출하는 것은 각각 호출에 의해 반환된 토큰 뒤의 null 문자를 삽입하여 `strToken` 를 수정합니다,  `context` 포인터는 문자열이 읽혀졌는지와 문자열 안에서 읽혀질 다음 토큰의 위치를 추적합니다.  `strToken`에서 다음 토큰을 읽기 위해, `strToken` 인수에 대한 `NULL` 값과 함께 `strtok_s` 을 호출하고 같은 `context` 매개 변수를 전달합니다.  `NULL` `strToken` 인수는 수정된 `strToken` 에서 다음 토큰을 검색하는 `strtok_s` 을 발생시킵니다.  `strDelimit` 인수는 다음에 대한 호출에서 값을 가질 수 있기 때문에 구분 기호 집합이 달라질 수 있습니다.  
  
 `context` 매개 변수가 `strtok` 및 `_strtok_l`에 사용되는 정적 버퍼를 대체한 후, 동일한 스레드에서 동시에 두 개의 문자열을 구문 분석할 수 있습니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strtok_s`|\<string.h\>|  
|`_strtok_s_l`|\<string.h\>|  
|`wcstok_s,`<br /><br /> `_wcstok_s_l`|\<string.h\> 또는 \<wchar.h\>|  
|`_mbstok_s,`<br /><br /> `_mbstok_s_l`|\<mbstring.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
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
  
  **토큰:**  
 **A**  
 **다른**  
 **string**  
 **string**  
 **의**  
 **구문 분석**  
 **토큰**  
 **at**  
 **및**  
 **연결을 편집하여**  
 **일부**  
 **동일한**  
 **more**  
 **유용합니다.**  
 **토큰**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)