---
title: "_strnset_s, _strnset_s_l, _wcsnset_s, _wcsnset_s_l, _mbsnset_s, _mbsnset_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnset_s_l"
  - "_strnset_s"
  - "_mbsnset_s"
  - "_strnset_s_l"
  - "_wcsnset_s_l"
  - "_wcsnset_s"
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
  - "_mbsnset_s_l"
  - "wcsnset_s"
  - "_tcsnset_s_l"
  - "_wcsnset_s"
  - "_mbsnset_s"
  - "_wcsnset_s_l"
  - "_strnset_s_l"
  - "strnset_s_l"
  - "_tcsnset_s"
  - "_strnset_s"
  - "strnset_s"
  - "mbsnset_s_l"
  - "mbsnset_s"
  - "wcsnset_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnset_s 함수"
  - "_mbsnset_s_l 함수"
  - "_strnset_s 함수"
  - "_strnset_s_l 함수"
  - "_tcsnset_s 함수"
  - "_tcsnset_s_l 함수"
  - "_wcsnset_s 함수"
  - "문자 초기화"
  - "mbsnset_s 함수"
  - "mbsnset_s_l 함수"
  - "strnset_s 함수"
  - "strnset_s_l 함수"
  - "tcsnset_s 함수"
  - "tcsnset_s_l 함수"
  - "wcsnset_s 함수"
ms.assetid: 9cf1b321-b5cb-4469-b285-4c07cfbd8813
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# _strnset_s, _strnset_s_l, _wcsnset_s, _wcsnset_s_l, _mbsnset_s, _mbsnset_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

특정된 문자열의 문자를 주어진 문자로 초기화합니다.  이러한 버전의 [\_strnset, \_strnset\_l, \_wcsnset, \_wcsnset\_l, \_mbsnset, \_mbsnset\_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함됩니다.  
  
> [!IMPORTANT]
>  `_mbsnset_s` 와 `_mbsnset_s_l` 는 Windows 런타임에서 실행되는 어플리케이션에서는 사용될 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
errno_t _strnset_s(  
   char *str,  
   size_t numberOfElements,  
   int c,  
   size_t count   
);  
errno_t _strnset_s_l(  
   char *str,  
   size_t numberOfElements,  
   int c,  
   size_t count,  
   locale_t locale  
);  
errno_t _wcsnset_s(  
   wchar_t *str,  
   size_t numberOfElements,  
   wchar_t c,  
   size_t count   
);  
errno_t _wcsnset_s_l(  
   wchar_t *str,  
   size_t numberOfElements,  
   wchar_t c,  
   size_t count,  
   _locale_t locale  
);  
errno_t _mbsnset_s(  
   unsigned char *str,  
   size_t numberOfElements,  
   unsigned int c,  
   size_t count   
);  
errno_t _mbsnset_s_l(  
   unsigned char *str,  
   size_t numberOfElements,  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `str`  
 변경할 문자열입니다.  
  
 `numberOfElements`  
 이 `str` 버퍼의 크기입니다.  
  
 `c`  
 문자 설정입니다.  
  
 `count`  
 바꿀 문자의 개수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 성공하면 0이고, 그렇지 않으면 오류 코드입니다.  
  
 이러한 함수는 해당 함수 인수의 유효성을 검사합니다.  만약 `str` 이 유효한 null로 끝나는 문자열이 아니거나 크기 인수가 0 과 같거나 적을 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 로 설명되는 유효한 매개 변수 처리기는 호출합니다.  이러한 집합과 함수 반환 오류 코드가 계속 실행이 허용 되는 경우 `errno` 해당 오류 코드를 설정합니다.  구체적인 값을 적용 하지 않는 경우, 기본 오류 코드는 `EINVAL` 입니다.  
  
## 설명  
 이러한 함수는 대게 `c` 인 `str` 의 `count` 문자들을 설정합니다.  만약 `count` 가 `str` 의 크기보다 큰 경우, `str` 크기는 `count` 대신하여 사용됩니다.  이 `count` 가 `numberOfElements` 보다 큰 경우 오류가 발생하고 매개 변수는 `str` 크기보다 더 큽니다.  
  
 `_wcsnset_s` 및 `_mbsnset_s` 는 와이드 문자 및 `_strnset_s`의 멀티 바이트 문자 버전입니다.  이 `_wcsnset_s` 의 문자열 인수는 와이드 문자열입니다; `_mbsnset_s` 은 `` 멀티 바이트 문자열입니다.  그렇지 않으면 이들 세 함수는 동일하게 작동합니다.  
  
 출력값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며,`_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다.  이 동작을 사용하지 않으려면 [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsnset_s`|`_strnset_s`|`_mbsnbset_s`|`_wcsnset_s`|  
|`_tcsnset_s_l`|`_strnset_s_l`|`_mbsnbset_s_l`|`_wcsnset_s_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_strnset_s`|\<string.h\>|  
|`_strnset_s_l`|\<tchar.h\>|  
|`_wcsnset_s`|\<string.h\> 또는 \<wchar.h\>|  
|`_wcsnset_s_l`|\<tchar.h\>|  
|`_mbsnset_s`, `_mbsnset_s_l`|\<mbstring.h\>|  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_strnset_s.c  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[15] = "This is a test";  
   /* Set not more than 4 characters of string to be *'s */  
   printf( "Before: %s\n", string );  
   _strnset_s( string, sizeof(string), '*', 4 );  
   printf( "After:  %s\n", string );  
}  
```  
  
  **전:이것은 테스트입니다.**  
**후: \* \* \*이 테스트입니다.**   
## 해당 .NET Framework 항목  
 [System::String::Replace](https://msdn.microsoft.com/en-us/library/system.string.replace.aspx)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)