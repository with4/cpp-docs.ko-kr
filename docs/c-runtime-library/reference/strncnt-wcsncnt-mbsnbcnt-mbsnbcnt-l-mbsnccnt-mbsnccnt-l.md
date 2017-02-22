---
title: "_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbcnt_l"
  - "_mbsnccnt"
  - "_wcsncnt"
  - "_strncnt"
  - "_mbsnccnt_l"
  - "_mbsnbcnt"
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
apitype: "DLLExport"
f1_keywords: 
  - "_mbsnbcnt"
  - "wcsncnt"
  - "_tcsnbcnt"
  - "_mbsnccnt"
  - "_ftcsnbcnt"
  - "mbsnbcnt"
  - "strncnt"
  - "mbsnbcnt_l"
  - "mbsnccnt_l"
  - "mbsnccnt"
  - "_strncnt"
  - "_wcsncnt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnbcnt 함수"
  - "_mbsnbcnt_l 함수"
  - "_mbsnccnt 함수"
  - "_mbsnccnt_l 함수"
  - "_strncnt 함수"
  - "_tcsnbcnt 함수"
  - "_wcsncnt 함수"
  - "mbsnbcnt 함수"
  - "mbsnbcnt_l 함수"
  - "mbsnccnt 함수"
  - "mbsnccnt_l 함수"
  - "strncnt 함수"
  - "tcsnbcnt 함수"
  - "wcsncnt 함수"
ms.assetid: 2a022e9e-a307-4acb-a66b-e56e5357f848
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자 또는 지정된 횟수 내에서 바이트 수를 반환합니다.  
  
> [!IMPORTANT]
>  `_mbsnbcnt`, `_mbsnbcnt_l`, `_mbsnccnt`, 및 `_mbsnccnt_l` 는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
size_t _strncnt(  
   const char *str,  
   size_t count  
);  
size_t _wcsncnt(  
   const wchar_t *str,  
   size_t count  
);  
size_t _mbsnbcnt(  
   const unsigned char *str,  
   size_t count   
);  
size_t _mbsnbcnt_l(  
   const unsigned char *str,  
   size_t count,  
   _locale_t locale  
);  
size_t _mbsnccnt(  
   const unsigned char *str,  
   size_t count  
);  
size_t _mbsnccnt_l(  
   const unsigned char *str,  
   size_t count,  
   _locale_t locale  
);  
  
```  
  
#### 매개 변수  
 `str`  
 변경할 문자열입니다.  
  
 `count`  
 문자 수 또는 바이트를 `str`로 검사할 수 있습니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `_mbsnbcnt` 및 `_mbsnbcnt_l` 는 `str` 의 멀티 바이트 문자의 첫번째로 파악된 `count` 바이트 수를 반환합니다.  `_mbsnccnt` 및 `_mbsnccnt_l` 는 `str` 의 멀티 바이트 문자의 첫번째로 파악된 `count` 바이트 수를 반환합니다.  검사 하기 전에 NULL 문자가 발생 경우 `str` 가 NULL 문자 앞에 있는 문자 또는 바이트 수 반환 완료 합니다.  `str` 이 `count` 문자 또는 바이트보다 적게 구성된 경우, 문자열에서 문자 또는 바이트 수를 반환 합니다.  `count` 가 0 보다 작은 경우, 0을 반환합니다.  이전 버전에서는 이러한 함수는 형식의 반환 값을 `int` 대신 `size_t` 로 반환했습니다.  
  
 `_strncnt` 은 1 바이트 문자열의 바이트 `str` 의 `count` 바이트의 첫번째 문자의 수를 반환합니다.  `_wcsncnt` 은 `str`와이드 캐릭터 스트링의 첫 번째 `count` 와이드 문자의 문자수를 반환합니다.  
  
## 설명  
 `_mbsnbcnt` 및 `_mbsnbcnt_l` 는 `str` 의 멀티 바이트 문자의 첫번째로 파악된 `count` 바이트 수를 반환합니다.  `_mbsnbcnt` 및 `_mbsnbcnt_l` 는 `mtob` 을 대체하고 `mtob`대신 사용 해야 합니다.  
  
 `_mbsnccnt` 및 `_mbsnccnt_l` 는 `str` 의 멀티 바이트 문자의 첫번째로 파악된 `count` 바이트 수를 반환합니다.  `_mbsnccnt` 및 `_mbsnccnt_l` 가 더블 바이트 문자의 두 번째 바이트는 NULL이 발생한 경우, 첫 번째 바이트는 NULL로 간주 되고, 개수 반환된 값에 포함 되지 않습니다.  `_mbsnccnt` 및 `_mbsnccnt_l` 는 `btom` 을 대체하고 `btom`대신 사용 해야 합니다.  
  
 `str` 은 null 포인터 이거나 또는 `count` 가 0 입니다. 이는 함수에 설명 된대로 잘못된 매개 변수 처리기를 호출한 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 입니다, `errno` 는 `EINVAL`, 을 설정하고, 함수는 0을 반환합니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|--------|--------------------------------|----------------|-------------------|  
|`_tcsnbcnt`|`_strncnt`|`_mbsnbcnt`|`_wcsncnt`|  
|`_tcsnccnt`|`_strncnt`|`_mbsnbcnt`|`n/a`|  
|`_wcsncnt`|`n/a`|`n/a`|`_mbsnbcnt`|  
|`_wcsncnt`|`n/a`|`n/a`|`_mbsnccnt`|  
|`n/a`|`n/a`|`_mbsnbcnt_l`|`_mbsnccnt_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbsnbcnt`|\<mbstring.h\>|  
|`_mbsnbcnt_l`|\<mbstring.h\>|  
|`_mbsnccnt`|\<mbstring.h\>|  
|`_mbsnccnt_l`|\<mbstring.h\>|  
|`_strncnt`|\<tchar.h\>|  
|`_wcsncnt`|\<tchar.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_mbsnbcnt.c  
  
#include  <mbstring.h>  
#include  <stdio.h>  
  
int main( void )  
{  
   unsigned char str[] = "This is a multibyte-character string.";  
   unsigned int char_count, byte_count;  
   char_count = _mbsnccnt( str, 10 );  
   byte_count = _mbsnbcnt( str, 10 );  
   if ( byte_count - char_count )  
      printf( "The first 10 characters contain %d multibyte characters\n", char_count );  
   else  
      printf( "The first 10 characters are single-byte.\n");  
}  
```  
  
## Output  
  
```  
The first 10 characters are single-byte.  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)