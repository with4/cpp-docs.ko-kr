---
title: "_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcsset"
  - "_mbsset"
  - "_strset_l"
  - "_strset"
  - "_wcsset_l"
  - "_mbsset_l"
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
  - "mbsset"
  - "_strset_l"
  - "_mbsset"
  - "_strset"
  - "mbsset_l"
  - "strset_l"
  - "_wcsset"
  - "_ftcsset"
  - "wcsset_l"
  - "_tcsset_l"
  - "_mbsset_l"
  - "_wcsset_l"
  - "_fstrset"
  - "_tcsset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fstrset 함수"
  - "_ftcsset 함수"
  - "_mbsset 함수"
  - "_mbsset_l 함수"
  - "_strset 함수"
  - "_strset_l 함수"
  - "_tcsset 함수"
  - "_tcsset_l 함수"
  - "_wcsset 함수"
  - "_wcsset_l 함수"
  - "문자[C++], 설정"
  - "fstrset 함수"
  - "ftcsset 함수"
  - "mbsset 함수"
  - "mbsset_l 함수"
  - "문자열[C++], 문자 설정"
  - "strset_l 함수"
  - "tcsset 함수"
  - "tcsset_l 함수"
  - "wcsset_l 함수"
ms.assetid: c42ded42-2ed9-4f06-a0a9-247ba305473a
caps.latest.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# _strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자에 문자열의 문자를 설정합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_strset\_s, \_strset\_s\_l, \_wcsset\_s, \_wcsset\_s\_l, \_mbsset\_s, \_mbsset\_s\_l](../../c-runtime-library/reference/strset-s-strset-s-l-wcsset-s-wcsset-s-l-mbsset-s-mbsset-s-l.md)를 참조하십시오.  
  
> [!IMPORTANT]
>  `_mbsset` 와 `_mbsset_l` 는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
char *_strset(  
   char *str,  
   int c   
);  
char *_strset_l(  
   char *str,  
   int c,  
   locale_t locale  
);  
wchar_t *_wcsset(  
   wchar_t *str,  
   wchar_t c   
);  
wchar_t *_wcsset_l(  
   wchar_t *str,  
   wchar_t c,  
   locale_t locale  
);  
unsigned char *_mbsset(  
   unsigned char *str,  
   unsigned int c   
);  
unsigned char *_mbsset_l(  
   unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `str`  
 설정할 Null 종료 문자열입니다.  
  
 `c`  
 문자 설정입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 변경된 문자열에 대한 포인터를 반환합니다.  
  
## 설명  
 이 `_strset` 함수는 `str` 에서 \( `char`로 변환될\) `c` 인 모든 문자로 설정합니다 \(널 종료 문자 제외\).  `_wcsset`및  `_mbsset_l`  는  `_strset` 의 멀티 바이트 문자 또는 와이드 문자 버전입니다. 인수 및 반환 값의 데이터 형식에 따라 달라집니다.  그렇지 않다면 이러한 함수는 동일하게 작동합니다.  
  
 `_mbsset` 매개 변수의 유효성을 검사합니다.  `str` 이 null 포인터인 경우, 설명된 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, `_mbsset` 는 `NULL` 을 반환하고, `errno` 에 `EINVAL`를 설정합니다.  `_strset` 와 `_wcsset` 는 매개 변수를 확인 하지 않습니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 버전이 현재 로캘을 사용하거나 `_l` 접미사가 있는 버전이 전달된 로캘 매개 변수 대신일 경우를 제외하고는 해당 함수의 버전과 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
> [!IMPORTANT]
>  이러한 함수는 버퍼 오버런 위협에 노출될 수 있습니다.  버퍼 오버런은 불필요한 권한 상승을 발생시킬 수 있으므로 시스템 공격에 사용될 수 있습니다.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsset`|`_strset`|`_mbsset`|`_wcsset`|  
|`_tcsset_l`|`_strset_l`|`_mbsset_l`|`_wcsset_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_strset`|\<string.h\>|  
|`_strset_l`|\<tchar.h\>|  
|`_wcsset`|\<string.h\> 또는 \<wchar.h\>|  
|`_wcsset_l`|\<tchar.h\>|  
|`_mbsset`, `_mbsset_l`|\<mbstring.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_strset.c  
// compile with: /W3  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[] = "Fill the string with something.";  
   printf( "Before: %s\n", string );  
   _strset( string, '*' ); // C4996  
   // Note: _strset is deprecated; consider using _strset_s instead  
   printf( "After:  %s\n", string );  
}  
```  
  
  **이전: 동물과 문자열을 채웁니다.**  
**후에: \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbsnbset, \_mbsnbset\_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [\_strnset, \_strnset\_l, \_wcsnset, \_wcsnset\_l, \_mbsnset, \_mbsnset\_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)